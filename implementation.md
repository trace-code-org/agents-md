# Organization Requirements
**API between frontend and backend:** graphql  
**Coding Style:** Strongly domain-driven and modular (colocation of what belongs together)

### Project Requirements
Project requirements can be found in versioned files (`requirements/project.vN.md`) inside the project root.
They have to be followed as long as they don't contradict the organization requirements.

#### Versions
For every new revision of the project requirements, create a new `requirements/project.v{N+1}.md` file containing the requirement delta only.
Do not rewrite or mutate older version files after they are created.
The effective requirements are distributed across the ordered delta history (`requirements/project.v1.md` ... `requirements/project.vN.md`), so one cannot derive the full requirement state from only the newest file.
Implementation must therefore consider all revisions up to the highest version.
Any change in this project must be reflected in a new version-delta. Even if it is only a bug-fix.

#### Archive folders are not implementation input
Folders named like `archive*` (for example `archive`, `archive-v1`, `archive-2026`) are historical snapshots.
Do not use archive-folder content as implementation input when building the current version, unless the human explicitly requests it.
Current implementation must be derived from active requirement files and active project sources only.

#### Requirement coverage by automated tests
Every project requirement must be validated by automated tests.
If one test is not sufficient to validate a requirement, add as many automated tests as needed until the requirement is fully covered.

### Docker
Frontend and backend should have their own docker-containers. They should be managed with docker-compose.
A Makefile should contain all the necessary docker-compose commands.


### Authentication
Requirements for "logging in" and "to register" as a user imply that there needs to be some authentication in the system. This normally also implies that there are resources that can only be accessed by the user, when he is authenticated.


## Frontend
If requirements don't mention how something should be achievable with the specified system, it normally means that it should be achievable by the user via frontend.

#### Technologies
Typescript, React, React-Relay, Tailwind

#### TypeScript configuration
Use a preset-based `tsconfig.json` via `extends` (for example `@tsconfig/*`) and only override project-specific options.
This keeps projects reproducible while avoiding repeated boilerplate defaults.

#### UI consistency and style
Use a consistent and modern UI design system across the app (typography, spacing, components, and interaction patterns should feel cohesive).

#### Screens
Event if it is not mentioned, applications should normally be divided into multiple screens.


## Backend
Technologies: Go, PostgreSQL (relational database)

#### Database
Even if it is not mentioned in the requirements. If there needs to be persistend data, one should normally add a postgres-db via docker-compose.
If a database is used, all the functions of the cmdrunner dbcommand.Standard commands should be implemented.
The db:data:load command should load some seed-data.

#### Commands
If some commands have to be executed from the cli. It should be implemented using the cmdrunner package: github.com/timble-one/cmdrunner
The package is private until now and therefore projects are created from a go-workspace including the cmdrunner-package.
