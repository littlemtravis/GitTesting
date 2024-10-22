# For more information, please refer to https://aka.ms/vscode-docker-python
FROM python:3.10 AS base

ENV \ 
    # Keeps Python from generating .pyc files in the container
    PYTHONDONTWRITEBYTECODE=1 \
    PYTHONFAULTHANDLER=1 \
    # Turns off buffering for easier container logging
    PYTHONUNBUFFERED=1 \
    # The seed that is used for generating the hash(). Fixed is good for development but random may be better for production.
    PYTHONHASHSEED=0 \
    # PYTHONPATH=":./src" \
    # Poetry's configuration:
    POETRY_NO_INTERACTION=1 \
    POETRY_VIRTUALENVS_CREATE=false \
    POETRY_CACHE_DIR='/var/cache/pypoetry' \
    POETRY_HOME='/usr/local' \
    POETRY_VERSION=1.8.4

RUN apt-get update \
    && apt-get install -y sudo \
    && useradd -ms /bin/bash codespace

USER codespace
WORKDIR /home/codespace

# RUN curl -sSL https://install.python-poetry.org | python3 -

# COPY pyproject.toml poetry.lock /

# # Project initialization:
# RUN poetry install