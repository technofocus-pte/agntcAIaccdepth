Claro! Aqui está a tradução para português brasileiro do texto que você enviou:
# Exercício 1: Entendendo o Ciclo de Vida do Desenvolvimento de Flows

## Visão Geral do Laboratório

Neste laboratório, você irá explorar o ciclo de vida do desenvolvimento de aplicações de IA usando o Prompt Flow do Azure AI Foundry. Você começará entendendo o processo estruturado, que inclui as fases de inicialização, experimentação, avaliação, refinamento e produção. Aprenderá sobre os diferentes tipos de flows, como Standard, Chat e Evaluation flows, e como eles atendem a diversas necessidades de aplicação. Também vai se aprofundar no conceito de flows e nodes dentro do Prompt Flow, que permitem o processamento contínuo de dados e a execução de tarefas.

## Objetivo do Laboratório

Neste laboratório, você realizará o seguinte:

- Tarefa 1: Compreender o Ciclo de Vida do Desenvolvimento de Flows

### Tarefa 1: Compreender o Ciclo de Vida do Desenvolvimento de Flows (APENAS LEITURA)

O Prompt Flow oferece um processo bem definido que facilita o desenvolvimento fluido de aplicações de IA. Ao utilizá-lo, você pode avançar efetivamente pelas etapas de desenvolvimento, teste, ajuste e implantação de flows, resultando na criação de aplicações de IA completas.

O ciclo de vida consiste nas seguintes etapas:

- **Inicialização**: Identificar o caso de uso de negócio, coletar dados de exemplo, aprender a construir um prompt básico e desenvolver um flow que expanda suas capacidades.
- **Experimentação**: Executar o flow com dados de exemplo, avaliar o desempenho do prompt e iterar no flow, se necessário. Continuar experimentando até ficar satisfeito com os resultados.
- **Avaliação e refinamento**: Avaliar o desempenho do flow com um conjunto maior de dados, analisar a eficácia do prompt e refinar conforme necessário. Avançar para a próxima etapa se os resultados atenderem aos critérios desejados.
- **Produção**: Otimizar o flow para eficiência e eficácia, implantá-lo, monitorar o desempenho em ambiente de produção e coletar dados de uso e feedback. Utilizar essas informações para melhorar o flow e contribuir para as etapas anteriores para futuras iterações.

> **Nota**: Ao seguir essa abordagem estruturada e metódica, o Prompt Flow permite que você desenvolva, teste rigorosamente, ajuste e implante flows com confiança, resultando na criação de aplicações de IA robustas e sofisticadas.

### Tarefa 1.1: Entender os tipos de flows

Nesta tarefa, você irá explorar os diferentes tipos de flows no Azure AI Foundry:

1. Acesse o Azure AI Foundry pelo link abaixo:

   ```
   https://ai.azure.com/
   ```
2. No Azure AI Foundry, clique em `Prompt flow` no painel à esquerda e depois selecione `+ Criar`. Aqui você pode iniciar um novo flow escolhendo um tipo de flow ou um modelo da galeria.

- **Flow padrão (Standard flow)**: Projetado para desenvolvimento geral de aplicações, o flow padrão permite criar um flow usando uma ampla gama de ferramentas integradas para desenvolver aplicações baseadas em LLM. Oferece flexibilidade e versatilidade para aplicações em diferentes domínios.
- **Flow de chat (Chat flow)**: Voltado para desenvolvimento de aplicações conversacionais, o flow de chat amplia as capacidades do flow padrão e oferece suporte aprimorado para entradas/saídas de chat e gerenciamento de histórico. Com modo de conversa nativo e recursos integrados, você pode desenvolver e depurar aplicações dentro de um contexto conversacional.
- **Flow de avaliação (Evaluation flow)**: Projetado para cenários de avaliação, o flow de avaliação permite criar um flow que utiliza as saídas de execuções anteriores como entradas. Esse tipo de flow possibilita avaliar o desempenho dos resultados anteriores e gerar métricas relevantes, facilitando a análise e melhoria dos modelos ou aplicações.

  ![](../../pt-media/day-4/02.png)

### Tarefa 1.2: Entender um flow

Nesta tarefa, você irá explorar o **Prompt flow**, um recurso dentro do Azure AI Foundry.

1. Um flow no Prompt flow funciona como um workflow executável que simplifica o desenvolvimento da sua aplicação de IA baseada em LLM. Ele fornece uma estrutura completa para gerenciar o fluxo de dados e o processamento dentro da aplicação.

2. O Prompt flow é um recurso dentro do Azure AI Foundry que permite a criação de flows. Os flows são workflows executáveis que geralmente consistem em três partes:

   - **Entradas (Inputs)**: Representam dados que entram no flow. Podem ser diferentes tipos de dados como strings, números inteiros ou booleanos.
   - **Nós (Nodes)**: Representam ferramentas que realizam processamento de dados, execução de tarefas ou operações algorítmicas.
   - **Saídas (Outputs)**: Representam os dados produzidos pelo flow.

     ![](../../pt-media/day-4/ex-4/prompt.png)

3. Dentro de um flow, os nodes são essenciais, representando ferramentas específicas com capacidades únicas. Esses nodes lidam com processamento de dados, execução de tarefas e operações algorítmicas, com suas entradas e saídas. Conectando os nodes, você cria uma cadeia contínua de operações que orienta o fluxo de dados pela aplicação.

4. Para facilitar a configuração e ajuste dos nodes, é fornecida uma representação visual da estrutura do workflow por meio de um gráfico DAG (Grafo Acíclico Dirigido). Esse gráfico mostra as conexões e dependências entre os nodes, oferecendo uma visão clara do fluxo completo.

### Tarefa 1.3: Explorar as ferramentas disponíveis no Prompt Flow

Nesta tarefa, você vai explorar as ferramentas disponíveis no Prompt Flow dentro do Azure AI Foundry.

1. As ferramentas são os blocos fundamentais de construção de um flow.

2. Três ferramentas comuns são:

   - **Ferramenta LLM**: Permite criar prompts personalizados usando Large Language Models.
   - **Ferramenta Python**: Permite executar scripts Python personalizados.
   - **Ferramenta Prompt**: Prepara prompts em forma de strings para cenários complexos ou integração com outras ferramentas.

   ![](../../pt-media/day-4/19.png)

3. Cada ferramenta é uma unidade executável com uma função específica. Você pode usar uma ferramenta para realizar tarefas como resumir textos ou fazer chamadas a APIs. É possível usar várias ferramentas dentro de um flow e reutilizar a mesma ferramenta diversas vezes.

4. Um dos principais benefícios das ferramentas do Prompt Flow é a integração fácil com APIs de terceiros e pacotes Python open source. Isso não só melhora a funcionalidade dos grandes modelos de linguagem como também torna o processo de desenvolvimento mais eficiente para os desenvolvedores.

## Revisão

Neste laboratório, você completou as seguintes tarefas:

- Compreendeu o Ciclo de Vida do Desenvolvimento de Flows

### Você concluiu o laboratório com sucesso. Clique em **Próximo >>** para continuar para o próximo exercício.
