# LINUX

## O que é?

É um sistema operacional open source (código livre), tem portabilidade alta (posso editar esse sistema operacional de acordo com necessidade), facilmente personalizável, seguro por essência e possui uma série de compiladores e interpretadures mais comuns já instalados por padrão. Exemplos: Ubuntu, linux mint, elementary OS;

## Terminal

`pwd`: comando para visualizar o diretório que nosso terminal está <br>
`man pwd`: visualizo o manual do comando pwd <br>
`ls`: lista conteúdo do diretório <br>
`ls -lah`: conteúdo mais detalhado do ls <br>
`man ls`: manual do ls <br>
`cd /caminhoOQualQueroAcessar`: para acessar outro diretório <br>
`cd`: sem nenhum argumento, leva para home <br>
`cd ..`: subo um nível no diretório (volto para pasta anterior) <br>
* Tecla TAB ajuda a autocompletar os comandos <br>
`mkdir nomeDoDiretorio`: cria um diretório chamado nomeDoDiretorio <br>
`mkdir -p exemplo1/comandos`: o -p cria uma árvore de diretórios, neste caso a pasta comandos dentro da pasta exemplo1, ambas inexistentes. <br>
`touch arquivo1.txt arquivo2.txt`: comando touch cria arquivos, nesse caso os arquivo1.txt e arquivo2.txt <br>
`cp arquivo1.txt arquivo2.txt`: este comando, cp, copia o arquivo1.txt em arquivo2.txt <br>
`cp -r terminal terminal3`: este comando, com -r copia diretório <br>
`rm arquivo1.txt`: remove o arquivo <br>
`rm -r terminal`: remove o diretorio, se eu colocar -rf, ele força a remoção de tudo que tem dentro do diretório <br>
`rm *.txt`: remove tudo que tem final .txt <br>
`exit`: sai do terminal <br>


## Pacotes Terminal

`apt`: gerenciador de pacotes do linux que permite instalar e remover pacotes de aplicativos pelo terminal <br>
`apt-get update`: atualizar o apt para pegar as últimas informações de pacotes disponíveis para distribuição linux <br>
`apt install nomeDoAplicativo`: exemplo de aplicativo: tree, instala o aplicativo <br>
`tree`: monta uma arvore de arquivos de diretório do sistema <br>
`ctrl + l`: limpa o terminal <br>
`tree -L 1`: mostra somente um nível, o L sendo level e o número a seguir a quantidade de levels <br>
`apt purge tree`: remove o pacote e todos os arquivos temporários criados <br>
`apt remove tree`: remove só a instalação, sem remover outrod arquivos gerados pelo pacote <br>

## VIM ou VI

`vi nomeDoArquivo`: ex vi texto.txt, esse comando entra no arquivo em modo de exibição, não há possibilidade de editar <br>
`I`: Para editar o texto, clicar na tecla I e na parte inferior do texto vai aparecer --INSERT--, indicando que é possível editar. <br>
`ESC`: O vi edita qualquer tipo de arquivo. Depois de terminar de editar, clicar em ESC para sair do modo de edição. <br>
`:q!`: sair sem salvar <br>
`:wq`: salvar e sair <br>
`:q`: sair sem ter editado o texto <br>
`/texto`: quando não está em modo INSERT, ele pesquisa a palavra no arquivo ao apertar enter e apresenta a primeira palavra correspondente ao texto. Se o texto tem mais repetições da palavra ao longo do texto, ao apertar `n`, a próxima ocorrência da palavra `texto` é destacada. A busca é case sentitiv, ou seja, faz diferença escrever com maiúsculas e minúsculas. <br>
`d`: ao clicar 2x na letra d, sem estar em modo de edição, uma linha é deletada. Se eu digitar um número e 2x a letra d, 5 linhas serão deletadas. <br>
`u`: desfaz a última alteração. <br>
`g`: 2x a letra g, leva o cursor para o início do arquivo <br>
`shift + g`: leva para o final do arquivo <br>
`:10`: me leva para linha 10, o número corresponde a linha que eu quero ir. <br>

## CAT

`cat nomeDoArquivo`: lê o arquivo e joga o conteúdo no terminal <br>
`man cat`: ver manual cat <br>
`cat -e nomeArquivo`: mostra caracteres especiais (não printáveis) <br>
`cat nomeArquivo | more`: navega em conteúdo grande, mostrando página por página. Para passar as páginas, usa-se o ESPAÇO ou as setas para navegar. <br>
`tail -1 nomeArquivo`: mostra o fim do arquivo, nesse caso, a última linha. Se -9, mostra as últimas 9 linhas. <br>
`head -1 nomeArquivo`: mostra o topo do arquivo, nesse caso a primeira linha. <br>
`tail -f nomeArquivo`: acompanha/monitora tudo que está sendo inserido nesse arquivo (muito usado para acompanhar as últimas linhas de um arquivo de log, por exemplo, onde linhas são inseridas enquando o arquivo está sendo visualizado) <br>
`cat nomeArquivo | grep palavra`: traz todas as linhas que tem palavra dentro do arquivo ou log. <br>
`cat nomeArquivo | grep -n palavra`: o mesmo a cima, mas o -n diz em qual linha está a palavra. <br>
`cat nomeArquivo | egrap -v "palavra1|palavra2|palavra3"`: egrap trabalha com vários termos juntos. O -v indicar que são termos que não vão aparecer. <br>
`tar -cvf nomeArquivoASerCriado nomaDaPasta`: gera um arquivo chamado omeArquivoASerCriado com tudo da pasta nomeDaPasta compactado nele. <br>
`zip npmeArquivoZip.zip nomePasta`: cria um zip chamado npmeArquivoZip.zip com o conteúdo nomePasta <br>
`unzip npmeArquivoZip.zip`: descompacta os arquivos do zip <br>


## Avançado

`ifconfig`: visualiza as informações das interfaces de rede no nosso terminal <br>
`ip addr show`: exibe as informações do IP da máquina <br>
`ping www.site.com`: direcionar um teste de rede a um determinado destino <br>
`telnet www.site.com 10`: Ele testa conectividade, mas exige que direcione a conectividade para uma porta, no caso desse exemplo a porta número 10. Para sair da porta: CTRL + ] e para sair do telnet: \q<br>
`ssh usuario@servidor`: conectar em host remoto. Para sair desse servidor: `exit` <br>
`netstat -lpt`: mostra todas as conexões ativas e portas em listen (abertas) na máquina. O -lpt lista o protocolo de TCP. `ps`: após netstat, exibe mais informações. E o `ps aux` process list de uma forma mais organizada.<br>
`kill -n`: forçar o encerramento de uma porta que está em uso. Se n = -9 encerra na hora. Se -2, ele manda um sinal pra encerrar, então ele espera até encerrar. <br>
`top`: exibe as informações dos processos em execução e os processos que estão consumindo recursos (uso de CPU). Para sair do top: q<br>
`df`: exibe o espaço de disco livre no ambiente linux. Se usar -h após, as infos ficam organizadas, mais legíveis. <br>
`du`: exige o tamanho de todos os arquivos. Se usar  ´du -sh *´ vai mostrar todos os arquivos só da pasta em que está <br>
`env`: todas as variáveis de ambiente nesse terminal linux. Se `echo $PATH`: mostra Path dos executáveis nesse terminal linux. Pode alterar PATH por qualquer variável de ambiente existente. <br>
