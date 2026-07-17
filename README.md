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

```shell
# Start the Gentoo container
docker run -ti --rm gentoo/stage3

# Inside the container, sync the portage tree
emerge-webrsync

# Install eselect-repository
emerge --oneshot app-eselect/eselect-repository vim

# Add the overlay
eselect repository add goreleaser-gentoo-smoke-overlay git https://github.com/arran4/goreleaser-gentoo-smoke-overlay.git

# Sync the overlay
emaint sync -r goreleaser-gentoo-smoke-overlay

# Install the package
emerge -va app-misc/goreleaser-gentoo-smoke-bin --autounmask --autounmask-continue --autounmask-write
```
