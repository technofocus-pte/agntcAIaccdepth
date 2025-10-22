# Exercício 1: Configurar o Azure AI Foundry SDK e Provisionar Recursos

Neste exercício, você irá configurar o Azure AI Foundry SDK. Isso inclui configurar o ambiente, implantar modelos base e garantir a integração perfeita com os serviços Azure AI para recuperação de conhecimento e inferência.

### Tarefa 1: Configurando os recursos de pré-requisito

1.  Na página do Portal do Azure +++, na caixa Pesquisar recursos na
    parte superior do portal, insira +++Azure AI Foundry+++, e, em
    seguida, selecione Azure AI Foundry em Services.

   ![](./94a8a4ac803f60ed8c841748afb0d61433e9c9ae.png "Inserting image...")

2.  No painel de navegação esquerdo do AI Foundry, selecione **AI
    Hubs**. Na página AI Hubs, clique em **Create** e selecione **Hub**
    no menu suspenso.

   ![](./99a0768b01ab56eefb0cc7ace8e7b16969ce7b20.png "Inserting image...")

3.  No painel **Create an Azure AI hub** insira os seguintes detalhes:

    1.  Subscription : **Leave default subscription**

    2.  Resource Group : **AgenticAI**

    3.  Region : **EastUS**

    4.  Name :
        [*+++ai-foundry-hub@lab.LabInstance.Id*](mailto:+++ai-foundry-hub@lab.LabInstance.Id)+++

    5.  Connect AI Services incl. OpenAI : Clique em **Create New**

    6.  Connect AI Services incl. OpenAI : Forneça um nome
        [*+++my-ai-service@lab.LabInstance.Id*](mailto:+++my-ai-service@lab.LabInstance.Id)+++

    7.  Clique em **Save**, e em **Next:Storage**

   ![](./37f898e34ae9640e3be49ad44b08b3a25c5f6ce0.png "Inserting image...")

   ![](./f91554f2e5284213d9dc726deb7179be1a862610.png "Inserting image...")

4.  Clique na guia **Review + Create** e em **Create.**

   ![](./7e10049b0c843b34265c63c5b8b2b62b5f4707a6.png "Inserting image...")

   ![](./260ab537a6cd4d8f3f53296458e4d531f2e6a5e4.png "Inserting image...")

5.  Aguarde a conclusão da implementação e clique em **Go to resource**.

   ![](./3057b9f6e918a10c10714db7c7ff3218e370c970.png "Inserting image...")

6.  No painel **Overview**, clique em **Launch Azure AI Foundry**. Isso
    o levará ao portal do Azure AI Foundry.

   ![](./bac34bfec19690f04d8bdb5449ae2c360901c656.png "Inserting image...")

7.  Selecione **+ New project** em Hub Overview.

   ![](./91ab786bd25d8a10be7a64c9f068aa8831afc6c5.png "Inserting image...")

8.  Forneça o nome do projeto como
    [*+++ai-foundry-project@lab.LabInstance.Id*](mailto:+++ai-foundry-project@lab.LabInstance.Id)+++
    e em seguida, selecione **Create**.

   ![](./6ca9f9fb318315e6b2c11b3c14717a4e7f0300f7.png "Inserting image...")

9.  Em seu **AI Foundry project**, navegue até a seção **My assets**, e
    selecione **Models + endpoints**. Clique em **Deploy model** e
    escolha **Deploy base model** para prosseguir.

   ![](./fe16fd57d4571b52bbc83400f9116499de961cd0.png "Inserting image...")

10. Na janela **Select a model**, busque por **+++gpt-4o+++**, selecione
    **gpt-4o** e selecione **Confirm.**

   ![](./d5cb563fd519de1820757bf3e93f37c27b0b639e.png "Inserting image...")

11. Na janela **Deploy model gpt-4o**, selecione **Customize**.

   ![](./8e251fb5cbc8d6209938d740bed5a85c7917055f.png "Inserting image...")

   - Deployment Name: **gpt-4o**

   - Deployment type: **Global Standard**

   - Altere o **Model version** para **2024-08-06 (Default)**

   - Altere o **Tokens per Minute Rate Limit** para **200K**

   - Clique em **Deploy (5)**

   ![](./4926510288dc7a78b6bc58d641adb25f9d1a4757.png "Inserting image...")

12. Navegue de volta para o **Azure Portal** e busque por **+++AI
    Search+++** e selecione o recurso **AI Search**

   ![](./e11b4a768e4e91fb9ee4028d16c323fc6f3f9076.png "Inserting image...")

13. Na página **AI Foundry | AI Search**, selecione **+ Create** para
    criar um recurso Azure OpenAI.

   ![](./c57592d74be7f24361468440b17f75c95140b73d.png "Inserting image...")

14. Na página **Create a Search service**, forneça as seguintes
    configurações e selecione **Next (6)**:

   | **Campo** | **Valor** |
   |:----|:-----|
   | Subscription | Manter a assinatura padrão |
   | Resource group | **AgenticAI** |
   | Region | **East US 2** |
   | Name | +++aisearch@lab.LabInstance.Id+++ |
   | Pricing tier | **Standard S0** |

   ![](./25b890709b264cfc69cea0b8b728b61df5b7c410.png "Inserting image...")

15. Selecione **Review + create** e **Create**

   ![](./e0f343a5229d0770584dfe280d45ffff120e5aae.png "Inserting image...")

16. De volta à guia Azure AI Foundry, selecione **Management Center**.

   ![](./08833a26ec373ef89b7160fa3b63557b0ddc2193.png "Inserting image...")

17. Em **Project** selecione **Connected resources**. Em seguida,
    selecione **+New connection**. Selecione **Azure AI Search**, e
    escolha **Add connection** e **Close**.

   ![](./52ff35049d2f7ff7b92755c12b33359ce1466ff7.png "Inserting image...")

   ![](./d2231a10de24a345cd86fe039daf580e59c72787.png "Inserting image...")

18. Em seguida, selecione **Connected resources** abaixo do seu hub do
    Foundry. Em seguida, selecione **+New connection**. Selecione
    **Azure AI Search**, e escolha **Add connection** e **Close**.

   ![](./5416215bb897e48826b6724c2acaa87d071cdb1b.png "Inserting image...")

   ![](./258043cbfbb6afa27014ba4469c82111e4dc3cea.png "Inserting image...")

   ![](./1091f959787d893fc1d121f494d3567f38292a56.png "Inserting image...")

### Tarefa 2: Instalar os requisitos do Projeto

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

### Tarefa 3: Configurar Variáveis de Ambiente

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
