# Multi-Container Pods no Kubernetes

Um **Multi-Container Pod** no Kubernetes é um Pod que contém mais de um contêiner. Esses contêineres compartilham o mesmo contexto de execução e recursos, como rede e armazenamento, e são projetados para trabalhar juntos de maneira próxima.

## Características dos Multi-Container Pods

- **Compartilhamento de Recursos:** Todos os contêineres dentro de um Pod compartilham o mesmo endereço IP, namespace de rede e volumes montados. Isso permite que eles se comuniquem facilmente entre si usando localhost.

- **Cooperação Estrita:** Multi-container Pods são usados quando os contêineres precisam cooperar estreitamente para fornecer uma funcionalidade completa. Eles são executados no mesmo nó e compartilham recursos como CPU e memória.

- **Design Patterns:** Existem vários padrões de design para multi-container Pods, incluindo Sidecar, Ambassador e Adapter, cada um com seu propósito específico.