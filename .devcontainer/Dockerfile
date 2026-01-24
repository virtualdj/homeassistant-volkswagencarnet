FROM mcr.microsoft.com/devcontainers/python:3.13-bookworm

# Remove broken Yarn repo (MUST be before any apt update)
RUN rm -f /etc/apt/sources.list.d/*yarn*

# Install your apt deps
RUN apt update && \
    apt install -y --no-install-recommends \
        ffmpeg \
        libturbojpeg0 \
        libpcap-dev \
    && rm -rf /var/lib/apt/lists/*

# Make sure scripts are executable
RUN chmod +x /workspaces/*/.devcontainer/scripts/* || true
