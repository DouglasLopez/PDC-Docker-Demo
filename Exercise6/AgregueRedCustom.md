## Como ver los logs de un servicio

Use el archivo anterior

Verifique la sintaxys especificado en [Compose- Networing](https://docs.docker.com/compose/networking/)

Examine la sintaxis de networking y trate de definir una red con su nombre donde los dos contenedores se hablen entre si

Agrugue el servicio contenedor3 para hacer ping a contenedor4

Haga que contenedor4 y contenedor3 sean parte de la red myred<nombre>

Trate de hacer ping hacia contenedor1 y contenedor2 respectivamente desde contenedor3 y 4

Actualice el stack creado en el paso anterior

```
 docker stack deploy --compose-file=docker-compose.yml <mynombre>
```


Verifique el servicio nuevo recien creado con los comandos aprendidos

```
docker service ls
```

Encuentre los contenedores y observe los logs



