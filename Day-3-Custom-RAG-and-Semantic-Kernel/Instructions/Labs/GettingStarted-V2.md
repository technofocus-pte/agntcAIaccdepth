# Laboratórios Práticos - Dia 3

# Desenvolvendo um Aplicativo Customizado RAG Usando Azure AI Foundry e Semantic Kernel

### Duração Estimada Total: 4 Horas

## Visão Geral

Neste laboratório prático, você aprenderá a construir um aplicativo customizado de Retrieval-Augmented Generation (RAG) usando o SDK do Azure AI Foundry. Você implementará um pipeline RAG que indexa e recupera dados relevantes para aprimorar as respostas geradas pela IA. Por fim, você avaliará e otimizará o desempenho do sistema medindo a precisão da recuperação, a qualidade da resposta e a eficiência. Ao final da sessão, você terá uma solução RAG funcional que integra as capacidades do Azure AI para um aprimoramento na recuperação de conhecimento e geração de respostas.

Usando o **SDK do Azure AI Foundry** em conjunto com o **Semantic Kernel**, os participantes criarão interações dinâmicas baseadas em prompts e integrarão **plugins** úteis — como utilitários de tempo e clima — para estender a funcionalidade do chatbot.

Ao término do laboratório, você terá experiência prática em construir uma solução RAG funcional e escalável que aproveita as capacidades do Azure AI e o ecossistema de plugins do Semantic Kernel para aprimorar a recuperação de conhecimento e a geração inteligente de respostas.

## Objetivo

Ao final deste laboratório, você será capaz de:

- **Construir um pipeline RAG**: Neste exercício prático, os participantes aprenderão como construir um pipeline Retrieval-Augmented Generation (RAG) para aprimorar respostas geradas por IA. Eles irão indexar fontes de conhecimento, implementar um pipeline de recuperação e gerar respostas enriquecidas com dados relevantes. Além disso, integrarão telemetria para monitorar e otimizar o desempenho do sistema.

- **Avaliar e Otimizar o Desempenho do RAG**: Neste exercício prático, os participantes aprenderão como avaliar e otimizar o desempenho de um sistema Retrieval-Augmented Generation (RAG). Usarão avaliadores do Azure AI para medir a precisão da recuperação, implementar métodos para avaliar a qualidade das respostas e interpretar resultados para ajustar a eficiência do sistema.

- **Fundamentos do Semantic Kernel**: Construir uma experiência de chat inteligente conectando o Semantic Kernel com o GPT-4o através de um aplicativo inicial simples.

- **Plugins do Semantic Kernel**: Estender as capacidades do seu chatbot construindo e integrando plugins customizados do Semantic Kernel.

## Pré-requisitos

Os participantes devem possuir:

- Familiaridade com o portal Azure AI Foundry.
- Entendimento básico sobre grandes modelos de linguagem e suas aplicações.
- Familiaridade com conceitos do Semantic Kernel, como plugins, planners e AI skills.

## Explicação dos Componentes

- **Azure AI Foundry**: O Azure AI Foundry fornece a infraestrutura fundamental, incluindo modelos de IA, bancos de dados vetoriais e recursos necessários para implantar e gerenciar pipelines Retrieval-Augmented Generation (RAG). Esta plataforma permite a criação de aplicações de IA que utilizam sistemas de recuperação para aumentar a precisão e relevância das respostas geradas pela IA.

- **Azure OpenAI**: O serviço Azure OpenAI fornece acesso via API REST aos poderosos modelos de linguagem da OpenAI, que se integram aos seus dados, permitindo interações personalizadas e seguras.

- **Modelos Azure OpenAI**: Oferecem modelos de linguagem grandes pré-treinados e customizáveis para diversas aplicações de IA. Esses modelos ajudam a construir soluções poderosas orientadas por IA, gerando conteúdos personalizados e contextualmente relevantes a partir de prompts bem elaborados.

- **Azure AI Search**: Antes conhecido como Azure Cognitive Search, é um sistema corporativo de recuperação de informações que permite armazenar, indexar e pesquisar seus dados, viabilizando aplicações poderosas de geração aumentada por recuperação (RAG) e motores de busca empresariais.

- **Visual Studio Code**: Serve como ambiente de desenvolvimento para construir a aplicação RAG, integrando mecanismos de recuperação com respostas geradas por IA.

- **Pipeline Retrieval-Augmented Generation (RAG)**: Um pipeline RAG aprimora respostas geradas por IA integrando conhecimento externo no processo de geração. Ele recupera informações pertinentes de um banco de dados vetorial com base nas consultas do usuário, que são usadas para enriquecer as respostas da IA, resultando em saídas mais precisas e contextualmente relevantes.

- **Avaliação & Monitoramento (Azure AI Foundry)**: Rastreia desempenho do modelo, precisão da recuperação e qualidade das respostas, possibilitando otimização contínua e depuração.

- **Semantic Kernel**: Uma estrutura de orquestração de IA que conecta **LLMs, plugins e APIs** para ampliar as capacidades da IA.

- **SDKs Python & APIs REST**: Usados para interagir com **Azure AI Foundry, Semantic Kernel e serviços OpenAI**.
