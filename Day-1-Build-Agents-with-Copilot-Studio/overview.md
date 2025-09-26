# 실습 1일차

# Copilot Studio에서 에이전트 빌드하기

### 예상 소요 시간: 4시간

## 개요

이번 실습 과정을 통해서 Microsoft 365 Copilot 및 Copilot Studio를 활용하여 AI가 제공하는 창의성과 자동화 기능을 활용하여 직원 경험을 향상시키는 방법을 살펴봅니다. 먼저 Microsoft Designer 기반의 이미지 생성(Image Generator) 기능을 활용하여 간단한 텍스트 프롬프트로 시각적으로 매력적인 콘텐츠를 생성하는 것부터 시작합니다. 이어지는 실습에서는 Microsoft 365 Copilot을 활용하여 직원 전환 프로세스를 간소화하는 방법을 안내합니다. 이 과정에는 내부 후보자 식별, 전환 계획 수립, 커뮤니케이션 자료 생성 등이 포함됩니다. 또한 Copilot Studio를 사용하여 온보딩 워크플로를 자동화하고, 교육 자료를 구축하며, 성과 추적 기능을 구현합니다. 마지막으로, 직원의 성과를 체계적으로 인정하는 프로세스를 구축할 수 있도록 '포상 및 격려 에이전트(Awards and Recognition agent)'를 작성해 볼 것입니다. 이를 통해 조직 내 참여와 성장을 촉진하는 문화를 조성할 수 있을 것입니다. 

## 목표

이번 실습을 마치면 다음을 수행할 수 있습니다. 

- **Copilot Studio 에이전트 빌더 살펴보기**: Microsoft 365 Copilot과 Designer를 활용하여 자연어 프롬프트로부터 매력적인 시각 자료를 손쉽게 생성하는 AI 기반 도구를 살펴봅니다.
- **Copilot Studio로 인사 지원 에이전트 만들기**: Microsoft 365 Copilot과 Copilot Studio를 활용하여 인재 선별, 면접 일정 조율, 교육 자료 개발, 피드백 수집, 성과 평가 수행 등 HR 프로세스를 간소화합니다.
- **HR 에이전트에 작업(Action) 통합하기**: Copilot Studio에서 에이전트를 생성하여 직원들이 Microsoft 365 Copilot을 통해 구체적이고 체계적인 추천서 양식을 제출할 수 있도록 지원합니다.
- **HR 작업 수행을 위해 Microsoft Copilot Studio의 자율 기능 활성화하기**: Microsoft Copilot Studio를 사용하여 추천 요약을 생성하고, 수상 이력과 제출된 추천서를 효율적으로 확인할 수 있는 기능을 구현합니다.
- (선택) **Microsoft 365 Copilot에서 시맨틱 인덱스(Semantic Index) 살펴보기**: 시맨틱 인덱스는 컨텍스트 기반 데이터 검색을 향상시키고, 지능형 인사이트를 제공하며, Microsoft Copilot 도구와 원활하게 통합되어 생산성과 의사결정을 개선할 수 있도록 지원합니다.

## 사전 요구 사항

참가자는 다음 사항에 대한 기본적인 이해 또는 경험이 있어야 합니다:

- Microsoft 365 생태계 및 해당 애플리케이션에 대한 기본적인 이해.
- Microsoft 365 Copilot 및 해당 인터페이스에 대한 경험.
- AI 생성 콘텐츠를 위한 프롬프트 작성 경험.
- Copilot Studio 또는 Power Platform 도구를 활용한 워크플로 자동화에 대한 지식.
- 온보딩(Onboarding), 성과 추적 등 직원 관련 프로세스에 대한 이해.
- 직원들의 인사 이동, 포상, 직원 몰입도와 같은 HR 실무에 대한 이해.

## 구성 요소 설명

- **M365 Copilot**: M365 Copilot은 Word, Excel, PowerPoint, Outlook, Teams에 AI의 강력한 기능을 통합하여 생산성과 창의성을 향상시키는 도구 입니다.
- **Copilot Studio**: Copilot Studio는 비즈니스 요구사항을 기반으로 AI Copilot을 직접 구축하고, 사용자 정의하며, 관리할 수 있는 도구 입니다.
