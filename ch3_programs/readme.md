# ⚙️ Programas Compilados vs. Interpretados, Variables y la Variable `$PATH`

---

## 🏗️ 1. Compilados vs. Interpretados

Un programa es un conjunto de instrucciones ejecutables por la computadora, y un **ejecutable** es el archivo que contiene dicho programa. Se dividen principalmente en dos tipos:

### ⚡ Programas Compilados

* **¿Qué son?** El código fuente escrito por humanos se traduce a **código máquina (binario)** antes de ejecutarse.


* **Ventaja:** La CPU ejecuta directamente este binario sin intermediarios.


* **Ejemplos:** Lenguajes como **Go, C y Rust**.


* **Dato curioso:** Si intentas abrir el ejecutable (ej. con `cat /bin/sh`), solo verás caracteres ilegibles/binarios.



### 📜 Programas Interpretados

* **¿Qué son?** El código fuente es leído y ejecutado paso a paso en tiempo real por otro programa llamado **intérprete**.


* **Requisito:** La máquina debe tener instalado el intérprete correspondiente.


* **Ejemplos:** **Python, Ruby, JavaScript** o scripts de shell (`.sh`) interpretados por el propio programa shell.



---

## 🔍 2. El Comando `which` y Ejecutables

* 📍 **`which`**: Revela la ubicación exacta en el disco de un comando/ejecutable del sistema:


```bash
which sh
# /bin/sh

```


* 🏃 **Ejecutar archivos locales (`./`)**:
* Para ejecutar un script dentro de la carpeta actual, se debe anteponer `./` (ej. `./program.sh`).


* El punto (`.`) representa el directorio actual. Esto evita que la shell confunda tu archivo con un comando global del sistema (como `ls` o `mkdir`).





---

## 🪄 3. El Shebang (`#!`)

Es una directiva colocada en la **primera línea** de un script que le indica al sistema qué intérprete utilizar para ejecutarlo.

* **Sintaxis general:**
```bash
#! intérprete [argumentos-opcionales]

```


* **Ejemplo para Python 3:**
```python
#!/usr/bin/python3

```


* **Ejemplo para Shell:**
```bash
#!/bin/sh

```



---

## 🐚 4. Tipos Comunes de Shell

* **`sh` (Bourne Shell):** El shell original de Unix, simple, estándar POSIX y sin muchas facilidades de interfaz moderna.


* **`bash` (Bourne Again Shell):** El más popular en distribuciones Linux; añade funciones avanzadas sobre `sh`.


* **`zsh` (Z Shell):** El shell por defecto en macOS; comparte gran compatibilidad con Bash pero con mejoras adicionales.



---

## 🌐 5. Variables de Entorno

A diferencia de las variables locales de terminal, las **variables de entorno** están disponibles para todos los procesos hijos y programas ejecutados dentro de esa sesión.

* 👁️ **`env`**: Lista todas las variables de entorno activas.


* 📤 **`export`**: Exporta una variable para que los scripts y subprocesos tengan acceso a ella:


```bash
export WARN_MESSAGE="Alerta del sistema"
./warn.sh

```


* ⏱️ **Temporal para un único comando:**
```bash
WARN_MESSAGE="Alerta temporal" ./warn.sh

```


* ❌ **`unset`**: Elimina una variable de entorno de la sesión:


```bash
unset WARN_MESSAGE

```



---

## 🛣️ 6. La Variable `$PATH`

### ¿Por qué es crucial?

Sin `$PATH`, tendrías que escribir la ruta completa de cada programa que quieres ejecutar (por ejemplo, escribir `/bin/ls` en lugar de solo `ls`).

* **¿Cómo funciona?** Contiene una lista de carpetas separadas por dos puntos (`:`). Cuando escribes un comando, la shell busca un ejecutable con ese nombre en cada una de esas rutas, en orden.


* **Ver su valor actual:**
```bash
echo $PATH
# Ejemplo: /usr/local/bin:/usr/bin:/bin

```



### ➕ Agregar un directorio a `$PATH`

Si descargas o creas scripts y quieres ejecutarlos por su nombre desde cualquier ubicación, agrega su directorio a tu variable:

```bash
export PATH="$PATH:$HOME/mi-carpeta/bin"

```

> 💡 **Nota:** Referenciar `$PATH` al inicio conserva todas las rutas existentes y agrega la nueva al final mediante `:`. Este cambio dura mientras la terminal permanezca abierta.
> 
> 

---

## 📋 Tabla Resumen de Comandos

| Comando | Función Principal | Ejemplo |
| --- | --- | --- |
| **`which`** | Muestra la ruta del ejecutable de un comando

 | `which python3` |
| **`./script.sh`** | Ejecuta un archivo en el directorio actual

 | `./genids.sh`<br> |
| **`env`** | Lista todas las variables de entorno

 | `env`<br> |
| **`export`** | Declara/exporta una variable de entorno

 | `export ENTORNO="prod"` |
| **`unset`** | Remueve una variable de la sesión

 | `unset ENTORNO`<br> |
| **`echo $PATH`** | Consulta los directorios de búsqueda de comandos

 | `echo $PATH`<br> |