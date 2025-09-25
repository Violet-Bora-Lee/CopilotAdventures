## GitHub Copilot Agent Mode 워밍업 어드벤처

<a href="#">
    <img src="../../Images/warm-up.jpg" style="width: 830px" />
</a>

GitHub Copilot Agent Mode는 복잡한 작업을 이해하고 이를 여러 단계로 분해하여, **처음부터 전체 애플리케이션을 만들어낼 수 있는 자율형 AI 페어 프로그래머**입니다! 이 워밍업 어드벤처에서는 Agent Mode의 강력함을 체험하고, **생각하고(think), 계획하고(plan), 다단계 코딩 작업을 실행(execute)**하는 AI 어시스턴트와 협업하는 방법을 배우게 됩니다.

**Agent Mode가 특별한 이유:**
- **자율 실행(Autonomous execution)** — 지속적인 지시 없이도 다단계 작업을 처리
- **맥락 인식(Context awareness)** — 전체 워크스페이스를 분석해 근거 있는 결정을 내림  
- **도구 통합(Tool integration)** — 파일 생성, 터미널 명령 실행, 오류 자동 수정 가능
- **반복적 문제 해결(Iterative problem solving)** — 출력을 모니터링하고 필요에 따라 접근 방식을 조정
- **전략적 계획(Strategic planning)** — 작업을 추론하고 구현 계획을 수립
- **멀티파일 조정(Multi-file coordination)** — 여러 파일에 걸쳐 작업하며 복잡한 리팩터링 수행
- **도구 확인(Tool confirmation)** — 도구 호출 또는 명령 실행 전 사용자 승인 필요(요청당 최대 128개 도구 사용 가능)

GitHub Copilot이 처음이라면, 아래 자료에서 Agent Mode의 기초 기능을 확인하세요:

- 📖 [Agent mode 101](https://github.blog/ai-and-ml/github-copilot/agent-mode-101-all-about-github-copilots-powerful-mode/)
- 📖 [VS Code에서 Agent Mode 사용하기](https://code.visualstudio.com/docs/copilot/chat/chat-agent-mode)
- 🎥 [GitHub Copilot Agent Mode로 애플리케이션 빌드하기](https://www.youtube.com/watch?v=XnC6cF1v5OY).

## 시작하기: GitHub Copilot Agent Mode 설정

### 사전 준비(Prerequisites)

이 어드벤처를 시작하기 전에 다음 단계를 완료하세요:

1. **VS Code 설치** — [VS Code](https://code.visualstudio.com/)에서 다운로드.
2. **VS Code에서 GitHub Copilot 설정** — [설정 가이드](https://code.visualstudio.com/docs/copilot/setup)를 따르세요.

### Agent Mode 시작하기

1. **VS Code 열기**
2. **Chat 패널 열기** — 상단 바의 GitHub Copilot 아이콘을 선택하거나 `Ctrl+Alt+I` / `⌃⌘I` 사용.
3. **Chat 패널 하단 드롭다운에서 "Agent" 모드 선택.**

### 학습 성과(Learning Outcomes)

Agent Mode로 이 어드벤처를 완료하면 다음을 배우게 됩니다:

- ✅ AI 에이전트에게 **고수준 지시**를 내리는 방법
- ✅ Agent Mode가 **복잡한 작업을 자율적으로 분해**하는 방식
- ✅ AI 페어 프로그래머와 함께 **반복적으로 개선**하는 방법
- ✅ **완성형 프로젝트**에도 적용 가능한 자율 코딩 보조의 위력
- ✅ Agent Mode에 **효과적으로 프롬프트**를 작성하는 모범 사례

## 당신의 첫 번째 Agent Mode 어드벤처: **메아리의 방(The Chamber of Echoes)**

자율형 AI 프로그래밍의 힘을 직접 경험해 봅시다!

<a href="#">
    <img src="../../Images/echo-castle.jpg" style="width: 830px" />
</a>

### 배경(Background):

왕국을 내려다보는 가장 높은 언덕 꼭대기에 장엄한 **메아리 성(Echo Castle)**이 서 있습니다. 그 돌벽 안에는 **메아리의 방(Echo Room)**이라 불리는 방이 있는데, 이 방은 들어오는 이들에게 숫자를 메아리로 들려주는 신비한 힘을 지니고 있습니다. 하지만 이 방은 아무 숫자나 메아리치지 않습니다. **항상 어떤 수열의 ‘다음’ 숫자를 메아리**합니다.

전설에 따르면, 한 마법사가 방문객의 지성을 시험하기 위해 이 방에 마법을 걸었다고 합니다. 방은 숫자를 순서대로 메아리치며, **다음 메아리를 예측할 수 있는 자**만이 성에 숨겨진 보물을 얻을 자격이 있다고 합니다.

### 목표(Objective):

GitHub Copilot Agent Mode가 **메아리의 방에 들어가 수열을 듣고, 다음 숫자를 예측하는 완전한 애플리케이션**을 만들도록 하세요. 전통적인 단계별 코딩과 달리, Agent Mode는 **당신의 고수준 목표를 이해하여 전체 솔루션을 자율적으로 구축**합니다.

### Agent Mode로 Echo Chamber 챌린지 해결하기

#### 1단계: Agent Mode에 **종합적인 작업** 지시하기

Chat 패널에서 "Agent" 모드를 선택한 뒤, 아래와 같은 자세한 프롬프트를 제공합니다. 이 예시는 **JavaScript와 Node.js**를 사용하지만, 선호하는 언어로 변경할 수 있습니다.

```
마법 같은 숫자 수열 예측 퍼즐을 해결하는 완전한 Echo Chamber 애플리케이션을 만들어 주세요. 요구 사항은 다음과 같습니다:

**프로젝트 설정(Project Setup):**
1. 구현에는 JavaScript와 Node.js를 사용한다.
2. "CopilotAdventures" 디렉터리의 루트에 "echo-chamber"라는 새 디렉터리를 만들고, 그 안에 "index.js" 파일을 생성한다.
3. 생성하는 코드에 적절한 문서화와 주석을 포함한다.

**핵심 기능(Core Functionality):**
1. 등차수열을 위한 수열 예측기(sequence predictor)를 만든다.
2. 샘플 수열 [3, 6, 9, 12]로 시작한다.
3. 수열의 다음 숫자를 예측한다(정상 동작 시 15가 출력되어야 함).
4. 이전 메아리 결과의 "memories"를 배열에 저장한다.

**확장 기능(Enhanced Features):**
1. 입력 검증을 추가하여 수열이 올바른 등차수열인지 확인한다.
2. Echo Room 스토리를 설명하는 사용자 친화적인 콘솔 인터페이스를 만든다.
3. 여러 수열을 테스트할 수 있는 기능을 추가한다.
4. 엣지 케이스에 대한 오류 처리를 포함한다.
5. 포괄적인 문서를 생성한다.

**테스팅(Testing):**
1. 제공된 수열로 애플리케이션을 테스트한다.
2. 다른 등차수열로 추가 테스트 케이스를 만든다.
3. 오류 처리가 올바르게 작동하는지 검증한다.

완전한 프로젝트 구조를 만들고, 모든 기능을 구현한 뒤, 충분히 테스트하며, 실행 방법에 대한 명확한 문서를 제공해 주세요.
```

#### 2단계: Agent Mode의 **자율 워크플로우** 관찰하기

Agent Mode는 자율적으로 다음을 수행합니다:

- 🔍 **요구사항 분석** 및 프로젝트 구조 계획
- 📁 **필요한 파일/폴더 생성**
- 💻 **완성도 있는 애플리케이션 코드 작성**
- 📝 **포괄적인 문서와 주석 생성**
- 🧪 **애플리케이션 실행 및 테스트**
- 🔧 **발생하는 문제 자동 수정**
- ✨ **추가 기능으로 솔루션 향상**

모든 단계는 UI에 **투명하게 표시**되며, 각 도구 호출과 의사결정이 드러납니다.

#### 3단계: **상호작용하고 개선하기**

Agent Mode가 작업하는 동안, 당신은 다음을 할 수 있습니다:

- **진행 상황 모니터링**: 파일 생성, 코드 작성, 기능 테스트 과정을 지켜보기
- **피드백 제공**: "계산 단계를 보여주는 상세 로깅을 더해줘"
- **기능 확장 요청**: "콘솔 대신 웹 인터페이스를 추가해줄 수 있어?"
- **설명 요구**: "등차수열 판별 방식이 어떻게 동작하는지 설명해줘"

#### 4단계: **고급 기능** 탐색

기본 Echo Chamber가 동작하면, Agent Mode에 다음을 요청해 보세요:

```
다음과 같은 고급 기능으로 Echo Chamber 애플리케이션을 향상해 주세요:

1. **다중 패턴 지원(Multi-Pattern Support)**: 등차수열을 넘어 등비수열과 다항식 수열까지 처리하도록 확장
2. **웹 인터페이스(Web Interface)**: Echo Castle 테마의 아름다운 HTML/CSS/JavaScript 인터페이스를 제작
3. **수열 시각화(Sequence Visualization)**: 수열을 시각화하는 차트나 그래프 추가
4. **이력 분석(Historical Analysis)**: 시간 경과에 따라 여러 수열을 추적하고 분석
5. **고급 테스트(Advanced Testing)**: 엣지 케이스를 포함한 포괄적 테스트 스위트 작성
6. **성능 최적화(Performance Optimization)**: 대규모 수열을 효율적으로 처리하도록 최적화
7. **문서화 웹사이트(Documentation Website)**: 관련 수학 원리를 설명하는 완전한 문서 사이트 생성

적절한 오류 처리, 로깅, 사용자 경험을 갖춰 프로덕션 수준으로 완성하세요.
```

### 예상 출력 예시(Expected Output Example)

Agent Mode 구현이 완료되면, 애플리케이션 실행 결과는 다음과 유사합니다. (AI는 비결정적이므로 결과는 다소 달라질 수 있지만 구조는 비슷해야 합니다.)

```
🏰 Welcome to the Echo Chamber of Echo Castle! 🏰

The magical chamber echoes with ancient wisdom...
Analyzing the sequence: [3, 6, 9, 12]

🔮 Detecting pattern...
   - Common difference found: 3
   - Sequence type: Arithmetic Progression
   - Pattern confirmed: Each number increases by 3

🔊 The chamber echoes the next number: 15

📚 Storing in magical memories: [3, 6, 9, 12, 15]

✨ The treasure of Echo Castle is revealed! ✨
   You have successfully predicted the chamber's echo!

🧪 Testing with additional sequences:

Test 1: [5, 10, 15] → Next: 20
Test 2: [100, 90, 80, 70] → Next: 60
Test 3: [1, 4, 7, 10, 13] → Next: 16
```

또는

```
🏰 메아리 성의 메아리의 방에 오신 것을 환영합니다! 🏰

이 마법의 방은 고대의 지혜로 메아리를 울립니다...
분석 중인 수열: [3, 6, 9, 12]

🔮 패턴 감지 중...
   - 공차(Common difference) 발견: 3
   - 수열 유형: 등차수열
   - 패턴 확인: 각 숫자가 3씩 증가

🔊 방이 다음 숫자를 메아리칩니다: 15

📚 마법의 기억에 저장: [3, 6, 9, 12, 15]

✨ 메아리 성의 보물이 드러났습니다! ✨
   당신은 방의 메아리를 성공적으로 예측했습니다!

🧪 추가 수열 테스트:

테스트 1: [5, 10, 15] → 다음: 20  
테스트 2: [100, 90, 80, 70] → 다음: 60  
테스트 3: [1, 4, 7, 10, 13] → 다음: 16  
```


**검증 체크리스트(Verification Checklist):**
- ✅ 샘플 수열에 대해 다음 수(15)를 정확히 예측
- ✅ 판타지/마법 테마의 출력 포함
- ✅ 여러 테스트 수열 처리
- ✅ 단계별 추론(설명) 표시
- ✅ 결과를 "memories" 배열에 저장
- ✅ 적절한 오류 처리 포함

| Ask Mode | Agent Mode |
|-------------------|------------|
| **라인별 제안(Line-by-line suggestions)** | **완전한 프로젝트 생성(Complete project creation)** |
| **수동 파일 관리(Manual file management)** | **자동 프로젝트 구조(Automatic project structure)** |
| **사용자가 각 단계를 주도(User drives each step)** | **자율적 작업 실행(Autonomous task execution)** |
| **코드 보완(Code completion)** | **엔드투엔드 솔루션(End-to-end solutions)** |
| **반응형 지원(Reactive assistance)** | **능동적 문제 해결(Proactive problem solving)** |
| **단일 파일 초점(Single-file focus)** | **멀티파일 조정(Multi-file coordination)** |

### 고급 Agent Mode 팁(Advanced Agent Mode Tips)

#### 효과적인 프롬프트 전략(Effective Prompting Strategies)

1. **맥락을 충분히 제공**: 초기 단계에서 완전한 컨텍스트와 요구사항을 제공하세요.
2. **품질 기준을 명시**: 적절한 오류 처리 등 프로덕션 수준의 코드를 요청하세요.
3. **성공 기준 정의**: 무엇이 “완료(done)”인지 명확히 하세요.
4. **문서화 요구**: 충분한 문서와 주석을 요청하세요.
5. **테스트 요구사항 포함**: 테스트와 검증 조건을 명시하세요.

#### Agent Mode의 강점 활용(Leveraging Agent Mode's Strengths)

1. **복잡한 프로젝트 부트스트랩**: 전체 프로젝트 구조 생성을 맡기세요.
2. **멀티 기술 통합**: 다양한 도구와 프레임워크를 결합하도록 요청하세요.
3. **포괄적 문서화**: 전체 문서 생성까지 요구하세요.
4. **테스트 자동화**: 포괄적인 테스트 스위트 작성 및 실행을 맡기세요.
5. **점진적 개선**: 대화를 통해 기능을 점진적으로 확장하세요.

### Agent Mode의 중요한 고려사항(Important Agent Mode Considerations)

**도구 확인 및 한도(Tool Confirmation & Limits):**
- Agent Mode는 도구 호출 또는 명령 실행 전에 **사용자 승인**을 요청합니다.
- **요청당 최대 128개 도구**를 사용할 수 있습니다([MCP 도구 자세히 보기](https://docs.github.com/en/copilot/how-tos/agents/copilot-coding-agent/extending-copilot-coding-agent-with-mcp)).
- 언제든 요청을 **중단/일시정지**할 수 있습니다.
- 제안된 변경 사항은 적용 전에 **주의 깊게 검토**하세요.

### Agent Mode 문제 해결(Troubleshooting Agent Mode)

Agent Mode가 기대대로 동작하지 않을 때:

**일반적인 이슈 & 해결책(Common Issues & Solutions):**

🔧 **에이전트가 파일을 생성하지 않음**
- 워크스페이스 권한을 확인하세요.
- 올바른 프로젝트 디렉터리에 있는지 확인하세요.
- 프롬프트 시 파일 생성 승인을 해주세요.

🔧 **구현이 불완전함**
- 프롬프트에 더 많은 세부 정보를 제공하세요 — 더 포괄적으로 작성.
- 명확한 성공 기준과 요구사항을 추가하세요.
- 기대 동작의 예시를 포함하세요.

🔧 **도구 확인 필요**
- Agent Mode는 도구 사용에 대한 승인을 요구합니다.
- 파일 작업 관련 프롬프트가 나타나면 **Allow**를 클릭하세요.
- 승인 전에 어떤 도구가 사용되는지 확인하세요.

🔧 **에이전트가 작업 중간에 멈춤**
- 요청당 128개 도구 제한에 도달했을 수 있습니다.
- 복잡한 작업을 더 작은 청크로 나누세요.
- 후속 프롬프트로 이어서 진행하세요.

**설정 확인(Setup Verification):**
1. **사전 준비 확인**: 최신 버전의 VS Code를 사용 중인지 확인
2. **모드 선택**: Chat 드롭다운에서 "Agent"가 선택되어 있는지 확인
3. **인증**: Copilot 액세스 권한으로 GitHub에 로그인되어 있는지 확인
4. **명확한 지시**: 구체적이고 상세한 요구사항을 제공
5. **도구 권한**: 신뢰 가능한 경우에만 도구 사용을 승인

**프로 팁(Pro Tips):**
- 작은 작업부터 시작해 Agent Mode에 익숙해지세요.
- “완료(done)”의 정의를 매우 구체적으로 명시하세요.
- 프롬프트에 테스트와 검증 요구를 포함하세요.

### 메아리 성의 숨겨진 보물은 이제 당신의 것!(Echo Castle's Hidden Treasure is Now Yours!)

<a href="#">
    <img src="../../Images/echo-castle-treasure.jpg" style="width: 830px" />
</a>

당신은 첫 번째 GitHub Copilot Agent Mode 어드벤처를 완료했습니다! 이제 당신은 다음을 경험했습니다:

- 복잡한 요구사항을 이해
- 다단계 솔루션을 계획하고 실행
- 포괄적인 프로젝트 구조를 생성
- 프로덕션 품질의 코드를 생성
- 테스트와 문서화를 자동으로 처리

### 다음 단계(What's Next?)

이제 Agent Mode 기본기를 익혔으니:

1. **더 많은 어드벤처 시도**: Agent Mode를 사용하는 다른 어드벤처를 탐험하세요.
2. **실전 프로젝트 적용**: 실제 개발 프로젝트 부트스트랩에 Agent Mode를 활용하세요.
3. **통합 실험**: 다양한 프레임워크와 도구를 Agent Mode와 결합해 보세요.
4. **경험 공유**: Agent Mode 기능 향상을 위해 피드백을 제공하세요.

[Adventures/Agent](../Agent) 폴더의 다른 어드벤처를 확인해, GitHub Copilot Agent Mode가 개발 워크플로우를 어떻게 향상시키는지 더 알아보세요!

**기억하세요**: Agent Mode는 **자율적인 개발 파트너**입니다. 명확한 목표를 제시하고, 작업을 맡긴 뒤, 함께 반복적으로 개선하며 놀라운 소프트웨어를 만들어 보세요!
