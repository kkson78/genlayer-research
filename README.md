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



---



