fennix
======

El objetivo de este proyecto es el de crear material de la mayor calidad posible de forma colaborativa.

Hoy en día cada foro y comunidad de seguridad crea su propio material, muchas veces ese material no esta completo del todo, es muy básico, y con faltas ortográficas.
Con el propósito de cambiar esto nació este proyecto, pero para eso necesitábamos que los usuarios pudieran colaborar activamente, por eso que decidimos usar github para que cualquier usuario de cualquier lugar, no solo de Hack x Crack (foro de donde salio este proyecto originalmente) pueda proponer cambios o correcciones al material.

Para los nuevos textos se debera clonar la branch "develop", crear la carpeta del nuevo texto y cuando este completo mandar una pull request. En la branch master en principio no se aceptaran pull request.

Creamos el canal IRC #fennix en freenode (irc.freenode.net) para discutir la organización del proyecto

Notas
------
* Cuidar mínimamente la ortografía y evitar el uso de emoticonos
* Los commits deben ser específicos
* Estrcturar los textos en varios archivos latex
* Usar la plantilla de la carpeta "plantilla"

Estructura de los libros
------------------------
El archivo de clase es fennix.cls, por lo que debe usarse como documento de clase. El documento debe tener la estructura siguiente:

```TeX
\documentclass{fennix}

\begin{document}

\title{Título del documento}
\author{Autor del documento}
\date{}
\maketitle
\begin{resumen}
Aquí debe ir un resumen del documento
\end{resumen}

\begin{requisitos}
\begin{itemize}
\item Aquí deben ir los requisitos necesarios para entender el documento
\end{itemize}
\end{requisitos}

Aquí el cuerpo del documento

\begin{colabs}
Aquí los colaboradores con un enlace de contacto, tal cual se encuentra en la plantilla:

Colaborador 1: email1

...
\end{colabs}

\end{document}
```
El entorno "requisitos" ya incluye el índice, no hace falta incluir un \tableofcontents.

En el archivo plantilla/plantilla.tex se encuentra lo anterior para poder empezar a escribir.

El archivo ejemplo/prueba.tex es el cuaderno original de piou sobre punteros reescrito en parte mediante latex. Contiene tablas, trozos de código, secciones, subsecciones, etc. por lo que puede servir como referencia para algunas cosas básicas. La versión compilada es ejemplo/prueba.pdf.

Compilacion de un libro
-----------------------
Para compilar hace falta tener instalada una distribución completa de LaTeX. Los repositorios Linux suelen contener el paquete texlive-full que incluye todo lo necesario. En sistemas con apt:

 ``sudo apt-get install texlive-full``

Para compilar el documento (obligatorio usar XeLaTeX, no LaTeX ni pdfLaTeX):

 ``xelatex archivo.tex``

Creará el archivo archivo.pdf
