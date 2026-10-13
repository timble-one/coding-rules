# Requirement Modules

- **MODULE-001**: Requirements imported from external modules must be copied into the `spec/modules/` directory and treated as normative project requirements.
- **MODULE-002**: When an imported module's source declares a version other than version zero, that version must be recorded in the local module file so the exact source specification remains traceable.

## Example Usage
The following is an example spec, how requirement-modules should be included into a project-specification:

```
Use these requirement modules:
github.com/timble-one/coding-rules/requirement-modules.md
github.com/timble-one/coding-rules/autodeployment.md v3
```