# **Crear una imagen en Docker**
## **Primero creamos un Dockerfile:**
```
$touch Dockerfile
```
## **En el Dockerfile definimos que imagen queremos obtener:**
```
Ex:
FROM ubuntu
RUN touch /usr/src/mi-carpeta
```
## **Para construir esta imagen, ejecutamos lo siguiente:**
```
$docker build -t ubuntu:my-image
Ex:
$docker build -t ubuntu:jesus
```
## **Subir imagen a tu repositorio de docker-hub**
```
$docker push tu-usuario-docker/tag-imagen-creada
Ex:
$docker push jesusch92/ubuntu:jesus
> Si accedes a tu repositorio de [docker-hub](https://hub.docker.com/) lo podrás ver
```