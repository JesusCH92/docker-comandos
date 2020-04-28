### **Correr un contenedor:**
```
$docker run name_imagen
```

### **Correr un contenedor dandole un nombre:**
```
$docker run --name nombre_dado_al_contenedor name_image
Ex:
$docker run --name hola-mundo hello-world
```

### **Mostrar todos los contenedores:**
```
$docker ps
```

### **Mostrar todos los contenedores (aunque el proceso ha finalizado):**
```
$docker ps -a
```

### **Inpeccionar un contenedor (obtener toda la metadata del contenedor):**
```
$docker inspect id_contenedor
$docker inspect nombre_contenedor
```

### **Inspeccionar un contenedor filtrando por campos especificos**
```
$docker inspect -f '{{json .Config.Env}}' nombre_contenedor
Donde:
- Config es un atributo del objeto metadata del contenedor ($docker inspect nombre_contenedor)
- Env es un atributo dentro de Config
```

### **Renombrar el nombre de un contenedor:**
```
$docker rename nombre_actual_contenedor nuevo_nombre_contenedor
```

### **Mostrar el output de un contenedor:**
```
$docker logs nombre_contenedor
```

### **Eliminar un contenedor:**
```
$docker rm nombre_contenedor
```

### **Eliminar un contenedor, aunque este corriendo:**
```
$docker rm -f nombre_contenedor
```

### **Mostrar la lista de los id de los contenedores:**
```
$docker ps -aq
```

### **Eliminar todos los contenedor:**
```
$docker rm $(docker ps -aq)
```

### **Eliminar todos los contenedor, aunque esten levantados:**
```
$docker rm -f $(docker ps -aq)
```

### **Correr un contenedor en modo interactivo:**
```
$docker run -it name_image
Ex:
$docker run -it ubuntu
```

### **Levantar un contenedor, despejando la terminal "detach" :**
```
$docker run -detach --name nombre_que_le_doy_contenedor name_image
Ex:
$docker run -detach --name server nginx
```

### **Levantar un contenedor, despejando la terminal "detach" e indicandole en que puerto de mi maquina quiero escucharlo:**
```
$docker run -d --name nombre_que_le_doy_contenedor -p puerto_de_mi_host:puerto_contenedor name_image
Ex:
$docker run -d --name server -p 8080:80 nginx
Donde:
- "-d": "-detach"
- "-p": "-publish"
Ex: Si quiero levantar el mismo servicio, debo cambiar el nombre y otro puerto de mi maquina:
$docker run -d --name server3 -p 8081:80 nginx
```

### **Levantar un contenedor, indicandole que carpetas quiero vincular entre mi host y el contenedor**
```
$docker run --name db -d -v path_de_la_carpeta_de_mi_host:path_carpeta_contenedor name_image
Donde:
- "-v": -volumen
Ex:
$docker run --name db -d -v /mnt/c/Users/jcoca/OneDrive/Escritorio/platzi-docker/docker-comandos/mongodata:/data/db mongo
- Con esto ya podemos crear una base de datos y cuando eliminemos el contenedor y lo volvamos a levantar los datos de nuestra 
base de datos no se eliminarán
```