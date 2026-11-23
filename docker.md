# Docker v5
- Everything must be wrapped inside docker container(s) so it can be deployed easily.
- There must be these two python3 files to execute code easily with docker-compose:
   - ./dev for scripts or dev-stuff
   - ./prod for production-stuff
- Use docker compose v2.
- Everything must run on a docker-version that commes with the docker.io package for the latest LTS-debian version.
   - One can assume that docker-cli, docker-buildx and docker-compose are available.
   - It is the best to also use this docker-version on the dev-server. This way docker-version problems can be adressed early.
- For production web-services, use restart=unless-stopped
