# 練習 1：設定 Azure AI Foundry SDK 並佈建資源

在本練習中，您將設定 Azure AI Foundry SDK，包括環境配置、部署基礎模型，並確保與 Azure AI 服務的無縫整合，以進行知識檢索與推論。

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













