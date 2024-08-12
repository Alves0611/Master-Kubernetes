# Static Pods no Kubernetes

**Static Pods** são Pods que são gerenciados diretamente pelo kubelet em um nó específico, em vez de serem gerenciados pelo servidor de API do Kubernetes. Eles são usados principalmente para componentes críticos do sistema que precisam ser executados em nós específicos.



## Características dos Static Pods

- **Gerenciamento pelo Kubelet:** Static Pods são definidos diretamente no sistema de arquivos do nó onde o kubelet está executando. O kubelet detecta e gerencia esses Pods automaticamente.
  
- **Independência do API Server:** Static Pods não são criados via API Server do Kubernetes, o que significa que eles não aparecem na lista de Pods do cluster até que o kubelet os registre.

- **Arquivos de Configuração:** Eles são definidos por arquivos de configuração YAML ou JSON localizados em um diretório específico no nó (geralmente `/etc/kubernetes/manifests`).

- **Não Atualizáveis Diretamente:** Para atualizar um Static Pod, você deve modificar o arquivo de configuração no sistema de arquivos do nó. O kubelet detectará a mudança e recriará o Pod.

## Conclusão 

Static Pods são úteis para garantir que componentes críticos do sistema estejam sempre em execução em nós específicos, independentemente do estado do API Server. Eles são gerenciados diretamente pelo kubelet, o que oferece uma camada extra de resiliência para partes vitais do cluster Kubernetes.