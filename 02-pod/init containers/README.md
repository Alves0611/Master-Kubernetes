# Init Containers no Kubernetes

**Init Containers** são contêineres especiais que são executados antes dos contêineres de aplicação (os contêineres principais) em um Pod. Eles são úteis para preparar o ambiente para a execução dos contêineres principais.

## O que são Init Containers?

- **Execução Sequencial:** Init containers são executados sequencialmente, um após o outro. Cada init container deve completar com sucesso antes que o próximo inicie e antes que qualquer contêiner principal comece.

- **Preparação do Ambiente:** Eles são usados para realizar tarefas de configuração ou inicialização que devem ser concluídas antes que os contêineres principais possam ser executados.

- **Isolamento:** Init containers têm suas próprias imagens e podem usar ferramentas ou utilitários diferentes dos contêineres principais.

## Exemplos de Uso

- **Esperar por Serviços Externos:** Verificar se um serviço externo (como um banco de dados) está disponível antes de iniciar a aplicação principal.
  
- **Configuração Inicial:** Configurar arquivos de configuração ou baixar dependências que a aplicação principal precisa.

- **Checagem de Pré-requisitos:** Garantir que certas condições sejam atendidas antes de iniciar os contêineres principais, como verificar se um volume de armazenamento está montado corretamente.