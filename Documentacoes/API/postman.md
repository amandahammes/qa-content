# Testes API com Postman

[APIS Públicas](https://publicapis.dev/)

**API:** interface de programação de aplicações que traz como objetivo expor um serviço sem que as pessoas precisem conhecer qual a sua estrutura.
API => abstrai o que está no backend e entrega pro client somente as informações solicitadas em REST.

**REST:** modelo de arquitetura que fornece diretrizes para que os sistemas distribuídos se comuniquem diretamente usando os princípios e protocolos existentes da Web.

    Services: Camada dentro do backend que armazena as regras de negócio;
    Repository: Responsável por trafegar as informações entre a regra de negócios e o banco de dados ou sistema de armazenamento;
    Controller: implementação da API/Rest buscando as informações através dos serviços; 


É muito importante que o QA saiba como uma API funciona e quais os conceitos relacionados a API e o backend.

#### **Request & Response**

    Request: requisição que o cliente envia ao servidor. Ela possui todas as informações acerca do que o cliente espera receber de volta.
    Response: é a resposta do servidor ao pedido do cliente. Ela pode conter os dados que o cliente espera ou uma resposta de erro.

Para fazer Request e receber Response pelo terminal (bash):

$ curl -X POST -is http://endereco/caminho/auth -d ' { conteúdo do Json, ex: "email": "email@mail.com", "senha": "123456" }' -H 'Content-Type: appication/json'

Onde: 
-i => organiza o conteúdo do cabeçalho do response;
-s => remove informações do tempo de resposta;
-d => dados a serem inseridos;
-H => header;

#### Headers

Parte do Request em que coloca-se informações técnicas que auxiliam o servidor a processar o que está sendo enviado na requisição.


#### Swagger

Docuemntação da interface que você está interagindo.

### Materiais úteis

[Json Formatter](https://jsonformatter.org/)
