# manifest-tool

This repo defines the `hkjn/manifest-tool` Docker image.

## Pushing multi-arch manifest for this image

This image can be used to push the multi-arch manifest for itself (how recursive!):

```
docker run -v $HOME/.docker:/home/go/.docker:ro --rm -it hkjn/manifest-tool:amd64 push from-args --platforms linux/amd64,linux/arm --template hkjn/manifest-tool:ARCH --target hkjn/manifest-tool
```

Adjust `amd64` if not building on that architecture. The mount of `$HOME/.docker` is necessary to share the credentials for pushing to hub.docker.com.
