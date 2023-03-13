ARG PYTHON_BASE
ARG PYTHON_VERSION

FROM python:$PYTHON_VERSION-$PYTHON_BASE

LABEL org.opencontainers.image.source=https://github.com/rez0n/docker-base

ENV PYTHONUNBUFFERED=1 \
    PYTHONFAULTHANDLER=1 \
    PYTHONHASHSEED=random \
    PIP_NO_CACHE_DIR=off \
    PIP_DISABLE_PIP_VERSION_CHECK=on \
    PIP_DEFAULT_TIMEOUT=100


# Install dependencies
RUN apt-get update && apt-get install --no-install-recommends --yes \
    awscli whois net-tools nano git openssh-client ca-certificates \
    libpq-dev gcc python3-dev \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Install Poetry
RUN pip install poetry gunicorn gevent
