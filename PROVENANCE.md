# Provenance

Created: 2026-07-03

This repository contains a ready-to-install Linux amd64 deploy package for an
isolated MinIO CE VM. It intentionally does not include build caches, cloned
upstream source trees, Docker preview files, or temporary scan output.

## Source policy

- Server source: official upstream MinIO CE, `https://github.com/minio/minio`
- Client source: official upstream MinIO Client, `https://github.com/minio/mc`
- Full web console source: AGPL `opens3/console`, `https://github.com/opens3/console`
- No third-party MinIO server fork, mirror, or repacked binary is used.
- The server binary is official MinIO CE source plus the documented local
  dependency and CVE hardening patches in `SECURITY.md`.

MinIO AIStor / Enterprise-only features are not part of this CE package. If
those features are required without using a fork, use an official MinIO AIStor
license/subscription.

The bundled full web console is not MinIO AIStor and is not affiliated with
MinIO, Inc. It is a community-maintained AGPL fork of the former full MinIO
Console UI, intended to provide a complete management interface for
MinIO-compatible servers.

## Shipped artifacts

| File | Source tag/commit | SHA256 | Notes |
| --- | --- | --- | --- |
| `bin/minio` | MinIO `RELEASE.2025-10-15T17-29-55Z`, commit `9e49d5e7a648f00e26f2246f4dc28e6b07f8c84a` | `beebdd52649d9b931104d4b9fa787ec3d0ca8e7b1b3791c404d773a31c26e505` | Security dependency bumps + local CVE hardening patches. |
| `bin/mc` | `RELEASE.2025-08-13T08-35-41Z`, commit `7394ce0dd2a80935aded936b09fa12cbb3cb8096` | `8840f9aeed280a60cb86462e58d358bac6fd1f95dd4fe9609333404bfae95024` | Unmodified official upstream client. |
| `bin/minio-console` | `opens3/console` commit `78fe28aac68393f3762899b544bccd4b5b2f616e` | `0d067424272e132e287687b3821f423e22c7d38f3c6bb7aec34579acb35b9703` | Full console fork with internal MinIO logo/favicon rebrand. |

The full file list and checksums are recorded in `CHECKSUMS.sha256`.

## Release archive

The deploy archive this repository was restored from was:

```text
minio-ce-deploy.tar.gz
SHA256: 93d3ce063a55172223c253973665e24b3820d668bd527306aa25de14b4efbf35
```

Use `CHECKSUMS.sha256` to verify the unpacked repository contents.
