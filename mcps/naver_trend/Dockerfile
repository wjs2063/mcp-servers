FROM python:3.13-slim
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/
LABEL authors="jeonjaehyeon"

WORKDIR /app

COPY uv.lock pyproject.toml ./
RUN uv sync --no-dev && uv pip list
COPY .env .

COPY ./mcps/naver_trend/server.py .

ENTRYPOINT ["uv","run","python","server.py"]