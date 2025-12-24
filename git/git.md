# GIT

## Conceito
Sistema de controle de versão distribuída, escalado e rápido com conjunto de comandos ricos que provém a operações de alto nível e acesso completo ao internals (recursos internos do git).
O git é usado para administrar o código em mais de um repositório local (ligado a um repositório remoto).
Ele permite que o desenvolvedor possa ter a cópia do repositório inteiramente em sua máquina, permitindo que ele trabalhe de forma independente e completa, sem se preocupar com o que os outros devenvolvedores estão fazendo. Assim como os outros desenvolvedores podem ter cada um um repositório em suas máquinas.
Este modelo facilita muito o trabalho offline não precisa todo mundo estar conectado ao repositório de controle de versão, permitindo que somente quando as alterações forem enviadas para o repositório remoto sejam incorporadas de fato as alterações na base de código principal.
Git é um sistema de controles de versão existentes no mercado e o mais utilizado atualmente e serve para controlar, organizar e garantir que as modificações sejam incorporadas de forma mais saudável possível na base oficial de código.
A base oficial de código permite o armazenamento, o acesso ao histórico de todas as modificações e em todos os arquivos do repositório.


## Fazendo o download

[Site oficial GIT](https://git-scm.com/)

Para baixar o git, é necessário encontrar a versão correta para o seu sistema operacional (Windows, Linux e/ou MacOS).
No caso do Windows, baixa-se um instalador (clicar em next até concluir).
No linux, algumas versões já trazem o git previamente instalado, importante validar se ele está instalado com o comando: `git --version`. Caso não apareça a versão, é necessário instalá-lo. No ubuntu, rodar os comandos: `apt update` e em seguira `apt install git`. Ao final do segundo comando, o git estará instalado. Para confirmar, usar novamente o comando: `git --version`.
No caso do MacOS, rodar o comando: `brew install git`.


## Configuração

Configurar nome e e-mail de quem está usando o git. Por quê? Ele é um controle de versão, então toda vez que commitar um arquivo, adicionar alteração em um arquivo, ele vai armazenar quem alterou, quando, onde, enfim, todas essas informações. Para fazer essa configuração, usar a base de comando `git config -- global`.
O `--global` é usado caso queira configurar na máquina como um todo, ficando `git config --global`
O `--local` é usando somente no projeto aberto, ficando `git config --local`
UserName: `git config --global user.name "NOME AQUI"`
E-mail: `git config --global user.email "EMAIL@AQUI"`
Para comfirmar se foram adicionadas com sucesso: `git config --global -l`


## Iniciando repositório

Para iniciar, vamos usar o comando: `git init`
Quando inicia, cria-se a branch chamada *master*.
Para saber o estado atual do repisotório: `git status`.


## Comandos git para commit

`git add #`: adiciona o arquivo no git, onde # é o nome do arquivo, podem ser mais arquivos separados somente por espaço.
`git add .`: adiciona todos os arquivos alterados, sendo todos representado pelo ponto.
`git commit -m "mensagem descrevendo sobre o que é esse commit"`: é um sabe no código que gera um hash pra cada commit que identifica o commit exclusivamente nesse repositório. É importante que a mensagem seja explicativa, para que as outras pessoas que manipulam o código, saibam do que se trata essa alteração, esse commit.
`git restore --staged nomeDoArquivo`: retira arquivo que foi add com git add para que não seja commitado.


## Comandos branchs

`git checkout -b nomeDaBranch`: checkout serve para alternar entre branchs, mas o -b cria uma nova branch, então o comando cria e entra na nova branch criada.
`git checkout nomeDaBranchQueQueroIr`: para alterar para outra branch já existente.
`git log`: ver histórico commitado na branch onde estamos, se usado `git log -p`, o resultado vai mostrar tudo que tem de diferente em cada commit. Para sair do do git log, digita-se `:q`. Se eu quiser um log resumido: `git log --oneline` (onde ele mostra o hash e a mensagem do commit).


## vim

`vim nomeDoArquivo`: abre o arquivo no vi do git para edição.
`:q`: sai do vim sem salvar.
`:wq`: salva e sai do arquivo.


## Outros comandos

`git rm nomeDoArquivo`: remove o arquivo local.


## .gitignore

`.gitignore` é um arquivo que fica na pasta principal do projeto (assim como o readme) em que são adicionados nomes de arquivos do projeto que serão ignorados pelo git ao fazer commits realizar push para o repositório remoto. Exemplos de arquivos que não devem ser commitados nem enviados ao repositório remoto: .node, .env, etc.
`*-local.md`: asterisco usado para definir todos, nesse caso, todos os arquivos com sufixo igual a *-local.md*
