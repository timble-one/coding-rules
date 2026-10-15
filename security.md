# Security v3

- The project must contain a makefile with an `audit` and an `update` target.
- The two targets address all dependencies of the project.
- The `audit` target has to list all vulnarabilities of the current dependencies.
- The `update-dependencies` target has to update all dependencies. If there are semantic dependency-versions specified, they should not be changed. Updates should only be done inside of these guards (normally only minor or patch udpates).
