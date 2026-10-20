# Bienvenido a Aprender Linux

En este curso trabajarás como un «desarrollador forense» contratado por la empresa ficticia **"WorldBanc"** para investigar una brecha de seguridad. Utilizarás únicamente la línea de comandos para recorrer archivos, manipular texto y rastrear actividades sospechosas.

## 1. El comando `echo`

El comando `echo` imprime texto en tu pantalla. Es el equivalente al *"Hola Mundo"* de la línea de comandos.

### 📝 Tarea

1. En la shell de la derecha, escribe el siguiente comando: Bash
    
    ```bash
    echo "I use Linux btw"
    ```
    
2. Presiona `Enter` para ejecutarlo.
3. Envía las comprobaciones de la shell (*Submit*).

> **Nota:** Durante los primeros capítulos de este curso permanecerás en el navegador. Más adelante, una vez que te sientas cómodo, te ayudaremos a configurar tu propia máquina.
> 

## 2. ¿Qué es una Shell?

El programa de la derecha que lee tus comandos y los ejecuta es una **shell**. Las shells realizan muchas tareas, pero su función principal es interpretar las órdenes que escribes y luego ejecutarlas.

### El concepto REPL

A las shells a menudo se las llama **REPL**, siglas en inglés para:

- **R (Read):** Lee el comando que escribes.
- **E (Eval):** Evalúa el comando, generalmente ejecutando otros programas en tu computadora.
- **P (Print):** Imprime la salida del comando.
- **L (Loop):** Bucle que vuelve a mostrar el *prompt* para que puedas ingresar otro comando.

### 📝 Tarea: El comando `expr`

El comando `expr` evalúa una expresión simple e imprime el resultado. Es una excelente manera de observar el ciclo REPL en acción.

1. En la shell, ejecuta: Bash
    
    ```bash
    expr 123456 + 7890
    ```
    
2. Luego, usando la misma sintaxis, imprime el resultado de $420 - 69$ (usando el operador ).
3. Envía las comprobaciones.

### 💡 Consejo: *Prompt* vs. Salida (*Output*)

A veces existe confusión entre el prompt y la salida. Veamos una sesión de ejemplo:

Bash

```bash
wagslane:~$ echo hello
hello
wagslane:~$
```

- **El prompt que recibes:** `wagslane:~$` (indica que la shell está lista para recibir una instrucción).
- **El comando ingresado:** `echo hello`.
- **La salida impresa:** `hello`.
- **Nuevo prompt:** `wagslane:~$` (lista para el siguiente comando).

## 3. Línea de comandos (CLI) vs. Interfaz gráfica (GUI)

Términos como «terminal», «shell», «línea de comandos», «CLI» y «símbolo del sistema» a menudo se usan indistintamente. En general, hacen referencia a programas que te permiten interactuar con tu computadora mediante texto.

La alternativa es una **interfaz gráfica de usuario (GUI)**. Ocurre cuando usas el ratón para hacer clic en iconos, botones y menús.

### Desventajas de las interfaces gráficas (GUI):

1. **Tienen menos poder:** Una CLI ofrece mucho más control sobre tu sistema operativo. En una GUI estás limitado a lo que el desarrollador haya programado en la interfaz.
2. **Son más lentas:** Una vez que conoces los comandos, escribirlos es mucho más rápido que navegar entre interminables menús.
3. **No son automatizables:** Los comandos se pueden copiar, pegar y programar en scripts; los clics no.
4. **Tienen menos estilo:** Serás invitado a un 90% menos de salidas románticas si eres usuario exclusivo de GUI.

### 📝 Tarea: El comando `whoami`

El comando `whoami` imprime el nombre del usuario con el que has iniciado sesión actualmente.

1. Ejecuta `whoami` en la shell.
2. Envía las comprobaciones.

## 4. ¿Qué es exactamente una Terminal?

Poniéndonos técnicos, la **terminal** es sólo una parte de ese ecosistema. Históricamente, una terminal era un dispositivo físico (teclado y monitor) para introducir comandos en una computadora central.

Hoy en día, cuando decimos «terminal», nos referimos a un **emulador de terminal**:

- El **emulador de terminal** es la ventana que procesa tus pulsaciones de teclas y dibuja el texto en pantalla.
- La **shell** es el programa interno que realmente interpreta y decide qué comandos se pueden ejecutar.

## 5. Variables en la Shell

Nuestra terminal utiliza una shell Bash en memoria. En tu propia máquina probablemente usarás **Bash** o **Zsh**.

Las shells no solo ejecutan programas; también son lenguajes de programación con variables, funciones y bucles.

### Declarar una variable

Bash

```bash
name="Lane"
```

> **Importante:** No agregues espacios alrededor del signo igual `=`. Debe ir todo pegado.
> 

### Usar una variable

Para leer el contenido de una variable, debes anteponerle el signo `$`:

Bash

```bash
echo $name
# Salida: Lane
```

### Interpolar variables en texto

Bash

```bash
echo Hello $name
# Salida: Hello Lane
```

### 📝 Tarea: Crear e interpolar variables

En la shell de la derecha, define las siguientes tres variables:

- `bankname` con el valor `"WorldBanc"`
- `founded` con el valor `"1969"`
- `ceo` con el valor `"Jeff Gates"`

Luego, ejecuta un comando `echo` usando las variables dinámicas para imprimir exactamente:

> `WorldBanc was founded in 1969 by Jeff Gates`
> 

#### Solución de referencia:

Bash

```bash
bankname="WorldBanc"
founded="1969"
ceo="Jeff Gates"
echo $bankname was founded in $founded by $ceo
```

## 6. Historial de Comandos

Para ver la lista de comandos que has ejecutado previamente, utiliza el comando `history`. Esto facilita volver a ejecutarlos o copiarlos a un script.

### 📝 Tarea

1. Usa `echo` para imprimir: `Investigating WorldBanc`.
2. Ejecuta `whoami`.
3. Ejecuta `history` para ver ambos comandos en la lista.
4. Envía las comprobaciones.

#### Ejemplo de sesión:

Bash

```bash
variable="WorldBanc"
echo Investigating $variable
whoami
history
```

## 7. Navegar por el Historial

En lugar de reescribir comandos largos, puedes usar atajos de teclado:

- **Tecla `↑` (Flecha arriba):** Retrocede paso a paso en el historial de comandos.
- **Tecla `↓` (Flecha abajo):** Avanza hacia los comandos más recientes.

### Limpiar la pantalla (`clear`)

Si la terminal tiene demasiado texto, puedes limpiarla ejecutando el comando `clear` o pulsando `Ctrl + L`. Esto **no** borra el historial de comandos, solo despeja la vista actual.

### 📝 Tarea

1. Usa `echo` para imprimir: `Case file: WorldBanc`.
2. Presiona `↑` para recuperar el comando y pulsa `Enter` para volver a ejecutarlo.
3. Ejecuta el comando `clear` (escribe el comando, no uses `Ctrl+L`) para despejar la pantalla.
4. Envía las comprobaciones de la shell.