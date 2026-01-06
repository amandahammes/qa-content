# Automação API com RestAssured

## O que é o REST Asssured

RestAssured é uma biblioteca Java de código aberto, poderosa e flexível, usada para simplificar a automação de testes de APIs RESTful, permitindo enviar requisições HTTP (GET, POST, PUT, DELETE) e validar respostas (JSON, XML, cabeçalhos, status) de forma legível e eficiente, usando uma sintaxe fluente e BDD (Given/When/Then) para testes claros e de fácil manutenção.

## Plano de Testes

Para implementar automação com REST Assured, primeiro deve-se planejar o escopo do projeto, fazer o levantamento de cenários de acordo com as prioridades que mais fizerem sentido para o projeto.

Devem ser levados os consideração os principais endpoints e seus "caminhos felizes", mas também os "tristes".

## Tecnologias a serem usadas

Após isso, também é muito importante escolher as tecnologias que mais façam sentido para o projeto: versão do java, framework de teste, bibliotecas de API e de relatórios.

Sugestões do que usar:

- Linguagem: Java 21
- Gerenciamento projeto Java: Maven
- Framework de Teste: [JUnit Jupiter API](https://mvnrepository.com/artifact/org.junit.jupiter/junit-jupiter-api)
- Bibliotecas: [Rest Assured](https://mvnrepository.com/artifact/io.rest-assured/rest-assured), [Jackson Databind](https://mvnrepository.com/artifact/com.fasterxml.jackson.core/jackson-databind), [Hamcrest](https://mvnrepository.com/artifact/org.hamcrest/hamcrest)

[Para procurar outras dependências do Maven](https://mvnrepository.com/)

    * Jackson Databind: O Jackson Databind é uma biblioteca fundamental do ecossistema Java, responsável por fornecer a funcionalidade de data binding (ligação de dados), que permite a conversão automática e eficiente entre objetos Java (conhecidos como POJOs, ou Plain Old Java Objects) e dados formatados, como JSON.

    * Hamcrest: O Hamcrest é uma biblioteca que permite escrever afirmações (assertions) mais expressivas e legíveis em testes unitários. Em vez de usar métodos de asserção simples e genéricos (como assertEquals(esperado, real)), o Hamcrest introduz o conceito de "matchers" (comparadores) que tornam a intenção do teste mais clara, quase como se estivesse lendo uma frase em inglês. 