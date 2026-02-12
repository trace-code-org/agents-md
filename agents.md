# Organization Requirements

## Technologies
 - Frontend: Typescript, React, React-Relay, Tailwind
 - Backend: Go, PostgreSQL (relational database)
 - Generally: GraphQL, Docker (Compose)

## Coding Style
Strongly domain-driven and modular (colocation of what belongs together)

## Project Requirements
Project requirements can be found inside the project.md file inside the project root.
They have to be followed as longs they don't contradict with the organization-requirements.

## Terminology
### Authentication
Requirements for "logging in" and "to register" as a user imply that there needs to be some authentication in the system. This normally also implies that there are resources that can only be accessed by the user, when he is authenticated.
### Frontend
If requirements don't mention how something should be achievable with the specified system, it normally means that it should be achievable by the user via frontend.

## Database
Even if it is not mentioned in the requirements. If there needs to be persistend data, one should normally add a postgres-db via docker-compose.
The database and the schema need to be created automatically if the database does not exist or is empty.
If database tables are empty, seed-data needs to be inserted automatically.

## Makefile
There should be a makefile, that includes all the important commands, needed for running the application.

## Screens
Event if it is not mentioned, applications should normally be divided into multiple screens.
