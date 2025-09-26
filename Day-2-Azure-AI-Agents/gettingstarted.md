# Laboratorio práctico - Día 2

# Agentes de Azure AI

### Duración estimada total: 4 horas

## Descripción general

Este laboratorio práctico ofrece una introducción completa a la construcción de agentes de IA utilizando el SDK de Azure AI Agent Service. Comenzarás creando agentes de IA con Azure AI Agent Service. A lo largo del laboratorio, explorarás técnicas para la colaboración entre agentes, automatización y ejecución de tareas. Al finalizar esta experiencia, tendrás experiencia práctica en el diseño, despliegue y gestión de agentes de IA para construir aplicaciones inteligentes, escalables y eficientes impulsadas por IA.

## Objetivo

Al finalizar este laboratorio, podrás:

- **Configurar un proyecto de IA y realizar Chat Completion desde VS Code:** Este laboratorio práctico te guiará en la configuración del entorno para construir agentes de IA. Comenzarás configurando un proyecto de IA en Azure AI Foundry, desplegando un modelo de lenguaje grande (LLM) y modelos de embedding. Luego, conectarás Visual Studio Code al proyecto de IA y realizarás una llamada de chat completion para validar la configuración, asegurando una integración y funcionalidad sin problemas.

- **Construir un agente de IA simple:** En este laboratorio práctico, serás introducido a los agentes de IA en Azure y aprenderás a construir un agente de IA simple. Crearás un agente que genera una gráfica de barras comparando planes de beneficios de salud, aprovechando las capacidades de IA para procesar datos y visualizar información de manera efectiva.

- **Desarrollar un sistema multiagente:** En este ejercicio práctico, construirás un sistema multiagente donde cuatro agentes de IA colaboran para generar reportes sobre documentos de planes de salud. Crearás un Search Agent para recuperar información de pólizas desde Azure AI Search, un Report Agent para generar reportes detallados, un Validation Agent para asegurar el cumplimiento de requisitos especificados y un Orchestrator Agent para gestionar la comunicación entre todos los agentes. Este laboratorio te brindará experiencia práctica en el diseño y coordinación de agentes de IA para tareas complejas.

## Prerrequisitos

Los participantes deben tener:

- **Visual Studio Code (VS Code):** Dominio en el uso de Visual Studio Code para programar, depurar y gestionar extensiones para varios lenguajes y frameworks.
- **Habilidades de desarrollo:** Conocimientos básicos de programación en Python o JavaScript, experiencia con APIs, SDKs y trabajo en Visual Studio Code.
- **Conceptos de Azure AI y la nube:** Comprensión de Azure AI Foundry, desarrollo de agentes de IA, despliegue de LLMs y modelos de embedding, y trabajo con Azure AI Search para recuperación basada en vectores.
- **IA y procesamiento de datos:** Conocimiento de prompt engineering, flujos de chat completion, modelos de embedding, generación aumentada por recuperación (RAG) y técnicas de filtrado de contenido.
- **Diseño de sistemas y coordinación multiagente:** Comprensión de arquitecturas de agentes de IA, diseño de agentes de recuperación, validación y orquestación, y coordinación de interacciones multiagente.

## Explicación de componentes

- **Azure AI Foundry:** Plataforma en la nube para desarrollar, desplegar y gestionar modelos de IA. Permite a los usuarios configurar proyectos de IA, desplegar modelos de lenguaje grandes (LLMs) e integrar modelos de embedding para mejorar aplicaciones de IA.
- **Azure AI Hub:** Componente central de Azure AI Foundry, es un recurso de Azure de alto nivel que proporciona un entorno central, seguro y colaborativo para que los equipos construyan, gestionen y desplieguen aplicaciones de IA, ofreciendo acceso a varios servicios de Azure AI con una sola configuración.
- **Azure AI Search:** Servicio de búsqueda basado en vectores que habilita la generación aumentada por recuperación (RAG) mediante la indexación y recuperación de documentos relevantes para mejorar las respuestas generadas por IA.
- **Azure AI Services:** Conjunto de servicios de IA en la nube que permite a desarrolladores y científicos de datos construir aplicaciones inteligentes, ofreciendo APIs y modelos preconstruidos y personalizables para tareas como voz, visión, lenguaje y conocimiento.
- **Azure Key Vault:** Servicio en la nube que almacena y gestiona de forma segura secretos, certificados y claves criptográficas, permitiendo el acceso a usuarios y aplicaciones autorizadas, mejorando la seguridad y reduciendo riesgos de filtración de datos.
- **LLMs y Embeddings:** Comprensión de los modelos de lenguaje grandes (LLMs), sus capacidades y cómo se utilizan los embeddings para similitud de texto, búsqueda y recuperación de conocimiento en aplicaciones de IA.
