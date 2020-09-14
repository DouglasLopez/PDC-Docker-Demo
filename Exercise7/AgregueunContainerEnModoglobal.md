## Como ver los logs de un servicio

Use el archivo anterior

Modifique el servicio contenedor1 y agregue lo siguiente

```
    deploy:
      replicas: 2
      resources:
        limits:
          memory: 512M
```

Modifique el contenedor2 y agregue lo siguiente

```
    deploy:
      mode: global
      resources:
        limits:
          memory: 512M
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



