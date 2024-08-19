# StatefulSets no Kubernetes

**StatefulSets** são um tipo de controlador no Kubernetes usado para gerenciar e implantar conjuntos de pods que exigem identificação estável e armazenamento persistente. Eles são particularmente úteis para aplicativos que precisam manter um estado ou precisam de uma ordem específica na criação, exclusão e escalabilidade dos pods, como bancos de dados ou sistemas distribuídos.

## Características Principais do StatefulSet

1. **Identidade Estável:**
   - Cada pod gerenciado por um StatefulSet recebe um identificador único e persistente. Esses identificadores são mantidos mesmo quando os pods são reiniciados ou substituídos.
   - O nome dos pods segue o padrão `<nome-do-statefulset>-<índice>`, onde `<índice>` é um número que reflete a ordem de criação dos pods.

2. **Persistência:**
   - StatefulSets são usados em conjunto com Persistent Volume Claims (PVCs) para fornecer armazenamento persistente aos pods. Cada pod tem seu próprio PVC, garantindo que o armazenamento associado a um pod não seja compartilhado com outros pods.
   - Mesmo que um pod seja movido para outro nó ou reiniciado, ele manterá o acesso ao mesmo volume persistente.

3. **Ordem de Implementação e Destruição:**
   - Os pods em um StatefulSet são criados e destruídos em uma ordem predefinida (sequencial). Por exemplo, o pod com índice `0` será criado antes do pod com índice `1`.
   - Da mesma forma, ao escalar para baixo, o Kubernetes destruirá os pods na ordem inversa (do mais alto para o mais baixo).

4. **Ordens de Atualização:**
   - StatefulSets garantem que a atualização dos pods ocorra de maneira controlada, um por vez, na ordem correta, garantindo que a aplicação mantenha sua integridade durante o processo de atualização.


