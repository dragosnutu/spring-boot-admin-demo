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

If you run both admin and gateway demos you'll see that if you start and stop the gateway project admin will not refresh
the app list.
It detects that gateway service is down. After you start it again it seems that it never comes back in.
If you restart admin service it will refresh the app list, and you'll see gateway up again.