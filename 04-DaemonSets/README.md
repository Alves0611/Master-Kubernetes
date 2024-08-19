# DaemonSets no Kubernetes

Um **DaemonSet** é um objeto no Kubernetes que garante que uma cópia de um pod específico esteja rodando em cada nó do cluster. Isso é particularmente útil para tarefas que precisam ser executadas em todos os nós, como monitoramento, coleta de logs ou execução de agentes de rede.

![alt text](../images/daemonSet.png)

## Funcionamento Básico

- Quando um DaemonSet é criado, o Kubernetes garante que um pod correspondente seja agendado em todos os nós disponíveis.
- Se um novo nó for adicionado ao cluster, o DaemonSet automaticamente agendará um pod nesse nó.
- Se um nó for removido, os pods do DaemonSet naquele nó são excluídos automaticamente.

## Uso Comum

- **Monitoramento:** Ferramentas como Prometheus Node Exporter ou Datadog Agent são implantadas usando DaemonSets para coletar métricas de todos os nós.
- **Coleta de Logs:** Soluções como Fluentd ou Logstash são implantadas como DaemonSets para coletar logs em todos os nós.
- **Networking:** DaemonSets podem ser usados para executar componentes de rede, como agentes CNI (Container Network Interface), em todos os nós.

## Recursos e Configurações

- **PodTemplate:** O DaemonSet inclui um template de pod que define qual contêiner deve ser executado em cada nó. Esse template é semelhante ao que você usaria em um Deployment ou um ReplicaSet.
- **Selectors:** Assim como outros controladores, o DaemonSet usa seletores para identificar quais pods são gerenciados por ele.
- **Tolerations e NodeSelectors:** Para limitar os nós onde os DaemonSets devem ser executados, você pode usar tolerations e nodeSelectors. Isso permite, por exemplo, que você execute o DaemonSet apenas em nós específicos ou tolere certos tipos de "taints" nos nós.

## Cenários de Atualização

O Kubernetes permite a atualização dos DaemonSets de forma controlada. Por padrão, um DaemonSet não atualizará automaticamente seus pods, a menos que a política de atualização seja configurada. Isso garante que novas versões dos pods sejam aplicadas de forma segura, minimizando a interrupção.

## Diferenças em Relação a Outros Controladores

- **Deployment/ReplicaSet:** Enquanto um Deployment ou ReplicaSet cria múltiplas réplicas de um pod em nós diferentes, um DaemonSet garante exatamente um pod por nó.
- **StatefulSet:** DaemonSets não garantem ordenação ou persistência de dados como os StatefulSets. Eles focam em garantir a execução uniforme de pods em todos os nós.

## Conclusão

DaemonSets são uma ferramenta poderosa no Kubernetes para garantir que determinados tipos de serviços ou aplicações sejam executados em todos os nós do cluster, garantindo cobertura completa de monitoramento, coleta de logs ou outras tarefas de manutenção em todo o ambiente Kubernetes.
