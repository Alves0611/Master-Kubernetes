# Probes no Kubernetes

![alt text](../../images/probles.png)
![alt text](../../images/probles1.png)

Os probes no Kubernetes são mecanismos de verificação de saúde utilizados para monitorar o estado dos containers em execução. Eles garantem que os containers estejam funcionando corretamente e, se necessário, tomam ações como reiniciar o container ou removê-lo temporariamente do serviço. Existem três tipos principais de probes: **liveness probe**, **readiness probe** e **startup probe**.

## Tipos de Probes

### 1. Liveness Probe
A **liveness probe** é usada para verificar se um container está "vivo" ou saudável. Se o container falhar nessa verificação, o Kubernetes reiniciará o container automaticamente. Esse tipo de probe é útil para detectar situações em que o container entrou em um estado irrecuperável, onde o reinício é a única solução.

### 2. Readiness Probe
A **readiness probe** verifica se um container está pronto para receber tráfego. Embora a liveness probe garanta que o container esteja vivo, a readiness probe garante que ele esteja pronto para aceitar conexões. Se a readiness probe falhar, o container será temporariamente removido do serviço de balanceamento de carga até que esteja pronto novamente.

### 3. Startup Probe
A **startup probe** é usada para verificar se um container conseguiu iniciar corretamente. Esse tipo de probe é especialmente útil para containers que possuem um tempo de inicialização mais longo, evitando que liveness probes normais falhem antes que o container esteja completamente pronto. A startup probe informa ao Kubernetes que o container ainda está em processo de inicialização e não deve ser reiniciado prematuramente.
