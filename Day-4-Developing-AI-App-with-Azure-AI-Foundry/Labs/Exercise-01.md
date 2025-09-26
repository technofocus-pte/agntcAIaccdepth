# Ejercicio 1: Comprendiendo el Ciclo de Vida del Desarrollo de Flujos

## Descripción del laboratorio
En este laboratorio, explorarás el ciclo de vida del desarrollo de aplicaciones de IA usando Prompt Flow de Azure AI Foundry. Comenzarás entendiendo el proceso estructurado, incluyendo las etapas de inicialización, experimentación, evaluación, refinamiento y producción. Aprenderás sobre los diferentes tipos de flujos, como Standard, Chat y Evaluation, y cómo se adaptan a diversas necesidades de aplicación. También profundizarás en el concepto de flujos y nodos dentro de Prompt Flow, que permiten un procesamiento de datos y ejecución de tareas sin fricciones.

## Objetivo del laboratorio

En este laboratorio, realizarás lo siguiente:
- Tarea 1: Comprender el ciclo de vida del desarrollo de flujos
  
### Tarea 1: Comprender el ciclo de vida del desarrollo de flujos (SOLO LECTURA)

Prompt Flow ofrece un proceso bien definido que facilita el desarrollo fluido de aplicaciones de IA. Al usarlo, puedes avanzar eficazmente por las etapas de desarrollo, prueba, ajuste y despliegue de flujos, resultando en la creación de aplicaciones de IA completas.

El ciclo de vida consta de las siguientes etapas:

- **Inicialización**: Identifica el caso de negocio, recopila datos de ejemplo, aprende a construir un prompt básico y desarrolla un flujo que extienda sus capacidades.
- **Experimentación**: Ejecuta el flujo con datos de ejemplo, evalúa el desempeño del prompt y repite el flujo si es necesario. Experimenta continuamente hasta estar satisfecho con los resultados.
- **Evaluación y refinamiento**: Evalúa el desempeño del flujo ejecutándolo con un conjunto de datos más grande, evalúa la efectividad del prompt y refina según sea necesario. Avanza a la siguiente etapa si los resultados cumplen con los criterios deseados.
- **Producción**: Optimiza el flujo para eficiencia y efectividad, despliega el flujo, monitorea el desempeño en un entorno productivo y recopila datos de uso y retroalimentación. Usa esta información para mejorar el flujo y contribuir a etapas anteriores para nuevas iteraciones.

  >**Nota**: Siguiendo este enfoque estructurado y metódico, Prompt Flow te permite desarrollar, probar rigurosamente, ajustar y desplegar flujos con confianza, resultando en la creación de aplicaciones de IA robustas y sofisticadas.

### Tarea 1.1: Comprender los tipos de flujos

En esta tarea, explorarás los diferentes tipos de flujos en Azure AI Foundry.
1. Navega a Azure AI Foundry usando el siguiente enlace:
    ```
    https://ai.azure.com/
    ```
1. En Azure AI Foundry, haz clic en `Prompt flow` en el panel izquierdo y luego selecciona `+ Create`. Aquí puedes iniciar un nuevo flujo seleccionando un tipo de flujo o una plantilla de la galería.

- **Standard flow**: Diseñado para el desarrollo general de aplicaciones, el flujo estándar te permite crear un flujo usando una amplia gama de herramientas integradas para desarrollar aplicaciones basadas en LLM. Proporciona flexibilidad y versatilidad para desarrollar aplicaciones en diferentes dominios.
- **Chat flow**: Orientado al desarrollo de aplicaciones conversacionales, el Chat flow amplía las capacidades del flujo estándar y proporciona soporte mejorado para entradas/salidas de chat y gestión del historial de conversaciones. Con el modo de conversación nativo y funciones integradas, puedes desarrollar y depurar aplicaciones en un contexto conversacional.
- **Evaluation flow**: Diseñado para escenarios de evaluación, el Evaluation flow te permite crear un flujo que toma como entrada los resultados de ejecuciones previas. Este tipo de flujo permite evaluar el desempeño de ejecuciones anteriores y generar métricas relevantes, facilitando la evaluación y mejora de modelos o aplicaciones.

  ![](./media/image-48.png)

### Tarea 1.2: Comprender un flujo
En esta tarea, explorarás **Prompt Flow**, una funcionalidad dentro de Azure AI Foundry.

1. Un flujo en Prompt Flow funciona como un flujo de trabajo ejecutable que agiliza el desarrollo de tu aplicación de IA basada en LLM. Proporciona un marco integral para gestionar el flujo y procesamiento de datos dentro de tu aplicación.

1. Prompt Flow es una característica dentro de Azure AI Foundry que te permite crear flujos. Los flujos son flujos de trabajo ejecutables que suelen constar de tres partes:

    - **Inputs**: Representan los datos que se pasan al flujo. Pueden ser de diferentes tipos como cadenas, enteros o booleanos.
    - **Nodes**: Representan herramientas que realizan procesamiento de datos, ejecución de tareas u operaciones algorítmicas.
    - **Outputs**: Representan los datos producidos por el flujo.

      ![](./media/image-49.png)

1. Dentro de un flujo, los nodos son protagonistas, representando herramientas específicas con capacidades únicas. Estos nodos manejan el procesamiento de datos, la ejecución de tareas y operaciones algorítmicas, con entradas y salidas. Al conectar nodos, estableces una cadena de operaciones que guía el flujo de datos a través de tu aplicación.

1. Para facilitar la configuración y ajuste de los nodos, se proporciona una representación visual de la estructura del flujo mediante un grafo DAG (Directed Acyclic Graph). Este grafo muestra la conectividad y dependencias entre nodos, proporcionando una visión clara de todo el flujo de trabajo.

### Tarea 1.3: Explorar las herramientas disponibles en Prompt Flow

En esta tarea, explorarás las herramientas disponibles en Prompt Flow dentro de Azure AI Foundry.

1. Las herramientas son los bloques fundamentales de un flujo.

1. Tres herramientas comunes son:

    - **LLM tool**: Permite la creación de prompts personalizados utilizando Large Language Models.
    - **Python tool**: Permite la ejecución de scripts Python personalizados.
    - **Prompt tool**: Prepara prompts como cadenas para escenarios complejos o integración con otras herramientas.

    ![](./media/image-50.png)
   
1. Cada herramienta es una unidad ejecutable con una función específica. Puedes usar una herramienta para tareas como resumir texto o hacer una llamada a una API. Puedes usar varias herramientas en un flujo y usar una herramienta varias veces.

1. Uno de los principales beneficios de las herramientas de Prompt Flow es su integración fluida con APIs de terceros y paquetes open source de Python. Esto no solo mejora la funcionalidad de los modelos de lenguaje, sino que también hace más eficiente el proceso de desarrollo para los desarrolladores.
   
## Revisión
En este laboratorio completaste las siguientes tareas:
- Comprender el ciclo de vida del desarrollo de flujos

### Has completado exitosamente el laboratorio. Haz clic en **Next >>** para continuar con el siguiente ejercicio.
