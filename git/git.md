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
`git remote add origin codigoHTTPSdoRepoRemoto`: comando que faz a conexão entre repositório local.
`git push -u origin master`: envia pela primeira vez os commits locais para repositório remoto.
`git pull`: Traz do repositório remoto, da mesma branch que eu estou, todas as alterações, tudo que tem de novo no remoto. Ou seja, do remoto para o local. 
`git push`: Envia todas as alterações commitadas da branch local para o repositório remoto.


## .gitignore

`.gitignore` é um arquivo que fica na pasta principal do projeto (assim como o readme) em que são adicionados nomes de arquivos do projeto que serão ignorados pelo git ao fazer commits realizar push para o repositório remoto. Exemplos de arquivos que não devem ser commitados nem enviados ao repositório remoto: .node, .env, etc.
`*-local.md`: asterisco usado para definir todos, nesse caso, todos os arquivos com sufixo igual a *-local.md*


## Git flow

![Exemplo gitflow](/imagens/gitflow.png)

* Branch master (ou main): a linha do tempo principal, ou seja, a que vai ter o código de produção.
Só se manda para a master, quando o códiog está pronto, entregável: já foi testado, já foi validado, já foi homologado...

* Branch develop: é um branch design, é a partir dele que os devs vão desenvolver as features. Ele é o espelho da master, mas está uns pontos a frente antes de ir para a master, por conta das features.

* Feature branch: branch criada a partir de develop para desenvolver uma nova feature da equipe. A feature vai ser desenvolvida, feitos os commits e depois incorporada novamente a develop.

* Release branch: candidato a ir para a produção. Nele são feitos testes, corrigidos bugs para garantir que tudo vá para a master funcionando corretamente. Caso tenha alterações na release, elas vão para develop e para master.


## Pull request

Pedido para que o branch original, faça um pull das atualizações enviadas. Ou seja, no caso de uma feature, a branch da feature vai fazer um pedido para atualizar a branch develop.
Code review: outro membro da equipe confere o código do pull request para ver se está tudo ok. Também é uma boa prática para aprender com os outro colegas.
Merge: incorpora o feature que foi feito pull request, na branch solicitada, no caso do exemplo acima, a develop.


## Resolução de Conflitos

Quando, ao realizar um pull request, uma outra alteração no mesmo arquivo/linhas que a melhoria da branch do pull request, foi feita por outra branch/pull request para a branch de destino, haverá um conflito. Ou seja, se a branch a fez uma melhoria na linha 10 do arquivo index.html, mergeando para a develop e a branch b também fez ula alteração nessa mesma linha, quando a branch b for realizar o pull request para a develop, haverá conflitos. Mas como resolvê-los?
Para resolver local, vou dar um pull na branch de destino, no caso a develop, faço um checkout para a branch que deu conflito, no exemplo a branch b e vou dar um `git merge develop`. Isso vai fazer com que o conflito apareça no repositório local. Para resolver o conflito, ver a modificação em `git status`. Vou abrir o arquivo pelo `vim nomeDoArquivoEmConflito` e vou ver, conforme imagem abaixo, nas linhas que estão acontecendo o conflito, uma tag: <<<<< HEAD, que mostra onde começa o conflito e que diz que esse trecho de código está na branch que foi recentemente implementada e que gerou o conflito, no caso do nosso exemplo a branch b, separado por ======= que finaliza o código da branch do conflito para o código da branch que está recebendo esse pull request, no nosso caso a develop, finalizando com >>>>>>> develop, pra sinalizar que é o fim do conflito na branch develop.

![Exemplo conflito](/imagens/conflito-exemplo.png)

Caso eu queira manter os dois códigos, somente apago as tags <<<<< HEAD, ======= e >>>>>>> develop, mantendo os dois textos.
Caso eu queira manter só um, apago o outro e apago as tags.

Depois de arrumar as alterações e salvar (`:wq`), rodar os comandos:
`git add .` para adicionar a alteração do conflito
`git commit -m "corrigido conflito"`
`git push origin branchB`

Depois disso, o conflito vai ter desaparecido do pull request no repositório remoto e será possível realizar o merge.