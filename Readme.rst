Base_Python
===========

*Esta es la estructura base para la creación de cualquer proyecto.*

El contenedor incluye todos los módulos base para generar análisis de datos.


**Ejecutaremos el contenedor indicando dónde están los datos y la applicacion, en caso de querer modificar el código de esta:**

.. code-block:: console

    $ docker run -it --name base_python --rm -v /datosInBase/:/datosIn -v $(pwd):/app base_python

**Para producción, si hemos incluído los ficheros de src o notebooks, en /app, será suficiente abrir el contenedor con la ruta a los datos:**

.. code-block:: console

    $ docker run -it --name base_python --rm -v datosInBase:/datosIn -v datosOutBase:/datosOut base_python

**Si tenemos que actualizar la imagen del contenedor añadiremos como etiqueta del mismo el código del commit:**

.. code-block:: console

    $ docker build -f ./docker/Dockerfile . -t base_python:cod_commit

**Para conocer el código del commit generado ejecutaremos:**


.. code-block:: console

    $ git log -3 --pretty=format:"%h %s"



Creación de la capa de documentación
------------------------------------

Ejecutar la siguiente línea de comando:

.. code-block:: console

    $ sphinx-quickstart docs


*Más información sobre cómo documentar con* `sphinx <https://www.sphinx-doc.org/en/master/tutorial/getting-started.html>`_ *en este enlace.*


