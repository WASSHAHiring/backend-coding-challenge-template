# Backend Engineer Technical Challenge

## Purpose

The goal of this challenge is to provide us with a better understanding of your work style and skills. We will pay particular attention to:

- Adherence to language idioms and good coding principles.
- The presence of appropriate build and dependency management tools.
- The application of concept such as DDD, TDD and so on.

We want to stress that the solution should not take more than a couple of hours to complete. The goal is not to have a complete, robust solution, but to see how you proceed when you need to produce an MVP in a minimal amount of time. 

## Task Description

Write an MVP for an API server for a Twitter-like service. Users can follow other users, and they can tweet messages. Each user has a home timeline feed that lists all tweets from all other users.

Please use this template repository as the base for your work. You can use the template as usual, or fork it. Please send us a link to the repository you created, containg the following:

- Your source code.
- A README file with instructions for building and executing the source code. 

## Requirements

- There is no need for authentication and authorisation.
- There is no need for persistence of tweet data to disk, as this is an MVP.
- There should be an option to build and run the solution as a container.
- You may use your language or framework of choice for the implementation, but **Django** should be preferred.
- The server should be executable with a single command.
- The server should be able run on Windows, Linux and OSX (Including M1 and M2 devices). 

## API Specification

The MVP for the tweet system should implement the following RESTful-like JSON API endpoints. The API specification can be viewed in the OpenAPI [specification](tweetlike.yml).

