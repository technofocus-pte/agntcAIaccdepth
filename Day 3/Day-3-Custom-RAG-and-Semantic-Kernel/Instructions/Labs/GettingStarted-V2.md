# Hands-on Labs - Day 3

# Developing a Custom RAG App Using Azure AI Foundry and Explore Semantic Kernel

### Overall Estimated Duration: 4 Hours

## Overview

In this hands-on lab, you will learn how to build a custom Retrieval-Augmented Generation (RAG) application using the Azure AI Foundry SDK. You will implement an RAG pipeline that indexes and retrieves relevant data to enhance AI-generated responses. Finally, you will evaluate and optimize the system’s performance by measuring retrieval accuracy, response quality, and efficiency. By the end of the session, you will have a functional RAG solution that integrates Azure AI capabilities for enhanced knowledge retrieval and response generation.
Using the **Azure AI Foundry SDK** in conjunction with **Semantic Kernel**, participants will create dynamic, prompt-based interactions and integrate useful **plugins**—such as time and weather utilities—to extend chatbot functionality.
By the end of the lab, you will have hands-on experience building a functional, scalable RAG solution that leverages Azure AI capabilities and the plugin ecosystem of Semantic Kernel for enhanced knowledge retrieval and intelligent response generation.

## Objective

By the end of this lab, you will be able to:

- **Building a RAG pipeline**: In this hands-on exercise, participants will gain insights about building a Retrieval-Augmented Generation (RAG) pipeline to enhance AI-generated responses. They will index knowledge sources, implement a retrieval pipeline, and generate responses enriched with relevant data. Additionally, they will integrate telemetry logging to monitor and optimize system performance.

- **Evaluate and Optimize RAG Performance**: In this hands-on exercise, participants will gain insights about evaluating and optimizing the performance of a Retrieval-Augmented Generation (RAG) system. They will use Azure AI evaluators to assess retrieval accuracy, implement evaluation methods to measure response quality, and interpret results to fine-tune the system’s efficiency.

- **Semantic Kernel Fundamentals**: Build an intelligent chat experience by connecting Semantic Kernel with GPT-4o through a simple starter app.

- **Semantic Kernel Plugins**: Extend your chatbot’s capabilities by building and integrating custom Semantic Kernel plugins.
  
## Prerequisites

Participants should have:

- Familiarity with the Azure AI Foundry portal.
- Basic understanding of large language models and their applications.
- Familiarity with Semantic Kernel concepts such as plugins, planners, and AI skills

## Explanation of Components

- **Azure AI Foundry**: Azure AI Foundry provides the foundational infrastructure, including AI models, vector databases, and necessary resources for deploying and managing Retrieval-Augmented Generation (RAG) pipelines. This platform enables the creation of AI applications that utilize retrieval systems to enhance the accuracy and relevance of AI-generated responses.

- **Azure OpenAI**: Azure OpenAI Service provides REST API access to OpenAI's powerful language models, which integrate with your data, enabling customized and secure interactions.

- **Azure OpenAI Models**: Azure OpenAI Models offer pre-trained and customizable large language models for various AI applications. These models help build powerful AI-driven solutions by generating tailored and contextually relevant content based on well-crafted prompts.

- **Azure AI Search**: Azure AI Search, formerly known as Azure Cognitive Search, is an enterprise-ready information retrieval system that allows you to store, index, and search your data, enabling powerful retrieval-augmented generation (RAG) applications and enterprise search engines. 

- **Visual Studio Code**: Serves as the development environment for building the RAG application, integrating retrieval mechanisms with AI-generated responses.

- **Retrieval-Augmented Generation (RAG) Pipeline**: A Retrieval-Augmented Generation (RAG) pipeline enhances AI-generated responses by integrating external knowledge into the generation process. It involves retrieving pertinent information from a vector database based on user queries, which is then used to augment the AI's responses, leading to more accurate and contextually relevant outputs. 

- **Evaluation & Monitoring (Azure AI Foundry)**: Tracks model performance, retrieval accuracy, and response quality, enabling continuous optimization and debugging.

- **Semantic Kernel**: An AI orchestration framework that connects **LLMs, plugins, and APIs** for enhanced AI capabilities.
  
- **Python SDKs & REST APIs**: Used to interact with **Azure AI Foundry, Semantic Kernel, and OpenAI services**.
