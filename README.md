# arm-dependencies

[![Deploy Docker Image](https://github.com/alexhyett/arm-dependencies/actions/workflows/deploy-docker.yml/badge.svg)](https://github.com/alexhyett/arm-dependencies/actions/workflows/deploy-docker.yml)
[![Docker](https://img.shields.io/docker/pulls/automaticrippingmachine/arm-dependencies.svg)](https://hub.docker.com/r/automaticrippingmachine/arm-dependencies)

[![GitHub license](https://img.shields.io/github/license/alexhyett/arm-dependencies)](https://github.com/alexhyett/arm-dependencies/blob/main/LICENSE)
[![GitHub forks](https://img.shields.io/github/forks/alexhyett/arm-dependencies)](https://github.com/alexhyett/arm-dependencies/network)
[![GitHub stars](https://img.shields.io/github/stars/alexhyett/arm-dependencies)](https://github.com/alexhyett/arm-dependencies/stargazers)
[![GitHub issues](https://img.shields.io/github/issues/alexhyett/arm-dependencies)](https://github.com/alexhyett/arm-dependencies/issues)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/alexhyett/arm-dependencies)](https://github.com/alexhyett/arm-dependencies/pulls)

![PyPI - Python Version](https://img.shields.io/pypi/pyversions/django)

[![Discord](https://img.shields.io/discord/576479573886107699)](https://discord.gg/FUSrn8jUcR)

## Overview
This repo codifies the requirements for building and running Automatic Ripping Machine, and provides a docker container that has everything preinstalled. All you need to do is install the ARM source and set up files.

The `arm-dependencies`Docker image is rebuilt every night, so you should always get the most up-to-date versions of MakeMKV and Handbrake when you build ARM from this image.


## Usage
### Git Repo
To add this manually, run the following command:
```shell
git submodule add -b main https://github.com/alexhyett/arm-dependencies arm-dependencies
git submodule update --init --recursive
git config -f .gitmodules submodule.arm-dependencies.update rebase
git submodule update --remote
```

In your fork's `requirements.txt`, replace everything with
```text
-r arm-dependencies/requirements.txt
```

### Docker Container
To base your docker container on `arm-dependencies`, add this to the top of your `Dockerfile`:
```dockerfile

FROM automaticrippingmachine/arm-dependencies AS base
```
