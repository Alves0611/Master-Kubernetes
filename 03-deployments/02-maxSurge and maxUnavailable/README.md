# Kubernetes Deployment Configuration

Este README descreve como configurar os parâmetros `maxSurge` e `maxUnavailable` em um Deployment no Kubernetes para gerenciar atualizações contínuas (rolling updates) de forma eficiente.

## Parâmetros de Atualização Contínua

### `maxSurge`

- **Descrição**: O `maxSurge` define o número máximo de pods adicionais que podem ser criados além do número desejado de réplicas durante uma atualização.
- **Exemplo**: Se `maxSurge` estiver definido como `2`, durante uma atualização o Kubernetes pode criar até 2 pods adicionais para garantir a continuidade do serviço.
- **Valores Aceitos**: Um número inteiro ou uma porcentagem. Se for uma porcentagem, é calculada com base no número de réplicas desejadas.

### `maxUnavailable`

- **Descrição**: O `maxUnavailable` define o número máximo de pods que podem estar indisponíveis durante uma atualização.
- **Exemplo**: Se `maxUnavailable` estiver definido como `1`, no máximo 1 pod pode estar indisponível enquanto novos pods são criados.
- **Valores Aceitos**: Um número inteiro ou uma porcentagem. Se for uma porcentagem, é calculada com base no número de réplicas desejadas.