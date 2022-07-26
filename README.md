# GameShell: un "juego" para aprender el shell de Unix
===========================================

![Illustration inspired by the game](Images/illustration-small.png)

Enseñar a estudiantes universitarios de primer año o estudiantes de secundaria a utilizar un shell de Unix
no siempre es la tarea más fácil o entretenida. Inicialmente, GameShell fue ideado
como una herramienta para ayudar a los estudiantes de la
[Université Savoie Mont Blanc](https://univ-smb.fr) para interactuar con un
shell  *real*, de una manera que se pueda fomentar el aprendizaje y al mismo tiempo los alumnos se puedan divertir. 

La idea inicial, por parte de Rodolphe Lepigre, era iniciar una sesión en bash con
un archivo de configuración que definía las "misiones", que luego sería
"validado" para avanzar en el juego.

Aquí está el resultado...

![GameShell's first mission](Images/gameshell_first_mission_small.gif)


No dudes en enviarnos tus comentarios, preguntas o sugerencias.
Podes abrir un [issues](https://github.com/phyver/GameShell/issues) o 
enviar un [pull requests](https://github.com/phyver/GameShell/pulls).
Estamos particularmente interesados ​​en cualquier nueva misión que vos
podrías crear!


Cómo jugar?
---------------

**Nota:** GameShell está en desarrollo: la versión actual 
no ha sido ampliamente probada por los estudiantes. Siéntase libre de informar todo
problema que pueda encontrar y cualquier sugerencia de mejora 
abriendo un [issue](https://github.com/phyver/GameShell/issues/new).

GameShell debería funcionar en cualquier sistema Linux estándar y
también en macOS y BSD (pero estos sistemas han sido menos probados). En Debian o
Ubuntu, las únicas dependencias (aparte de `bash`) son `awk` y
`gettext-base` (el primero suele instalarse por defecto). Algunas
de las misiones tienen dependencias adicionales: se cancelarán si 
las dependencias no se satisfacen. En Debian o Ubuntu, ejecute el 
siguiente comando para instalar todas las dependencias de juegos y misiones.
```sh
$ sudo apt install gettext man-db procps psmisc nano tree bsdmainutils x11-apps wget
```
Revisa el [user manual](doc/user_manual.md) para ver como instalar
las dependencias en otros sistemas (macOS, BSD, ...).

Suponiendo que todas las dependencias estan instaladas, podes probar la última versión del 
juego ejecutando los siguientes dos comandos en una terminal.
```sh
$ wget https://github.com/phyver/GameShell/releases/download/latest/gameshell.sh
$ bash gameshell.sh
```
El primer comando descargará la última versión del juego como un archivo autoextraíble y 
el segundo comando inicializará y ejecutara el juego desde este archivo. 
Las instrucciones para jugar se dan directamente en el juego.

Cuando salgas del juego (con `control-d` o el comando `gsh exit`), tu progreso se guardará en un nuevo 
archivo (llamado `gameshell-save.sh`). Se puede ejecutar ese script para reanudar el juego donde lo dejaste.


Si prefiere no ejecutar scripts extraños en su computadora, 
puede generar una imagen de Docker con :
```sh
$ mkdir GameShell; cd GameShell
$ wget --quiet https://github.com/phyver/GameShell/releases/download/latest/Dockerfile
$ docker build -t gsh .
$ docker run -it gsh
```
**Atención:** Su progreso **NO** se guardará cuando salga del juego, 
y se necesitan opciones adicionales si desea iniciar X programas desde GameShell. 
Consulte [esta sección](./doc/deps.md#running-GameShell-from-a-docker-container) 
del manual del usuario.


Documentacion
-------------

Para obtener más información sobre GameShell, están disponibles los siguientes documentos (solo en inglés):
- El [manual de usuario](doc/user_manual.md) explica, entre otras cosas, 
cómo iniciar el juego en todas las plataformas compatibles (Linux, macOS, BSD), 
cómo iniciar el juego desde la fuente y cómo generar un archivo 
de juego personalizado (que es útil para usar el juego como parte de un curso).
- El [manual del desarrollador](doc/dev_manual.md) explica, entre otras cosas, 
cómo crear una nueva misión, cómo traducir el juego y las misiones, 
y cómo participar en el desarrollo del juego.


¿Quién desarrolla GameShell?
----------------------------

### Desarrolladores

El juego está desarrollado por:
* [Pierre Hyvernat](http://www.lama.univ-smb.fr/~hyvernat) (desarrollador principal,
  [pierre.hyvernat@univ-smb.fr](mailto:pierre.hyvernat@univ-smb.fr)),
* [Rodolphe Lepigre](https://lepigre.fr).

### Colaboladores de misiones

* Pierre Hyvernat
* Rodolphe Lepigre
* Christophe Raffalli
* Xavier Provencal
* Clovis Eberhart
* Sébastien Tavenas
* Tiemen Duvillard

### Agradecimientos

* Todos los estudiantes que probaron las primeras versiones del juego.
* Joan Stark (alias jgs) que creó cientos de arte ASCII a finales de los 90. 
  La mayoría del arte ASCII que encontrarás en GameShell se debe a ella.


Licencia
-------

GameShell se lanza bajo el [GPLv3](https://www.gnu.org/licenses/gpl-3.0.en.html).

Enlace a este repositorio si usa GameShell.

GameShell es de código abierto y de uso gratuito. 
Una forma de reconocer el trabajo que requirió es enviando una postal real a

```
  Pierre Hyvernat
  Laboratoire de Mathématiques, CNRS UMR 5127
  Université de Savoie
  73376 Le Bourget du Lac
  FRANCE
```

