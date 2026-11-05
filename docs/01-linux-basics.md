# Linux Basics

## Objetivo

Aprender los comandos fundamentales de Linux para poder administrar sistemas, analizar incidentes y trabajar en entornos SOC.

---

# pwd

## Descripción

Muestra el directorio actual en el que nos encontramos.

## Sintaxis

```bash
pwd
```

## Ejemplo

```bash
lucas@DESKTOP:~/soc-learning-lab$ pwd

/home/lucas/soc-learning-lab
```

## Uso en SOC

Permite verificar desde qué ubicación se están ejecutando comandos o scripts.

---

# ls

## Descripción

Lista archivos y carpetas.

## Sintaxis

```bash
ls
```

## Opciones útiles

```bash
ls -l
```

Vista detallada.

```bash
ls -la
```

Muestra también archivos ocultos.

```bash
ls -lah
```

Formato legible para humanos.

## Ejemplo

```bash
ls -lah
```

## Uso en SOC

Identificación rápida de archivos sospechosos o directorios desconocidos.

---

# cd

## Descripción

Permite cambiar de directorio.

## Sintaxis

```bash
cd carpeta
```

## Ejemplos

Entrar a una carpeta:

```bash
cd docs
```

Volver un nivel:

```bash
cd ..
```

Volver al directorio personal:

```bash
cd ~
```

## Uso en SOC

Navegación rápida entre directorios de logs y evidencias.

---

# mkdir

## Descripción

Crea directorios.

## Sintaxis

```bash
mkdir nombre_directorio
```

## Ejemplo

```bash
mkdir laboratorio
```

## Uso en SOC

Organizar evidencias y reportes de incidentes.

---

# touch

## Descripción

Crea archivos vacíos.

## Sintaxis

```bash
touch archivo.txt
```

## Ejemplo

```bash
touch evidencia.log
```

## Uso en SOC

Creación de documentación y archivos de prueba.

---

# cat

## Descripción

Muestra el contenido de archivos.

## Sintaxis

```bash
cat archivo.txt
```

## Ejemplo

```bash
cat README.md
```

## Uso en SOC

Visualizar rápidamente archivos de configuración y logs.

---

# cp

## Descripción

Copia archivos o directorios.

## Sintaxis

```bash
cp origen destino
```

## Ejemplo

```bash
cp evidencia.log respaldo.log
```

## Uso en SOC

Preservar evidencias antes de analizarlas.

---

# mv

## Descripción

Mueve o renombra archivos.

## Sintaxis

```bash
mv origen destino
```

## Ejemplo

```bash
mv archivo.txt evidencia.txt
```

## Uso en SOC

Organizar evidencia y renombrar archivos descriptivamente.

---

# rm

## Descripción

Elimina archivos.

## Sintaxis

```bash
rm archivo.txt
```

## Ejemplo

```bash
rm prueba.txt
```

## Uso en SOC

Eliminar archivos temporales.

⚠️ Usar con cuidado, no existe papelera.

---

# find

## Descripción

Busca archivos y directorios.

## Sintaxis

```bash
find ruta -name nombre
```

## Ejemplo

```bash
find . -name "*.log"
```

## Uso en SOC

Localiza* logs, malware o*artefactos.

---

# grep

## Descr*pción

Busca texto dentro de archi*os.

## Sintaxis

```bash*grep "texto" archivo
```

## Ejemp*o

```bash*grep "error" sistema.log
```

##*Uso en SOC

Buscar indicadores de *