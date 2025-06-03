FROM rust:1.87-bookworm

# Add a vscode user with UID/GID 1000 (default expected by VS Code)
RUN apt-get update && apt-get install -y sudo \
    && groupadd --gid 1000 vscode \
    && useradd -s /bin/bash --uid 1000 --gid vscode -m vscode \
    && echo "vscode ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers.d/nopasswd \
    && chmod 0440 /etc/sudoers.d/nopasswd

USER vscode
WORKDIR /home/vscode