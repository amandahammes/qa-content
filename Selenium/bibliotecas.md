# Bibliotecas

* JUnit

    O JUnit é um framework de testes para Java que atua como o "motor" da sua automação, sendo responsável por organizar, executar e validar os testes do Selenium. Enquanto o Selenium é a ferramenta que interage com o navegador (clica, escreve, navega), o JUnit fornece as anotações (como @Test, @BeforeEach e @AfterEach) para definir a ordem de execução, além de oferecer as asserções (como assertEquals) para verificar se o resultado esperado no site realmente aconteceu, gerando relatórios de sucesso ou falha ao final do processo.

    O [JUnit Jupiter Aggregator](https://mvnrepository.com/artifact/org.junit.jupiter/junit-jupiter) funciona como um "combo" que reúne em uma única dependência as bibliotecas junit-jupiter-api (anotações), junit-jupiter-engine (motor de execução) e junit-jupiter-params (testes parametrizados), garantindo que todas trabalhem na mesma versão e simplificando o seu pom.xml.

        1. junit-jupiter-api: Contém as anotações principais (como @Test, @BeforeEach) e as asserções para você escrever o código do teste.

        2. junit-jupiter-engine: É o "motor" que realmente executa os testes e faz a ponte com o Maven ou sua IDE.

        3. junit-jupiter-params: Fornece suporte para testes parametrizados, permitindo rodar o mesmo teste com diferentes conjuntos de dados.


* Webdrivermanager

O [WebDriverManager](https://mvnrepository.com/artifact/io.github.bonigarcia/webdrivermanager) é uma biblioteca utilitária que automatiza o gerenciamento dos drivers de navegadores (como o ChromeDriver e o Geckodriver) em projetos Selenium, eliminando a necessidade de baixar, salvar e configurar manualmente os arquivos executáveis .exe em pastas locais. Ao ser executado, ele identifica automaticamente a versão do navegador instalado na máquina do usuário, baixa a versão correspondente do driver e configura as propriedades do sistema necessárias, garantindo que os testes de automação não quebrem sempre que o navegador receber uma atualização automática.


* AventStack (ExtentReports)

O [AventStack](https://mvnrepository.com/artifact/com.aventstack/extentreports) uma biblioteca de relatórios avançados. Enquanto o JUnit gera relatórios simples em texto ou XML, o ExtentReports cria um dashboard em HTML moderno, com gráficos, filtros, logs coloridos e a capacidade de anexar screenshots dos erros automaticamente. Em resumo, ele transforma os resultados brutos dos testes em um relatório visual profissional.


* JavaFaker

O [JavaFacker]() uma biblioteca para geração de dados aleatórios (fictícios). Em vez de você inventar um nome, CPF ou endereço fixo no seu código, o Faker gera dados válidos e diferentes a cada execução. Em resumo, ele cria "massa de dados" dinâmica (nomes, e-mails, senhas) para que seus testes não fiquem viciados sempre nos mesmos valores.


* ShutterBug

O [ShutterBug](https://mvnrepository.com/artifact/com.assertthat/selenium-shutterbug) é uma biblioteca especializada em tirar prints da tela de forma avançada. O Selenium puro consegue tirar prints básicos, mas o Shutterbug resolve problemas que o Selenium sozinho não consegue lidar bem.

[]()

[Selenium](https://mvnrepository.com/artifact/org.seleniumhq.selenium/selenium-java)