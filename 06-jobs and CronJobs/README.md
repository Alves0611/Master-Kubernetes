# Jobs e CronJobs no Kubernetes

## Introdução

No Kubernetes, **Jobs** e **CronJobs** são recursos utilizados para a execução de tarefas que não precisam ser contínuas, como scripts ou tarefas em segundo plano que são concluídas uma vez ou executadas em intervalos regulares.

## Jobs

Um **Job** no Kubernetes é responsável por garantir que um ou mais pods sejam executados até a conclusão bem-sucedida de uma tarefa específica. Ele é útil para tarefas que precisam ser executadas uma única vez ou até um determinado número de vezes.

### Características dos Jobs:

- **Execução Única**: Um Job pode ser configurado para executar uma única tarefa.
- **Execução em Paralelo**: É possível configurar múltiplas réplicas para que a tarefa seja executada em paralelo em vários pods.
- **Reexecução**: Se um pod falhar, o Job pode ser configurado para tentar executar o trabalho novamente até que ele seja concluído com sucesso.

