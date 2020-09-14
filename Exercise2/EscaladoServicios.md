## Como Escalar un servicio en docker swarm

En una terminal ssh en el nodo manager corra el siguiente comando reemplace el nombre del servicio

```

	docker service scale <mynombre>=8
```

Verifique si su servicio escalo correctamente

```
	docker service ps <mynombre>

```

En el resto de nodos corra el comando docker ps para ver donde esta corriendo su servicio

```
	docker ps
```

Elimine al azar un par de contenedores 

```
docker kill <id del contenedor>
```


Verifique el balanceo del servicio nuevamente

```
	docker service ps <mynombre>

```