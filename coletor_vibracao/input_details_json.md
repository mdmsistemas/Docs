# Coletor vibração
## Input (Gerente rotas --> Anaq)

### 1 - Formato do arquivo json:

Nome       |  Tipo | Descrição
:---------:|:---------------:|:-------------:
id    | string | Id da rota
execRouteId       | string | Id da execução da rota
name       | string | Nome da rota
userExecRoute | array | Ver tabela 1.1
monitoredPoints | array | Ver tabela 1.2
isFinished | boolean | Indica se a rota foi finalizada
tdmsBase64 | string | Conteúdo do arquivo TDMS gerador na coleta,<br/>convertido para base64.

#### 1.1 - Detalhes do array "userExecRoute"

Nome       |  Tipo | Descrição
:---------:|:---------------:|:-------------:
id | string | Id do UsuarioExecutaRota
userId | string | Id do usuário
startedAt | Date (ISO8601) | Início da execução
endedAt | Date (ISO8601) | Fim da execução
systems | array | Ver tabela 1.1.1

##### 1.1.1 - Detalhes do array "systems"

Nome       |  Tipo | Descrição
:---------:|:---------------:|:-------------:
id | string | Id do sistema
startedAt | Date (ISO8601) | Início do sistema
endedAt | Date (ISO8601) | Fim do sistema

#### 1.2 - Detalhes do array "monitoredPoints"

Nome       |  Tipo | Descrição
:---------:|:---------------:|:-------------:
id | string | Id do Ponto Monitorado
userExecRouteId | string | Id do UsuarioExecutaRota
systemId | string | Id do Sistema 
dateTime | Date (ISO8601) | Data e hora da leitura do ponto monitorado
state | int | O estado da leitura do ponto<br/>(0 - Desligado, 1 - OK, 2 - Em manutenção)
