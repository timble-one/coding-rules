# git
Add a `.githooks` folder containing a `pre-commit` hook assuming that the developer configured `git config --global core.hooksPath .githooks`.
The `pre-commit` hook must run the linting target of the project's package manager.
