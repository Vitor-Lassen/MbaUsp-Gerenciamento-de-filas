# Imagem oficial do Python 3.9 slim
FROM python:3.9-slim

# Define o diretório de trabalho dentro do container
WORKDIR /code

RUN apt-get update && apt-get install -y \
    build-essential \
    gcc \
    libffi-dev \
    libssl-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Copia apenas os arquivos necessários para evitar carregar arquivos desnecessários
COPY requirements.txt /code/
RUN pip install --upgrade pip
# Instala as dependências diretamente do requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copia apenas o diretório 'app' para dentro do container
COPY . /code/app
