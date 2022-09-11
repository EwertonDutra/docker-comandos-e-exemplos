# Anotações

## Dockerfile
### RUN
Executado em tempo de build, construção da imagem
O RUN normalmente não se fica colocando vários e sim usa o && para colocar vários comandos juntos, para evitar várias camadas

`RUN apt-get update && apt-get install -y \
        apache2 \
        apache2-utils \
        vim \
        && apt-get clean \
		&& rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*`
Essas '\' são usadas para quebrar a linha e manter mais legível 

### EXPOSE 
Normalmente usado para expor uma porta do hospedeiro:container, ex: 80:80

### CMD
Usado para executar algo quando o container for levantado, ex: `CMD ["apache2ctl", "-D", "FOREGROUND"]`
Mas tem duas formas de executar: Shell form (o container precisa ter o shell) ou Exec Form (esse não precisa do shell, a "maioria")
<img width="431" alt="CMD" src="https://user-images.githubusercontent.com/13201575/189529976-2e9a5257-51da-4025-a81d-a77c0d33e6bc.png">

### ENTRYPOINT - Não é substituído pela execução, parâmetros na hora de rodar o container
```
FROM ubuntu:18.04
RUN apt-get update && apt-get install -y iputils-ping apache2 
ENTRYPOINT ["apache2ctl"]
```

Você pode passar parâmetro para esse container que sempre executa algo

### ENV 
`ENV var1=Ewerton var2=Dutra`
Você passa ENV para o container

### VOLUME
Para criar volume para o container, pelo que vi até o momento seria mais útil para imagens por exemplo, se eu não for usar o S3 😁

### Warning 
Camadas no docker tem um limite, parece 127, po isso é bom evitar ao máximo ter muitas camadas além de outros problemas

