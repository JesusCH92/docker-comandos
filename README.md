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

### **Mostrar la lista de los id de los contenedores:**
```
$docker ps -aq
```

### **Eliminar todos los contenedor:**
```
$docker rm $(docker ps -aq)
```

### **Correr un contenedor en modo interactivo:**
```
$docker run -it name_image
Ex:
$docker run -it ubuntu
```