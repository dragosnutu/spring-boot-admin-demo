# Demo for spring admin

## Required tools

1. Docker
2. Kubernetes
3. doctl - for managing kubernetes
4. skaffold - for managing deploy in k8s

## Run

In dev mode with monitoring active

```shell
skaffold dev
```

In run mode

```shell
skaffold run --tail --port-forward
```

You can then open http://localhost:8180 to verify the admin ui.

## Current issues

1. Start admin project see - https://github.com/dragosnutu/spring-boot-admin-demo
2. Start gateway project see - https://github.com/dragosnutu/spring-boot-gateway-demo
3. Check admin UI, and you'll see it detects the gateway service
4. Stop gateway and wait a bit like 1 minute.
5. Admin UI detects that gateway is down.
6. Start gateway again
7. Admin UI will never refresh the gateway app to status UP it will remain down.