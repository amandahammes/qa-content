# Docker

## Virtualização x Containers

Benefícios que a vitualização trouxe: num único servidor com seu hardware, seu sistema operacional, um hypervisor e abaixo disso, as VMs, com um sistema operacional para cada VM. Na virtualização temos hardware e sofware virtualizado de forma independente e isolado para cada aplicação.

Na forma de containers, o cenário muda, pois não se isola a máquina/servidor inteiro, só se isola o processo, a aplicação que se vai rodar. Isso facilita, pois diminui a quantidade de camadas utilizando containers e alterando o hypervisor pelo docker engineer.

![Exemplo virtualização x docker](/imagens/docker-vm-container.png)
Retirado de [Zdnet](http://www.zdnet.com/article/what-is-docker-and-why-is-it-so-darn-popular/)

## Instalação e criação de containers

[Documentação Oficial Docker](https://docs.docker.com/)
