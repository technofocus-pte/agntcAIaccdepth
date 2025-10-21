# 練習 1：設定 Azure AI Foundry SDK 並佈建資源

在本練習中，您將設定 Azure AI Foundry SDK，包括環境配置、部署基礎模型，並確保與 Azure AI 服務的無縫整合，以進行知識檢索與推論。

## 練習 1: 設置 Azure AI Foundry SDK 並預配資源

### 任務 1: 設置先決條件資源

1.  在“Azure 門戶”頁上
    +++[https://portal.azure.com+++](https://portal.azure.com+++/),
    在門戶頂部的“搜索資源”框中, enter +++Azure AI Foundry+++,
    ，然後在“服務”下選擇“Azure AI Foundry”。

    ![A screenshot of a chat AI-generated content may be
incorrect.](./media/image1.png)

2.  在 AI Foundry 的左側導航窗格中，選擇 **AI 中心**. 在“AI
    中心”頁面上，單擊“**創建**”，然後 **從下拉列表中選擇**“中心”。

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image2.png)

3.  在“**創建 Azure AI 中心**”窗格中，輸入以下詳細信息：

    - 訂閱 : **Leave default subscription**

    - 資源組 : **AgenticAI**

    - 地區 : **EastUS**

    - 名字: <+++ai-foundry-hub@lab.LabInstance.Id>+++

    - 連接 AI 服務，包括. OpenAI : 點擊 **Create New**

    - 連接 AI 服務，包括. OpenAI : 提供名稱
      <+++my-ai-service@lab.LabInstance.Id>+++

    - 點擊 **Save**, 其次**Next:Storage**

    ![](./media/image3.png)

    ![A screenshot of a computer AI-generated content may be
incorrect.](./media/image4.png)

4.  點擊 **Review + Create** 然後選擇 **Create.**

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image5.png)

    ![A screenshot of a computer AI-generated content may be
incorrect.](./media/image6.png)

5.  等待部署完成，然後單擊轉到**資源**.

    ![A screenshot of a computer AI-generated content may be
incorrect.](./media/image7.png)

6.  在“概述”窗格中，單擊“**啟動 Azure AI Foundry**”。這會導航到 Azure AI
    Foundry 門戶。

    ![A screenshot of a computer AI-generated content may be
incorrect.](./media/image8.png)

7.  在中心概述上選擇 **+ New project** 

    ![A screenshot of a computer AI-generated content may be incorrect.](./media/image9.png)

8.  將項目名稱提供為<+++ai-foundry-project@lab.LabInstance.Id>+++
    然後選擇**創建。**

    ![A screenshot of a computer AI-generated content may be
incorrect.](./media/image10.png)

9.  在 **AI Foundry project**，導航到“**我的資產**”部分,
    然後選擇 **模型 + endpoints**. 點擊 **Deploy model**,
    然後選擇 **Deploy base model** 以繼續.

    ![](./media/image11.png)

10. 在 **Select a model** 窗口, 搜索 **+++gpt-4o+++**,
    選擇**gpt-4o** 並選擇 **Confirm**

    ![A screenshot of a computer AI-generated content may be
incorrect.](./media/image12.png)

11. 在 **Deploy model gpt-4o** 窗口, 選擇 **Customize**.

    ![A screenshot of a computer AI-generated content may be
incorrect.](./media/image13.png)

    -   Deployment 名稱: **gpt-4o**

    -   Deployment 類型: **Global Standard**

    -    將**Model version to 2024-08-06 (Default)**

    -   將每分鐘令牌數速率限制更改為 **200K**

    -   點擊**Deploy (5)**

    ![A screenshot of a computer AI-generated content may be
incorrect.](./media/image14.png)

12. 導航回**Azure Portal** 並搜索**+++AI Search+++** ，然後選擇 **AI
    搜索**資源.

    ![A screenshot of a computer AI-generated content may be
incorrect.](./media/image15.png)

13． 在 **AI Foundry | AI Search** 頁面, 選擇 **+ Create** 以創建 Azure OpenAI 資源。

    ![A screenshot of a search engine AI-generated content may be
incorrect.](./media/image16.png)

13. 在 **Create a Search service** 頁面 提供以下設置和選擇 **Next (6)**:

    | 設置  |  價值 |
    |:-----|:-----|
    | 訂閱  | 保留默認訂閱  |
    | 資源組  | **AgenticAI**  |
    | 區域  |  **East US 2** |
    |  名字 | +++aisearch@lab.LabInstance.Id+++ |
    | 定價層  | **Standard S0**  |

    ![A screenshot of a search service AI-generated content may be incorrect.](./media/image17.png)

14. 選擇 **Review + create**, 然後 **Create**

    ![A screenshot of a search service AI-generated content may be
incorrect.](./media/image18.png)

15. 返回到“Azure AI Foundry”選項卡，選擇**Management Center**.

    ![A screenshot of a computer AI-generated content may be
incorrect.](./media/image19.png)

16. 在項目下，選擇**Connected resources**. 然後選擇 **+New connection**.
    選擇 **Azure AI Search**, 然後選擇**Add connection** 然後 **Close**.

    ![A screenshot of a computer AI-generated content may be
incorrect.](./media/image20.png)

    ![A screenshot of a search engine AI-generated content may be
incorrect.](./media/image21.png)

17. 然後,在 Foundry 中心下選擇 **Connected resources**  。然後選擇**+New
    connection**. 選擇 **Azure AI Search**, 然後選擇 **Add
    connection** 然後 **Close**.

    ![A screenshot of a computer AI-generated content may be
    incorrect.](./media/image22.png)

    ![A screenshot of a computer AI-generated content may be
    incorrect.](./media/image23.png)

    ![A screenshot of a search engine AI-generated content may be
    incorrect.](./media/image24.png)


### 任務 1：安裝專案所需的套件

在此任務中，您將從 GitHub 複製專案的儲存庫，以取得建立聊天應用程式所需的檔案。

1. 在您的 **Lab VM**上啟動 **Visual Studio Code**。

2. 點選 **File**，然後選擇 **Open Folder**。

3. 前往 `C:\LabFiles\Day-3-Custom-RAG-and-Semantic-Kernel` ，選取 **Custom-RAG-App** 資料夾，然後點選 **Select folder**。

4. 點選 **是的，我相信作者**。

    ![](../media/af25.png)

5. 展開 **scenarios** **(1)**，然後展開 **rag/custom-rag-app** **(2)**。選取 **requirements.txt** **(3)**。此檔案包含設定 Azure AI Foundry SDK 所需的套件 **(4)**。

    ![](../media/af-27.png)

     >**注意**：此檔案包含使用 Azure AI Foundry SDK 建立與管理 AI 應用程式所需的套件，包括驗證、AI 推論、搜尋、資料處理與遙測記錄等功能。

6. 右鍵點選 **rag/custom-rag-app** **(1)** 資料夾，然後選擇 **Open in Integrated Terminal** **(2)**。

    ![](../media/af26.png)

7. 在終端機中執行以下指令以安裝所需套件：

    ```bash
    pip install -r requirements.txt
    ```

     ![](../media/af28.png)    

      >**注意** ：請等待安裝完成，這可能需要一些時間。


### 任務 2：設定環境變數

在此任務中，您將設定並配置必要的環境變數，以確保您的 RAG 應用程式能與 Azure AI Foundry 服務無縫整合。

1. 在瀏覽器中開啟新分頁，並使用以下連結前往 Azure AI Foundry 入口網站。

   ```
    https://ai.azure.com/
   ```

2. 點選左上角的 **Azure AI Foundry** 圖示。
3. 選取您在本實驗中先前建立的 AI Foundry 專案，例如  **ai-foundry-project-{suffix}** **(1)**
4. 前往該專案 **ai-foundry-project-{suffix}** 的 **概觀** **(1)**頁面，然後複製 **專案連接字串** **(2)** ，並貼到記事本中。您將在下一步使用它。

5. 回到 **Visual Studio Code**。

6. 右鍵點選 `.env.sample` **(1)** 檔案，然後選擇 **Rename** **(2)**。

    ![](../media/af29.png)

7. 將檔案重新命名為 `.env`。

8. 點選 `.env` **(1)** 檔案，將其中的 **your_connection_string** **(2)** 替換為您在步驟 4 中複製的 **案連接字串**。

    ![](../media/af32.png)

    ![](../media/af33.png)

9. 更新檔案中的以下變數值：
    - CHAT_MODEL="gpt-4o"
    - EVALUATION_MODEL="gpt-4o"
    - INTENT_MAPPING_MODEL="gpt-4o"
10. 按下 **Ctrl+S** 儲存檔案。

### 回顧

本練習引導參與者完成在 Azure AI Foundry 中建立專案、部署與管理 AI 模型，以及建立 Azure AI Search 服務以進行高效的資料檢索。參與者將搜尋服務整合至專案中，並從 GitHub 複製包含必要資源的儲存庫，最後設定環境變數以確保系統能順利執行。

在本次練習中，您已完成以下項目：
- 任務 1：安裝專案所需的套件
- 任務 2：設定環境變數

### 恭喜！您已成功完成本次實驗課程！
### 請點選導覽連結，以繼續進行下一個實驗課程。













