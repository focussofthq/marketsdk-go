# Releasing

Go has no registry upload. A release is a tag on this public repository; the module proxy fetches it
on first request.

```bash
git tag v1.0.0
git push origin v1.0.0
GOPROXY=https://proxy.golang.org go list -m github.com/focussofthq/marketsdk-go@v1.0.0
```

The tag must be the module version with a `v` prefix, and the module path in `go.mod` must be this
repository's path, which the generator sets.
