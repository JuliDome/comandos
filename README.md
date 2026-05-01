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
schtasks /delete /tn "Nombre de tarea" /f
```
## Terminal de Windows PowerShell
### Programas instalados
```powershell
# Mostrar lista de los programas instalados con sus IDs locales:
winget list
```
### Búsqueda
```powershell
# Buscar un programa en el catálogo de Microsoft por su nombre con sus IDs globales:
winget search "Nombre del programa"
```
### Instalación
```powershell
# Instalar un programa por su ID global:
winget install --id "ID de aplicación" --exact
```
### Desinstalación
```powershell
# Desinstalar un programa por su ID local:
winget uninstall --id "ID de aplicación"
```
