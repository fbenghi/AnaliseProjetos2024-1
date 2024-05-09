# **Análise de Projetos e Sistemas**
## Exemplo - Casos de uso
Prof. Felipe Marx Benghi 

## Exemplo 1

> Requisito A.1: O sistema de gerenciamento de conteúdo permitirá que um `Administrador` crie uma nova conta de blog, desde que os detalhes pessoais do novo blogueiro sejam verificados usando o Banco de Dados de Credenciais.


### Caso de Uso: UC001 - Criar uma Nova Conta de Blog

|Campo|Descrição|
|---|---|
| Requisitos Relacionados | Requisito A.1. |
| Descrição Detalhada     | Um autor novo ou existente solicita uma nova conta de blog ao Administrador. |
| Pré-Condições           | Prova de identidade do autor. |
| Pós-Condição de Sucesso | Uma nova conta de blog é criada para o autor. |
| Pós-Condição de Falha   | A solicitação para uma nova conta de blog é rejeitada. |
| Atores Principais       | Administrador. |
| Atores Secundários      | Banco de Dados de Credenciais de Autores |
| Gatilho                 | O Administrador pede ao sistema a criação de uma nova conta de blog |
| Casos Incluídos         | Nenhum. |

**Fluxo Principal**

| Passo | Ação |
|---|---|
| 1 | O Administrador solicita ao sistema para criar uma nova conta de blog. |
| 2 | O Administrador seleciona um tipo de conta. |
| 3 | O Administrador insere os detalhes do autor. |
| 4 | Os detalhes do autor são verificados usando o Banco de Dados de Credenciais de Autores. |
| 5 | A nova conta de blog é criada. |
| 6 | Um resumo dos detalhes da nova conta de blog é enviado por email ao autor. |

**Fluxos Alternativos** 
| Passo | Ação |
|---|---|
| 4.1 | O Banco de Dados de Credenciais do Autor não verifica os detalhes do autor. |
| 4.2 | A aplicação para uma nova conta de blog do autor é rejeitada. |

## Exemplo 2

> Requisito A.2: O sistema de gerenciamento de conteúdo deve permitir que um administrador crie um novo Wiki pessoal, desde que os detalhes pessoais do autor solicitante sejam verificados usando o Banco de Dados de Credenciais de Autores

### Caso de Uso: UC002 - Criar um novo Wiki Pessoal

|Campo|Descrição|
|---|---|
| Requisitos Relacionados   | Requisito A.2 |
| Descrição Detalhada       | Um autor novo ou existente solicita um novo Wiki pessoal ao Administrador. |
| Pré-Condições             | O autor possui comprovante de identidade apropriado. |
| Pós-Condição de Sucesso   | Um novo Wiki pessoal é criado para o autor. |
| Pós-Condição de Falha     | A aplicação para um novo Wiki pessoal é rejeitada. |
| Atores Principais         | Administrador. |
| Atores Secundários        | Banco de Dados de Credenciais de Autores |
| Gatilho                   | O Administrador solicita ao CMS para criar um novo Wiki pessoal |
| Casos Incluídos           | Nenhum. |

**Fluxo Principal**

| Passo | Ação |
|---|---|
| 1 | O Administrador solicita ao sistema para criar um novo Wiki pessoal |
| 2 | O Administrador insere os detalhes do autor |
| 3 | Os detalhes do autor são verificados usando o Banco de Dados de Credenciais de Autores |
| 4 | O novo Wiki pessoal é criado |
| 5 | Um resumo dos detalhes do novo Wiki pessoal é enviado por email ao autor |

**Fluxos alternativos**

| Passo | Ramificação | Ação |
|---|---|---|
| 3.1 | O Banco de Dados de Credenciais de Autores não verifica os detalhes do autor |	
| 3.2 | A aplicação do autor para um novo Wiki pessoal é rejeitada |


## Exemplo A.2 (Reescrevendo Casos de Uso anteriores)

### Caso de Uso: UC003 - Verificar Identidade

|Campo|Descrição|
|---|---|
| Requisitos Relacionados      | A.1 e A.2     |
| Descrição Detalhada          | Os detalhes do autor devem ser verificadas e precisas. |
| Pré-Condições                | O autor possui comprovante de identidade apropriado. |
| Pós-Condição de Sucesso      | Detalhes são verificados |
| Pós-Condição de Falha        | Detalhes não são verificados |
| Atores Principais            | Base de Dados de Credencial de Autores        |
| Atores Secundários           | Nenhum |
| Gatilho                      | Detalhes do autor são fornecidas para verificação |

**Fluxo Principal**

| Passo | Ação |
|-------|------|
| 1     | Detalhes são fornecidos ao sistema. |
| 2     | A Base de Dados de Credencial de Autores verifica os detalhes |
| 3     | Os detalhes do autor são considerados verificados pela Base de Dados de Credencial de Autores |


**Fluxos alternativos**

| Passo | Ramificação | Ação |
|-------|-------------|------|
| 2.1   | As credenciais do autor não são verificadas. | 
| 2.2   | Os detalhes são retornados como reprovados |


### Caso de Uso: UC001 - Criar uma Nova Conta de Blog

|Campo|Descrição|
|---|---|
| Requisitos Relacionados | Requisito A.1. |
| Descrição Detalhada     | Um autor novo ou existente solicita uma nova conta de blog ao Administrador. |
| Pré-Condições           | Prova de identidade do autor. |
| Pós-Condição de Sucesso | Uma nova conta de blog é criada para o autor. |
| Pós-Condição de Falha   | A solicitação para uma nova conta de blog é rejeitada. |
| Atores Principais       | Administrador. |
| Atores Secundários      | Banco de Dados de Credenciais de Autores |
| Gatilho                 | O Administrador pede ao sistema a criação de uma nova conta de blog |
| Casos Incluídos         | UC003 - Verificar Identidade |

**Fluxo Principal**

| Passo | Ação |
|---|---|
| 1 | O Administrador solicita ao sistema para criar uma nova conta de blog. |
| 2 | O Administrador seleciona um tipo de conta. |
| 3 | O Administrador insere os detalhes do autor. |
| 4 `inclui`: Verificar Identidade | Os detalhes do autor são verificados usando o Banco de Dados de Credenciais de Autores. |
| 5 | A nova conta de blog é criada. |
| 6 | Um resumo dos detalhes da nova conta de blog é enviado por email ao autor. |

**Fluxos Alternativos** 
| Passo | Ação |
|---|---|
| 4.1 | A aplicação para uma nova conta de blog do autor é rejeitada. |


### Caso de Uso: UC002 - Criar um novo Wiki Pessoal

|Campo|Descrição|
|---|---|
| Requisitos Relacionados    | Requisito A.2 |
| Descrição Detalhada        | Um autor novo ou existente solicita um novo Wiki pessoal ao Administrador. |
| Pré-Condições              | O autor possui comprovante de identidade apropriado. |
| Pós-Condição de Sucesso    | Um novo Wiki pessoal é criado para o autor. |
| Pós-Condição de Falha      | A aplicação para um novo Wiki pessoal é rejeitada. |
| Atores Principais          | Administrador. |
| Atores Secundários         | Banco de Dados de Credenciais de Autores |
| Gatilho                    | O Administrador solicita ao sistema para criar um novo Wiki pessoal |
| Casos Incluídos            | UC003 - Verificar Identidade |


**Fluxo Principal**

| Passo | Ação |
|---|---|
| 1 | O Administrador solicita ao sistema para criar um novo Wiki pessoal |
| 2 | O Administrador insere os detalhes do autor |
| 3 `inclui`: Verificar Identidade |  Os detalhes do autor são verificados usando o Banco de Dados de Credenciais de Autores |
| 4 | O novo Wiki pessoal é criado |
| 5 | Um resumo dos detalhes do novo Wiki pessoal é enviado por email ao autor |

**Fluxos alternativos**

| Passo | Ação |
|-------|------|
| 3.1   | Uma nova Wiki pessoal não é criada | 




## Exemplo 3

> Requisito A.3: O sistema de gerenciamento de conteúdo deverá manter todo o histórico de solicitações recusadas dos autores.

|Campo|Descrição|
|---|---|
| Requisitos Relacionados | Requisito A.1, Requisito A.2 |
| Descrição Detalhada     | Um autor novo ou existente solicita uma nova conta de blog ao Administrador. |
| Pré-Condições           | Prova de identidade do autor. |
| Pós-Condição de Sucesso | Uma nova conta de blog é criada para o autor. |
| Pós-Condição de Falha   | A solicitação para uma nova conta de blog é rejeitada. |
| Atores Principais       | Administrador. |
| Atores Secundários      | Banco de Dados de Credenciais de Autores |
| Gatilho                 | O Administrador pede ao sistema a criação de uma nova conta de blog |
| Casos Incluídos         | UC003 - Verificar Identidade |

**Fluxo Principal**

| Passo | Ação |
|---|---|
| 1 | O Administrador solicita ao sistema para criar uma nova conta de blog. |
| 2 | O Administrador seleciona um tipo de conta. |
| 3 | O Administrador insere os detalhes do autor. |
| 4 `inclui`: Verificar Identidade | Os detalhes do autor são verificados usando o Banco de Dados de Credenciais de Autores. |
| 5 | A nova conta de blog é criada. |
| 6 | Um resumo dos detalhes da nova conta de blog é enviado por email ao autor. |

**Fluxos Alternativos** 
| Passo | Ação |
|---|---|
| 4.1 | A aplicação para uma nova conta de blog do autor é rejeitada. |
| 4.2   | **A solicitação recusada é armazenada como parte do histórico do autor** |

### Caso de Uso: UC002 - Criar um novo Wiki Pessoal


|Campo|Descrição|
|---|---|
| Requisitos Relacionados    | Requisito A.2 |
| Descrição Detalhada        | Um autor novo ou existente solicita um novo Wiki pessoal ao Administrador. |
| Pré-Condições              | O autor possui comprovante de identidade apropriado. |
| Pós-Condição de Sucesso    | Um novo Wiki pessoal é criado para o autor. |
| Pós-Condição de Falha      | A aplicação para um novo Wiki pessoal é rejeitada. |
| Atores Principais          | Administrador. |
| Atores Secundários         | Banco de Dados de Credenciais de Autores |
| Gatilho                    | O Administrador solicita ao sistema para criar um novo Wiki pessoal |
| Casos Incluídos            | Verificar Identidade |

**Fluxo Principal**

| Passo | Ação |
|---|---|
| 1 | O Administrador solicita ao sistema para criar um novo Wiki pessoal |
| 2 | O Administrador insere os detalhes do autor |
| 3 `inclui`: Verificar Identidade |  Os detalhes do autor são verificados usando o Banco de Dados de Credenciais de Autores |
| 4 | O novo Wiki pessoal é criado |
| 5 | Um resumo dos detalhes do novo Wiki pessoal é enviado por email ao autor |

**Fluxos alternativos**

| Passo | Ação |
|-------|------|
| 3.1   | Uma nova Wiki pessoal não é criada | 
| 3.2   | **UC-005 A solicitação recusada é armazenada como parte do histórico do autor** |

