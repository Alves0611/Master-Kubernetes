# Init Containers no Kubernetes

**Init Containers** são contêineres especiais que são executados antes dos contêineres de aplicação (os contêineres principais) em um Pod. Eles são úteis para preparar o ambiente para a execução dos contêineres principais.

## O que são Init Containers?

- **Execução Sequencial:** Init containers são executados sequencialmente, um após o outro. Cada init container deve completar com sucesso antes que o próximo inicie e antes que qualquer contêiner principal comece.

- **Preparação do Ambiente:** Eles são usados para realizar tarefas de configuração ou inicialização que devem ser concluídas antes que os contêineres principais possam ser executados.

- **Isolamento:** Init containers têm suas próprias imagens e podem usar ferramentas ou utilitários diferentes dos contêineres principais.

