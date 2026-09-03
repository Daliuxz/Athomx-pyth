# Athomx-pyth

Introducción a GIT y GITHUB.

-----------------------------------------------------------------------------------------------------------------------

# Comandos Git

- git fetch origin | *Sincronizar las ramas que se encuentran en el repositorio remoto.*

- git add . | *Agregar todos los cambios del repositorio.*

- git add "FILES" | *Agregar los archivos seleccionados al repositorio.*

- git commit -m | *Agregar una descripción breve entre comillas dobles ("").*

- git push origin RAMA | *Subir los cambios al repositorio remoto.*

- git branch -a | *Mostrar todas las ramas disponibles en el repositorio. Tanto local como remoto.*

- git checkout RAMA | *Moverse entre ramas.*

- git pull origin RAMA | *Traer los cambios del repositorio remoto al local.*

-----------------------------------------------------------------------------------------------------------------------

# Conceptos

- PR o PA: Pull request | *Validación del codigo/funcion/version/fix y pasar los cambios a la rama principal.*

-----------------------------------------------------------------------------------------------------------------------

# Crear PULL REQUEST

*Se obtiene las ultimas actualizaciones de la rama principal.*
- git fetch --prune; git pull origin | *Actualiza y trae los cambios mas recientes del repositorio remoto.*

- git branch -a | *Mostrar todas las ramas disponibles en el repositorio. Tanto local como remoto.*

*Creación de la nueva rama*
- git checkout -b RAMA-NUEVA | *Creamos una nueva rama del repositorio en local.*

*Se suben los cambios del feature de la nueva funcionalidad*
- git add . | *Agregar todos los cambios del repositorio.*
- git commit -m | *Agregar una descripción breve entre comillas dobles ("").*

- git push origin RAMA-NUEVA | *Enviar los cambios de la rama nueva al repositorio remoto.*

*Se enviara un PULL REQUEST desde github.*

*Proceso de eliminación del feature enviado.*
- git branch -d RAMA-A-ELIMINAR | Se borra la rama del repositorio local.
- git push origin --delete RAMA-A-ELIMINAR | Se eliminara la rama del repositorio remoto.

*Se obtiene las ultimas actualizaciones de la rama principal.*
- git fetch | Actualizar la información del repositorio.
- git fetch --prune | Actualizar los cambios pendientes que pueda tener el repositorio remoto.

-----------------------------------------------------------------------------------------------------------------------

# Generar nuevas ramas de trabajo

*Se obtiene las ultimas actualizaciones de la rama principal.*
- git fetch --prune; git pull origin | *Actualiza y trae los cambios mas recientes del repositorio remoto.*

*Seleccionar la nueva rama creada en github*
- git checkout RAMA | *Moverse a la nueva rama.*

*Crear nueva rama de funcionalidad (Nombres de ramas)*
- git checkout -b feature/NUEVA-FUNCIONALIDAD | *Crear nueva funcionalidad en Desarrollo.*
- git checkout -b release/NUEVA-VERSION | *Crear liberación de codigo. Desarrollo -> Producción.*
- git checkout -b hotfix/NUEVA-ARREGLO | *Corregir errores criticos en la rama Producción.*

*Se suben los cambios del feature de la nueva funcionalidad*
- git add . | *Agregar los cambios que se van a subir.*
- git commit -m | *Agregar una descripción breve entre comillas dobles ("").*

- git push origin feature/NUEVA-FUNCIONALIDAD | *Enviar los cambios de la rama nueva al repositorio remoto.*

*Se enviara un PULL REQUEST desde github.*

*Se obtiene las ultimas actualizaciones de la rama.*
- git checkout RAMA; git pull origin | *Seleccionar RAMA y traer los cambios mas recientes del repositorio remoto.*

*Proceso de eliminación del feature enviado.*
- git branch -D feature/NUEVA-FUNCIONALIDAD | *Forzar la eliminación de la rama del repositorio local.*
- git fetch --prune; git pull origin | *Actualiza y trae los cambios mas recientes del repositorio remoto.*

-----------------------------------------------------------------------------------------------------------------------

# Generar una version para liberar

*Se obtiene las ultimas actualizaciones de la rama.*
- git checkout RAMA; git pull origin RAMA | *Seleccionar RAMA y traer los cambios mas recientes del repositorio remoto.*

*Creación del release de la nueva version*
- git checkout -b release/VERSION | *Crear nueva rama para la version que se va a actualizar.*

*Se suben los cambios del release de la nueva version*
- git add . | *Agregar los cambios que se van a subir.*
- git commit -m | *Agregar una descripción breve entre comillas dobles ("").*

- git push origin release/VERSION | *Enviar los cambios de la rama nueva al repositorio remoto.*

*Se enviara un PULL REQUEST desde github.*

*Subir al main manualmente*
- git checkout main; git pull origin main | *Seleccionar RAMA y traer los cambios mas recientes del repositorio remoto.*
- git merge --no-ff release/VERSION -m "DESCRIPCION DEL MERGE" | *Unir los cambios al repositorio local principal.*

*Proceso no requerido pero recomendado.*
- git tag -a VERSION -m "DESCRIPCION DEL MARCADOR DEL REPOSITORIO" | *Creación de un marcador de estado al momento de hacer el merge.*

- git push origin main | *Subir los cambios del merge al repositorio remoto.*

*Proceso de limpieza de la rama desarrollo.*
- git checkout RAMA; git pull origin RAMA | *Seleccionar RAMA y traer los cambios mas recientes del repositorio remoto.*
- git merge --no-ff release/VERSION -m "DESCRIPCION DEL MERGE DE REGRESO" | *Unir los cambios al repositorio local de la RAMA.*
- git commit -m | *Agregar una descripción breve entre comillas dobles ("").*

*Proceso de eliminación del release enviado.*
- git branch -D release/VERSION | *Forzar la eliminación de la rama del repositorio local.*
- git push origin --delete release/VERSION | *Se eliminara la rama del repositorio remoto.*

-----------------------------------------------------------------------------------------------------------------------


