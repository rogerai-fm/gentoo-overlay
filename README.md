# RogerAI Gentoo overlay

A Portage overlay for [RogerAI](https://rogerai.fyi) - a two-way radio for GPUs.
Provides `net-misc/roger-bin`, the prebuilt `roger` client (installs the `rogerai`
back-compat alias too).

## Install

```sh
eselect repository add roger git https://github.com/rogerai-fm/gentoo-overlay.git
emerge --sync roger

# roger-bin is ~arch and ships under the source-available PolyForm Perimeter license:
echo 'net-misc/roger-bin ~amd64'                   | sudo tee /etc/portage/package.accept_keywords/roger-bin
echo 'net-misc/roger-bin PolyForm-Perimeter-1.0.0' | sudo tee /etc/portage/package.license/roger-bin
emerge net-misc/roger-bin
```

Then run `roger`. The ebuild fetches the statically-linked release binary (one build runs
on glibc and musl alike), so there is nothing to compile.
