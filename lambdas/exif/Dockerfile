FROM public.ecr.aws/lambda/python:3.13

# install uv
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

############
#
# TODO: implement the rest of the image
#
############
COPY pyproject.toml ${LAMBDA_TASK_ROOT}/

WORKDIR /var/task

COPY pyproject.toml .

RUN uv sync --no-cache

COPY handler.py .

ENV PYTHONPATH="${LAMBDA_TASK_ROOT}/.venv/lib/python3.13/site-packages"

CMD ["handler.exif_handler"]
