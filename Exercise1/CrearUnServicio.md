## Como Crear un servicio en docker swarm

Ingrese a uno de los docker swam managers y corra el siguiente comando, reemplaze su nombre en el nombre del servicio ejemplo `francisco`

```
	docker service create --replicas 1 --name <mynombre> alpine ping docker.com
```	

Verifique que su servicio se encuentra corriendo

```
	docker service ls
```

Verifique cual es la configuracion de su servicio

```
	docker service inspect --pretty <mynombre>

```

Abra una sesion se ssh a los nodos worker y corra el siguiente comando, encuentre en que nodo esta corriendo su servicio

```
	docker ps

```

Elimine a proposito el contenedor para ver como el servicio lo reinicia automaticamente

```
docker kill <id del contenedor>
```