# 🧭 Guía Rápida del Sistema de Archivos en Linux

El sistema de archivos (*filesystem*) organiza todos los datos en una estructura de árbol invertido. Parte desde la **raíz** (`/`) y contiene directorios (carpetas) y archivos (datos binarios planos).

---

## 📍 1. Navegación y Rutas

* 📌 **`pwd`** (*print working directory*): Muestra la ruta completa del directorio donde estás parado.


* 🗂️ **`ls`** (*list*): Lista los archivos y carpetas del directorio actual o de uno específico (`ls carpeta`).


* 🚶 **`cd`** (*change directory*): Cambia de directorio.


* `cd carpeta`: Entra a una carpeta.


* `cd ..`: Sube un nivel al directorio padre.


* `cd ~` o `cd $HOME`: Regresa directamente a tu directorio personal (*home*).





### 🗺️ Rutas Absolutas vs. Relativas

* **Absoluta** 🌐: Comienza siempre desde la raíz (`/`) y apunta al mismo archivo sin importar dónde estés (ej. `/home/user/archivo.txt`).


* **Relativa** 📍: Depende de tu ubicación actual y no inicia con `/` (ej. `documentos/archivo.txt` o `../archivo.txt`).



---

## ⚡ 2. Productividad en Terminal

* ⇥ **Tecla `Tab` (Autocompletado):** Completa nombres de archivos, carpetas y comandos con solo escribir las primeras letras. Si hay varias coincidencias, presionar dos veces muestra las opciones disponibles.



---

## 📄 3. Visualización de Archivos

* 🐱 **`cat`**: Muestra todo el contenido de uno o más archivos de corrido.


* 🔝 **`head`**: Imprime las primeras líneas (por defecto 10, o personalizado con `head -n 5 archivo`).


* 🔚 **`tail`**: Imprime las últimas líneas (por defecto 10, o `tail -n 5 archivo`).


* 📖 **`less`**: Paginador interactivo para archivos largos (*"less is more"*):


* `Espacio`: Avanzar una página.


* `b`: Retroceder una página.


* `/`: Buscar texto dentro del archivo.


* `q`: Salir.





---

## 🛠️ 4. Creación, Edición y Eliminación

* ✍️ **`touch archivo.txt`**: Crea un archivo vacío (o actualiza su fecha de modificación).


* 📁 **`mkdir carpeta`**: Crea un directorio nuevo.


* 📦 **`mv origen destino`**: Mueve archivos/carpetas o se usa para **renombrarlos** (`mv viejo.txt nuevo.txt`).


* 📋 **`cp origen destino`**: Copia archivos.


* `cp -r carpeta/ nueva_carpeta/`: Copia recursivamente directorios completos.




* 🗑️ **`rm archivo.txt`**: Elimina archivos de forma permanente (sin papelera).


* `rm -r carpeta/`: Elimina un directorio y todo su contenido recursivamente.





---

## 🔍 5. Búsqueda

### 📝 Buscar dentro del contenido (`grep`)

* **Simple**: `grep "PALABRA" archivo.log` (busca coincidencias exactas dentro del archivo).


* **Múltiples archivos**: `grep "PALABRA" file1.log file2.log`.


* **Recursivo en carpetas**: `grep -r "PALABRA" .` (busca en el directorio actual y todos sus subdirectorios).



### 🏷️ Buscar archivos por nombre (`find`)

* **Nombre exacto**: `find ruta/ -name archivo.txt`.


* **Patrón con comodín (`*`)**:
* `find ruta/ -name "*.txt"` (todos los archivos terminados en `.txt`).


* `find ruta/ -name "*reporte*"` (cualquier archivo cuyo nombre contenga la palabra "reporte").





---

## 🧠 Chuleta Resumen (Cheat Sheet)

| Acción | Comando | Ejemplo |
| --- | --- | --- |
| **¿Dónde estoy?** | `pwd` | `pwd`<br> |
| **Ver contenido** | `ls` | `ls -la` |
| **Moverse** | `cd` | `cd ..` / `cd ~`<br> |
| **Crear archivo vacío** | `touch` | `touch notas.txt`<br> |
| **Crear carpeta** | `mkdir` | `mkdir proyectos`<br> |
| **Leer archivo** | `cat` / `less` | `less logs.txt`<br> |
| **Mover / Renombrar** | `mv` | `mv doc.txt carpeta/`<br> |
| **Copiar** | `cp` | `cp -r dir1/ dir2/`<br> |
| **Borrar** | `rm` | `rm -r basura/`<br> |
| **Buscar texto** | `grep` | `grep -r "ERROR" .`<br> |
| **Buscar archivos** | `find` | `find . -name "*.csv"`<br> |