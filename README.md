# Docker-Fundamentos
Docker Fundamentos  :books: :whale:-Repositório criado para estudar docker

## Aula 1
- O que eu posso resolver com Docker?

Padronização e produtividade. Resolver um problema antigo que são os impasses entre desenvolvedor e o time de infraestrutura (na minha máquina funciona).

- Simplicidade e configurações rápidas;
- Multi-Plataforma;

## Aula 2
- Configuração do docker em uma máquina virtual Linux

## Aula 3
Aprendendo os primeiros comandos
```shell
docker --version
```
```shell
docker version
```
```shell
docker info
```
```shell
docker
```
```shell
docker images
```
```shell
docker container ls
```
```shell
docker container ls
```
```shell
docker container --all
```

```shell
docker container ls --all
```

## Aula 4

```shell
docker container run --publish 80:80 nginx
```
```shell
docker container start ID-CONTAINER
```
```shell
docker container stop ID-CONTAINER
```
```shell
docker container run --name nome_desejado -d --publish n_porta:n_porta nome_da_imagem
```

```shell
docker container logs nome_da_imagem
```
```shell
docker container top nome_da_imagem
```

```shell
docker container rm id_container
```

## Aula 5 
Na aula 5 foi proposto um desafio que consisita, basicamente, em:
- Criar 3 containers: nginx,mysql e httpd;
- Executar os containers em modo detach e com nomes;
- Executar o nginx na porta 80:80, o httpd na porta 8080:80 e o mysql na porta 3306:3306;
- Ao final remover todos os containers.

## Aula 6
Resposta ao desafio proposto

```shell
docker container run -d --publish 8080:80 --name db -e MYSQL_RANDOM_ROOT_PASSWORD = yes mysql
```
```shell
docker exec -it db bash
```
```shell
docker container run -d --publish 8080:80 --name webserver httpd
```
```shell
docker container run -d --publish 8080:81 --name proxy nginx
```
```shell
docker container rm id_httpd id_nginx id_mysql
```
## Aula 7

- Entendendo o que é uma imagem Docker;
- Utilizando o Docker Hub Registry
- Gerenciando imagens locais

```shell
docker pull imagem
```

```shell
docker pull imagem:version
```
```shell
docker imagem history name_image
```
```shell
docker imagem inspect name_image
```
```shell
docker login
```
```shell
docker push nome_image
```

## Aula 8
Na aula 8 o professor propôs um desafio de imagens do docker
### Parte 1 do desafio
- Download da imagem mysql/mysql-server:5.7;
- Download da imagem zabbix/zabbix-server-mysql;
- Download da imagem zabbix/zabbix-web-nginx-mysql;
- Realizar a tag zabbix/zabbix-server-mysql treinaweb/zabbix-mysql;
- Realizar a tag zabbix/zabbix-web-nginx-mysql treinaweb/zabbix-nginx.
### Parte 2 do desafio
- Iniciar o container mysql-server;
- Declarar o nome mysql-server
- Declarar a variável MYSQL_DATABASE = "zabbix"
- Declarar a variável MYSQL_USER = "zabbix"
- Declarar a variável MYSQL_PASSWORD = "zabbix_pwd"
- Declarar a variaável MUSQL_ROOT_PASSWORD = "root_pws"
- Utilizar a imagem mysql:5.7
- Utilizar a formatação : --character-set-server = utf8 -- collation-server = utf8_bin
## Parte 3 do desafio

