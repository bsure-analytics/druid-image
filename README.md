# Druid Image

Multi-arch (`linux/amd64`, `linux/arm64`) container images of [Apache Druid](https://druid.apache.org), because the
official `apache/druid` image is published for `linux/amd64` only.

```shell
docker pull ghcr.io/bsure-analytics/druid:38.0.0
```

The image is a drop-in replacement for `apache/druid` of the same version: it is built by the upstream
[Dockerfile](https://github.com/apache/druid/blob/master/distribution/docker/Dockerfile) at the release tag, unchanged,
from the official binary release, after verifying its SHA-512 checksum and its signature against the Apache Druid
[KEYS](https://downloads.apache.org/druid/KEYS). The binary release is pure Java, so both architectures get the very
same Druid with the same extensions.

This is an unofficial build, not a release of the Apache Software Foundation.

## Releases

The version to publish is `DRUID_VERSION` in [`.github/workflows/publish.yaml`](.github/workflows/publish.yaml).
Renovate opens a pull request when Apache publishes a new Druid release. The pull request builds and smoke-tests both
architectures; merging it publishes the tag. Published tags are never overwritten.

## License

[Apache License 2.0](LICENSE), like Apache Druid itself.
