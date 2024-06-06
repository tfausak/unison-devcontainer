FROM --platform=linux/amd64 mcr.microsoft.com/devcontainers/base:debian
ARG UNISON_VERSION=latest
USER vscode
RUN \
  set -o errexit -o xtrace; \
  sudo apt-get update; \
  sudo apt-get install --assume-yes --no-install-recommends fzf xdg-utils; \
  mkdir --parents ~/.local/bin ~/unison; \
  cd ~/unison; \
  url=$( if test "$UNISON_VERSION" = latest; \
    then echo 'https://github.com/unisonweb/unison/releases/latest/download/ucm-linux.tar.gz'; \
    else echo "https://github.com/unisonweb/unison/releases/download/release%2F$UNISON_VERSION/ucm-linux.tar.gz"; \
    fi ); \
  curl --location --output ucm.tgz "$url"; \
  tar --extract --file ucm.tgz; \
  ln --symbolic $PWD/ucm ~/.local/bin
ENV UCM_WEB_UI=/home/vscode/unison/ui
ENV UCM_PORT=8080
ENV UCM_TOKEN=unison
