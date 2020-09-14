## Como ver los logs de un servicio

En una terminal ssh en el nodo manager descargue el archivo de ejemplo de este ejercicio
```
wget https://raw.githubusercontent.com/DouglasLopez/PDC-Docker-Demo/master/Exercise4/src/docker-compose.yml

```

Examine la sintaxis del archivo y trate de entenderla

Cree el servicio corriendo el siguiente comando

```
 docker stack deploy --compose-file=docker-compose.yml <mynombre>
```

Verifique el servicio nuevo recien creado con los comandos aprendidos

```
docker service ls
```

