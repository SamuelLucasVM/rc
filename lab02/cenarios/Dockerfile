# Dockerfile
FROM python:3.11-slim

# Define o diretório de trabalho
WORKDIR /app

# Instala as dependências (flask e requests)
RUN pip install --no-cache-dir flask requests

# Copia o script para dentro do container
COPY roteador.py .

# Cria uma pasta para os arquivos de configuração
RUN mkdir -p /app/config

# O comando de inicialização usa variáveis de ambiente que definiremos no docker-compose
CMD python roteador.py \
    -p $ROUTER_PORT \
    -f /app/config/$CONFIG_FILE \
    --network $ROUTER_NETWORK \
    --interval $UPDATE_INTERVAL
