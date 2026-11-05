Guía Completa: Crear un Repositorio GitHub desde Ubuntu WSL y VS Code
Objetivo
Crear un laboratorio SOC utilizando:

Windows 11
WSL (Ubuntu)
Git
GitHub
Visual Studio Code
Y publicar el proyecto en GitHub completamente desde la terminal.

Paso 1 - Instalar WSL
Abrir PowerShell como Administrador:

wsl --install
Reiniciar el equipo.

Verificar:

wsl -l -v
Paso 2 - Instalar Ubuntu
Listar distribuciones disponibles:

wsl --list --online
Instalar Ubuntu:

wsl --install Ubuntu-24.04
Reiniciar si es necesario.

Crear:

Usuario Linux
Contraseña Linux
Verificar acceso:

wsl
Debería aparecer:

usuario@DESKTOP:~$
Paso 3 - Actualizar Ubuntu
Dentro de Ubuntu:

sudo apt update
sudo apt upgrade -y
Paso 4 - Instalar Git
Instalar:

sudo apt install git -y
Verificar:

git --version
Paso 5 - Instalar Visual Studio Code
Desde Windows instalar VS Code.

Luego abrir Ubuntu y ejecutar:

code .
Si VS Code se abre, la integración está funcionando correctamente.

Paso 6 - Crear el proyecto
Ir al directorio personal:

cd ~
Crear carpeta del laboratorio:

mkdir soc-learning-lab
Entrar:

cd soc-learning-lab
Paso 7 - Crear estructura inicial
Crear carpetas:

mkdir docs
mkdir terraform
mkdir docker
mkdir screenshots
mkdir diagrams
Crear archivos:

touch README.md

touch docs/01-linux-basics.md
touch docs/02-networking.md
touch docs/03-git-github.md

touch terraform/main.tf
touch terraform/variables.tf
touch terraform/outputs.tf

touch docker/docker-compose.yml
Ver estructura:

tree
Si no está instalado:

sudo apt install tree -y
Paso 8 - Inicializar Git
Dentro del proyecto:

git init
Verificar:

git status
Paso 9 - Configurar Identidad Git
Configurar nombre:

git config --global user.name "Lucas"
Configurar email de GitHub:

git config --global user.email "tu_correo_github"
Verificar:

git config --global --list
Salida esperada:

user.name=Lucas
user.email=tu_correo_github
Paso 10 - Instalar GitHub CLI
Instalar:

sudo apt install gh -y
Verificar:

gh --version
Paso 11 - Iniciar sesión en GitHub
Ejecutar:

gh auth login
Seleccionar:

GitHub.com
HTTPS
Login with a web browser
Copiar el código proporcionado.

Abrir:

https://github.com/login/device

Ingresar el código.

Autorizar GitHub CLI.

Verificar:

gh auth status
Paso 12 - Crear README
Editar:

nano README.md
Contenido:

# SOC Learning Lab

Laboratorio para aprender:

- Linux
- Redes
- Docker
- Terraform
- Wazuh
- SOC Operations

## Objetivos

Construir un entorno SOC desde cero.
Guardar:

Ctrl + O
Enter
Ctrl + X
Paso 13 - Primer Commit
Agregar archivos:

git add .
Crear commit:

git commit -m "Initial SOC lab structure"
Ver historial:

git log --oneline
Paso 14 - Crear Repositorio en GitHub
Desde la carpeta del proyecto:

gh repo create soc-learning-lab \
--public \
--source=. \
--remote=origin \
--push
Esto hace automáticamente:

Crea el repositorio en GitHub.
Agrega el remoto origin.
Realiza el push inicial.
Paso 15 - Verificar el remoto
git remote -v
Salida esperada:

origin https://github.com/usuario/soc-learning-lab.git
Paso 16 - Abrir el Repositorio
gh repo view --web
Se abrirá GitHub en el navegador.

Flujo Diario de Trabajo
Ver cambios:

git status
Agregar cambios:

git add .
Crear commit:

git commit -m "Descripción de cambios"
Enviar a GitHub:

git push
Actualizar desde GitHub:

git pull
Próximos pasos del laboratorio SOC
Linux básico
Redes básicas
Docker
Terraform
Wazuh
Casos de detección SOC
Automatización
Documentación continua en GitHub