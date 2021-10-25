**Ejecutaremos el contenedor indicando dónde están los datos y la applicacion:**

```docker run -it --name base_python --rm -v $(pwd)/datos_base/:/datos -v $(pwd)/base_python:/app base_python```

**En caso de que generemos una versión con código fuente en /app, para producción será suficiente abrir
el contenedor con la ruta a los datos:**

```docker run -it --name base_python --rm -v $(pwd)/datos_base/:/datos base_python```

**Generaremos una imagen con el nombre del contenedor más el código del commit en el nombre.**

```docker build -f ./docker/Dockerfile . -t base_python```

**Para conocer el valor del commit con la información mínima:**

```git log -3 --pretty=format:"%h %s"```