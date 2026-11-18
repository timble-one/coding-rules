# Dev-Server
- These instructions are meant to be applied directly and not by the implementation of this project.
- The idea is that this spec can be put onto an empty dev-server and have the server configured by the agent (you).
- If one deploys the implementation of this application, one can assume that the server itself is allready configured.

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
