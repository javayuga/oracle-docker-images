# Oracle Database on Docker
Sample Docker build files to facilitate installation, configuration, and environment setup for DevOps users. For more information about Oracle Database please see the [Oracle Database Online Documentation](https://docs.oracle.com/en/database/oracle/oracle-database/index.html).

## SingleInstance
Provides Docker build files to create an Oracle Database Single Instance Docker image. For more details, see [SingleInstance/README.md](./SingleInstance/README.md).

## RAC 
Provides Docker build files to create an Oracle RAC Database docker image. For more details, see [RAC/README.md](./RAC/README.md).


# Running locally

docker run --name oracle_18_xe \
-p 1521:1521 -p 5500:5500 \
-e ORACLE_SID=xplorer \
-e ORACLE_PDB=xplorer \
-e ORACLE_PWD=xplorer \
-e ORACLE_CHARACTERSET=ISO-8859-1 \
-v /d/pub/data/oradata:/opt/oracle/oradata \
oracle/database:18.4.0-xe



docker run --rm --volumes-from 1840-docker-compose_database_1 -v $(pwd):/backup ubuntu tar cvf /backup/mcan.tar /opt/oracle/oradata