<h3> Em 2024-1</h3>

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/1089174c-cb91-498e-9531-6a6f19638958" />


<h3> NextSchema</h3>
  
O NextSchema foi desenvolvido com o objetivo de automatizar o acesso ao pipeline da empresa Dom Rock. Este sistema facilita a configuração das fontes de dados do pipeline, tornando o processo mais eficiente.

Com o NextSchema, os usuários podem fazer o upload de arquivos CSV contendo dados de negócios. O sistema então orienta o cliente durante as diversas etapas, ajudando a definir quais itens devem ser processados para análise, conforme o progresso do processo.

<h3> Tecnologias Utilizadas </h3>
  
<h3> Banco de Dados: </h3>

Linguagem de Consulta Estruturada (SQL); Ferramenta de consulta: MySQL.

<h3> Back-end:</h3>

Linguagem de programação: Java;
Framework: Spring;
IDE: InteliJ;
Requisições: Postman;
Segurança: Java Security Mananger;
Testes Unitários.

<h3> Front-End:</h3>

Linguagem: HTLM, C# e Java Script.
IDE: VS Code.
Modelo de interface: Figma.

<h3> Gestão de equipe: </h3>

Jira.

<h3> Comunicação: </h3>

WhatsApp;
Discord;
E-mail Hotmail.

<h3> Contribuições Pessoais </h3>

Durante o desenvolvimento do projeto Spring, contribuí para a implementação e execução de testes de integração e documentação dos endpoints. Meu trabalho envolveu as seguintes etapas principais:

<h3> Configuração do Ambiente, Execução e Validação de Testes </h3>

Para configurar o ambiente de testes, adicionei as dependências necessárias no pom.xml e configurei as propriedades específicas no application-test.properties. Isso incluiu a definição da URL do banco de dados MySQL, o driver, e as credenciais de acesso.

Além disso, utilizei anotações como <code>@SpringBootTest</code> para carregar o contexto completo da aplicação e realizar testes de integração com endpoints específicos.

Configurei perfis específicos para testes no arquivo application-test.properties, garantindo que os testes fossem executados em um ambiente controlado. Isso incluiu a configuração de propriedades do banco de dados e outras dependências necessárias para os testes.

Realizei a execução dos testes de integração utilizando o Maven e analisei os resultados para identificar e corrigir quaisquer problemas. 

Os testes foram estruturados para cobrir diferentes cenários e casos de uso, assegurando que a aplicação se comportasse como esperado em situações reais de uso.

Esta contribuição para os testes de integração garantiu a qualidade e a estabilidade da aplicação, ajudando a identificar problemas de integração precocemente e garantindo que as funcionalidades estivessem funcionando conforme esperado em um ambiente integrado.

<details>

<h3>Observe códigos retirados do projeto</h3>

Dependências necessárias no pom.xml:

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-test</artifactId>
    <scope>test</scope>
</dependency>
```
Propriedades específicas no application-test:

```xml
spring.datasource.url=jdbc:mysql://localhost:3306/dbnextschema
spring.datasource.username=devs
spring.datasource.password=password123
spring.jpa.hibernate.ddl-auto=update

# SpringDoc OpenAPI 3.1.6 Swagger 3
springdoc.swagger-ui.path=/docs-api.html
springdoc.api-docs.path=/docs-api
springdoc.packagesToScan=com.api.nextschema.NextSchema.web.controller


# Tamanho m�ximo do CSV
spring.servlet.multipart.max-file-size=500MB

#Inje��o de depend�ncia m�tua
spring.main.allow-circular-references=true


# Secret token
api.security.token.secret=${JWT_SECRET:my-secret-key}
```
Anotações como <code>@SpringBootTest</code>:

```xml
package com.api.nextschema.NextSchema;

import org.junit.jupiter.api.Test;
import org.springframework.boot.test.context.SpringBootTest;

@SpringBootTest
class NextSchemaApplicationTests {
   NextSchemaApplicationTests() {
   }

   @Test
   void contextLoads() {
   }
}
```

</details>

<h3> Documentação e Melhoria Contínua: </h3>

Implementei a documentação dos endpoints da API utilizando o Swagger. 

A documentação inclui um resumo, uma descrição detalhada e as possíveis respostas HTTP para cada endpoint. 

Isso garante que os desenvolvedores que utilizam a API tenham uma compreensão clara de como interagir com os diferentes recursos disponíveis.

<details>

<h3>Observe códigos retirados do projeto</h3>
  
Um exemplo de implementação da documentação que realizei neste projeto:

```xml
  @Operation(
    summary = "Criar uma nova coluna.",
    description = "Recurso para criar uma nova coluna",
    responses = {
        @ApiResponse(responseCode = "201", description = "Recursos criados com sucesso",
            content = @Content(mediaType = "application/json", array = @ArraySchema(schema = @Schema(implementation = ColunaResponseDto.class)))),
        @ApiResponse(responseCode = "400", description = "Nome da coluna não pode ser nulo.",
            content = @Content(mediaType = "application/json", schema = @Schema(implementation = ErrorMessage.class))),
        @ApiResponse(responseCode = "400", description = "O tamanho de nome não pode ser menor que 1 caracteres e maior que 30 caracteres.",
            content = @Content(mediaType = "application/json", schema = @Schema(implementation de ErrorMessage.class))),
        @ApiResponse(responseCode = "400", description = "Metadata não pode ser nulo.",
            content = @Content(mediaType = "application/json", schema = @Schema(implementation de ErrorMessage.class))),
    }
)
@PostMapping
public ResponseEntity<List<ColunaResponseDto>> create(@Valid @RequestBody List<ColunaCreateDto> createDtos) {
    List<ColunaResponseDto> colunasCriadas = new LinkedList<>();

    for (ColunaCreateDto coluna : createDtos) {
        Coluna colunaCriada = colunaService.criarColuna(ColunaMapper.toColuna(coluna));
        colunasCriadas.add(ColunaMapper.toDto(colunaCriada));
    }
    return ResponseEntity.status(HttpStatus.CREATED).body(colunasCriadas);
}
```

</details>


<h3>Hard Skills:</h3>

- Spring Boot:
Desenvolvi uma sólida compreensão de Spring Boot para criar aplicações robustas e escaláveis.

- Testes de Integração:
Trabalhei com testes de integração para garantir a qualidade do código e a funcionalidade dos endpoints.

- Maven:
Aperfeiçoei minhas habilidades em Maven para gerenciar dependências e automatizar a execução de testes.

- Documentação de Endpoints (Swagger):
Utilizei Swagger para documentar APIs de forma clara e fácil de usar.

- Gestão de Dependências e Automação:
Aprofundei conhecimentos na integração de componentes e automação de processos com Maven.

<h3>Soft Skills:</h3>

- Comunicação Eficaz: 
Colaborei com as equipes de desenvolvimento e QA para alinhar expectativas e resolver problemas.

- Resolução de Problemas: 
Enfrentei e corrigi desafios técnicos relacionados à integração de componentes.

- Gerenciamento de Tempo: 
Organizei e priorizei tarefas, garantindo a execução eficiente do projeto.

- Atenção aos Detalhes: 
Desenvolvi uma atenção rigorosa aos detalhes para assegurar a precisão dos testes realizados.

- Adaptabilidade: 
Ajustei estratégias rapidamente em resposta a mudanças nos requisitos do projeto, mantendo a eficiência.

---

