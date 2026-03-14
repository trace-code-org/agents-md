# Fullstack Implementation

Frontend and backend must have their own docker-containers. They must be managed with docker-compose.

## Frontend
If requirements don't mention how something should be achievable with the specified system, it means that it must be achievable by the user via frontend.

#### Technologies
Typescript, React, React-Relay, Tailwind

#### TypeScript configuration
Use a preset-based `tsconfig.json` via `extends` (for example `@tsconfig/*`) and only override project-specific options.
This keeps projects reproducible while avoiding repeated boilerplate defaults.

#### UI consistency and style
Use a consistent and modern UI design system across the app (typography, spacing, components, and interaction patterns must feel cohesive).

#### Screens
Even if it is not mentioned, applications must be divided into multiple screens.


## Backend
**Technologies:** Go, PostgreSQL (relational database)
If there is no cmdrunner-module available via workspace. Stop the implementation and ask your human to provide it immediately.

#### Database
If a database is used, all the functions of the cmdrunner dbcommand. Standard commands must be implemented.
The db:data:load command must load some seed-data.

#### Commands
If some commands have to be executed from the cli. It must be implemented using the cmdrunner package: github.com/timble-one/cmdrunner
The package is private until now and therefore projects are created from a go-workspace including the cmdrunner-package.
