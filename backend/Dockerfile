FROM python:3.12
EXPOSE 8000
WORKDIR /app
ENV PATH="${PATH}:/root/.local/bin"
RUN <<EOF
apt-get update
apt-get install -y pipx libpq-dev gcc python3-dev
pipx ensurepath
pipx install poetry==1.8.3
# poetry config virtualenvs.create false
EOF

COPY poetry.lock pyproject.toml /app
RUN poetry install
COPY . /app
CMD ["poetry", "run", "python", "manage.py", "runserver", "0.0.0.0:8000"]