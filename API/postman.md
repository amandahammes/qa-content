# O que é o Postman?

O Postman é uma ferramenta que dá suporte à documentação das requisições feitas pela API, ou seja, permite a criação de requisições HTTP personalizadas. Possui ambiente para a documentação, execução de testes de APIs e requisições em geral.

**Teste de APIs** oferece um ambiente para testar as APIs, possibilitando a validação de respostas e a automação de testes.

**Ambientes** Possibilita a configuração de ambientes, permitindo alternar entre diferentes conjuntos de variáveis e configurações de forma fácil e rápida.

# Como funciona?

Quando abrimos o Postman teremos um ambiente com mais ou menos essa visualização:

<img src="../imagens/postman1.jpg" width="70%" alt="visao geral postman"><br>

É possível criar uma nova Collection clicando no + do lado esquerdo do input de pesquisa de colections.

Depois de criar uma nova Collection, é possível criar novas requests nos três pontos ao lado do nome da Collection e em Add request:

<img src="../imagens/postman2.jpg" width="30%" alt="criar request"><br>

Ao clicar, aparecerá uma nova aba onde será possível preencher os campos de informações da request. O primeiro é o método a ser escolhido: POST, GET, PUT DELETE. Ao lado o caminho para a requisição.

<img src="../imagens/postman3.jpg" width="70%" alt="aba request"><br>

**Lembrando que é possível checar as informações na documentação da API (no caso desse exemplo é o Swagger):

<img src="../imagens//swagger1.jpg" width="70%" alt="exemplo swagger"><br>

Logo abaixo é possível inserir o Body, selecionando o tipo, por exemplo JSON e em seguida completando com as informações a serem enviadas na requisição. Para enviar, é só clicar em "Send".

<img src="../imagens/postman4.jpg" width="60%" alt="body da requisição"><br>

É possível criar uma variável fixa para o endereço base da aplicação selecionando o endereço e clicando em "Set as a variable" ou clicando em Environments > Globals.

<img src="../imagens/postman7.jpg" width="90%" alt="caminho para criar variaveis globais"><br>

Para selecionar a variável global no endereço, é só colocar o nome da variável entre chaves:

<img src="../imagens/postman8.jpg" width="50%" alt="Usando variável global"><br>

Também é possível criar uma variável global para o token. Para isso, é necessário criar a variável da mesma maneira que explicado acima, porém, com o token muda a cada acesso, os campos de valores ficam vazios.

Em seguida, é necessáriop ir ao requerimento de autenticação, selecionar a aba Tests, criar uma const para a resposta como na imagem abaixo, clicar em "Set a global variable" e dentro colocar o nome da variável global entre aspas e a const como na imagem abaixo.

<img src="..//imagens/postman14.jpg" width="50%" alt="setando token na autenticação"><br>

Então, em cada request que for feito é possível colocar a variável global token em Headers > Authorization para não precisar trocar manualmente a cada nova autenticação.

<img src="../imagens/postman15.jpg" width="50%" alt="inserindo token na request"><br>

Na aba "Tests" é possível criar scripts que serão executados após o recebimento da resposta da execução do teste.

Dito isso, para finalizar, é possível criar Scripts de testes para garantir que o response seja o esperado pela aplicação:

<img src="../imagens/postman16.jpg" width="70%" alt="teste status code">

E caso o resultado do teste depois do response, nesse caso afirmativo:

<img src="../imagens/postman17.jpg" width="70%" alt="resultado teste"> <br>

# Como importar uma API por JSON do Swagger

Clicar em ... e Import: <br><br>
<img src="../imagens/importar-api-json-swagger.png" width="50%" alt="Onde clicar no postman para importar colection por html">

Colar link de json do Swagger: <br><br>
<img src="../imagens/importar-api-json-swagger-2.png" width="50%" alt="Colar link com caminho do json">

Onde encontrar o link do Json na página Swagger de documentação da API: <br><br>
<img src="../imagens/importar-api-json-swagger-3.png" width="50%" alt="Onde no swagger encontrar o link do json (exemplo de ServeRest)">

Conteúdo do link de Json do Swagger: <br><br>
<img src="../imagens/importar-api-json-swagger-4.png" width="80%" alt="Mostrando conteúdo do link json/swagger">

Após colar link na tela da imagem 2, selecionar Postman Collection e Import: <br><br>
<img src="../imagens/importar-api-json-swagger-5.png" width="50%" alt="Ao colar link na tela de imagem 2, últimos passos antes do import">

Resultado da Collection após import: <br><br>
<img src="../imagens/importar-api-json-swagger-6.png" width="30%" alt="Resultado da Collection importada no Postman">