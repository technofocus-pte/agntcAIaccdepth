# Laboratorio práctico - Día 3

# Desarrollo de una aplicación RAG personalizada usando Azure AI Foundry y exploración de Semantic Kernel

### Duración estimada total: 4 horas

## Descripción general

En este laboratorio práctico, aprenderás a construir una aplicación personalizada de Recuperación Aumentada de Generación (RAG) utilizando el SDK de Azure AI Foundry. Implementarás un pipeline RAG que indexa y recupera datos relevantes para mejorar las respuestas generadas por IA. Finalmente, evaluarás y optimizarás el rendimiento del sistema midiendo la precisión de recuperación, la calidad de las respuestas y la eficiencia. Al finalizar la sesión, tendrás una solución RAG funcional que integra capacidades de Azure AI para una recuperación de conocimiento y generación de respuestas mejoradas.
Utilizando el **SDK de Azure AI Foundry** junto con **Semantic Kernel**, los participantes crearán interacciones dinámicas basadas en prompts e integrarán **plugins** útiles—como utilidades de tiempo y clima—para extender la funcionalidad del chatbot.
Al final del laboratorio, tendrás experiencia práctica construyendo una solución RAG funcional y escalable que aprovecha las capacidades de Azure AI y el ecosistema de plugins de Semantic Kernel para una recuperación de conocimiento avanzada y generación inteligente de respuestas.

## Objetivo

Al finalizar este laboratorio, podrás:

- **Construir un pipeline RAG**: En este ejercicio práctico, los participantes aprenderán a construir un pipeline de Recuperación Aumentada de Generación (RAG) para mejorar las respuestas generadas por IA. Indexarán fuentes de conocimiento, implementarán un pipeline de recuperación y generarán respuestas enriquecidas con datos relevantes. Además, integrarán registro de telemetría para monitorear y optimizar el rendimiento del sistema.

- **Evaluar y optimizar el rendimiento de RAG**: En este ejercicio práctico, los participantes aprenderán a evaluar y optimizar el rendimiento de un sistema RAG. Utilizarán evaluadores de Azure AI para medir la precisión de recuperación, implementarán métodos de evaluación para medir la calidad de las respuestas e interpretarán los resultados para ajustar la eficiencia del sistema.

- **Fundamentos de Semantic Kernel**: Construir una experiencia de chat inteligente conectando Semantic Kernel con GPT-4o a través de una aplicación inicial sencilla.

- **Plugins de Semantic Kernel**: Ampliar las capacidades del chatbot construyendo e integrando plugins personalizados de Semantic Kernel.
  
## Prerrequisitos

Los participantes deben tener:

- Familiaridad con el portal de Azure AI Foundry.
- Conocimientos básicos de modelos de lenguaje grandes y sus aplicaciones.
- Familiaridad con conceptos de Semantic Kernel como plugins, planners y AI skills.

## Explicación de componentes

- **Azure AI Foundry**: Azure AI Foundry proporciona la infraestructura fundamental, incluyendo modelos de IA, bases de datos vectoriales y recursos necesarios para desplegar y gestionar pipelines de Recuperación Aumentada de Generación (RAG). Esta plataforma permite la creación de aplicaciones de IA que utilizan sistemas de recuperación para mejorar la precisión y relevancia de las respuestas generadas por IA.

- **Azure OpenAI**: Azure OpenAI Service proporciona acceso a través de REST API a los potentes modelos de lenguaje de OpenAI, que se integran con tus datos, permitiendo interacciones personalizadas y seguras.

- **Modelos de Azure OpenAI**: Los modelos de Azure OpenAI ofrecen modelos de lenguaje grandes preentrenados y personalizables para diversas aplicaciones de IA. Estos modelos ayudan a construir soluciones potentes impulsadas por IA generando contenido adaptado y contextualmente relevante a partir de prompts bien diseñados.

- **Azure AI Search**: Azure AI Search, anteriormente conocido como Azure Cognitive Search, es un sistema de recuperación de información empresarial que permite almacenar, indexar y buscar tus datos, habilitando potentes aplicaciones RAG y motores de búsqueda empresariales.

- **Visual Studio Code**: Sirve como entorno de desarrollo para construir la aplicación RAG, integrando mecanismos de recuperación con respuestas generadas por IA.

- **Pipeline de Recuperación Aumentada de Generación (RAG)**: Un pipeline RAG mejora las respuestas generadas por IA integrando conocimiento externo en el proceso de generación. Implica recuperar información pertinente de una base de datos vectorial según las consultas del usuario, que luego se utiliza para enriquecer las respuestas de la IA, logrando resultados más precisos y contextualmente relevantes.

- **Evaluación y monitoreo (Azure AI Foundry)**: Rastrea el rendimiento del modelo, la precisión de recuperación y la calidad de las respuestas, permitiendo la optimización y depuración continua.

- **Semantic Kernel**: Un framework de orquestación de IA que conecta **LLMs, plugins y APIs** para capacidades de IA mejoradas.
- **Python SDKs y REST APIs**: Utilizados para interactuar con **Azure AI Foundry, Semantic Kernel y servicios de OpenAI**.
