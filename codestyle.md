# Codestyle v1

## Architecture
- Code must be strongly domain-driven and modular: colocate what belongs together.
- Exclusive file/folder dependencies must be wrapped in a folder; if the dependency is unidirectional, name the folder after the dependant file.
- File names should not contain namespace parts.

## Simplicity
- Keep code as minimal as possible; use standard functionality and well-known libraries when they make code simpler.
- Use the programming language, framework, or library that makes code simplest and most readable.

## File structure
- If a single class is not the only thing in a file, extract constants longer than three lines from the class.
- If a file contains multiple classes and one depends on another, the dependent class must come first.

## Extraction
- A function can never exceed 15 lines except pure mapping-functions; otherwise extract it.
- Don't make micro-extractions: if a function and its exclusively referenced extraction are each shorter than 5 lines, undo the extraction.

## Pure mapping-function
A pure mapping-function only maps date and nothing else. It must not contain loops.

## Dependency-levels in files
The following dependency-rules apply to both of these units: functions and classes

 - If a unit in a file depends directly on multiple subunits, those subunits may stay in the same file, but their own dependencies must be moved out.
 - The file may contain only the parent unit and its direct subunits.
 - Move deeper dependency levels into a separate dependant-named file or folder.
 - A same-file dependency chain with infinite levels is allowed only when each unit has exactly one exclusive dependant in that file, so the file reads strictly top-down as a single chain.
