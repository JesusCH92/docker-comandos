# **NETWORKS**
## **Listar networks:**
```
$docker network ls
```
## **Crear una network y permitir que `varios contenedores` puedan  conectarse a esta red:**
```
$docker network create --attachable nombre-de-mi-red
Ex:
$docker network create --attachable jesusnetwork
```
## **Conectar un `contenedor` a la `red`**
```
$docker network connect nombre-de-mi-red nombre-del-contenedor-que-deseo-conectar
Ex:
$docker network connect jesusnetwork dbMongo
```
> En este ejemplo dbMongo, es un contenedor creado de la imagen de mongo, para crearlo debes ejecutar:
```
$docker run -d --name dbMongo mongo
```
