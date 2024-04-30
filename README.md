# firebird-api

__Aqui está uma representação em linguagem Mermaid para os diagramas solicitados:__

### Diagrama de Casos de Uso

```mermaid
graph TD;
    Cliente -- Enviar Dados (POST) --> API
    Cliente -- Obter Dados (GET) --> API
    Cliente -- Atualizar Dados (PUT) --> API
    Cliente -- Excluir Dados (DELETE) --> API
```

### Diagrama de Classes

```mermaid
classDiagram
    class Model {
        - atributos
        + validação()
    }
    class Controller {
        + get()
        + post()
        + put()
        + delete()
    }
    class Database {
        + inserir()
        + obter()
        + atualizar()
        + excluir()
    }
    Model <|-- Controller
    Controller --> Database
```

### Diagrama de Sequência

```mermaid
sequenceDiagram
    Cliente->>Controller: POST dados JSON
    Controller->>Model: Validar dados
    Model->>Controller: Dados válidos
    Controller->>Database: Armazenar dados
    Database->>Controller: Dados armazenados
    Controller->>Cliente: Resposta com sucesso
```

### Diagrama de Componentes

```mermaid
graph TD;
    API -- Interage com --> BancoDeDadosFirebird
    API -- Interage com --> ServidorWeb
```

### Diagrama de Atividade

```mermaid
graph TD;
    Cliente --> |Envia requisição POST| API
    API --> |Valida dados| Model
    Model --> |Dados válidos| API
    API --> |Armazena dados| BancoDeDadosFirebird
    API --> |Responde com sucesso| Cliente
```

Esses diagramas fornecem uma visão geral dos diferentes aspectos da arquitetura de um sistema de API com um banco de dados Firebird. Você pode ajustar esses diagramas conforme necessário para refletir os detalhes específicos do seu projeto.
