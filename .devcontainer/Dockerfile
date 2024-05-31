FROM --platform=linux/amd64 mcr.microsoft.com/devcontainers/base:debian
USER vscode
RUN \
  set -o errexit -o xtrace; \
  mkdir --parents ~/.local/bin ~/unison; \
  cd ~/unison; \
  curl --output ucm.tgz curl --location --output ~/unison/ucm.tgz \
    https://github.com/unisonweb/unison/releases/latest/download/ucm-linux.tar.gz; \
  tar --extract --file ucm.tgz; \
  ln --symbolic $PWD/ucm ~/.local/bin
