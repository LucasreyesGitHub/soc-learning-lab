# Módulo 01 - Lección 2: Comandos Esenciales de Inspección y Navegación

En Linux, las instrucciones se envían con la siguiente anatomía:
`Comando Base` + `Opciones (-opcion)` + `Argumento (Archivo/Ruta)`.

---

## 1. `pwd` (Print Working Directory)
- **Qué hace:** Imprime en pantalla la ruta absoluta exacta del directorio donde estás parado.
- **Sintaxis:** `pwd`
- **Ejemplo básico:**
  `pwd` (Salida típica: `/home/analista`)
- **Uso en SOC:** Confirmar la ubicación exacta antes de guardar evidencias forenses o ejecutar scripts.

---

## 2. `ls` (List)
- **Qué hace:** Lista los archivos y subcarpetas dentro de un directorio.
- **Sintaxis:** `ls [opciones] [directorio]`
- **Ejemplo básico:**
  `ls -la /var/log`
  *(Opción `-l` lista detalles como permisos y tamaño; opción `-a` muestra archivos ocultos que empiezan por `.`).*
- **Uso en SOC:** Identificar herramientas o scripts ocultos dejados por atacantes (ejemplo: `.backdoor.sh`).

---

## 3. `cd` (Change Directory)
- **Qué hace:** Cambia la ubicación actual del usuario a otra carpeta.
- **Sintaxis:** `cd [ruta_destino]`
- **Ejemplo básico:**
  - `cd /var/log/` (Entra a la carpeta de registros)
  - `cd ..` (Sube un nivel en el árbol de carpetas)
  - `cd ~` (Regresa a la carpeta personal del usuario)
- **Uso en SOC:** Desplazarse rápidamente a directorios de análisis o configuración.

---

## 4. `mkdir` y `touch`
- **Qué hace:** `mkdir` crea directorios nuevos; `touch` crea archivos de texto vacíos.
- **Sintaxis:**
  - `mkdir [nombre_carpeta]`
  - `touch [nombre_archivo]`
- **Ejemplo básico:**
  - `mkdir caso_001`
  - `touch caso_001/evidencia.txt`
- **Uso en SOC:** Crear estructuras organizadas para almacenar pruebas recopiladas durante un incidente.

---

## 5. `cat`, `head` y `tail` (Inspección de Archivos)
- **Qué hace:**
  - `cat`: Muestra el contenido completo de un archivo en pantalla.
  - `head`: Muestra las primeras 10 líneas de un archivo.
  - `tail`: Muestra las últimas 10 líneas de un archivo. Con la opción `-f`, lee los cambios en tiempo real.
- **Sintaxis:**
  - `cat [archivo]`
  - `head -n [numero_lineas] [archivo]`
  - `tail -n [numero_lineas] -f [archivo]`
- **Ejemplo básico:**
  - `head -n 20 /var/log/auth.log`
  - `tail -f /var/log/syslog`
- **Uso en SOC:** Usar `tail -f` para ver eventos de autenticación en vivo mientras un ataque de fuerza bruta está ocurriendo.

---

## 6. `cp`, `mv` y `rm` (Gestión de Archivos)
- **Qué hace:** `cp` copia archivos; `mv` mueve o renombra archivos; `rm` elimina archivos o carpetas.
- **Sintaxis:**
  - `cp [origen] [destino]`
  - `mv [origen] [destino]`
  - `rm -rf [archivo_o_carpeta]` *(Atención: `-r` elimina recursivamente y `-f` fuerza la acción sin solicitar confirmación)*.
- **Ejemplo básico:**
  - `cp /var/log/auth.log ./resguardo_auth.log`
  - `mv resguardo_auth.log evidencia_final.log`
  - `rm evidencia_final.log`
- **Uso en SOC:** Duplicar registros de eventos a un entorno seguro para analizarlos sin modificar los archivos originales.