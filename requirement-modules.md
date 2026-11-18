# Requirement Modules v1

- Requirements imported from external modules must be copied into the `spec/modules/` directory and treated as normative project requirements.
- When an imported module's source declares a version other than version zero, that version must be recorded in the local module file so the exact source specification remains traceable.
- It is not allowed to alter module-files in any way. Updating the requirements-modules according to the references is the only thing an agent is allowed to change in the spec-folder.

## Usage
The following is an example spec, how requirement-modules should be included into a project-specification:

```
Use these requirement modules:
- github.com/timble-one/coding-rules/requirement-modules.md v0
- github.com/timble-one/coding-rules/autodeployment.md v3
```