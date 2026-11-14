# Traefik v1

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
      traefik.http.routers.${TRAEFIK_ROUTER:?Set TRAEFIK_ROUTER}.rule: "Host(`${APP_HOST:?Set APP_HOST}`)"
      traefik.http.routers.${TRAEFIK_ROUTER}.entrypoints: "websecure"
      traefik.http.routers.${TRAEFIK_ROUTER}.tls: "true"
      traefik.http.routers.${TRAEFIK_ROUTER}.tls.certresolver: "letsencrypt"
      traefik.http.services.${TRAEFIK_ROUTER}.loadbalancer.server.port: "80"
      traefik.http.routers.${TRAEFIK_ROUTER}-http.rule: "Host(`${APP_HOST}`)"
      traefik.http.routers.${TRAEFIK_ROUTER}-http.entrypoints: "web"
      traefik.http.routers.${TRAEFIK_ROUTER}-http.middlewares: "${TRAEFIK_ROUTER}-https"
      traefik.http.middlewares.${TRAEFIK_ROUTER}-https.redirectscheme.scheme: "https"
      traefik.http.middlewares.${TRAEFIK_ROUTER}-https.redirectscheme.permanent: "true"

networks:
  proxy:
    external: true

```

Keep in mind, that the project-name-tld is a placeholder and must be replaced by a unique name.
It is a good practice to use the domain-name including subdomain(s) and top-level-domain because it has to be unique on the server.


**Multienvironment Projects**  
If projects have a prod-specific compose-file (e.g. `compose.prod.yaml`) it should be assumed that the reverse-proxy is only used in production and the above configurations should therefore be applied to the according compose file.
