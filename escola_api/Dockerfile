# 1. Imagem base
FROM python:3.11-slim

# 2. Diretorio de trabalho
WORKDIR /app

# 3. Instalar o Poetry e configurar para NAO criar virtualenv
RUN pip install poetry && poetry config virtualenvs.create false

# 4. Copiar arquivos de dependencia e instalar
COPY pyproject.toml poetry.lock ./
RUN poetry install --no-root

# 5. Copiar o codigo da aplicacao
COPY . .

# 6. Expor a porta
EXPOSE 5000

# 7. Comando de inicializacao
CMD python -m flask --app app run --host 0.0.0.0 --port 5000