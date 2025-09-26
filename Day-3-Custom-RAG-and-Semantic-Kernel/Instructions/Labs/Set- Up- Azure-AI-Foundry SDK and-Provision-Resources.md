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
