# Módulo 01 - Lección 1: Introducción a Linux y Conceptos Clave

## Objetivos
- Entender qué es un Sistema Operativo, qué es Linux y por qué es la base de la infraestructura de ciberseguridad.
- Comprender la diferencia entre la interfaz gráfica (GUI) y la terminal de comandos (CLI).
- Dominar la estructura del árbol de directorios de Linux y los tipos de rutas.
- **Importancia para SOC:** El 90% de los servidores corporativos, sensores de red y plataformas SIEM (como Wazuh) corren sobre Linux. La terminal es el medio principal para investigar incidentes de seguridad.

---

## Recursos de Estudio

### Términos de búsqueda para YouTube (Contenido en Español):
- `Qué es la Terminal o CLI de Linux explicacion desde cero`
- `Estructura de directorios en Linux explicacion`
- `Comandos basicos de Linux para Ciberseguridad`

### Documentación de Referencia:
- [Documentación Oficial de Ubuntu (Español)](https://help.ubuntu.com/l10n/es/)
- [GNU Coreutils Reference Manual](https://www.gnu.org/software/coreutils/manual/)

---

## Conceptos Importantes

### 1. ¿Qué es un Sistema Operativo y qué es Linux?
- **Definición:** El programa principal que administra el hardware del equipo (procesador, memoria RAM, almacenamiento). Linux es un sistema operativo de código abierto, gratuito y de alto rendimiento.
- **Ejemplo:** El sistema operativo Android en dispositivos móviles está construido sobre el núcleo (kernel) de Linux.
- **Aplicación en Ciberseguridad:** Es el sistema preferido por atacantes (Red Team) y defensores (Blue Team / SOC) porque otorga control total sobre los procesos y la red sin restricciones de interfaz gráfica.

### 2. GUI vs CLI (Interfaz Gráfica vs Terminal)
- **Definición:**
  - **GUI (Graphical User Interface):** Interfaz visual compuesta por ventanas, botones, iconos y uso de ratón.
  - **CLI (Command Line Interface):** Interfaz de texto (terminal) donde se ejecutan instrucciones enviando comandos desde el teclado.
- **Ejemplo:** En GUI abres una carpeta haciendo doble clic sobre un icono. En CLI escribes `cd /var/log` y presionas Enter.
- **Aplicación en Ciberseguridad:** Los servidores en entornos de producción no instalan GUI para ahorrar recursos y reducir la superficie de ataque. El analista SOC debe operar 100% por CLI.

### 3. La Estructura de Directorios (El Árbol de Carpetas)
- **Definición:** En Linux no existen letras de disco (`C:`, `D:`). Todo el sistema cuelga de un único punto de origen llamado **Raíz**, representado por la barra diagonal `/`.
- **Directorios clave para un SOC:**
  - `/` **(Raíz):** El origen de todo el árbol de carpetas.
  - `/home`: Carpetas personales de los usuarios estándar.
  - `/var/log`: Ubicación donde el sistema y las aplicaciones guardan sus archivos de **log** (registros de eventos).
  - `/etc`: Contiene las configuraciones del sistema operativo y sus servicios.
  - `/tmp`: Carpeta de archivos temporales con permisos de escritura globales.
- **Aplicación en Ciberseguridad:** Los ciberdelincuentes suelen alojar artefactos maliciosos en `/tmp` porque no requiere permisos especiales para guardar archivos.

### 4. Rutas Absolutas vs Rutas Relativas
- **Ruta Absoluta:** La ubicación exacta de un archivo comenzando obligatoriamente desde la raíz `/` (ejemplo: `/var/log/auth.log`).
- **Ruta Relativa:** La ubicación calculada a partir de la carpeta donde estás parado en ese momento (ejemplo: `log/auth.log` si ya te encuentras dentro de `/var`).
- **Aplicación en Ciberseguridad:** Al redactar un informe de incidentes o crear reglas de detección en un SIEM, siempre se utilizan rutas absolutas para evitar ambigüedades.

---

## Checklist de Conocimientos
- [ ] Comprender la función de la terminal (CLI) frente a la interfaz gráfica (GUI).
- [ ] Ubicar el origen del sistema de archivos en la Raíz `/`.
- [ ] Memorizar las carpetas estratégicas: `/`, `/home`, `/var/log`, `/etc` y `/tmp`.
- [ ] Diferenciar entre una ruta absoluta y una ruta relativa.