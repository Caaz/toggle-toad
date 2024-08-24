FROM python:3.12
EXPOSE 8000
WORKDIR /app
ENV PATH="${PATH}:/root/.local/bin"
RUN <<EOF
apt-get update
apt-get install -y pipx libpq-dev gcc python3-dev
pip install poetry==1.8.3
poetry config virtualenvs.create false
EOF

COPY poetry.lock pyproject.toml /app
RUN poetry install --no-root
COPY . /app
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]