# Security v6

- The project must contain a python3 ./dev file with these commands: audit, update-dependencies, fix
- The commands address all security-relevant dependencies of the project.
- Security-relevant are dependencies, that
  - are used in production (dev-dependencies aren't relevant)
  - process input from outside the project’s defined trust boundary
  - provide security functions such as authentication, encryption, or certificate validation
  - consist of functionality actually used by the project
- `audit` lists all Security-relevant vulnerabilities.
- `update-dependencies` has to update all relevant dependencies. If there are semantic dependency-versions specified, they should not be changed. Updates should only be done inside of these guards (normally only minor or patch updates).
- `fix` has to apply all security-relevant dependancy fixes that are available.
