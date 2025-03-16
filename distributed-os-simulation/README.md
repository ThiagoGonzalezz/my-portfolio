# 🚀 C-Comenta - Sistema Operativo

## 📌 Descripción
C-Comenta es un simulador de sistema distribuido desarrollado como parte del Trabajo Práctico Cuatrimestral de la cátedra de Sistemas Operativos. Su objetivo es permitir la ejecución y planificación de procesos, administración de memoria y manejo de interfaces de entrada/salida mediante la implementación de distintos módulos que interactúan entre sí.

---

## 🏗️ Arquitectura del Sistema
El sistema está compuesto por los siguientes módulos:

### 🖥️ 1. Kernel
El **Kernel** es el módulo central del sistema, encargado de la planificación de procesos y la comunicación con los demás módulos. Entre sus responsabilidades se encuentran:
- **Gestión de procesos:** Creación, finalización y cambios de estado de los procesos en ejecución.
- **Planificación de CPU:** Utiliza algoritmos FIFO, Round Robin (RR) y Virtual Round Robin (VRR) para manejar la ejecución de procesos.
- **Gestión de recursos:** Manejo de instancias de recursos y sincronización mediante operaciones WAIT y SIGNAL.
- **Manejo de interfaces de I/O:** Coordinación con dispositivos de entrada y salida.
- **Interfaz de consola:** Permite ejecutar comandos como `INICIAR_PROCESO`, `FINALIZAR_PROCESO`, `PROCESO_ESTADO`, entre otros.

### ⚙️ 2. CPU
El **CPU** simula el ciclo de instrucción de un procesador real y ejecuta las instrucciones de los procesos planificados. Sus principales funciones incluyen:
- **Ejecutar el ciclo de instrucción:**
  - Fetch: Obtener la siguiente instrucción de memoria.
  - Decode: Interpretar la instrucción.
  - Execute: Ejecutar la operación correspondiente.
  - Check Interrupt: Verificar si el Kernel ha enviado una interrupción.
- **Manejo de registros:** Contiene registros de propósito general (AX, BX, CX, DX, etc.) y registros especiales (PC, SI, DI, etc.).
- **Traducción de direcciones:** Implementa una unidad de gestión de memoria (MMU) y una TLB para optimizar la traducción de direcciones lógicas a físicas.

### 🗄️ 3. Memoria
El **módulo de Memoria** es responsable de la gestión de la memoria principal y su interacción con la CPU y el Kernel. Sus principales funciones incluyen:
- **Gestión de tablas de páginas:** Asigna y libera marcos de memoria según los procesos en ejecución.
- **Traducción de direcciones:** Convierte direcciones lógicas en direcciones físicas utilizando un esquema de paginación.
- **Gestión de espacio de usuario:** Permite a los procesos leer y escribir datos en la memoria.
- **Manejo de expansión y reducción:** Ajusta dinámicamente el tamaño de los procesos en memoria.

### 🔌 4. Interfaz de I/O
Las **interfaces de entrada/salida (I/O)** permiten la interacción con dispositivos externos y el sistema de archivos. Se implementan diferentes tipos de interfaces:
- **Interfaces Genéricas:** Simulan dispositivos que realizan operaciones simples como `IO_GEN_SLEEP`.
- **Interfaces STDIN:** Capturan entrada del usuario y almacenan datos en memoria.
- **Interfaces STDOUT:** Muestran información en pantalla leyendo desde la memoria.
- **Interfaces DialFS:** Implementan un sistema de archivos basado en asignación contigua, permitiendo operaciones como `IO_FS_CREATE`, `IO_FS_WRITE`, `IO_FS_READ`, etc.

---

## 🛠️ Tecnologías y Conceptos Utilizados
- Lenguaje de programación **C**
- Programación concurrente y multihilo
- **Sockets** para comunicación entre módulos
- **Paginación** y administración de memoria
- **Planificación de procesos** (FIFO, RR, VRR)
- **Manejo de archivos** con un sistema de archivos simplificado

---

## 📋 Requisitos
- Linux
- GCC
- Make
- Bibliotecas necesarias de la cátedra (commons)

---

## 📦 Instalación
1. Clonar el repositorio:
   ```sh
   git clone <URL_DEL_REPOSITORIO>
   ```
2. Compilar el proyecto:
   ```sh
   make
   ```

---

## ▶️ Ejecución
1. Levantar los módulos en orden:
   ```sh
   ./memoria config/memoria.config &
   ./cpu config/cpu.config &
   ./kernel config/kernel.config &
   ./interfaz_io config/io.config &
   ```
2. Utilizar la consola del kernel para gestionar procesos:
   ```sh
   INICIAR_PROCESO script1
   ```

---

## ⚙️ Configuración
Cada módulo cuenta con un archivo de configuración en la carpeta `config/`, donde se definen los parámetros de conexión y comportamiento.

Ejemplo de configuración del Kernel:
```ini
PUERTO_ESCUCHA=8003
IP_MEMORIA=127.0.0.1
PUERTO_MEMORIA=8002
ALGORITMO_PLANIFICACION=VRR
QUANTUM=2000
```

---

## 📜 Logs
El sistema genera logs de eventos importantes en la carpeta `logs/`. Algunos logs clave incluyen:
- Creación de procesos: `Se crea el proceso <PID> en NEW`
- Finalización de procesos: `Finaliza el proceso <PID> - Motivo: <MOTIVO>`
- Acciones de memoria: `PID: <PID> - Accion: <LEER/ESCRIBIR> - Direccion: <DIRECCION>`

---

## 🧪 Pruebas
Para validar el correcto funcionamiento, se han definido tests unitarios y de integración, que se pueden ejecutar con:
```sh
make test
```

---

## 📜 Licencia
Este proyecto es de uso académico y pertenece a la cátedra de Sistemas Operativos de la UTN FRBA.

