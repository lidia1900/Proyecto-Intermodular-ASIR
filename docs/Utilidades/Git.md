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