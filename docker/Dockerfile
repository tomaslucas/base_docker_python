##Descargamos la imagen base del sistema operativo##
FROM python:3.9-slim-buster 

##Actualizamos el sistema##
RUN apt update && pip install --upgrade pip && apt install -y git

##Añadimos el usuario con el que vamos a trabajar
RUN adduser --disabled-password bob
USER bob
WORKDIR /app

##Copiamos el fichero con los paquetes a instalar y como lanzar jupyter##
COPY --chown=bob:bob . .

##Instalamos poetry
RUN python -m pip install poetry && python -m poetry config virtualenvs.create false && python -m poetry install 

##Añadimos a la variable environment el directorio local del nuevo usuario
ENV PATH="/home/bob/.local/bin:${PATH}"

##Exponemos el puerto de jupyter##
EXPOSE 8888

##Ejecutamos la bash por defecto##
CMD ["/bin/bash"]
