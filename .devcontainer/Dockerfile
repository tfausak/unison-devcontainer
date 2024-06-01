FROM --platform=linux/amd64 mcr.microsoft.com/devcontainers/base:debian
USER vscode
RUN \
  set -o errexit -o xtrace; \
  sudo apt-get update; \
  sudo apt-get install --assume-yes --no-install-recommends fzf xdg-utils; \
  mkdir --parents ~/.local/bin ~/unison; \
  cd ~/unison; \
  curl --output ucm.tgz curl --location --output ~/unison/ucm.tgz \
    https://github.com/unisonweb/unison/releases/latest/download/ucm-linux.tar.gz; \
  tar --extract --file ucm.tgz; \
  ln --symbolic $PWD/ucm ~/.local/bin
ENV UCM_WEB_UI=/home/vscode/unison/ui
ENV UCM_PORT=8080
ENV UCM_TOKEN=unison
