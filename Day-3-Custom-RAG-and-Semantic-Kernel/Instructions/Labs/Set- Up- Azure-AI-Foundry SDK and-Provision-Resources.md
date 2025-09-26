# Exercício 1: Configurar o Azure AI Foundry SDK e Provisionar Recursos

Neste exercício, você irá configurar o Azure AI Foundry SDK. Isso inclui configurar o ambiente, implantar modelos base e garantir a integração perfeita com os serviços Azure AI para recuperação de conhecimento e inferência.

### Tarefa 1: Instalar os requisitos do Projeto

Nesta tarefa, você irá clonar o repositório do GitHub do projeto para acessar os arquivos necessários para construir o aplicativo de chat.

1. Na sua **VM do Laboratório**, abra o **Visual Studio Code**.

2. Clique em **Arquivo (1)**, depois em **Abrir Pasta**.

3. Navegue até `C:\LabFiles\Day-3-Custom-RAG-and-Semantic-Kernel` **(1)**, selecione a pasta **Custom-RAG-App (2)** e então clique em **Selecionar pasta (3)**.

4. Clique em **Sim, eu confio no autor**.

   ![](../media/af25.png)

5. Expanda **scenarios (1)**, depois **rag/custom-rag-app (2)**. Selecione **requirements.txt (3)**. Este arquivo contém os pacotes necessários para configurar o Azure AI Foundry SDK. **(4)**

   ![](../media/af-27.png)

   > **Nota:** Este arquivo contém os pacotes necessários para construir e gerenciar uma aplicação com IA utilizando o Azure AI Foundry SDK, incluindo autenticação, inferência de IA, busca, processamento de dados e registro de telemetria.

6. Clique com o botão direito na pasta **rag/custom-rag-app (1)**, depois selecione **Abrir no Terminal Integrado (2)**.

   ![](../media/af26.png)

7. Instale os pacotes necessários executando o seguinte comando:

   ```bash
   pip install -r requirements.txt
   ```

   ![](../media/af28.png)

   > **Nota:** Aguarde a instalação terminar. Pode demorar um pouco.

### Tarefa 2: Configurar Variáveis de Ambiente

Nesta tarefa, você irá configurar as variáveis de ambiente necessárias para garantir a integração perfeita entre seu aplicativo RAG e os serviços do Azure AI Foundry.

1. Abra uma nova aba no navegador e acesse o portal Azure AI Foundry pelo link abaixo:

   ```
   https://ai.azure.com/
   ```

2. Clique no ícone **Azure AI Foundry** no canto superior esquerdo.

3. Selecione o projeto AI Foundry que você criou anteriormente no laboratório, ou seja, **ai-foundry-project-{suffix}(1)**.

4. Vá para a página **Visão Geral (1)** do projeto **ai-foundry-project-{suffix}** e copie a **String de conexão do projeto (2)** para um bloco de notas. Você usará essa string na próxima etapa.

5. Volte para o **Visual Studio Code**.

6. Clique com o botão direito no arquivo **.env.sample (1)** e selecione **Renomear (2)**.

   ![](../media/af29.png)

7. Renomeie o arquivo para `.env`.

8. Clique no arquivo **.env** e atualize os seguintes valores no arquivo

   - Substitua **your_connection_string** pela string de conexão do projeto que você copiou na Etapa 2.
   - CHAT_MODEL="gpt-4o"
   * EVALUATION_MODEL="gpt-4o"
   * INTENT_MAPPING_MODEL="gpt-4o"

      ![](../media/focus6.png)

9. Pressione **Ctrl+S** para salvar o arquivo.

### Revisão

Este exercício guiou os participantes na configuração de um projeto no Azure AI Foundry, implantação e gerenciamento de modelos de IA, e criação de um serviço Azure AI Search para recuperação eficiente de dados. Eles integraram o serviço de busca ao projeto, clonaram um repositório GitHub contendo os recursos necessários, e configuraram as variáveis de ambiente para garantir uma execução fluida.

Neste exercício, você realizou o seguinte:
- Tarefa 1: Instalar os requisitos do Projeto
- Tarefa 2: Configurar Variáveis de Ambiente

### Você concluiu com sucesso o exercício. Clique em **Próximo** para continuar para o próximo exercício.
