# Ejercicio 2: Construcción y Personalización de Prompt Flows

## Descripción del laboratorio

En este laboratorio, obtendrás experiencia práctica inicializando un proyecto de Prompt Flow en Azure AI Foundry, configurando el entorno necesario para comenzar a desarrollar, probar y refinar aplicaciones de IA. Crearás y personalizarás prompts dentro de Prompt Flow de Azure AI Foundry. Comenzando con la creación de un nuevo flujo, agregarás y configurarás la herramienta Prompt y desarrollarás un flujo que incorpore herramientas LLM (Large Language Model) y Prompt. Al crear un flujo de ejemplo y ejecutarlo con entradas personalizadas, aprenderás a monitorear la ejecución del flujo y evaluar los resultados, comprendiendo así los pasos prácticos para desarrollar, probar y refinar flujos de trabajo impulsados por IA.

## Objetivos del laboratorio

En este laboratorio, realizarás lo siguiente:

- Tarea 1: Crear y personalizar prompts
- Tarea 2: Desarrollar un flujo con herramientas LLM y Prompt

### Tarea 1: Crear y personalizar prompts

Crear y personalizar prompts implica diseñar preguntas o instrucciones específicas y dirigidas para obtener respuestas o acciones deseadas. Este proceso incluye definir objetivos claros, comprender a la audiencia y usar un lenguaje preciso para asegurar claridad y relevancia. La personalización puede refinar aún más los prompts para alinearlos con contextos o necesidades particulares, mejorando el compromiso y la efectividad en aplicaciones como educación, servicio al cliente e interacciones con IA.

1. Abre una nueva pestaña en el navegador y navega al portal de Azure AI Foundry usando el siguiente enlace:

   ```
    https://ai.azure.com/
   ```
1. Haz clic en el ícono de **Azure AI Foundry** en la parte superior izquierda.
1. Selecciona el proyecto de AI Foundry que creaste anteriormente en el laboratorio, es decir, **ai-foundry-project-{suffix} (1)**.
1. Desde el panel de navegación izquierdo, selecciona **Prompt flow (1)** > **+ Create (2)** para agregar la herramienta Prompt a tu flujo.

   ![](./media/prompt-flow.png)

1. En el panel **Create a new flow**, bajo **Standard flow**, haz clic en **Create (1)**, luego ingresa el siguiente nombre de carpeta y haz clic en **Create (3)**

   ```
   promptflow-{suffix}
   ```

   ![](./media/E2-T2-S7.png)

   > **Nota:** Si encuentras errores de permisos, espera 5 minutos y vuelve a crear el prompt flow con un nombre único cuando veas el error de que el nombre de la carpeta ya existe. Una vez creado el flujo, renómbralo a **promptflow-{suffix} (2)** seleccionando el **icono de edición (1)** y haz clic en **Save (3)**.

   ![](./media/gpt-4-demo11.png)


### Tarea 2: Desarrollar un flujo con herramientas LLM y Prompt

Desarrollar un flujo con modelos de lenguaje grandes (LLMs) y herramientas Prompt implica diseñar una interacción estructurada donde el LLM es guiado por prompts cuidadosamente elaborados para generar salidas deseadas. Este proceso normalmente incluye definir el objetivo, seleccionar los LLM apropiados y refinar iterativamente los prompts según las respuestas del modelo para asegurar precisión y relevancia. Las herramientas Prompt ayudan a gestionar y optimizar esta interacción, permitiendo un uso más eficiente y efectivo de los LLM en tareas como creación de contenido, análisis de datos y soporte automatizado al cliente.

1. Se abrirá la página de autoría de prompt flow. Ahora puedes comenzar a crear tu flujo. Por defecto verás un flujo de ejemplo. Este flujo de ejemplo tiene nodos para las herramientas LLM y Python.

1. Opcionalmente, puedes agregar más herramientas al flujo. Las opciones de herramientas visibles son **LLM, Prompt y Python**. Para ver más herramientas, selecciona **+ More tools**.

   ![](./media/d4-2.png)

1. Desde el **Graph**, selecciona **joke (1)**. Elige una conexión existente **ai-xxxxxxxx_aoai (2)** del menú desplegable y, para deployment, selecciona **gpt-4o (3)** en el editor de la herramienta LLM.

    ![](./media/d5.png)

1. Desplázate hacia arriba y, en **Input**, ingresa cualquier nombre de fruta de tu elección, como **Apple (1)**.

   ![](./media/apple-1.png)

1. Selecciona **Save (1)** y luego **Start compute session (2)**.

   ![](./media/save.png)

   > **Nota:** Puede tomar **10-15 minutos** iniciar la sesión de cómputo. Espera hasta que la sesión inicie.

1. Una vez que la sesión de cómputo haya finalizado, haz clic en el botón de reproducir dentro del nodo **joke** para ejecutar el **joke node**.

   ![](./media/joke-03.png)

1. Una vez que la ejecución del nodo **joke** se haya completado, haz clic en el nodo **echo (1)** del gráfico y luego haz clic en el botón **Play (2)**.

   ![](./media/d6.png)

1. Una vez que todos los nodos se hayan ejecutado correctamente, selecciona **Run** en la barra de herramientas.

   ![](./media/run-1.png)

1. Una vez que la ejecución del flujo haya finalizado, selecciona **View outputs** para ver los resultados del flujo. La salida se verá similar a la imagen mostrada a continuación.

   ![](./media/image-30.png)

1. Puedes ver el estado de ejecución del flujo y la salida en la sección **Outputs**.

   ![](./media/image-31.png)

1. Desde el menú superior, selecciona **+ Prompt (1)** para agregar la herramienta Prompt a tu flujo, ponle el nombre **modelflow (2)** y selecciona **Add (3)**.

   ![](./media/gpt-4-demo17.png)
   ![](<./media/gpt-4-demo(15).png>)

1. Agrega este código dentro de la herramienta Prompt **modelflow (1)** y selecciona **Validate and parse input (2)**

   ```jinja
   Welcome to Joke Bot !
   {% if user_name %}
    Hello, {{ user_name }}!
   {% else %}
    Hello there!
   {% endif %}
   Pick a category from the list below and get ready to laugh:
   1. 🐶 Animal Jokes – From pets to wildlife, it’s a zoo of laughs.
   2. 💼 Office Humor – Relatable jokes for the 9-to-5 grind.
   3. 💻 Tech & Programmer Jokes – Debug your mood with geeky giggles.
   4. 📚 School & Exam Jokes – A+ comedy for students and survivors.
   5. ⚡ One-Liners – Quick, witty, and straight to the funny bone.
   6. 😏 Sarcastic Jokes – Dry, sharp, and deliciously savage.
   ```

   ![](./media/gpt-4-demo16-1.png)

   > **Nota:** El botón **Validate and parse input** puede aparecer ocasionalmente deshabilitado (en gris). Sin embargo, aún puedes hacer clic en él; funcionará como se espera.


1. En la sección de input agrega el siguiente valor, selecciona **Save (2)** y **Run (3)**.

   - user_name: **John (1)**

     ![](./media/gpt-4-demo14-1.png)

1. Si encuentras alguna advertencia al ejecutar, como se muestra en la captura de pantalla a continuación, haz clic en **Run Anyway**.

   ![](./media/run-anway.png)

1. Una vez que la ejecución del flujo haya finalizado, selecciona **View outputs** para ver los resultados del flujo. La salida se verá similar a la imagen mostrada a continuación.

   ![](./media/output001.png)

1. Puedes ver el estado de ejecución del flujo y la salida en la sección Outputs.

   ![](./media/output1-2.png)

## Revisión

En este laboratorio completaste las siguientes tareas:

- Crear y personalizar prompts
- Desarrollar un flujo con herramientas LLM y Prompt

### Has completado exitosamente el laboratorio. Haz clic en **Next >>** para continuar con el siguiente ejercicio.
