Aplicación de consulta de datos a una BD.

El proyecto corre dentro de un cluster de Google Cloud, en el mismo se encuentran los diferentes pods tanto de la app
como de la base de datos en forma de volumen.

Se deben configurar los siguientes valores secrets en github/settings/secrets/actions del repositorio:

- DB_USER
- DB_PASSWORD
- DB_URL_DEVELOP
- DB_URL_PROD
- GKE_PROJECT
- GKE_SA_KEY


Para poder correr los archivos de migración se deben configurar manualmente en el cluster de GKE el Balanceador de 
Cargas para para servicio de mysql que tengamos en cada ambiente, luego agregar los valores en los secrets del 
repositorio, por ejemplo: 

- DB_URL_DEVELOP : jdbc:mysql://ip:puerto/nombreBaseDeDatos

