# Dev-Server v2
- These instructions are meant to be applied directly and not by the implementation of this project.
- The idea is that this spec can be put onto an empty dev-server and have the server configured by the agent (you).
- The application itself must be implemented under the assumption that the server-configuration is given.
- If you are currently implementing an application and reading this, you must make sure the application gets deployed at the default-host, so it is directly available after the implementation is finished.

##   Configuration
 - Install tmux and btop.
 - Install git with `git config --global init.defaultBranch main`
 - Configure this machine to do automatic updates daily and also restart itself automatically if necessary.
 - Configure the Firewall to have all ports closed for incomming trafik that is not needed.
 - If the application runs on an agent-configured machine, the default host ist specified in `spec/spec.md` or `spec.md`.

## Usage
If this requirement-module is used, you have to specify the default host in the main-spec like this:

```
default-host: `app-dev.example.tld`
```
