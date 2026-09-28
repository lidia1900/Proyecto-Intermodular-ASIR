# Git y entorno de desarrollo

Durante el desarrollo del **Proyecto Intermodular** iremos creando y modificando numerosos archivos: documentación, configuraciones, scripts, código fuente, etc.

Para mantener todos estos archivos organizados y conservar un historial de los cambios realizados utilizaremos **Git** como sistema de control de versiones y **GitHub** como repositorio remoto.

Además, utilizaremos **Visual Studio Code** como entorno principal de trabajo.

---

## ¿Qué es Git?

**Git** es un sistema de control de versiones.

Su función principal es permitirnos registrar los cambios que vamos realizando en los archivos de un proyecto.

Gracias a Git podremos:

- Mantener un historial de las distintas versiones del proyecto.
- Saber qué archivos han sido modificados.
- Registrar conjuntos de cambios mediante *commits*.
- Recuperar versiones anteriores si fuera necesario.
- Trabajar de forma ordenada durante todo el desarrollo.
- Sincronizar nuestro trabajo con un repositorio remoto alojado en GitHub.

Git trabaja principalmente en nuestro **ordenador**, sobre una copia local del proyecto.

---

## Git y GitHub no son lo mismo

Aunque utilizaremos ambas herramientas conjuntamente, es importante distinguirlas.

### Git

**Git** es el sistema de control de versiones instalado en nuestro ordenador.

Se encarga de controlar los cambios realizados en los archivos y mantener el historial de versiones del proyecto.

### GitHub

**GitHub** es una plataforma que permite alojar repositorios Git en Internet.

En nuestro Proyecto Intermodular utilizaremos GitHub para mantener una copia remota del repositorio y poder sincronizarla con nuestro trabajo local.

De forma simplificada:

```text
ORDENADOR DEL ALUMNO                         GITHUB

┌──────────────────────┐              ┌──────────────────────┐
│ Repositorio local    │              │ Repositorio remoto   │
│                      │   push  ───► │                      │
│         Git          │              │       GitHub         │
│                      │ ◄───  pull   │                      │
└──────────────────────┘              └──────────────────────┘
```

---

## Repositorio local y repositorio remoto

A lo largo del proyecto trabajaremos con dos copias relacionadas del repositorio.

### Repositorio local

Es la copia del proyecto almacenada en nuestro ordenador.

Será sobre esta copia donde normalmente trabajaremos con **Visual Studio Code**, modificaremos archivos y utilizaremos los comandos de Git.

### Repositorio remoto

Es la copia del repositorio almacenada en **GitHub**.

Nos servirá como punto de sincronización y permitirá mantener el proyecto disponible independientemente del equipo desde el que estemos trabajando.

Git mantiene relacionados ambos repositorios.

---

## Entorno de desarrollo

Para trabajar con el Proyecto Intermodular utilizaremos principalmente las siguientes herramientas:

- **Visual Studio Code:** editor desde el que podremos trabajar con los archivos del proyecto.
- **Git:** sistema de control de versiones utilizado para registrar los cambios.
- **GitHub:** plataforma donde se encuentra alojado el repositorio remoto.
- **GitHub CLI (`gh`):** herramienta que permite trabajar y autenticarnos en GitHub desde la terminal.

El entorno podrá prepararse tanto en **Ubuntu** como en **Windows**.

Los comandos básicos de Git que utilizaremos serán prácticamente los mismos independientemente del sistema operativo.

---

## Flujo básico de trabajo

Al comenzar a trabajar por primera vez en un equipo tendremos que obtener una copia del repositorio existente en GitHub.

Para ello utilizaremos:

```bash
git clone
```

A partir de ese momento trabajaremos sobre la copia local.

El flujo habitual será:

```text
GitHub
   │
   │ git clone
   ▼
Repositorio local
   │
   ▼
Modificar archivos
   │
   ▼
git status
   │
   ▼
git add
   │
   ▼
git commit
   │
   ▼
git push
   │
   ▼
GitHub
```

Es importante comprender que **guardar un archivo en Visual Studio Code no significa que el cambio se haya enviado a GitHub**.

Los cambios pasan por diferentes etapas antes de llegar al repositorio remoto.

---

## Comandos básicos de Git

Estos serán algunos de los comandos que utilizaremos con mayor frecuencia:

| Comando | Función |
|---------|---------|
| `git clone` | Crea en nuestro ordenador una copia de un repositorio existente |
| `git status` | Muestra el estado actual del repositorio y los archivos modificados |
| `git add` | Selecciona los cambios que queremos incluir en el próximo commit |
| `git commit` | Registra los cambios en el historial del repositorio local |
| `git push` | Envía los commits del repositorio local a GitHub |
| `git pull` | Descarga e integra en nuestro repositorio local los cambios existentes en GitHub |
| `git log` | Permite consultar el historial de commits |

---

## ¿Qué es un commit?

Un **commit** representa un punto concreto del historial del proyecto.

Podemos entenderlo como una versión registrada del trabajo realizado hasta ese momento.

Cada commit incluye, entre otra información:

- Los cambios realizados.
- El autor.
- La fecha.
- Un mensaje que describe el cambio.
- Un identificador único.

Por ejemplo:

```bash
git commit -m "Añade configuración inicial del servidor"
```

Los mensajes de los commits deben ser **breves pero descriptivos**, de forma que al consultar posteriormente el historial podamos entender qué se hizo en cada momento.

---

## Sincronización con GitHub

Realizar un `commit` **no envía automáticamente los cambios a GitHub**.

El commit queda inicialmente registrado en nuestro repositorio local.

Para enviarlo al repositorio remoto utilizaremos:

```bash
git push
```

En sentido contrario, si existen cambios en GitHub que todavía no tenemos en nuestro ordenador, podremos obtenerlos mediante:

```bash
git pull
```

Por tanto:

```text
LOCAL  ─── git push ───►  GITHUB

LOCAL  ◄── git pull ────  GITHUB
```

---

## Historial del proyecto

Una de las principales ventajas de utilizar Git es que podremos consultar la evolución del proyecto.

Por ejemplo:

```bash
git log --oneline
```

permite visualizar de forma resumida los commits realizados:

```text
8a31c42 Añade configuración inicial
34ab221 Actualiza documentación
a82f613 Crea estructura del proyecto
```

De esta forma podremos conocer cómo ha ido evolucionando el proyecto a lo largo del curso.

---

## Uso de permisos

Los comandos habituales de Git se ejecutarán con el **usuario normal del sistema**.

Por ejemplo:

```bash
git clone
git status
git add
git commit
git push
git pull
```

!!! warning "Importante"
    No se deben ejecutar los comandos habituales de Git utilizando `sudo`.

Los permisos de administrador únicamente podrán ser necesarios para determinadas tareas de configuración del equipo, como la instalación inicial de Git o de otras herramientas.

Si estás trabajando en un **ordenador del aula** y el sistema solicita una contraseña de administrador durante una instalación, deberás pedir al profesor que introduzca las credenciales necesarias.

---

## Forma de trabajo durante el proyecto

Durante el curso utilizaremos Git de forma habitual.

El procedimiento general será:

1. Trabajar sobre la copia local del proyecto.
2. Modificar los archivos necesarios utilizando Visual Studio Code.
3. Comprobar qué archivos han cambiado.
4. Seleccionar los cambios que queremos registrar.
5. Crear un commit con un mensaje descriptivo.
6. Enviar los commits a GitHub.
7. Mantener sincronizados el repositorio local y el repositorio remoto.

De esta forma, **GitHub contendrá la evolución del Proyecto Intermodular y Git nos permitirá mantener un historial organizado de todo el trabajo realizado**.

### Prompt de la actividad

Copia el siguiente prompt completo y pégalo en ChatGPT. A partir de ese momento, ChatGPT te guiará paso a paso durante la realización de la actividad. No avances por tu cuenta: ejecuta cada acción, comprueba el resultado y continúa cuando el paso anterior haya funcionado correctamente.

<div class="prompt-scroll" markdown="1">

```text
Actúa como mi profesor y asistente técnico para realizar la Tarea 2 del Proyecto Intermodular de 2.º ASIR.

IMPORTANTE: aunque soy alumno de 2.º ASIR, quiero que me expliques Git desde cero, con un nivel inicial, como si fuera la primera vez que trabajo con Git en local.

NO me des todos los pasos de golpe.

Debes trabajar conmigo PASO A PASO siguiendo estas reglas:

1. Explícame brevemente qué vamos a hacer en cada paso y para qué sirve.
2. Dame solamente el comando o acción correspondiente a ese paso.
3. Espera a que yo lo ejecute.
4. Yo te indicaré el resultado o te enviaré una captura de pantalla.
5. Comprueba el resultado antes de continuar.
6. Si aparece un error, ayúdame a resolverlo antes de avanzar.
7. No supongas nombres de usuario, rutas, nombres de repositorios ni URLs. Pregúntame o haz que los compruebe.
8. No me hagas utilizar `sudo` con comandos habituales de Git como `git clone`, `git add`, `git commit`, `git push` o `git pull`.
9. Si estamos en un ordenador Ubuntu del aula y una instalación requiere contraseña de administrador, indícame que debo pedir al profesor que introduzca la contraseña.
10. No pases al siguiente paso hasta que yo confirme que el anterior ha funcionado.


==========================================================
CONTEXTO DE LA TAREA
==========================================================

En la Tarea 1 ya creé mi Proyecto Intermodular.

Tengo:

- Una cuenta de GitHub.
- Un repositorio propio del Proyecto Intermodular.
- Documentación escrita en Markdown.
- Una web creada con MkDocs.
- La web publicada mediante GitHub Pages.

Ahora tengo que aprender a trabajar con una copia LOCAL del proyecto utilizando Git y Visual Studio Code.

Puedo encontrarme en uno de estos entornos:

A) Ordenador del aula:
- Ubuntu.
- Utilizo el usuario del turno de mañana.
- No dispongo de la contraseña de administrador.
- Si una instalación requiere `sudo`, debo pedir al profesor que introduzca la contraseña.

B) Ordenador personal con Ubuntu/Linux:
- Tengo permisos de administrador.

C) Ordenador personal con Windows:
- Tengo permisos de administrador.
- Trabajaré con Visual Studio Code y una terminal adecuada de Windows.

D) Máquina virtual propia con Ubuntu:
- Tengo permisos de administrador.

Lo primero que debes hacer es preguntarme en cuál de estos cuatro entornos estoy trabajando y adaptar todos los pasos posteriores a mi sistema.


==========================================================
OBJETIVOS
==========================================================

Debes guiarme hasta completar todo este proceso:

1. Identificar mi sistema operativo, usuario y directorio de trabajo.
2. Comprobar si Git está instalado.
3. Instalar Git si fuera necesario.
4. Comprobar la versión instalada.
5. Configurar mi identidad de Git:
   - user.name
   - user.email
6. Comprobar la configuración.
7. Crear una carpeta denominada `proyectos` dentro de mi directorio personal para utilizarla como espacio de trabajo de mis repositorios.
8. Obtener de GitHub la URL HTTPS de MI repositorio del Proyecto Intermodular.
9. Clonar MI repositorio mediante `git clone`.
10. Entrar en el repositorio.
11. Comprobar que Git reconoce correctamente el repositorio mediante `git status`.
12. Comprobar el repositorio remoto mediante `git remote -v`.
13. Abrir el proyecto con Visual Studio Code.
14. Realizar una modificación sencilla en un archivo existente del proyecto.
15. Guardar el archivo.
16. Utilizar `git status` y explicarme qué ha detectado Git.
17. Preparar el archivo mediante `git add`.
18. Volver a utilizar `git status` para comprobar el cambio de estado.
19. Crear un commit mediante `git commit`.
20. Explicarme claramente que el commit todavía es LOCAL y que aún no se ha enviado a GitHub.
21. Comprobar si GitHub CLI (`gh`) está instalado.
22. Instalar GitHub CLI si fuera necesario.
23. Autenticarme mediante `gh auth login`.
24. Guíame opción por opción durante la autenticación. No me des todas las respuestas de golpe.
25. Comprobar la autenticación mediante `gh auth status`.
26. Realizar `git push`.
27. Comprobar que el cambio aparece realmente en GitHub.
28. Consultar el historial mediante `git log --oneline` y explicarme qué representa.
29. Si el comando abre un visor, indícame cómo salir de él.


==========================================================
SEGUNDA PARTE: DOCUMENTACIÓN TÉCNICA REAL DEL PROYECTO
==========================================================

Después de comprobar que sé realizar el flujo básico de Git, ayúdame a ampliar la documentación REAL de mi Proyecto Intermodular.

No debes crear documentación genérica sobre Git.

Tengo que crear una nueva página de mi memoria técnica denominada:

"Entorno tecnológico"

Antes de indicarme dónde crearla, debes pedirme que te muestre la estructura actual de mi proyecto: carpetas, archivos y, si es necesario, el contenido de `mkdocs.yml`.

NO inventes rutas.

A partir de mi estructura real:

1. Indícame dónde crear `entorno-tecnologico.md`.
2. Ayúdame a añadirla correctamente a la navegación de `mkdocs.yml`.
3. Respeta la estructura que ya tenga mi documentación.

La página "Entorno tecnológico" deberá documentar MI proyecto y contener, al menos:

- Sistemas operativos previstos.
- Herramientas de desarrollo y administración.
- Tecnologías previstas.
- Servicios o componentes que inicialmente considero necesarios.
- Observaciones y decisiones técnicas iniciales.

No escribas automáticamente las decisiones técnicas por mí.

Pregúntame en qué consiste mi proyecto y ayúdame a identificar qué tecnologías tienen sentido.

Debo ser yo quien tome las decisiones finales.


==========================================================
VISUALIZACIÓN LOCAL CON MKDOCS
==========================================================

Después debes ayudarme a comprobar cómo queda la documentación antes de publicarla.

Primero comprueba si MkDocs está disponible.

Si no lo está, guíame para preparar un entorno virtual de Python `.venv` adecuado para mi sistema operativo.

Explícame brevemente:

- qué es un entorno virtual;
- para qué sirve `.venv`;
- por qué lo utilizamos en este proyecto.

Después:

1. Instala `mkdocs-material` dentro del entorno virtual.
2. Crea o modifica `.gitignore` para que `.venv/` NO se suba a GitHub.
3. Comprueba con `git status` que `.venv` está siendo ignorado.
4. Ejecuta `mkdocs serve`.
5. Indícame la dirección local que debo abrir en el navegador.
6. Haz que compruebe que "Entorno tecnológico" aparece correctamente en la web.
7. Indícame cómo detener el servidor de MkDocs.


==========================================================
ÚLTIMO CICLO DE GIT
==========================================================

Una vez comprobada la nueva página:

1. Ejecutaremos `git status`.
2. Revisaremos juntos qué archivos han cambiado.
3. Añadiremos únicamente los archivos necesarios.
4. Comprobaremos nuevamente `git status`.
5. Crearemos un commit con un mensaje descriptivo relacionado con la documentación técnica.
6. Realizaremos `git push`.
7. Comprobaremos el resultado en GitHub.
8. Comprobaremos la web publicada del Proyecto Intermodular.
9. Finalmente ejecutaremos `git status` y verificaremos que el repositorio local está sincronizado y el árbol de trabajo está limpio.


==========================================================
RUTINA DE TRABAJO
==========================================================

Cuando terminemos la actividad, explícame también cuál será el procedimiento habitual para continuar trabajando en el proyecto durante el curso.

Debo comprender la diferencia entre:

`git clone`
→ se utiliza para obtener por primera vez una copia local de un repositorio.

`git pull`
→ se utiliza cuando ya tengo el repositorio y quiero traer los últimos cambios existentes en GitHub.

`git push`
→ se utiliza para enviar a GitHub los commits que he realizado en mi repositorio local.

Ayúdame a comprender este ciclo:

GitHub
   ↓
git pull
   ↓
Repositorio local
   ↓
Modificar archivos
   ↓
git status
   ↓
git add
   ↓
git commit
   ↓
git push
   ↓
GitHub


==========================================================
SEGURIDAD Y EQUIPOS COMPARTIDOS
==========================================================

Si estoy utilizando el ordenador compartido del aula, ten especial cuidado con:

- permisos de archivos;
- propietarios de archivos;
- credenciales de GitHub;
- sesiones que puedan quedar abiertas.

Nunca soluciones un problema de permisos utilizando `sudo` indiscriminadamente.

Si aparece un error de permisos o de propiedad, primero hazme ejecutar comandos de diagnóstico como:

`whoami`

`pwd`

`ls -ld`

y analiza el resultado antes de proponer cambios.

El repositorio debe pertenecer al usuario con el que estoy trabajando.

No utilices `sudo` para:

`git clone`

`git add`

`git commit`

`git push`

`git pull`

Si el equipo es compartido, al finalizar recuérdame que debemos comprobar si es necesario cerrar la sesión de GitHub para no dejar mis credenciales disponibles para otro alumno.


==========================================================
FORMA DE TRABAJAR
==========================================================

No quiero que realices la tarea por mí.

Quiero que me enseñes a realizarla.

Por tanto:

- Una acción cada vez.
- Una explicación breve antes de cada acción.
- Espera siempre mi resultado.
- Si envío una captura, analízala antes de continuar.
- Si me equivoco, explícame qué ha ocurrido.
- No avances si existe un error pendiente.
- No inventes resultados de comandos.
- No inventes nombres de usuario, rutas ni repositorios.
- Adapta los comandos a Windows o Ubuntu según mi caso.
- Cuando haya varias posibilidades, explícame brevemente la diferencia y ayúdame a elegir.
- Utiliza lenguaje claro y adecuado para un alumno que está aprendiendo Git por primera vez.


==========================================================
REGLA FINAL
==========================================================

NO ME EXPLIQUES AHORA TODO EL PROCESO.

Trabaja conmigo paso a paso.

EMPIEZA ÚNICAMENTE preguntándome en cuál de estos entornos estoy trabajando:

A) Ordenador del aula con Ubuntu y usuario del turno de mañana.

B) Ordenador personal con Ubuntu/Linux.

C) Ordenador personal con Windows.

D) Máquina virtual propia con Ubuntu.

No me proporciones todavía ningún comando.
```

</div>