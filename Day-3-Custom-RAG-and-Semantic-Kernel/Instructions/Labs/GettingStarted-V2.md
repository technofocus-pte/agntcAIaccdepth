# 實驗課程 - 第 3 天

# 使用 Azure AI Foundry 開發自訂 RAG 應用程式並探索 Semantic Kernel

### 預估總時長：4 小時

## 課程概覽

在本次實驗課程中，您將學習如何使用 **Azure AI Foundry SDK** 建立自訂的檢索增強生成（Retrieval-Augmented Generation，RAG）應用程式。您將實驗一個 RAG 流程，能夠索引並擷取相關資料，以提升 AI 回應的品質。最後，您將透過評估檢索準確性、回應品質與效率來優化系統效能。課程結束時，您將擁有一個整合 Azure AI 能力的 RAG 解決方案，能夠強化知識檢索與回應生成。

透過結合 **Azure AI Foundry SDK** 與 **Semantic Kernel**，參與者將建立動態的提示式互動，並整合實用的 **外掛（plugins）**，例如時間與天氣工具，以擴充聊天機器人的功能。

完成本次實驗後，您將具備實驗一個可擴展的 RAG 解決方案的實務經驗，該解決方案結合 Azure AI 能力與 **Semantic Kernel** 的外掛生態系，實現智慧知識檢索與回應生成。

## 課程目標 

完成本次實驗後，您將能夠：

- **建立 RAG 流程**：在此實驗練習中，參與者將學習如何建立一個檢索增強生成（RAG）流程，以提升 AI 回應的品質。他們將索引知識來源、實驗檢索流程，並生成包含相關資料的回應。此外，也會整合遙測記錄功能，以監控並優化系統效能。

- **評估與優化 RAG 效能**：參與者將學習如何評估與優化 RAG 系統的效能。他們將使用 Azure AI 評估工具來檢查檢索準確性，實驗評估方法以衡量回應品質，並解讀結果以微調系統效率。

- **Semantic Kernel 基礎**：透過簡單的入門應用程式，將 **Semantic Kernel** 與 GPT-4o 連接，打造智慧聊天體驗。

- **Semantic Kernel 外掛**：透過建立並整合自訂的 **Semantic Kernel** 外掛，擴充聊天機器人的功能。
  
## 先決條件

參與者應具備以下條件：

- 熟悉 **Azure AI Foundry** 入口網站的操作。
- 基本了解大型語言模型（LLM）及其應用。
- 熟悉 **Semantic Kernel** 的概念，例如外掛（plugins）、規劃器（planners）與 AI 技能（AI skills）。

## 元件說明

- **Azure AI Foundry**：Azure AI Foundry 提供建構 RAG（檢索增強生成）流程所需的基礎架構，包括 AI 模型、向量資料庫及部署與管理所需的資源。此平台可用於建立結合檢索系統的 AI 應用程式，以提升 AI 回應的準確性與相關性。

- **Azure OpenAI**：Azure OpenAI 服務提供 REST API 存取 OpenAI 強大的語言模型，並可與您的資料整合，實現客製化且安全的互動。

- **Azure OpenAI 模型**：Azure OpenAI 模型提供預先訓練且可自訂的大型語言模型，適用於各種 AI 應用。這些模型可透過精心設計的 Prompt，產生具上下文意義的內容，協助打造強大的 AI 解決方案。

- **Azure AI Search**：Azure AI Search（前身為 Azure Cognitive Search）是一個企業級的資訊檢索系統，可用來儲存、索引與搜尋資料，支援強大的 RAG 應用與企業搜尋引擎。

- **Visual Studio Code**：作為開發環境，用於建構 RAG 應用，整合檢索機制與 AI 生成回應。

- **檢索增強生成 (Retrieval-Augmented Generation, RAG) 流程**：RAG 流程透過整合外部知識來強化 AI 回應的內容。它會根據使用者查詢，從向量資料庫中擷取相關資訊，並將其用於增強 AI 的回應，使輸出更準確且具上下文意義。

- **評估與監控 (Azure AI Foundry)**：用於追蹤模型效能、檢索準確性與回應品質，協助持續優化與除錯。

- **Semantic Kernel**：一個 AI 協調框架，可連接 **LLMs, plugins, and APIs**，以提升 AI 的能力。
  
- **Python SDKs & REST APIs**：用於與 **Azure AI Foundry, Semantic Kernel, and OpenAI services**服務 互動。
