## Como ver los logs de un servicio

En una terminal ssh en el nodo manager corra el siguiente comando reemplace el nombre del servicio

```
docker service logs <mynombre>
```

Verifique la salida del comando


## Drenar un nodo del swarm

En una terminal ssh en el nodo manager corra el siguiente comando para ver los nodos del cluster

```
docker node ls
```

Corra el comando `docker service ps` para verificar el estado de las tareas en los diferentes nodos

```
	docker service ps <mynombre>
```
Remueva uno de los nodos del cluster

```
	docker node update --availability drain <nombre del nodo>
```

Verifique el estado del nodo

```
	docker node inspect --pretty <nombre del nodo>
```

Verifique el estado de sus tareas

```
	docker service ps <mynombre>
```

En una terminal de ssh sobre el nodo drenado, Reinicie el nodo 

```
shutdown -r now
```

Una vez inicie nuevamente actualice el estado del nodo

```
	docker node update --availability active <nombre del nodo>
```


Verifique como se balancean las tareas al nodo

```
	docker node inspect --pretty <nombre del nodo>
```


## Reinicio inesperado

En una terminal ssh en el nodo manager corra el siguiente comando para ver los nodos del cluster

```
docker node ls
```

Corra el comando `docker service ps` para verificar el estado de las tareas en los diferentes nodos

```
	docker service ps <mynombre>
```

Reinicie uno de los nodos del cluster, en una terminal ssh sobre el nodo a reiniciar

```
shutdown -r now

```

Verifique el estado del nodo

```
	docker node inspect --pretty <nombre del nodo>
```

Verifique el estado de sus tareas

```
	docker service ps <mynombre>
```


Verifique como se balancean las tareas al nodo

```
	docker node inspect --pretty <nombre del nodo>
```
## Eliminar un nodo

En una terminal ssh en el nodo manager corra el siguiente comando para ver los nodos del cluster

```
docker node ls
```

Elimine un nodo con el siguiente comando

```
$ docker node rm <nombre o id del nodo>
```

Recuerde que si alguna vez tiene problemas como este puede forzar la eliminacion

```
Error response from daemon: rpc error: code = 9 desc = node  is not down and can't be removed

$ docker node rm --force <nombre del nodo>

Node <nombre del nodo> removed from swarm
```

Verifique el estado del nodo en el nodo manager


```
docker node ls
```

Verifique el estado del nodo en el nodo eliminaod

```
Docker info
```

Reinicie el nodo eliminado


## Agregar un nodo manualmente

En una terminal ssh en el nodo manager corra el siguiente comando para ver los nodos del cluster


```
 docker swarm join-token worker
```

copie el comando resultantte y peguelo En el nodo a agregar

```
docker swarm join-token worker

To add a worker to this swarm, run the following command:

    docker swarm join \
    --token SWMTKN-1-3pu6hszjas19xyp7ghgosyx9k8atbfcr8p2is99znpy26u2lkl-1awxwuwd3z9j1z3puu7rcgdbx \
    172.17.0.2:2377
```

## Eliminar un servicio


En una terminal ssh en el nodo manager corra el siguiente comando reemplace el nombre del servicio

```

	docker service rm <mynombre>
```

Verifique los servicios corriendo

```
	docker service ls

```

En el resto de nodos corra el comando docker ps para ver si esta corriendo su servicio

```
	docker ps
```
