# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.205.2/containers/debian/.devcontainer/base.Dockerfile

# [Choice] Debian version (use bullseye or stretch on local arm64/Apple Silicon): bullseye, buster, stretch
ARG VARIANT="buster"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

# ** [Optional] Uncomment this section to install additional packages. **
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    python3-all python3-setuptools python3-aiohttp python3-pytest python3-pytest-asyncio \
    devscripts quilt lintian debhelper dh-python git-buildpackage dput bash-completion

COPY devscripts.conf /etc/
COPY dput.cf /etc/
COPY git-to-deb.sh /etc/profile.d/
