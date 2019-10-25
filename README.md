# Backend

API desarrollado usando SpringBoot.

## Requerimientos

- JRE (Java Runtime Environment) 8 para ejecutar API
- JDK (Java Development Kit) 8 y Maven para compilar API

### Edición

El código fuente del backend se puede compilar y correr el servidor en modo de desarrollo usando:

```sh
mvn spring-boot:run
```

Para re-empacar el código como un archivo .jar hay que usar el comando:

```sh
mvn clean package
```

Esto creará una carpeta /target con el archivo jar compilado.

### Ejecución

Para correr el servidor con el backend simplemente hay que ejecutar el archivo .jar usando:

```sh
java -jar testapi-0.0.1-SNAPSHOT.jar
```

Esto levantará el servidor de forma local en el puerto **8080**. No debe de existir algún otro servicio corriendo en ese puerto.

```
http://localhost:8080
```

## Documentación API - Swagger

Para visualizar la documentación de los servicios hay que ir a la dirección:

```
http://localhost:8080/docapi/index.html#/mutation
```

## Datos de prueba

```
POST - localhost:8080/mutation/
```

Secuencias sin mutación - se espera código 403
```json
{
  "dna": ["ATGCGA","CAGTGC","TTATTT","AGACGG","GCGTCA","TCACTG"]
}
```
```json
{
  "dna": ["ATGCGA","CAGTGC","TTATAT","AGACGG","GCGTCA","TCACTG"]
}
```


Secuencia con mutación - se espera código 200
```json
{
"dna": ["ATGCGA","CACTAC","TCATCT","AGCCTG","CTCATA","TCACGG"]
}
```