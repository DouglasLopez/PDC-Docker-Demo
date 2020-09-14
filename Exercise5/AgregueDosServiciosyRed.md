## Como ver los logs de un servicio

En una terminal ssh en el nodo manager descargue el archivo de ejemplo de este ejercicio
```
wget https://raw.githubusercontent.com/DouglasLopez/PDC-Docker-Demo/master/Exercise5/src/docker-compose.yml

```

Examine la sintaxis del archivo y trate de entenderla

Cree el servicio corriendo el siguiente comando

Agregue otro servicio con el nombre contenedor2 que haga ping a contenedor1

```
    command: ping contenedor1
```


Modifique el servicio contenedor1 para hacer ping a contenedor2

```
    command: ping contenedor2
```

Actualice el stack creado en el paso anterior

```
 docker stack deploy --compose-file=docker-compose.yml <mynombre>
```


Verifique el servicio nuevo recien creado con los comandos aprendidos

```
docker service ls
```

Encuentre los contenedores y observe los logs



