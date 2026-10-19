# Security v4

- The project must contain a makefile with these targets: audit, update-dependencies, fix
- The two targets address all security-relevant dependencies of the project.
- Security-relevant dependencies process input from outside the project’s defined trust boundary or provide security functions such as authentication, encryption, or certificate validation. Relevance depends on functionality actually used by the project.
- The `audit` list all Security-relevant vulnerabilities.
- The `update-dependencies` target has to update all relevant dependencies. If there are semantic dependency-versions specified, they should not be changed. Updates should only be done inside of these guards (normally only minor or patch updates).
- The `fix` target has to apply all security-relevant dependancy fixes that are available.
