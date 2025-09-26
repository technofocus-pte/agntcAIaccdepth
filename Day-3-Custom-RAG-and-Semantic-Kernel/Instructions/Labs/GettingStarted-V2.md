# 실습 3일차

# Azure AI Foundry와 Semantic Kernel을 활용한 맞춤형 RAG 애플리케이션 개발

### 예상 소요 시간: 4시간

## 개요

이 실습에서는 **Azure AI Foundry SDK**를 사용하여 맞춤형 RAG(Retrieval-Augmented Generation, 검색 증강 생성) 애플리케이션을 구축하는 방법을 배웁니다. 관련 데이터를 인덱싱하고 검색하는 RAG 파이프라인을 구현하여 AI가 생성하는 응답의 품질을 향상시키게 됩니다. 또한 검색 정확도, 응답 품질, 효율성을 측정하여 시스템 성능을 평가하고 최적화하는 방법도 학습합니다. 실습이 끝나면 Azure AI 기능을 통합한 완전한 RAG 솔루션을 구현하게 됩니다. **Azure AI Foundry SDK**와 함께 **Semantic Kernel**을 활용하여 동적인 프롬프트 기반 상호작용을 생성하고, 시간 및 날씨와 같은 유용한 **플러그인(plugin)**을 통합하여 챗봇의 기능을 확장합니다.
실습을 마치면 Azure AI의 기능과 Semantic Kernel의 플러그인 생태계를 활용한 확장 가능한 RAG 솔루션을 구축하는 실제 경험을 얻게 됩니다.

## 목표

이 실습을 통해 다음을 수행하게 됩니다. 

- **RAG 파이프라인 구축**: 참가자는 검색 증강 생성(RAG) 파이프라인을 구축하여 AI 응답을 향상시키는 방법을 학습합니다. 지식 소스를 인덱싱하고, 검색 파이프라인을 구현하며, 관련 데이터로 보강된 응답을 생성합니다. 또한 성능 모니터링을 위한 텔레메트리 로깅(telemetry logging)을 통합합니다.
- **RAG 성능 평가 및 최적화**: 이 실습 과제에서는 참가자들이 검색 증강 생성(RAG, Retrieval-Augmented Generation) 시스템의 성능을 평가하고 최적화하는 방법을 학습니다. 참가자들은 **Azure AI 평가 도구(Azure AI evaluators)**를 활용하여 검색 정확도를 평가하고, 응답 품질을 측정하기 위한 평가 방법을 구현하며, 결과를 해석하여 시스템의 효율성을 미세 조정(fine-tune)하는 방법을 학습합니다.
- **Semantic Kernel 기초 학습**: Semantic Kernel을 GPT-4o와 연결한 간단한 스타터 애플리케이션을 통해 지능형 챗 경험을 구축합니다.
- **Semantic Kernel 플러그인 활용**: 맞춤형 Semantic Kernel 플러그인을 구축하고 통합하여 챗봇의 기능을 확장합니다.

## 사전 요구 사항

참가자는 다음 내용에 익숙해야 합니다:

- Azure AI Foundry 포털 사용 경험
- 대규모 언어 모델(LLM)의 기본 개념과 응용
- 플러그인, 플래너(planner), AI 스킬(skill)과 같은 Semantic Kernel 개념

## 구성 요소 설명

- **Azure AI Foundry**: Azure AI Foundry는 AI 모델, 벡터 데이터베이스, 그리고 RAG(Retrieval-Augmented Generation) 파이프라인의 배포 및 관리를 위한 필수 리소스를 포함한 기반 인프라를 제공합니다. 이 플랫폼은 검색 시스템을 활용하여 AI가 생성하는 응답의 정확도와 관련성을 향상시키는 AI 애플리케이션을 구축할 수 있도록 지원합니다.
- **Azure OpenAI**: Azure OpenAI Service는 OpenAI의 강력한 언어 모델에 대한 REST API 액세스를 제공하며, 데이터를 통합하여 맞춤형이면서도 안전한 상호작용을 가능하게 합니다.
- **Azure OpenAI 모델**: Azure OpenAI 모델은 다양한 AI 애플리케이션에 활용할 수 있는 사전 학습된(pre-trained) 및 맞춤형 대규모 언어 모델(LLM)을 제공합니다. 이러한 모델은 정교하게 설계된 프롬프트를 기반으로 상황에 맞는(contextually relevant) 맞춤형 콘텐츠를 생성함으로써 강력한 AI 기반 솔루션을 구축하는 데 도움을 줍니다.
- **Azure AI Search**: Azure AI Search는 이전에 Azure Cognitive Search로 알려졌던 엔터프라이즈급 정보 검색 시스템으로, 데이터를 저장, 인덱싱, 검색할 수 있는 기능을 제공합니다. 이를 통해 강력한 검색 증강 생성(RAG) 애플리케이션과 기업용 검색 엔진을 구현할 수 있습니다.
- **Visual Studio Code**: RAG 애플리케이션 개발을 위한 통합 개발 환경(IDE)으로, 검색 메커니즘과 AI 응답 생성을 통합하는 데 사용됩니다.
- **검색 증강 생성(RAG) 파이프라인**: 검색 증강 생성(RAG, Retrieval-Augmented Generation) 파이프라인은 외부 지식을 생성 과정에 통합함으로써 AI가 생성하는 응답의 품질을 향상시킵니다. 이 파이프라인은 사용자 쿼리에 기반하여 벡터 데이터베이스에서 관련 정보를 검색하고, 이를 AI의 응답에 보강하여 보다 정확하고 맥락에 부합하는 결과물을 생성하도록 돕습니다.
- **평가 및 모니터링 (Azure AI Foundry)**: 모델 성능, 검색 정확도, 응답 품질 등을 추적하여 지속적인 최적화 및 디버깅을 가능하게 합니다.
- **Semantic Kernel**: **LLM, 플러그인, 외부 API**를 연동하여 고급 AI 기능을 구현할 수 있는 AI 오케스트레이션 프레임워크입니다.
- **Python SDK 및 REST API**: **Azure AI Foundry, Semantic Kernel, OpenAI 서비스**를 프로그래밍적으로 연동하는 데 사용됩니다.

