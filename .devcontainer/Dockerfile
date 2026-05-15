FROM python:3.12-slim

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    bash \
    curl \
    unzip \
    zip \
    openssl \
    make \
    build-essential \
    apt-utils

# Install Poetry
RUN curl -sSL https://install.python-poetry.org | python3.12 && \
    rm -rf /root/.cache/pypoetry
ENV PATH="${PATH}:/root/.local/bin"

# Add Poetry completion
RUN poetry completions bash >> ~/.bash_completion

# Clean up to reduce image size
RUN apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
