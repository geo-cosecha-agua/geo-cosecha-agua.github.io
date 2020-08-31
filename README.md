# Sitio web del Portal Geoespacial del Proyecto Cosecha de Agua en Nicaragua

## Descripción general
Este repositorio contiene la documentación y el código fuente del sitio web del Portal Geoespacial del Proyecto Cosecha de Agua en Nicaragua, publicado en [https://geo-cosecha-agua.github.io/](https://geo-cosecha-agua.github.io/). El sitio fue construído con el generador de sitios estáticos [Jekyll](https://jekyllrb.com/) y alojado en el servicio de alojamiento [GitHub Pages](https://pages.github.com/) de [GitHub](https://github.com/). El diseño del sitio está basado en la plantilla [Business Frontpage](https://jekyll-themes.com/business-frontpage/).

En el resto de este documento, se detalla el procedimiento para clonar y modificar el código fuente del sitio en una estación de trabajo local, así como para actualizarlo en el repositorio GitHub. Para facilitar su implementación y mantenimiento, el procedimiento se realiza en un ambiente [Conda](https://docs.conda.io/).

## Procedimiento para clonación, modifición y actualización del sitio en GitHub
Los siguientes comandos deben ejecutarse en la línea de comandos del sistema operativo. Se recomienda utilizar la interfaz de línea de comandos de Anaconda. Se asume que el ambiente Conda ha sido creado de la manera que se muestra en la sección siguiente a esta.
```shell
# Activación del ambiente Conda
$ conda activate geo-cosecha-agua-sitio-web

# Clonación del repositorio
$ git clone https://github.com/geo-cosecha-agua/geo-cosecha-agua.github.io.git
$ cd geo-cosecha-agua.github.io

# Prueba del sitio con el servidor interno de Jekyll
$ jekyll serve
# El sitio debe estar disponible en http://127.0.0.1:4000/geo-cosecha-agua.github.io/

# Modificaciones al sitio web...
# modificaciones...
# modificaciones...

# Actualización del repositorio en GitHub
$ git add .
$ git commit -m "Comentario apropiado para reflejar los cambios"
$ git push

# Desactivación del ambiente Conda
$ conda deactivate
```

## Creación y configuración del ambiente Conda
El ambiente Conda solamente debe crearse una vez. Luego puede seguir usándose de la manera que se especifica en la sección anterior.
```shell
# Actualización de Conda
$ conda update -n base -c defaults conda

# Creación del ambiente
$ conda create -n geo-cosecha-agua-sitio-web

# Activación del ambiente
$ conda activate geo-cosecha-agua-sitio-web

# Instalación de paquetes
$ conda install -c conda-forge rb-jekyll imagemagick

# Desactivación del ambiente
$ conda deactivate
```

## Reducción del tamaño de las imágenes
Imágenes de los tableros de control
```shell
# Reducción del tamaño de las imágenes de los tableros de control
$ cd assets/img
$ convert tablero-control-beneficiarios-2020-08-30.png -resize 50% tablero-control-beneficiarios-2020-08-30-reducido.png
$ convert tablero-control-obras-2020-08-30.png -resize 50% tablero-control-obras-2020-08-30-reducido.png
```

Logo del proyecto cosecha de agua (se usa en el perfil de la organización GitHub)
```shell
# Reducción del tamaño del logo del Proyecto Cosecha de Agua
$ cd assets/img
$ convert logo-proyecto-cosecha-agua.png -resize 216x216\! logo-proyecto-cosecha-agua-reducido.png
```
