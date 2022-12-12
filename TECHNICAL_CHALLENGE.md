# Team lead technical challenge

# Purpose

The goal of this challenge is to provide us with a better understanding of your work style and skills. It consists of an architecture part and a coding part. We will pay particular attention to:

- For the coding part
    - Adherence to language idioms and good coding principles.
    - The presence of appropriate build and dependency management tools.
    - The application of concept such as DDD, TDD and so on.
- For the architecture part
    - The overall architecture of the system with respect to design decisions made to accommodate high performance requirements in a high load environment.

We want to stress that the solution should not take more than a couple of hours to complete. The goal is not to have a complete, robust solution, but to see how you proceed when you need to produce an MVP in a minimal amount of time. 

# Architecture Task

## Description

You need to create a system architecture document for a production deployment of a Twitter-like service. This is a separate exercise from the coding exercise. 

Please commit the following:

- A system architecture document

## Requirements

- The system should prioritise delivering tweets to follower feeds.
- There is no hard limit on how many followers a user can have, consider users having millions of followers.
- There is no hard limit on how many users a user can follow, consider users following hundreds of thousands of other users.
- The diagram should be accompanied by an explanation of the design decisions made.

# Coding Task

## Description

Write an MVP for an API server for a Twitter-like service. Users can follow other users, and they can tweet messages. Each user has a home timeline feed that lists all tweets from the users that they follow. 

Please commit the following:

- Your source code
- A README file with instructions for building and executing the source code

## Requirements

- There is no need for authentication and authorisation.
- There is no need for persistence of tweet data to disk, as this is an MVP.
- There should be an option to build and run the solution as a container.
- You may use your language of choice for the implementation, but Python, Rust or a JVM language would be preferred.

## API Specification

The MVP for the tweet system should implement the following RESTful-like JSON API endpoints. The below specifications do not cover error cases, which are left for the candidate to consider.

### Create an user

This API call creates a new user id.

**Request**: POST /user

**Request body**: Nothing, empty body.

**Response code**: HTTP 200

**Response body**:

```json
{ "uid": "USER-ID-HERE" }
```

### Create a tweet

This API call creates a new tweet. The maximum length of a tweet is 128 UTF-8 characters.

**Request**:  POST /user/**:uid**/tweet

**Request parameters**: uid → user id

**Request body**:

```json
{ "tweet": "tweet text here" }
```

**Response code**: HTTP 200.

### Get a user tweet feed

This API call returns a list of tweets in the user home timeline feed. For the purpose of the MVP this does not have to be paged.

**Request**: GET /user/:**uid**/feed

**Request parameters**: uid → user id of the user performing the operation.

**Response code**: HTTP 200

**Response body**: 

```json
{ 
	"tweets": [
			{
				"uid": "SOME-USER-ID-HERE", 
				"tweet_id": "TWEET-ID-HERE", 
				"body": "tweet text here"
			},
			{
				"uid": "ANOTHER-USER-ID-HERE", 
				"tweet_id": "TWEET-ID-HERE", 
				"body": "another tweet text here"
			},
	] 
}
```

### Follow a user

This API call registers a user as a follower of another user. Users cannot follow themselves.

**Request**:  POST /user/**:uid**/follow/

**Request parameters**: uid → user id of the user performing the operation.

**Request body**:

```jsx
{ "uid": "USER-ID-TO-BE-FOLLOWED-HERE" }
```

**Response code**: HTTP 200

**Response body**: None, empty