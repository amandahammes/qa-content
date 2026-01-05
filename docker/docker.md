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

[Docker Hub](https://hub.docker.com/)

Docker hub é a maior biblioteca do mundo em imagens de containers. Imagens que foram baixadas para utilização mais de um bilhão de vezes. Existem imagens para as mais diversas finalidades: banco de dados (ex mysql, mongodb, postgress), apache, etc. É do docker hub que vamos baixar a maioria das nossas imagens, ele é um register público de imagens para o docker. <br>

Cada imagem é como se fosse uma receita de o que precisa para rodar uma instância para aquilo que ela foi criada. Ex: uma imagem de um mysql, vai ter a instalação de todas as dependências necessárias para instalar um servidor de mysql e depois a instalação de fato de um servidor mysql. E em seguida a instalação e disponibilização do servidor no container. Tudo de forma reproduzível através de uma imagem, pois a imagem é exatamente isso: um guia de como reproduzir aquilo quantas vezes necessárias e expor a porta do servidor (a porta do mysql, caso usando um myslq, por exemplo). Isso faz com que o container tenha o serviço do banco 100% disponível para uso. <br>

[Imagem docker Sample Static Site](https://hub.docker.com/r/dockersamples/static-site)
Exemplo de site estático que o docker disponibiliza para estudo. <br>

`docker run dockersamples/static-site`: executar a imagem, no caso do exemplo, da dockersamples. Importante! As portas do projeto que rodamos no docker estão no container e não na máquina. <br>

`docker run -p 8080:80 -p 8443:443 -d dockersamples/static-site`: onde -p 8080:80 é a porta 8080 do host na porta 80 do container e -p 8443:443 é a porta 8443 do host na porta 443 do container. O -d significa detached (não vou atachar o client na saída do container, pois se eu ficar vendo a saída do container, não vai ter saída nenhuma, ele prende o terminal. Com o -d ele executa o container sem o output). <br>

`docker rmi nomeContainer/IDCONTAINER`: remove imagem <br>

## Imagens Personalizadas e Gestão de Volumes

`docker build -t nameSpace/nomeImagem:versão`: acrescenta no final -f nomeDoArquivo se o nome do arquivo não for dockerfile. Esse comando é para criar imagem de acordo com o que está no dockerfile. No exemplo, nameSpace/nomeImagem:versão = "amandakopper/nginx:1.0.0". -t: cria uma tag da imagem, definindo nameSpace/nomeImagem:versão. <br>

[Conteúdo de Exemplo do Arquivo DockerFile](/imagens/conteudo-dockerfile.png)

Para ver se essa imagem está funcional: `run -d -p 8080:80 --name NOMEACOLOCARNOCONTAINER nameSpace/nomeImagem:versão` e em seguida `docker ps`. <br>

`docker images`: lista as imagens docker criadas <br>

`pwd`: mostra o caminho completo da pasta atual. <br>

`docker run -d -p 8082:80 -v CAMINHOCOMPLETODOARQUIVO --name NOMECONTAINER nameSpace/nomeImagem:versão`:construindo novo container a partir de nameSpace/nomeImagem:versão. A mesma imagem criada acima, porém com o atributo -v CAMINHOCOMPLETODOARQUIVO.