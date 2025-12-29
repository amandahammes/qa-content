# LINUX

## O que é?

É um sistema operacional open source (código livre), tem portabilidade alta (posso editar esse sistema operacional de acordo com necessidade), facilmente personalizável, seguro por essência e possui uma série de compiladores e interpretadures mais comuns já instalados por padrão. Exemplos: Ubuntu, linux mint, elementary OS;

## Terminal

`pwd`: comando para visualizar o diretório que nosso terminal está
`man pwd`: visualizo o manual do comando pwd
`ls`: lista conteúdo do diretório
`ls -lah`: conteúdo mais detalhado do ls
`man ls`: manual do ls
`cd /caminhoOQualQueroAcessar`: para acessar outro diretório
`cd`: sem nenhum argumento, leva para home
`cd ..`: subo um nível no diretório (volto para pasta anterior)
* Tecla TAB ajuda a autocompletar os comandos
`mkdir nomeDoDiretorio`: cria um diretório chamado nomeDoDiretorio
`mkdir -p exemplo1/comandos`: o -p cria uma árvore de diretórios, neste caso a pasta comandos dentro da pasta exemplo1, ambas inexistentes.
`touch arquivo1.txt arquivo2.txt`: comando touch cria arquivos, nesse caso os arquivo1.txt e arquivo2.txt
`cp arquivo1.txt arquivo2.txt`: este comando, cp, copia o arquivo1.txt em arquivo2.txt
`cp -r terminal terminal3`: este comando, com -r copia diretório
`rm arquivo1.txt`: remove o arquivo
`rm -r terminal`: remove o diretorio, se eu colocar -rf, ele força a remoção de tudo que tem dentro do diretório
`rm *.txt`: remove tudo que tem final .txt
`exit`: sai do terminal

## Pacotes Terminal

`apt`: gerenciador de pacotes do linux que permite instalar e remover pacotes de aplicativos pelo terminal
`apt-get update`: atualizar o apt para pegar as últimas informações de pacotes disponíveis para distribuição linux
`apt install nomeDoAplicativo`: exemplo de aplicativo: tree, instala o aplicativo
`tree`: monta uma arvore de arquivos de diretório do sistema
`ctrl + l`: limpa o terminal
`tree -L 1`: mostra somente um nível, o L sendo level e o número a seguir a quantidade de levels
`apt purge tree`: remove o pacote e todos os arquivos temporários criados
`apt remove tree`: remove só a instalação, sem remover outrod arquivos gerados pelo pacote

## VIM ou VI

`vi nomeDoArquivo`: ex vi texto.txt, esse comando entra no arquivo em modo de exibição, não há possibilidade de editar. 
`I`: Para editar o texto, clicar na tecla I e na parte inferior do texto vai aparecer --INSERT--, indicando que é possível editar. 
`ESC`: O vi edita qualquer tipo de arquivo. Depois de terminar de editar, clicar em ESC para sair do modo de edição.
`:q!`: sair sem salvar
`:wq`: salvar e sair
`:q`: sair sem ter editado o texto
`/texto`: quando não está em modo INSERT, ele pesquisa a palavra no arquivo ao apertar enter e apresenta 

