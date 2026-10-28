# Development Container

The project uses a reproducible development container for implementation work.

## Development environment requirements

- **DEV-001**: The development container must be built from the repository-root `Dockerfile.dev`.
- **DEV-002**: The development container must preinstall all tools required to implement, validate, build, and test the project.
- **DEV-003**: Codex must be preinstalled in the development container, and the development Compose file must mount a Docker named volume at `CODEX_HOME` to persist Codex authentication tokens and conversation history outside the container.
- **DEV-004**: A development agent may install additional tools in the throwaway development VM when they are needed for implementation, but the agent must also add those tools to `Dockerfile.dev` so they remain available after rebuilding the development container.
- **DEV-005**: The development Compose file must bind-mount the host project directory read-write at `/workspace` in the development container so changes made inside the container persist in the host working tree.
- **DEV-006**: A repository-root `compose.dev.yaml` must define the development-container service, build it from `Dockerfile.dev`, and specify all runtime mounts required by the development environment.
- **DEV-007**: Host and development-container Bun installations must remain independent: `package.json` and `bun.lock` must stay shared through the project bind mount, while the container’s `/workspace/node_modules` and Bun package cache must use development-environment-specific Docker named volumes that mask the corresponding host paths.
- **DEV-008**: When running `bun run dev` directly on the host outside the development container, the `/api` proxy must default to `http://localhost:8080` when `API_UPSTREAM` is unset or empty; a nonempty `API_UPSTREAM` must override this default.
