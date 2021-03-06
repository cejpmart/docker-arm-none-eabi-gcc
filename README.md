## Tags

- `latest`, `*-bionic`- based on Ubuntu 18.04 LTS (bionic)
- `*-focal`- based on Ubuntu 20.04 LTS (focal)
- `*-arch` based on Arch Linux

## How to use this

    podman run --rm mcejp/arm-none-eabi-gcc:latest arm-none-eabi-gcc -v

The default working directory is `/work`, so you can mount your source code there as a volume.

It is recommended to pin a specific version of the image rather than using `latest`.

## What is included

- native toolchain of the base OS (binutils, gcc, make etc.)
- Git
- additional tools: bzip2, wget

## How to build this

    # Build all images & test them
    podman build -f Dockerfile -t mcejp/arm-none-eabi-gcc:latest
    podman build -f Dockerfile -t mcejp/arm-none-eabi-gcc:10-2020-q4-major-bionic
    podman build -f Dockerfile.arch -t mcejp/arm-none-eabi-gcc:10.2-arch
    podman build -f Dockerfile.ubuntu2004 -t mcejp/arm-none-eabi-gcc:10-2020-q4-major-focal

    # Commit changes & tag the toolchain version
    git tag 10-2020-q4-major

    # Configure image build triggers on Docker Hub, or manually push built images

    # Push the repository
    git push origin master 10-2020-q4-major
