# Criando e Gerenciando Containers

## Processo de Criação de um Container

O processo para criar um container envolve três etapas principais:

1. **Dockerfile:** Um arquivo de texto que contém todas as instruções para construir a imagem do container.
2. **Imagem:** O resultado do Dockerfile, que é uma blueprint para o container.
3. **Container:** A instância em execução da imagem.

![alt text](./images/docker.png)

## Considerações para Produção

Quando pensamos em um ambiente de produção, é essencial levar em conta algumas perguntas críticas:

- **E se a aplicação falhar?**
  - Como lidar com falhas e reiniciar automaticamente?
  
- **E se ela precisar escalar?**
  - Quais estratégias de escalabilidade utilizar?
  
- **E se houver múltiplos serviços?**
  - Como orquestrar vários containers e serviços?
  
- **E o Load Balancing?**
  - Como distribuir o tráfego de forma eficiente?
  
- **E se houver dados sensíveis?**
  - Como garantir a segurança e conformidade dos dados?
![alt text](./images/perguntas.png)