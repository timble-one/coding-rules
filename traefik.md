# Traefik

This is a standard, how to configure a web-project to be servable by traefik.

The following is an example of how a minimal docker compose file would have to look like:
```yaml
services:
  web:
    image: nginx:alpine
    restart: unless-stopped
    networks:
      - proxy
    labels:
      traefik.enable: "true"
      traefik.docker.network: "proxy"
      traefik.http.routers.project-name-tld.rule: "Host(`project-name.tld`)"
      traefik.http.routers.project-name-tld.entrypoints: "websecure"
      traefik.http.routers.project-name-tld.tls: "true"
      traefik.http.routers.project-name-tld.tls.certresolver: "letsencrypt"
      traefik.http.services.project-name-tld.loadbalancer.server.port: "80"
      traefik.http.routers.project-name-tld-http.rule: "Host(`project-name.tld`)"
      traefik.http.routers.project-name-tld-http.entrypoints: "web"
      traefik.http.routers.project-name-tld-http.middlewares: "project-name-tld-https"
      traefik.http.middlewares.project-name-tld-https.redirectscheme.scheme: "https"
      traefik.http.middlewares.project-name-tld-https.redirectscheme.permanent: "true"

networks:
  proxy:
    external: true

```

Keep in mind, that the project-name-tld is a placeholder and must be replaced by a unique name.
It is a good practice to use the domain-name including subdomain(s) and top-level-domain because it has to be unique on the server.
