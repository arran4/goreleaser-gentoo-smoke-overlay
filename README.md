# goreleaser-gentoo-smoke-overlay

Disposable output overlay for `arran4/goreleaser-gentoo-smoke`.

This repository is intentionally almost empty. Generated ebuilds are written
here by the source repo release workflow.

Do not add ebuilds manually.

To add this repository to your system, run:

```shell
eselect repository add goreleaser-gentoo-smoke-overlay git https://github.com/arran4/goreleaser-gentoo-smoke-overlay.git
```

## Example Testing in Docker

```
arran@arran-desktop:~ 59606
$ docker run -ti --rm gentoo/stage3
Unable to
find image 'gentoo/stage3:latest' locally
latest: Pulling from gentoo/stage3

1a22a095243b: Pull complete
Digest:
sha256:9d03b48eda632da09f469d384ce77ec05618060ed4e9ac295f8192a196e7539a

Status: Downloaded newer image for gentoo/stage3:latest
b88592f96474 / # em

emaint           emerge           emerge-webrsync  emirrordist

b88592f96474 / # eselect repository add goreleaser-gentoo-smoke-overlay git
https://github.com/arran4/goreleaser-gentoo-smoke-overlay.git
!!! Error: Can't
load module repository
b88592f96474 / # emerge-webrsync
emerge
--oneshot app-eselect/eselect-repository

eselect repository add
goreleaser-gentoo-smoke-overlay \
   git
https://github.com/arran4/goreleaser-gentoo-smoke-overlay.git

emaint sync -r
goreleaser-gentoo-smoke-overlay

```

and

```
b88592f96474 / #  emerge -va app-misc/goreleaser-gentoo-smoke-bin --autounmask
--autounmask-continue --autounmask-write

```
