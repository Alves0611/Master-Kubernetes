# PodDisruptionBudget (PDB) no Kubernetes

## Introdução

O **PodDisruptionBudget (PDB)** é um recurso fundamental no Kubernetes que ajuda a garantir a disponibilidade de aplicativos durante operações de manutenção, como atualizações de nós, escalonamento ou outras atividades que possam causar interrupções nos pods. Ele protege os pods contra interrupções involuntárias, assegurando que um número mínimo ou uma porcentagem de pods permaneça disponível enquanto outros são interrompidos.

## Funcionamento do PodDisruptionBudget

O PDB define restrições que limitam a quantidade de interrupções simultâneas em um grupo de pods. Essas restrições são definidas com base em dois parâmetros principais:

- **minAvailable**: Define o número mínimo de pods que devem estar disponíveis a qualquer momento. Se o número de pods disponíveis cair abaixo deste limite, novas interrupções não serão permitidas até que o número de pods disponíveis seja restaurado.

- **maxUnavailable**: Define o número máximo de pods que podem estar indisponíveis ao mesmo tempo. Se o número de pods indisponíveis atingir este valor, novas interrupções serão bloqueadas até que mais pods fiquem disponíveis.

## Exemplos de Uso

1. **Manutenção Planejada**: Em cenários onde é necessário garantir que pelo menos dois pods de um aplicativo estejam funcionando o tempo todo, um PDB pode ser configurado para garantir que, durante operações de manutenção, nunca mais do que um pod seja interrompido simultaneamente.

2. **Escalonamento de Nós**: Durante o processo de escalonamento de nós (quando nós são removidos ou desligados), o PDB garante que as interrupções sejam limitadas, mantendo o serviço disponível conforme os critérios estabelecidos.


## Considerações Importantes

- O PDB se aplica exclusivamente a interrupções voluntárias, como atualizações planejadas e escalonamento de nós. Ele não afeta interrupções involuntárias, como falhas de hardware ou problemas de rede.
- Configurar um PDB de forma excessivamente restritiva (por exemplo, exigindo que 100% dos pods estejam sempre disponíveis) pode dificultar operações de manutenção no cluster, uma vez que impede que qualquer pod seja interrompido.
- Em clusters grandes, onde há muitos nós e pods, uma configuração correta do PDB é essencial para equilibrar a necessidade de manutenção com a continuidade dos serviços.

## Conclusão

O PodDisruptionBudget é uma ferramenta essencial no Kubernetes para garantir a alta disponibilidade dos serviços, permitindo operações de manutenção necessárias sem comprometer a disponibilidade dos aplicativos. Ao utilizar PDBs, é possível assegurar que seus aplicativos permaneçam resilientes e disponíveis, mesmo durante atualizações e outras operações que envolvem interrupções nos pods.
