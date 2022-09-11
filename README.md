## Lista container ativos
`docker ps`

## Lista todos container
`docker ps -a`

## Para container
`docker stop 665_ID`

## Start (depois de criado)
`docker start nginx-docker (ID ou nome)`

## Rodar (cria) container
`docker run -d -p 3000:3000 --name node-docker2(nome container) node-docker-image (nome imagem ou ID)`

`docker run -d -p 80:80 --name nginx-docker nginx`

## Roda e já abre o container no TERMINAL - se for node, já roda node
`docker run -it ubuntu`

## BUILDAR container com tag
`docker build -t node-docker-image .`

## Exluir container 
`docker rm 52c5ebdce75f`

## LOGS de 1 containers
`docker logs nginx-docker (nome ou ID)`

## Listar imagens baixadas
`docker image ls`

## Excluir imagem
`docker rmi a4b22b431ff1`

## Limpar container - economizar espaço
`docker system prune`

# Extras

## Baixar imagem a parte
`docker pull fedora (nome da imagem)`

## Atalho sair do CONTAINER sem fecha-lo
`CTRL + P + Q`

## Entrar em um container no terminal (modo interativo)
`docker attach (nome ou ID)`

## Iniciar um container com um comando e deixar rodando por um tempo
docker run -d centos /bin/bash -c "ping 8.8.8.8 -c 50"

## Ver o que está sendo executado em um container TOP
docker top 441ea9b4c96a (ID)

## Maneiras diferentes de acessar um container
`nsenter -m -u -n -p -i -t 3480 (número do PID que descobre com inspect) /bin/bash`

## Descobrir PID
`docker inspect ID | grep Pid` > o primeiro número será o Pid

## OUTRA opção para acessar o container 
`docker exec -it ID /bin/bash`
