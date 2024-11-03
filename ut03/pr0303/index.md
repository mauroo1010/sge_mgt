# Instrucciones para Crear y Restaurar una Copia de Seguridad en Odoo con pg_dump

1.Generar la copia de seguridad con pg_dump:
    .Conéctate al contenedor de la base de datos:
        docker compose exec db bash

    .Parar el servicio de postgres:
        service postgresql stop
    
    .Realiza la copia de seguridad dentro del contenedor:
        pg_dump -U odoo odoo > backup.sql

    .Reactivo el servicio de PostgreSQL:
        service postgresql start

    .Sal del contenedor:
        exit
    .Apaga el contenedor

2.Copiar el archivo de copia de seguridad a la máquina principal:
    .Usa el siguiente comando cambiando ruta por la ruta donde quieras guardar el archivo:
        docker compose cp db:./backup.sql ./ruta/backup.sql

3.Eliminar los contenedores y limpiar los directorios mapeados:
    docker compose down
    sudo rm -rf dataPG/* sessions/* filestore/* addons/*

4.Recrear los contenedores:
    docker compose up -d
    .Verifica que el servidor no tiene datos accediendo a http://localhost:8069.

5.Restaurar la base de datos desde la copia de seguridad:
    .Entra al contenedor de la base de datos:
        docker compose exec db bash

    .Crea una nueva base de datos vacía:
        createdb -U odoo -O odoo odoo
    
    .Sal del contenedor y copia el archivo de respaldo de vuelta al contenedor:
        docker cp ./backup.sql <ID_CONTENEDOR>:/
    
    .Vuelve a entrar y restaura la copia de seguridad:
        psql -U odoo -d odoo < ./backup.sql

    .Sal del contenedor:
        exit
6.Verificar la restauración:
    .Accede a Odoo en tu navegador en http://localhost:8069 y verifica que los datos han sido restaurados correctamente.