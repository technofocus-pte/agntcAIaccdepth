# 练习 1：设置 Azure AI Foundry SDK 和配置资源

在本练习中，您将设置 Azure AI Foundry SDK。这包括配置环境、部署基础模型，以及确保与 Azure AI 服务的无缝集成，以实现知识检索和推理。

### 任务 1：安装项目所需依赖

在本任务中，您将克隆项目的 GitHub 仓库以访问构建聊天应用所需的文件。

1. 在您的 **实验虚拟机** 上，启动 **Visual Studio Code**。

1. 点击 **文件 (1)**，然后 **打开文件夹**。

1. 导航到 `C:\LabFiles\Day-3-Custom-RAG-and-Semantic-Kernel` **(1)**，选择 **Custom-RAG-App (2)** 文件夹，然后点击 **选择文件夹 (3)**。

1. 点击 **是，我信任作者**。

    ![](../media/af25.png)

1. 展开 **scenarios (1)**，然后 **rag/custom-rag-app (2)**。选择 **requirements.txt (3)**。该文件包含设置 Azure AI Foundry SDK 所需的包。**(4)**

    ![](../media/af-27.png)

     >**注意**：该文件包含使用 Azure AI Foundry SDK 构建和管理 AI 驱动应用程序所需的包，包括身份验证、AI 推理、搜索、数据处理和遥测日志记录。

1. 右键点击 **rag/custom-rag-app (1)** 文件夹，然后选择 **在集成终端中打开 (2)**。

    ![](../media/af26.png)

1. 运行以下命令安装所需的包。

    ```bash
    pip install -r requirements.txt
    ```

     ![](../media/af28.png)    

      >**注意：** 等待安装完成。这可能需要一些时间。


### 任务 2：配置环境变量

在本任务中，您将设置和配置必要的环境变量，以确保 RAG 应用程序与 Azure AI Foundry 服务之间的无缝集成。

1. 在浏览器中打开新标签页，使用以下链接导航到 Azure AI Foundry 门户

   ```
    https://ai.azure.com/
   ```

1. 点击左上角的 **Azure AI Foundry** 图标。
1. 选择您之前在实验中创建的 AI foundry 项目，即 **ai-foundry-project-{suffix} (1)**
1. 导航到 **ai-foundry-project-{suffix}** 的 **概述 (1)** 页面，然后复制 **项目连接字符串 (2)** 并粘贴到记事本中。您将在下一步中使用它。

1. 返回 **Visual Studio Code**。

1. 右键点击 **.env.sample (1)** 并选择 **重命名 (2)**。

    ![](../media/af29.png)

1. 将文件重命名为 `.env`。

1. 点击 `.env` **(1)** 文件，用您在步骤 2 中复制的 **项目连接字符串** 替换 **your_connection_string (2)**。

    ![](../media/af32.png)

    ![](../media/af33.png)

1. 在文件中更新以下值：
    - CHAT_MODEL="gpt-4o"
    - EVALUATION_MODEL="gpt-4o"
    - INTENT_MAPPING_MODEL="gpt-4o"
1. 按 **Ctrl+S** 保存文件。

## 回顾

本练习指导参与者在 Azure AI Foundry 中设置项目、部署和管理 AI 模型，以及创建 Azure AI Search 服务以实现高效的数据检索。他们将搜索服务与项目集成，克隆包含必要资源的 GitHub 仓库，并配置环境变量以确保无缝执行。

在本练习中，您已完成以下内容：
- 任务 1：安装项目所需依赖
- 任务 2：配置环境变量

### 您已成功完成实验。点击 **下一步** 继续下一个实验。 