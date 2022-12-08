# Wrapper for Jellyfin

[Jellyfin]The Free Software Media System
Jellyfin is the volunteer-built media solution that puts you in control of your media. Stream to any device from your own server, with no strings attached. Your media, your server, your way.

## Dependencies

- [docker](https://docs.docker.com/get-docker)
- [docker-buildx](https://docs.docker.com/buildx/working-with-buildx/)
- [yq](https://mikefarah.gitbook.io/yq)
- [toml](https://crates.io/crates/toml-cli)
- [make](https://www.gnu.org/software/make)
- [embassy-sdk]

## Cloning

Clone the project locally. Note the submodule link to the original project(s). 

```
git clone https://github.com/Michilis/Jellyfin-wrapper/
cd jellyfin-wrapper
git submodule update --init --recursive
docker run --privileged --rm tonistiigi/binfmt --install arm64,riscv64,arm
```

## Building

To build the project, run the following commands:

```
make
```

## Installing (on Embassy)

SSH into an Embassy device.
`scp` the `.s9pk` to any directory from your local machine.

```
scp jellyfin.s9pk root@<LAN ID>:/tmp
```

Run the following command to determine successful install:

```
embassy-cli auth login
embassy-cli package install /tmp/jellyfin.s9pk
```
