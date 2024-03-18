# Testes API - Introdução

[APIS Públicas](https://publicapis.dev/)

### **Introdução**

**API:** interface de programação de aplicações que traz como objetivo expor um serviço sem que as pessoas precisem conhecer qual a sua estrutura.
API => abstrai o que está no backend e entrega pro client somente as informações solicitadas em REST.

**REST:** modelo de arquitetura que fornece diretrizes para que os sistemas distribuídos se comuniquem diretamente usando os princípios e protocolos existentes da Web.

    Services: Camada dentro do backend que armazena as regras de negócio;
    Repository: Responsável por trafegar as informações entre a regra de negócios e o banco de dados ou sistema de armazenamento;
    Controller: implementação da API/Rest buscando as informações através dos serviços; 


É muito importante que o QA saiba como uma API funciona e quais os conceitos relacionados a API e o backend.

**Importância testes de API:** garantir o funcionamento correto das requisições, respostas (request e response) e funcionalidades da interface.

### **Request & Response**

    Request: requisição que o cliente envia ao servidor. Ela possui todas as informações acerca do que o cliente espera receber de volta.
    Response: é a resposta do servidor ao pedido do cliente. Ela pode conter os dados que o cliente espera ou uma resposta de erro.

Para fazer Request e receber Response pelo terminal (bash):

    $ curl -X POST -is http://endereco/caminho/auth -d ' { conteúdo do Json, ex: "email": "email@mail.com", "senha": "123456" }' -H 'Content-Type: appication/json'

Onde:

    -i => organiza o conteúdo do cabeçalho do response;
    -s => remove informações do tempo de resposta;
    -d => dados do body a serem inseridos;
    -H => insere header;


### **Como enviar dados para API/REST**

Através de Header, Query, Path e Body

    BODY => -d: Geralmente usado em métodos POST e PUT. Dentro dele eu passo uma string geralmente em JSON.
    
    HEADER => -H: Cabeçalhos com informações importantes. Envia-se entre aspas simples o nome do header, dois pontos e o valor dele. Pode ter mais de um por requisição curl.
    
    QUERY => depois do caminho da requisição, por exemplo um GET http://localhost:8089/api/v1/viagens?regiao=Norte&acompanhante=Isabelle o que vem depois do ? é uma query.

    PATH => quando vai alterar, adicionar ou deletar um objeto, você faz isso via path (normalmente o id do objeto). Assim como a query é no endpoint, depois do barra, por exemplo http://localhost:8089/api/v1/viagens/1


### **Swagger**

Um exemplo de documentação da interface que você está interagindo.

![Imagem Swagger 1](/imagens/swagger1.jpg)

![Imagem Swagger 1](/imagens/swagger2.jpg)

![Imagem Swagger 1](/imagens/swagger3.jpg)


## Técnicas de teste

### Unidade

Valida partes isoladas da API. Geralmente quem desenvolve e aplica é o desenvolvedor da API.

Exemplo: testar as Collections - coleções (que são conjuntos de requisições individuais que podem ser agrupadas e organizadas em uma estrutura hierárquica).

### Contrato

Verificar conformidade com especificações da API. Ou seja, comparar documentação da API e requisições realizadas para garantir alinhamento dos endpoints.

### Integração

Avaliar interação entre diferentes endpoints. Ou seja, obter detalhes da resposta, validando a consistência entre as informações recebidas.

### Particionamento de equivalência

???

## Report de bug

Evidenciar como deveria acontecer, e o retorno que não é o mesmo da documentação.


### Materiais úteis

[Json Formatter](https://jsonformatter.org/)


Fonte: [Curso de Testes de API Rest - Julio de Lima](https://www.youtube.com/playlist?list=PLf8x7B3nFTl17WeEVj405tHlstiq1kNBX)