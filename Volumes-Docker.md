### **Listar volume:**
```
$docker volume ls
```

### **Borrar todos los "volume" que no estan en uso por ningún contenedor:**
```
$docker volume prune
```

## **PERSISTIR DATOS ENTRE CONTENEDORES**
`Levantaremos un contenedor especificandole un volumen`

### **PRIMERO: Crear un volume nuevo para nuestros datos:**
```
$docker volume create nombre_volumen
Ex:
$docker volume create dbdata
```

### **SEGUNDO: Levantamos el contenedor con nuestro volume**
```
$docker run -d --name nombre_contenedor --mount src=nombre_volumen,dst=directorio_contenedor name_image
Ex:
$docker run -d --name db --mount src=dbdata,dst=/data/db mongo
```

### **TERCERO: Entramos al contenedor de forma interactiva y añadimos un dato:**
```
$docker exec -it db bash
- Entramos a mongo:
#mongo
- Añadimos datos:
>use platzi
>db.users.insert({ "name" : "my_user_name" })
```

### **Ahora si salimos y eliminamos el contenedor y lo volvemos a levantar:**
```
$docker rm -f db                                                        // Eliminamos el contenedor
$docker run -d --name db --mount src=dbdata,dst=/data/db mongo          // Levantamos nuevamente el contenedor
$docker exec -it db bash                                                // Entramos de forma interactiva
```

### **Encontraremos nuestros datos insertados**
```
#mongo
>use platzi
>db.users.find()
```