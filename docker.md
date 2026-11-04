# Docker v4
- Everything must be wrapped inside docker container(s) so it can be deployed easily.
- There must be these two python3 files to execute code easily with docker-compose:
   - ./dev for scripts or dev-stuff
   - ./prod for production-stuff
- Don't create a Makefile
- Use docker compose v2.
- For production web-services, use restart=unless-stopped
