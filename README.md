# comandos
En este repositorio se van a poner los comandos que crea de utilidad en determinados contextos y con determinadas plataformas, como lo pueden ser comandos de terminal de Windows 11 o comandos de Git.
## Terminal de Windows 11 (cmd)
### Actualizaciones
```cmd
:: Buscar y actualizar automáticamente a su última versión todos los programas instalados en el equipo:
winget upgrade --include-unknown --all --accept-package-agreements --accept-source-agreements
```
### Batería
```cmd
:: Realizar un reporte de batería:
powercfg /batteryreport
```
### Seguridad
```cmd
:: Sobreescribir de forma segura el espacio libre del disco C: sin tocar archivos actuales y activos:
cipher /w:C:
```
### DISM (Deployment Image Servicing and Management)
```cmd
:: Chequear si Windows ya sabe que tiene archivos corruptos:
dism /online /cleanup-image /checkhealth
```
```cmd
:: Escanear Windows para detectar archivos corruptos:
dism /online /cleanup-image /scanhealth
```
```cmd
:: Reparar archivos corruptos descargando versiones sanas desde Windows Update:
dism /online /cleanup-image /restorehealth
```
### Liberador de espacio en disco
```cmd
:: Abrir la configuración avanzada del perfil 1:
cleanmgr /sageset:1
```
```cmd
:: Ejecutar la configuración avanzada del perfil 1:
cleanmgr /sagerun:1
```
### Programador de tareas
```cmd
:: Mostrar todas las tareas programadas del sistema en formato de lista vertical:
schtasks /query /fo LIST
```
```cmd
:: Eliminar una tarea programada específica por su nombre sin confirmación:
schtasks /delete /tn "<nombre-de-tarea>" /f
```
## Terminal de Windows PowerShell
### Programas instalados
```powershell
# Mostrar la lista de los programas instalados con sus IDs locales:
winget list
```
### Búsqueda
```powershell
# Buscar un programa en el catálogo de Microsoft por su nombre con sus IDs globales:
winget search <nombre-del-programa>
```
### Instalación
```powershell
# Instalar un programa por su ID global:
winget install --id "<id-de-aplicación>" --exact
```
### Desinstalación
```powershell
# Desinstalar un programa por su ID local:
winget uninstall --id "<id-de-aplicación>"
```
## Git / GitHub
### Básico
```bash
# Inicializar un repositorio local en una carpeta:
git init
```
```bash
# Mostrar el estado del repositorio local:
git status
```
```bash
# Clonar un repositorio remoto en un directorio del disco:
# ACLARACIÓN: No debe haber ningún otro repositorio local en el directorio para no generar conflictos.
git clone <url>
```
```bash
# Bajar en la rama local actual los cambios de la rama remota seleccionada:
git pull origin <nombre-de-rama>
```
### Flujo estándar
```bash
# Añadir todos los cambios del directorio actual al área de preparación (Staging Area):
git add .
```
```bash
# Guardar los cambios del área de preparación en el historial del repositorio local:
git commit -m "<ejemplo-de-mensaje>"
```
```bash
# Subir los cambios de la rama local actual a la rama remota seleccionada:
# ACLARACIÓN: La rama puede o no estar creada en el repositorio remoto, pero tiene que estar creada en el repositorio local. La rama principal se suele llamar main o master. 
git push origin <nombre-de-rama>
```
### Flujo alternativo
```bash
# Añadir los cambios de un archivo en particular del directorio actual al área de preparación:
git add <ejemplo-de-archivo>
```
```bash
# Subir los cambios de la rama local actual a la rama remota seleccionada, vinculando esta última con el parámetro por defecto de los comandos git push y git pull:
git push -u origin <nombre-de-rama>
