# Documentación del proyecto

La documentación del **Proyecto Intermodular** se realizará utilizando **GitHub**, lo que permitirá mantener organizada y actualizada toda la información del proyecto a medida que avance el curso.

El objetivo será que cada alumno disponga de un repositorio propio en el que irá incorporando la documentación de las distintas fases de su proyecto. Esta documentación se transformará automáticamente en una **página web**, que constituirá la memoria técnica y permitirá consultar fácilmente la evolución y los resultados del trabajo realizado.

Para ello utilizaremos las siguientes tecnologías:

- **GitHub**
- **Markdown**
- **MkDocs**
- **Material for MkDocs**
- **GitHub Actions**
- **GitHub Pages**


## Actividad 1. Preparación del entorno de trabajo y documentación
En esta actividad vas a preparar el **entorno de trabajo y documentación que utilizarás durante el desarrollo del Proyecto Intermodular**.

Este entorno te permitirá **almacenar, organizar, desarrollar y documentar** tu proyecto en GitHub y generar, a partir de su documentación, una **página web que se irá actualizando a medida que avance el proyecto**.

### 1. Requisitos previos

Antes de comenzar la actividad debes disponer de:

- Una **cuenta de GitHub**. Si todavía no tienes una, créala en GitHub antes de comenzar la actividad.
- Acceso a **ChatGPT**, que utilizarás como guía durante todo el proceso.
- Un **navegador web**.
  
### 2. Metodología:

- **Aprendizaje práctico guiado**, utilizando la **IA generativa como herramienta de andamiaje**. ChatGPT actuará como guía, proporcionando instrucciones y explicaciones paso a paso durante el desarrollo de la actividad.

- **Learning by doing (aprender haciendo)**. Los conceptos y la relación entre las distintas tecnologías se irán descubriendo y comprendiendo **a medida que se utilizan de forma práctica**.

### 3. Pautas para la realización de la actividad

- **Copia el prompt completo**.
- Abre **ChatGPT** e inicia una **nueva conversación**.
- **Pega el prompt** y envíalo.
- Sigue las instrucciones que ChatGPT te vaya proporcionando.
- Realiza **un único paso cada vez** y comprueba que el resultado es correcto antes de continuar.
- Lee atentamente las explicaciones. El objetivo no es únicamente completar los pasos, sino **comprender qué estás haciendo y para qué sirve cada tecnología**.
- Si el resultado que obtienes no coincide con el esperado, **no continúes**. Explica a ChatGPT qué ha ocurrido y, si es necesario, adjunta una captura de pantalla para que pueda ayudarte a solucionar el problema.
- No ejecutes instrucciones diferentes a las indicadas en la actividad ni realices instalaciones en tu equipo.

"Recuerda"
    ChatGPT actuará como **guía**, pero eres tú quien debe realizar las acciones, comprobar los resultados y comprender el proceso.

### 4. Prompt de la actividad

Copia el siguiente prompt completo y pégalo en una **nueva conversación de ChatGPT**.



``` { .text .prompt-scroll }
Actúa como mi profesor y guía técnico para preparar el entorno de trabajo de mi
Proyecto Intermodular de 2.º de ASIR.

Quiero realizar todo el proceso yo mismo y entender qué estoy haciendo.
NO quiero que me des todos los pasos de golpe.

Debes guiarme PASO A PASO.


==========================================================
REGLAS IMPORTANTES
==========================================================

1. Dame únicamente un paso cada vez.

2. Explícame brevemente qué estamos haciendo y para qué sirve.

3. Después de cada paso, espera a que yo te confirme que lo he realizado
antes de continuar.

4. Si aparece un error, NO continúes. Ayúdame primero a localizarlo y
solucionarlo.

5. No des por supuesto que conozco GitHub, Markdown, MkDocs,
GitHub Actions o GitHub Pages.

6. Cuando aparezca por primera vez una tecnología o concepto nuevo,
explícame brevemente qué es.

7. Si tengo que escribir código o contenido en un archivo, dame exactamente
el contenido que debo escribir y explícame sus partes principales.

8. Trabajaremos SIEMPRE sobre la rama principal main, salvo la rama
gh-pages, que será creada y actualizada automáticamente para publicar
la web.

9. TODO el proceso se realizará utilizando exclusivamente la INTERFAZ WEB
DE GITHUB desde el navegador.

10. NO me des instrucciones para:
- instalar Git;
- utilizar comandos Git;
- clonar el repositorio;
- trabajar con un repositorio local;
- utilizar terminal o consola;
- instalar Python;
- utilizar pip;
- crear entornos virtuales;
- instalar MkDocs en mi ordenador;
- utilizar mkdocs serve;
- trabajar con VS Code.

11. MkDocs se instalará y ejecutará automáticamente en GitHub mediante
GitHub Actions. No necesito tener MkDocs instalado en mi ordenador.

12. Si la interfaz actual de GitHub es diferente de la que esperas,
pídeme una captura de pantalla antes de indicarme opciones que no
encuentres con seguridad.


==========================================================
OBJETIVO FINAL
==========================================================

Quiero crear un repositorio en GitHub para mi Proyecto Intermodular de ASIR,
documentar el proyecto mediante Markdown y convertir esa documentación en
una página web utilizando:

- GitHub
- Markdown
- MkDocs
- GitHub Actions
- GitHub Pages

Todo se realizará desde el navegador.

Debemos llegar progresivamente a una estructura similar a:

Proyecto-Intermodular-ASIR/
│
├── README.md
├── mkdocs.yml
│
├── docs/
│   ├── index.md
│   └── 01_introduccion.md
│
└── .github/
    └── workflows/
        └── deploy.yml


==========================================================
FASE 1. CREACIÓN DEL REPOSITORIO EN GITHUB
==========================================================

Guíame para crear desde mi cuenta de GitHub un repositorio para mi
Proyecto Intermodular.

Explícame brevemente qué es un repositorio de GitHub y para qué lo
utilizaremos.

El repositorio se llamará:

Proyecto-Intermodular-ASIR

Inicialmente quiero:

- utilizar la rama principal main;
- crear un README.md;
- realizar todo desde la interfaz web de GitHub.

Explícame brevemente qué función tendrá README.md.

No continúes hasta que confirme que el repositorio está creado.


==========================================================
FASE 2. PRIMER DOCUMENTO DEL PROYECTO
==========================================================

Una vez creado el repositorio, guíame para crear desde la interfaz web
de GitHub:

docs/01_introduccion.md

Explícame:

- qué es la carpeta docs;
- qué significa la extensión .md;
- qué es Markdown.

IMPORTANTE:

Cuando cree docs/01_introduccion.md, explícame que el archivo todavía
no quedará realmente creado en el repositorio hasta que guarde el cambio
mediante un commit.

Haz que realice un commit para crear el archivo.

Utiliza como mensaje:

"Creado documento inicial de introducción"

El commit debe realizarse directamente sobre la rama principal main.

No continúes hasta que confirme que el archivo existe.


==========================================================
FASE 3. CARACTERIZACIÓN INICIAL DEL RETO
==========================================================

Ayúdame a completar:

docs/01_introduccion.md

La introducción debe contener progresivamente:

# 1. Introducción

## 1.1. Título del reto
## 1.2. Contexto
## 1.3. Problemática o necesidad
## 1.4. Objetivos
### Objetivo general
### Objetivos específicos
## 1.5. Interesados

NO inventes inicialmente el contenido de mi proyecto.

Primero pregúntame cuál es mi idea de proyecto.

Después ayúdame a desarrollar CADA APARTADO POR SEPARADO.

Debes ayudarme especialmente a diferenciar entre PROBLEMA/NECESIDAD
y SOLUCIÓN.

En la problemática debo explicar la necesidad existente sin decidir todavía
qué servidores, sistemas operativos, aplicaciones, bases de datos o
tecnologías voy a utilizar.

Para los interesados, ayúdame a crear una tabla Markdown con esta estructura:

| Interesado | Relación con el proyecto | Necesidad principal |
|---|---|---|

Enséñame únicamente el Markdown que vaya necesitando y ayúdame a utilizar
Preview para comprobar el resultado.

Cuando terminemos, haz que guarde los cambios mediante un commit en main
con un mensaje descriptivo.


==========================================================
FASE 4. CONTROL DE VERSIONES DESDE GITHUB
==========================================================

Enséñame a comprender el control de versiones utilizando ÚNICAMENTE
la interfaz web de GitHub.

Explícame:

- qué es un commit;
- para qué sirve su mensaje;
- cómo consultar History;
- cómo ver qué ha cambiado entre versiones.

Haz que realice una pequeña modificación en docs/01_introduccion.md,
cree un nuevo commit y consulte posteriormente History.

NO utilices comandos Git ni repositorios locales.


==========================================================
FASE 5. PREPARACIÓN DE MKDOCS
==========================================================

Explícame primero qué es MkDocs y esta relación:

Archivos Markdown
        ↓
      MkDocs
        ↓
    Página web

Guíame para crear desde GitHub:

docs/index.md

Después crea conmigo, en la raíz del repositorio:

mkdocs.yml

Configúralo inicialmente con:

site_name: Proyecto Intermodular ASIR

nav:
  - Inicio: index.md
  - Introducción: 01_introduccion.md

Explícame la función de mkdocs.yml y la relación entre este archivo
y los documentos almacenados en docs.

Haz que guarde los cambios mediante commits en main.

NO me indiques que instale MkDocs en mi ordenador.


==========================================================
FASE 6. PUBLICACIÓN AUTOMÁTICA CON GITHUB ACTIONS
==========================================================

Explícame de forma sencilla qué es GitHub Actions.

Debo comprender esta idea:

Cambio en main
      ↓
GitHub Actions
      ↓
MkDocs
      ↓
Web generada

Guíame para crear desde GitHub:

.github/workflows/deploy.yml

Utiliza este workflow:

name: Publicar documentación MkDocs

on:
  push:
    branches:
      - main

permissions:
  contents: write

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
      - name: Descargar repositorio
        uses: actions/checkout@v4

      - name: Configurar Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.x'

      - name: Instalar MkDocs
        run: pip install mkdocs

      - name: Publicar web
        run: mkdocs gh-deploy --force

Explícame los bloques antes de hacer el commit.

Los comandos incluidos en deploy.yml son ejecutados automáticamente
por GitHub Actions. Yo NO debo ejecutarlos manualmente.

Después llévame a Actions para comprobar la ejecución.

Si aparece un error, NO continúes hasta localizarlo y solucionarlo.


==========================================================
FASE 7. COMPROBACIÓN DE LA RAMA GH-PAGES
==========================================================

Cuando GitHub Actions funcione correctamente, explícame que el workflow
genera automáticamente la página web con MkDocs y la publica en:

gh-pages

Todo este proceso lo realiza GitHub Actions automáticamente.
Yo NO tengo que ejecutar ningún comando ni utilizar un terminal.

Ayúdame a comprobar desde la interfaz web de GitHub que existen:

main
gh-pages

Explícame la diferencia:

main
→ contiene los archivos originales del proyecto y la documentación
que yo modifico.

gh-pages
→ contiene los archivos de la página web generados automáticamente
por MkDocs.

No debo modificar manualmente gh-pages.

Espera mi confirmación antes de continuar.


==========================================================
FASE 8. PUBLICACIÓN CON GITHUB PAGES
==========================================================

Explícame brevemente qué es GitHub Pages.

Guíame desde GitHub a:

Settings
→ Pages
→ Build and deployment

Configura:

Source:
Deploy from a branch

Branch:
gh-pages

Folder:
/ (root)

Haz que pulse Save y ayúdame a localizar el mensaje:

"Your site is live at..."

No continúes hasta que confirme que la web ha sido publicada.


==========================================================
FASE 9. COMPROBACIÓN DE LA WEB
==========================================================

Haz que abra la URL pública.

Debemos comprobar:

- que aparece la página Inicio;
- que aparece la página Introducción;
- que funciona el menú;
- que se visualiza correctamente el contenido Markdown.

Si algo no funciona, NO continúes hasta solucionarlo.


==========================================================
FASE 10. COMPROBAR EL CICLO COMPLETO
==========================================================

Hazme modificar una pequeña parte de:

docs/01_introduccion.md

desde GitHub.

Después haz que realice un commit en main.

Debemos comprobar:

Modificación Markdown
        ↓
Commit en main
        ↓
GitHub Actions
        ↓
MkDocs
        ↓
gh-pages
        ↓
GitHub Pages
        ↓
Web actualizada

Comprueba primero Actions y después la página web.


==========================================================
REGLA FINAL
==========================================================

Durante TODA la actividad trabaja exclusivamente con la interfaz web
de GitHub.

NO introduzcas:

- repositorios locales;
- terminal;
- Git por línea de comandos;
- git clone;
- Python local;
- pip local;
- entornos virtuales;
- VS Code;
- mkdocs serve;
- instalación local de MkDocs.

NO ME EXPLIQUES AHORA TODO EL PROCESO.

EMPIEZA ÚNICAMENTE POR EL PRIMER PASO:
crear el repositorio desde la interfaz web de GitHub.

```







  
