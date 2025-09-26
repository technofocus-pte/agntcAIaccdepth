# Ejercicio 2: Construye un agente de IA simple

## Tiempo estimado: 30 minutos
## Escenario del laboratorio
Los agentes de IA están diseñados para automatizar tareas y generar información basada en la entrada del usuario. En este laboratorio, aprenderás a construir un agente de IA simple que procese datos y genere una gráfica de barras comparando diferentes planes de beneficios de salud. Este agente de IA aprovecha los servicios de Azure AI para analizar y visualizar datos de manera eficiente.

## Objetivo del laboratorio
En este laboratorio, completarás las siguientes tareas:

- Tarea 1: Crear un agente de IA simple

## Tarea 1: Crear un agente de IA simple

En esta tarea, construirás un agente de IA simple que procese datos y genere una gráfica de barras comparando diferentes planes de beneficios de salud utilizando los servicios de Azure AI para el análisis y la visualización.

1. Abre el archivo **Lab 2 - Create A Simple AI Agent.ipynb**. Este notebook te guiará para construir un agente de IA simple que procese datos y genere una gráfica de barras comparando diferentes planes de beneficios de salud.

   ![](./media/ag62.png)

1. Selecciona la opción **Select kernel** disponible en la esquina superior derecha. Selecciona **venv (Python)** de la lista.

   ![](./media/lab1-24.png)

1. Ejecuta la siguiente celda para importar las librerías necesarias y cargar las variables de entorno para trabajar con proyectos de Azure AI. Esta configuración permite la autenticación segura y la interacción con los servicios de Azure AI.

   ![](./media/ag63.png)

1. Ejecuta la siguiente celda para conectarte a tu proyecto de Azure AI Foundry y acceder al modelo **GPT-4o** desplegado. Esto establece una conexión segura usando la cadena de conexión del proyecto y las credenciales de Azure.

   ![](./media/ag64.png)

1. Ejecuta esta celda para crear un **agente de IA simple** que procese datos y genere una gráfica de barras comparando diferentes planes de beneficios de salud usando Azure AI Foundry. Este script inicializa el agente de IA, envía un prompt con los datos de los planes de salud y solicita una gráfica de barras. El agente procesa la solicitud, genera la gráfica, guarda el archivo de imagen y luego elimina el agente.

   ![](./media/ag90.png)

1. Finalmente, observa el resultado.

   ![](./media/lab2-26.png)

## Revisión

En este laboratorio, lograste lo siguiente:
- Crear un agente de IA simple

### Has completado exitosamente el laboratorio. Haz clic en **Next** para continuar con el siguiente laboratorio.
