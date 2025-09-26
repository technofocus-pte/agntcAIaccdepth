# Laboratórios Práticos - Dia 2

# Agentes de IA no Azure

### Duração Estimada Total: 4 Horas

## Visão Geral

Este laboratório prático oferece uma introdução abrangente à criação de agentes de IA utilizando o SDK do Azure AI Agent Service. Você começará criando agentes de IA com o serviço Azure AI Agent. Ao longo do laboratório, explorará técnicas de colaboração entre agentes, automação e execução de tarefas. Ao final da experiência, você terá adquirido experiência prática em projetar, implantar e gerenciar agentes de IA para construir aplicações inteligentes, escaláveis e eficientes baseadas em IA.

## Objetivo

Ao final deste laboratório, você será capaz de:

- **Configurar o Projeto de IA e Realizar uma Conclusão de Chat a partir do VS Code:** Este laboratório guiará você na configuração do ambiente para construção de agentes de IA. Você começará configurando um Projeto de IA no Azure AI Foundry, implantando um Modelo de Linguagem Extensa (LLM) e modelos de embedding. Em seguida, conectará o Visual Studio Code ao Projeto de IA e fará uma chamada de conclusão de chat para validar a configuração, garantindo integração e funcionalidade sem falhas.

- **Construir um Agente de IA Simples:** Neste laboratório prático, você será apresentado aos Agentes de IA no Azure e aprenderá a construir um agente de IA simples. Você criará um agente que gera um gráfico de barras comparando planos de benefícios de saúde, aproveitando as capacidades da IA para processar dados e visualizar insights de forma eficaz.

- **Desenvolver um Sistema Multiagente:** Neste exercício prático, você construirá um sistema multiagente no qual quatro agentes de IA colaboram para gerar relatórios sobre documentos de planos de saúde. Você criará um Agente de Busca para recuperar informações de políticas no Azure AI Search, um Agente de Relatório para gerar relatórios detalhados, um Agente de Validação para garantir conformidade com os requisitos especificados, e um Agente Orquestrador para gerenciar a comunicação entre todos os agentes. Este laboratório proporcionará uma experiência prática no design e coordenação de agentes de IA para tarefas complexas.

## Pré-requisitos

Os participantes devem ter:

- **Visual Studio Code (VS Code):** Proficiência no uso do Visual Studio Code para codificação, depuração e gerenciamento de extensões para diversas linguagens e frameworks.
- **Habilidades de Desenvolvimento:** Conhecimento básico de programação em Python ou JavaScript, experiência com APIs, SDKs e uso do Visual Studio Code.
- **Conceitos de IA no Azure e em Nuvem:** Compreensão do Azure AI Foundry, desenvolvimento de Agentes de IA, implantação de LLMs e modelos de embedding, e uso do Azure AI Search para recuperação baseada em vetores.
- **IA e Processamento de Dados:** Conhecimento em engenharia de prompts, fluxos de trabalho de conclusão de chat, modelos de embedding, geração aumentada por recuperação (RAG) e técnicas de filtragem de conteúdo.
- **Design de Sistemas e Coordenação Multiagente:** Compreensão de arquiteturas de agentes de IA, design de agentes de recuperação, validação e orquestração, e coordenação de interações entre múltiplos agentes.

## Explicação dos Componentes

- **Azure AI Foundry:** Plataforma baseada em nuvem para desenvolvimento, implantação e gerenciamento de modelos de IA. Permite configurar projetos de IA, implantar Modelos de Linguagem Extensa (LLMs) e integrar modelos de embedding para aprimorar aplicações de IA.
- **Azure AI Hub:** Um componente central do Azure AI Foundry. É um recurso de alto nível no Azure que oferece um ambiente centralizado, seguro e colaborativo para equipes construírem, gerenciarem e implantarem aplicações de IA, com acesso a diversos serviços de IA do Azure com uma única configuração.
- **Azure AI Search:** Serviço de busca baseado em vetores que permite Geração Aumentada por Recuperação (RAG), indexando e recuperando documentos relevantes para melhorar as respostas geradas por IA.
- **Serviços de IA do Azure:** Conjunto de serviços de IA baseados em nuvem que permitem a desenvolvedores e cientistas de dados criarem aplicações inteligentes, oferecendo APIs e modelos pré-configurados e personalizáveis para tarefas como fala, visão, linguagem e conhecimento.
- **Azure Key Vault:** Serviço de nuvem que armazena e gerencia com segurança segredos, certificados e chaves criptográficas, permitindo acesso apenas a usuários e aplicações autorizadas, aumentando a segurança e reduzindo riscos de vazamento de dados.
- **LLMs e Embeddings:** Compreensão dos Modelos de Linguagem Extensa (LLMs), suas capacidades e como os embeddings são usados para similaridade de texto, busca e recuperação de conhecimento em aplicações de IA.