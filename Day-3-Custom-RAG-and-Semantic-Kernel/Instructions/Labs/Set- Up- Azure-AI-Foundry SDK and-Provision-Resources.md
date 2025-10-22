
### 연습 1: Azure AI Foundry SDK 설정 및 리소스 프로비저닝

작업 1: 필수 리소스 설정

1.  +++<https://portal.azure.com+++> 페이지의 **Azure Portal**에서, 포털
    상단의 **Search resources** 상자에 +++Azure AI Foundry+++를
    입력하고, **Services** 아래에서 **Azure AI Foundry**를
    선택하세요.![A screenshot of a chat AI-generated content may be
    incorrect.](./media/image1.png)

2.  AI Foundry의 왼쪽 탐색 창에서 **AI Hubs**를 선택하세요.  
    AI Hubs 페이지에서 **Create**를 클릭하고, 드롭다운에서 **Hub**를
    선택하세요.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image2.png)

3.  **Create an Azure AI hub** 창에서 다음 세부 정보를 입력하세요.

    - Subscription : **Leave default subscription**

    - Resource Group : **AgenticAI**

    - Region : **EastUS**

    - Name : <+++ai-foundry-hub@lab.LabInstance.Id>+++

    - Connect AI Services incl. OpenAI : **Create New**를 클릭하세요

    - Connect AI Services incl. OpenAI : 이름을
       <+++my-ai-service@lab.LabInstance.Id>+++로 입력하세요

    - **Save**를 클릭한 다음 **Next: Storage**를 클릭하세요

> ![](./media/image3.png)

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image4.png)

4.  **Review + Create** 탭을 클릭한 다음 **Create**를 클릭하세요.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image5.png)

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image6.png)

5.  배포가 완료될 때까지 기다린 다음 **Go to resource**를 클릭하세요.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image7.png)

6.  **Overview** 창에서 **Launch Azure AI Foundry**를 클릭하세요.  
    그러면 **Azure AI Foundry** 포털로 이동합니다.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image8.png)

7.  Hub Overview에서 **+ New project**를 선택하세요.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image9.png)

8.  프로젝트 이름을 +++ai-foundry-project@lab.LabInstance.Id+++로 입력한
    다음 **Create**를 선택하세요.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image10.png)

9.  **AI Foundry** 프로젝트에서 **My assets** 섹션으로 이동한 다음  
    **Models + endpoints**를 선택하세요.  
    **Deploy model**을 클릭하고, 계속하려면 **Deploy base model**을
    선택하세요.

![](./media/image11.png)

10. **Select a model** 창에서 +++gpt-4o+++를 검색하고, **gpt-4o**를
    선택한 다음 **Confirm**을 선택하세요.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image12.png)

11. **Deploy model gpt-4o** 창에서 **Customize**를 선택하세요.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image13.png)

- Deployment Name: **gpt-4o**

- Deployment type: **Global Standard**

- **Model version을 2024-08-06 (Default)로** 변경하세요.

- **Tokens per Minute Rate Limit**을 **200K**로 변경하세요.

- **Deploy (5)를** 클릭하세요.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image14.png)

12. **Azure Portal**로 돌아가 **+++AI Search+++**를 검색하고 **AI
    Search** 리소스를 선택하세요.

![A screenshot of a computer AI-generated content may be
incorrect.](./media/image15.png)

13. **AI Foundry | AI Search** 페이지에서 **+ Create**를 선택하여
    **Azure OpenAI** 리소스를 생성하세요.

![A screenshot of a search engine AI-generated content may be
incorrect.](./media/image16.png)

14. **Create a Search service** 페이지에서 다음 설정을 입력하고 **Next
    (6**)를 선택하세요:

   | Setting |Value  |
   |:------|:-------|
   | Subscription | 기본 Subscription을 그대로 유지하세요 |
   | Resource group |**AgenticAI**  |
   | Region | **East US 2** |
   |Name  | +++aisearch@lab.LabInstance.Id+++ |
   | Pricing tier | **Standard S0** |

   ![A screenshot of a search service AI-generated content may be incorrect.](./media/image17.png)

15. **Review + create**를 선택한 다음 **Create**를 선택하세요.

   ![A screenshot of a search service AI-generated content may be
incorrect.](./media/image18.png)

16. **Azure AI Foundry** 탭으로 돌아가 **Management Center**를
    선택하세요.

   ![A screenshot of a computer AI-generated content may be
incorrect.](./media/image19.png)

17. 프로젝트 아래에서 **Connected resources**를 선택하세요. 그런 다음
    **+ New connection**을 선택하세요. **Azure AI Search**를 선택하고
    **Add connection**을 선택한 다음 **Close**를 선택하세요.

   ![A screenshot of a computer AI-generated content may be
   incorrect.](./media/image20.png)

   ![A screenshot of a search engine AI-generated content may be
   incorrect.](./media/image21.png)

18. 다음으로 **Foundry hub** 아래의 **Connected resources**를
    선택하세요.  
    그런 다음 **+ New connection**을 선택하세요. **Azure AI Search**를
    선택하고 **Add connection**을 선택한 다음 **Close**를 선택하세요.

   ![A screenshot of a computer AI-generated content may be
   incorrect.](./media/image22.png)

   ![A screenshot of a computer AI-generated content may be
   incorrect.](./media/image23.png)

   ![A screenshot of a search engine AI-generated content may be
   incorrect.](./media/image24.png)


## 과제 2: 환경 변수 구성

이 과제에서는 RAG 애플리케이션과 Azure AI Foundry 서비스 간의 원활한 통합을 위해 필수 환경 변수를 설정하고 구성합니다.

1. 브라우저의 새 탭을 열고 아래 링크를 통해 Azure AI Foundry 포털로 이동합니다.

   ```
   https://ai.azure.com/
   ```

1. 왼쪽 상단의 **Azure AI Foundry** 아이콘을 클릭합니다.

1. 이전 실습에서 생성한 프로젝트인 **ai-foundry-project-<Deployment ID> (1)** 을 선택합니다.

1. **ai-foundry-project-<Deployment ID>** 의 **개요 (1)** 페이지로 이동하여, **프로젝트 연결 문자열 (2)** 을 복사한 뒤 메모장 등에 붙여넣어 둡니다. 다음 단계에서 사용됩니다.

1. 다시 **Visual Studio Code**로 돌아갑니다.

1. **.env.sample (1)** 파일을 마우스 오른쪽 클릭하고 **Rename (2)** 을 선택합니다.

   ![](../media/af29.png)

1. 파일 이름을 `.env`로 변경합니다.

1. `.env (1)` 파일을 클릭하고, **your\_connection\_string (2)** 부분을 앞서 복사한 **Project connection string**으로 교체합니다.

   ![](../media/af32.png)
   ![](../media/af33.png)

1. 다음 값을 파일에 업데이트합니다:

   * CHAT\_MODEL="gpt-4o"
   * EVALUATION\_MODEL="gpt-4o"
   * INTENT\_MAPPING\_MODEL="gpt-4o"

1. **Ctrl+S**를 눌러 파일을 저장합니다.

---

## 복습

이 실습을 통해서 Azure AI Foundry에서 프로젝트를 설정하고, AI 모델을 배포 및 관리하며, Azure AI Search 서비스를 생성하여 효율적인 데이터 검색이 가능하도록 하였습니다. 검색 서비스를 프로젝트에 통합하고, GitHub 저장소를 클론하여 필요한 리소스를 확보했으며, 실행을 위한 환경 변수도 구성하였습니다.

이 실습에서 완료한 항목은 다음과 같습니다:

* 과제 1: 프로젝트 필수 구성요소 설치
* 과제 2: 환경 변수 구성
