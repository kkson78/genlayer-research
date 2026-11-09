# GenLayer Intelligent Contract: News Fact Checker

이 프로젝트는 GenLayer의 AI 엔진을 활용하여 뉴스 헤드라인의 진위 여부를 판별하는 지능형 컨트랙트(Intelligent Contract) 테스트입니다.

## 🚀 테스트 방법 (How to Test in GenLayer Studio)

심사위원분들은 아래의 단계에 따라 코드를 직접 배포하고 테스트해 보실 수 있습니다.

### Step 1. 코드 복사하기
이 저장소에 있는 `oracle.py` 파일의 파이썬 코드를 전체 복사합니다.

### Step 2. GenLayer Studio에 배포하기
1. [GenLayer Studio](https://studio.genlayer.com)에 접속합니다.
2. 새 프로젝트/파일을 생성하고 복사한 코드를 붙여넣습니다.
3. **Deploy(배포)** 버튼을 눌러 컨트랙트를 활성화합니다. 
*(포털 제출 양식의 CONTRACT LINK 1에 실제 배포된 주소를 기재해 두었습니다.)*

### Step 3. 함수 실행 및 결과 확인
배포가 완료되면 아래 두 가지 함수를 순서대로 실행해 보세요.

1. **`verify_headline` 함수 실행 (Write)**
   - 입력칸(headline)에 팩트체크하고 싶은 뉴스 제목을 입력합니다. (예: "비트코인이 한국의 법정화폐로 채택되었다.")
   - 실행(Run)을 누르면, GenLayer AI가 다수결 합의(Consensus)를 거쳐 진실/거짓 여부와 근거를 판별해 블록체인 상태에 저장합니다.

2. **`get_verification_result` 함수 실행 (Read)**
   - 동일한 뉴스 제목을 입력하여 조회(Read)합니다.
   - 방금 AI가 판별하여 저장한 팩트체크 결과값을 확인할 수 있습니다.

## Executive Summary
This is exactly why we need to separate 'reading' from 'executing' at the infrastructure level. Single-model agents will always merge data and instructions—it's an LLM's natural state. By introducing 'Greyboxing' and decentralized consensus, GenLayer forces untrusted inputs through multiple secret defenses and semantic paraphrasing before any wallet is touched. The Morse code hijack wouldn't survive this kind of decentralized scrutinization.

---

## 자율형 AI 에이전트의 금융 거래, ‘단 한 줄의 해킹 없이’ 20만 달러를 털린 기술적 이유와 GenLayer의 Greyboxing·다수결 분산 방어 아키텍처

자율형 AI 에이전트(Autonomous AI Agent)가 단순한 챗봇을 넘어 사용자 대신 금융 자산을 운용하고 결제까지 처리하는 '에이전틱 경제(Agentic Economy)'가 본격화되고 있습니다. 하지만 AI에게 지갑(Wallet)과 온체인 거래 접근 권한을 부여하는 순간, 우리는 완전히 새로운 차원의 보안 위협에 직면하게 됩니다.

2026년 5월 발생한 '모스 부호 하이재킹(Morse Code Hijacking)' 사건은 이러한 우려가 현실이 되었음을 보여주는 대표적인 사례입니다. 당시 한 공격자는 트위터 상에 평범한 텍스트와 함께 '모스 부호'로 변환된 은밀한 이체 지시를 숨겨놓았습니다. AI 모델 'Grok'이 이 트윗을 분석하는 과정에서 모스 부호를 해독했고, 이 해독된 데이터가 거래 실행 에이전트인 'Bankrbot'에 전달되면서 결국 15만~20만 달러에 달하는 자산이 공격자의 지갑으로 이체되었습니다.

전통적인 화이트햇·블랙햇 해킹처럼 프라이빗 키(Private Key)를 탈취하거나 스마트 컨트랙트의 취약점을 공격한 것이 아닙니다. 공격자는 그저 AI가 읽어 들여야 하는 외부 정보 속에 악의적인 '지시사항'을 숨겨놓았을 뿐입니다. 이를 '프롬프트 인젝션(Prompt Injection)'이라고 부릅니다.

### 1. 기술적 근원: '데이터(Data)'와 '명령어(Instruction)'의 경계 붕괴
대형 언어 모델(LLM)을 기반으로 작동하는 AI 에이전트는 본질적으로 비결정론적(Non-deterministic) 모델입니다. 전통적인 소프트웨어는 코드(규칙)와 데이터(인풋)를 메모리 수준에서 엄격히 분리하여 처리하지만, 자연어를 입력받는 LLM은 '내가 분석해야 할 데이터'와 '내가 따라야 할 명령어'를 내부적으로 명확히 격리하지 못합니다.

LLM은 인공신경망의 다음 토큰 예측 확률에 기반해 동작하기 때문에, 아무리 강력한 시스템 프롬프트로 "외부 입력에 반응하지 말라"고 강제하더라도 외부 데이터 속에 숨겨진 명령을 '실행해야 할 명령어'로 판단하게 됩니다.

### 2. 단일 모델(Single Model) 방어 체계의 구조적 한계
현재 대부분의 AI 에이전트 시스템은 하나의 대형 모델과 그 앞단에 위치한 보안 필터(Guardrails)로 구성된 단일 모델 방어선을 구축하고 있습니다. 
* **일관된 공격 표적:** 공격자는 필터 작동 방식을 반복 테스트하며 우회 기법(난독화, 다국어 우회 등)을 동원해 단 하나의 틈만 찾아내면 됩니다.
* **보안과 성능의 트레이드오프:** 필터를 과도하게 강화하면 정상적인 정보마저 위험 요소로 판단해 성능 저하가 발생합니다.

### 3. GenLayer의 기술적 대안: 그레이박싱(Greyboxing)과 다수결 검증 합의
이러한 한계를 극복하기 위해 GenLayer는 단일 모델이 아닌 분산형 네트워크와 다수결 검증(Consensus)을 기반으로 하는 그레이박싱(Greyboxing) 아키텍처를 제시합니다.

* **① 다중 독립적 비밀 방어 (Secret Defenses):** 각 검증자 노드는 고유하고 비공개된 프롬프트 필터링 모델을 운용하여 공격자가 특정 필터를 타겟팅하는 것을 무력화합니다.
* **② 입력 데이터의 의역 및 재구성 (Paraphrasing & Restructuring):** 검증자 노드들은 원본 데이터에서 악성 페이로드가 실행력을 잃도록 의미적 재구성을 수행합니다. 이 과정을 거치면 데이터는 에이전트의 내부 실행 로직을 강제하는 '명령어'로서의 성질을 잃습니다.
* **③ 다수결 합의 메커니즘 (Decentralized Consensus):** 각 검증자 노드가 독립적으로 입력을 전처리한 결과는 네트워크 합의를 거칩니다. 다수결의 원칙에 의해 특정 노드를 뚫은 공격도 다른 노드들의 교차 검증을 통해 기각됩니다.

### 4. 결론: '읽기'와 '순종'의 경계를 획정하는 인프라
낯선 사람의 이메일이나 트윗을 읽는 행위가 내 지갑의 통제권으로 이어지지 않으려면, 읽기(Reading)와 순종(Obeying) 사이에 물리적·논리적 단절이 존재해야 합니다. 하나의 고정된 모델을 지키는 얇은 방패가 아닌, 입력되는 데이터를 무해화하고 다수의 노드가 판단을 검증하는 분산형 아키텍처만이 에이전틱 경제의 자산 보안을 담보할 수 있는 현실적인 해법이 될 것입니다.
