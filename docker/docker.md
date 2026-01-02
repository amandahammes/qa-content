# Docker

## Virtualização x Containers

Benefícios que a vitualização trouxe: num único servidor com seu hardware, seu sistema operacional, um hypervisor e abaixo disso, as VMs, com um sistema operacional para cada VM. Na virtualização temos hardware e sofware virtualizado de forma independente e isolado para cada aplicação.

Na forma de containers, o cenário muda, pois não se isola a máquina/servidor inteiro, só se isola o processo, a aplicação que se vai rodar. Isso facilita, pois diminui a quantidade de camadas utilizando containers e alterando o hypervisor pelo docker engineer.

![Exemplo virtualização x docker](/imagens/docker-vm-container.png)
Retirado de [Zdnet](http://www.zdnet.com/article/what-is-docker-and-why-is-it-so-darn-popular/)

Então, o que é um container? É um processo ou aplicação isolado da infraestrutura de outros containers e de qualquer outro processo externo. Possui um único objetivo de existencia e possui dentro dele tudo que precisa para executar o seu objetivo: binários, configurações e softwares de dependência. Um container é criado sempre a partir de uma imagem, seja ela local ou remota, pois ele é uma instância executável de uma imagem. Pode ser executado localmente ou remotamente por cloud.


## Instalação e criação de containers

[Documentação Oficial Docker](https://docs.docker.com/)

[Manual para Instalar WSL](/wsl/WSL.md)


## Primeiros passos com docker

No terminal, ver se docker foi instalado com sucesso: `docker --version`. <br>
Para ver o funcionamento: `docker run hello-world`

![Imagem e execução da run hello-world no docker](/imagens/docker_run.png)

Com a instalação do WSL, também é possível abrir um bash no linux com o docker: `docker run -it ubuntu bash`. Com esse comando, o docker vai abrir um bash do linux no terminal e será possível utilizar comandos do terminal linux, exemplo `ls -lh`. Para sair, enviar comando `exit` no terminal. <br>

Um dos primeiros comandos a executar no terminal ao utilizar docker é: `docker ps`. Ele vai nos mostrar sempre a lista de containers em execução. ps = proccess list. Para ver containers que foram executados, mas estão fechados: `docker ps -a`. <br>

Para reexecutar um container já fechado, eu preciso pegar o Container ID (que aparece no docker ps -a) e executar o comando: `docker start CONTAINER_ID`. Ele vai printar o ID novamente e se o comando `docker ps` for executado novamente, o container de bash do Ubuntu vai aparecer. <br>

No caso do exemplo do Ubuntu, para abrir o terminal bash que está executando: `docker exec -ti CONTAINER_ID bash` <br>

Para parar um container: `docker stop nomeDoContainer`. <br>

`docker start -a -i CONTAINER_ID`: para startar um container que foi parado (stop). -a para atachar o client no output, o -i para continuar interagindo com o container. Assim eu não tenho dois bashs, somente um. <br>

`docker rm CONTAINER_ID`: para deletar um container (container_id ou nome do container). <br>

Para nomear container: `docker run --name NOMEACOLOCARNOCONTAINER -it ubuntu bash`. <br>

## Criação de Imagens

