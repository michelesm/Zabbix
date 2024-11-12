### Estrutura Geral do Seminário

1. **Introdução ao Spring Test** - Introdução ao tema, relevância e panorama geral do Spring Test.
2. **Tipos de Testes no Spring** - Explicação dos tipos de testes suportados pelo Spring.
3. **Ferramentas de Testes e Configuração no Spring** - Ferramentas que o Spring oferece para configurar e rodar testes.
4. **Práticas Avançadas e Exemplos de Testes com Spring** - Demonstração de práticas recomendadas e exemplos de testes reais com Spring.

---

### Divisão do Conteúdo 

#### 1. **Mayara - Introdução ao Spring Test**
   - **Objetivo**: Introduzir o tema, destacar a importância dos testes automatizados e o papel do Spring Test.
   - **Conteúdo**:
     - Explicação geral sobre **Testes Automatizados** em projetos de software.
     - Importância de **testes unitários, de integração e de aceitação** no ciclo de desenvolvimento.
     - Introdução ao **Spring Test** e como ele facilita os testes de aplicações Spring Boot.
     - Descrição das principais funcionalidades do Spring Test, como **mocking**, **test context** e **integração com JUnit**.
   - **Duração Sugerida**: 5 minutos

#### 2. **Yohanna - Tipos de Testes no Spring**
   - **Objetivo**: Explicar os tipos de testes suportados pelo Spring e como eles se integram ao ciclo de desenvolvimento.
   - **Conteúdo**:
     - Explicação dos **Testes Unitários** no Spring: Conceito de testes unitários e como o Spring simplifica esses testes com o uso de mocks (Mockito).
     - Introdução aos **Testes de Integração** com Spring Test: Como configurar e executar testes de integração, incluindo exemplos de testes com banco de dados em memória (H2).
     - Explicação sobre os **Testes de Sistema**: Testes que verificam o comportamento completo da aplicação, com casos de uso e cenário de exemplo.
     - Breve introdução aos **Testes de Aceitação** usando o Spring, como a biblioteca **RestAssured** para testes de APIs REST.
   - **Duração Sugerida**: 10 minutos

#### 3. **Michele - Ferramentas de Teste e Configuração no Spring**
   - **Objetivo**: Apresentar as principais ferramentas e configurações oferecidas pelo Spring Test para criar um ambiente de teste adequado.
   - **Conteúdo**:
     - Explicação da integração com **JUnit** e sua importância no Spring Test.
     - Introdução ao **Mockito**, framework de mocking, e sua aplicação em testes unitários para simular comportamentos de componentes.
     - Configuração do **Spring Test Context** para testes de integração, incluindo uso de anotação `@SpringBootTest` para carregar o contexto da aplicação.
     - Uso de anotações importantes como `@MockBean`, `@Autowired`, `@TestConfiguration`.
     - Configuração e uso de banco de dados em memória (exemplo: **H2**) em testes de integração.
   - **Duração Sugerida**: 10 minutos

#### 4. **Pierre - Práticas Avançadas e Exemplos de Testes com Spring**
   - **Objetivo**: Demonstrar práticas avançadas e exemplos práticos de como realizar testes em uma aplicação Spring.
   - **Conteúdo**:
     - Demonstração prática de um **teste unitário** com JUnit e Mockito.
     - Demonstração de um **teste de integração** usando `@SpringBootTest` e banco de dados H2.
     - Explicação sobre **testes de APIs REST** com Spring MVC Test e o uso de `MockMvc` para simular requisições HTTP.
     - Apresentação de **boas práticas** em testes, como independência de teste, clareza e organização de código de teste.
     - Discussão sobre estratégias de cobertura de testes e ferramentas para avaliação de qualidade de código (ex.: SonarQube).
   - **Duração Sugerida**: 10 minutos

---

### Roteiro de Apresentação

1. **Introdução ao Spring Test** - Mayara 
   - Mayara inicia o seminário aborda a importância dos testes automatizados no desenvolvimento e como o Spring facilita a criação de testes para aplicações Java.
   
2. **Tipos de Testes no Spring** - Yohana 
   - Yohana explica as diferentes categorias de testes, destacando os testes unitários, de integração e de sistema.

3. **Ferramentas de Teste e Configuração no Spring** - Michele 
   - Michele detalha o uso das ferramentas essenciais do Spring Test, mostrando como configurar o ambiente de testes.
   - Explica o uso de JUnit, Mockito e banco de dados em memória, além das anotações principais para a criação de testes no Spring.

4. **Práticas Avançadas e Exemplos de Testes com Spring** - Pierre 
   - Pierre finaliza a apresentação com exemplos práticos de testes no Spring.
   - Demonstra como criar testes usando as ferramentas e práticas explicadas anteriormente e destaca boas práticas para manter um código de teste de qualidade.
