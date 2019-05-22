# REINSTALCIÓN AUTOMATIZADA DE UN GEOSERVER
Esta reinstalación de geoserver se hace a partir de un repositorio local, en donde se encuentran las carpetas  
con la información de los _WORKSPACES_ , _LAYERS_, y _STYLES_.

Este repositorio con la información es un respaldo de la información principal del _GEOSERVER_ que se quiere respaldar.

## Primeros Pasos
Para obtener una copia del proyecto basta con clonarlo desde el github :  

`git clone https://github.com/grupoioa/geoserver_reinstalacion.git`  

Tiene que existir un repositorio con la información necesaria para que pueda correr el script, es decir, se debe contar  
con los workspaces, layers y styles del _GEOSERVER_ que se quiere reinstalar.  

Se deben modificar las variables globales del archivo `main_reinstalar_geoserver.py`, estas variables corresponden a  
los valores del *Geoserver* que se quiere reinstalar:

  * USUARIO          *"El nombre del usuario en el Geoserver"*
  * PASSW            *"El password del usuario en el Geoserver"*
  * URL_GEOSERVER    *"La URL del Geoserver"*
  * PATH_WORKSPACE   *"La ruta de la carpeta en donde se encuentran listados los workspaces"*
  * PATH_LAYERS      *"La ruta de la carpeta en donde se encuentran listadas las capas(layers)"* 
  * PATH_STYLES      *"La ruta de la carpeta en donde se encuentran listados los estilos"*

### Prerrequisitos
Este proyecto se realizó sobre Ubuntu 16.04 LTS utilizando `python3` y `Geoserver 2.11.2`.
   #### PYTHON 3
   Para instalar python3 sobre Ubuntu, hacemos lo siguiente desde la terminal :
   
   `sudo apt-get install python3.6` 
   
   #### GEOSERVER v2.11.2
   Para obtener geoserver se puede ingresar a la [página][1], para descargar el `WAR` e instalarlo en el servidor de  
   aplicaciones `TOMCAT`:  
   
   `sudo cp geoserver.war /root/tomcat/webapps/`  
   
   Por último se tiene que reiniciar tomcat

## Probando
Para iniciar con la intalación del *GEOSERVER* se ejecuta la siguiente línea :
  
  `python3 main_reinstalar_geoserver.py`

#### Descripción

El programa se compone de 4 funciones importantes:

   * __create_workspaces_geoserver__  
   Función que limpia el GEOSERVER, esto es quitar los workspace, layer y style por default que vienen en el GEOSERVER.
   * __create_workspaces_geoserver__  
   Función que crea los _workspaces_ para después poder crear sus capas y sus estilos correspondientes. 
   * __put_layers_geoserver__  
   Función que instala las capas (layers) en el nuevo GEOSERVER. 
   * __put_styles_geoserver__  
   Función que instala los estilos (styles) que afectan a cada capa del GEOSERVER.  
   (NOTA: aun no se pueden asignar los estilos a la capa correspondiente directamente con una petición REST a GEOSERVER)

## Construido con
* [Python][2] Lenguaje de programación
* [Geoserver][3] Documentación usada.

## Versionando  
Usamos [SemVer][4] para versionar. Para las versiones disponibles, consulte [las etiquetas en este repositorio][5].

## Autores
* **Raúl Medina Peña** - [Github][6]

## Licencia
Este proyecto está licenciado bajo la licencia MIT; consulte el archivo [LICENSE.md](LICENSE.md) para obtener detalles.

## Agradecimientos  
* Agradecemos a [Olmo Zavala][7] por su colaboración y todo su apoyo en este proyecto.

[1]: http://geoserver.org/release/2.11.2/
[2]: https://www.python.org/
[3]: https://docs.geoserver.org/
[4]: https://semver.org/lang/es/
[5]: https://github.com/grupoioa/geoserver_reinstalacion/tags
[6]: https://github.com/rmedina09
[7]: https://github.com/olmozavala
