## 루모리아의 천체 정렬 - Agent Mode 어드벤처

<a href="#">
    <img src="../../../Images/lumoria.jpg"  style="width: 830px" />
</a>

### 배경(Background)

광대한 **갈락시아 성운(Galaxia Nebulae)** 속, 루모리아(Lumoria) 항성계에서 수천 년에 한 번 일어나는 희귀한 현상이 곧 발생하려 합니다.  
행성들이 루모리아 태양 주위를 돌며, 마치 춤추듯 일렬로 정렬되는 것입니다.  
이 정렬은 태양 빛이 각 행성에 도달하는 방식에 특별한 영향을 미칩니다. 왜냐하면 앞선 행성이 뒤의 행성에 그림자를 드리우기 때문입니다.

### 목표(Objective)

당신의 임무는 **천체 정렬 중 각 행성이 받는 빛의 강도**를 계산하는 시스템을 만드는 것입니다.  
행성들의 거리와 상대적 위치가 주어지면, 다른 행성의 그림자 때문에 빛의 강도가 줄어드는 행성을 판별해야 합니다.

**이 어드벤처에서는 GitHub Copilot Agent Mode를 활용하는 법을 배우게 됩니다** — 복잡한 작업을 이해하고 여러 단계로 분해하여, 처음부터 완전한 애플리케이션을 만들어낼 수 있는 자율형 AI 어시스턴트입니다!

### 사전 준비(Prerequisites)

시작하기 전에 아래 단계를 완료하세요:

1. **VS Code 설치** — [VS Code](https://code.visualstudio.com/)에서 다운로드  
2. **VS Code에서 GitHub Copilot 설정** — [설정 가이드](https://code.visualstudio.com/docs/copilot/setup) 참고  

### 학습 성과(Learning Outcomes)

이 어드벤처를 Agent Mode로 완료하면 다음을 배우게 됩니다:

- ✅ AI 에이전트에게 **고수준 지시**를 내리는 방법  
- ✅ Agent Mode가 **복잡한 작업을 자율적으로 분해**하는 방식  
- ✅ AI 페어 프로그래머와 함께 **반복적으로 개선**하는 방법  
- ✅ **완성형 프로젝트**에도 적용 가능한 자율 코딩 보조 경험  
- ✅ Agent Mode를 **효과적으로 프롬프트**하는 모범 사례  

### Agent Mode 설정하기

1. **VS Code 열기** 및 GitHub 로그인 확인  
2. **Chat 뷰 열기** — 상단 바의 채팅 아이콘 선택  
3. **Chat 패널 하단 드롭다운에서 "Agent" 모드 선택**  

### 요구 사항(Specifications)

이제 **천체 빛 계산 시스템**의 요구 사항을 정의해 보겠습니다.

1. **행성 데이터(Planetary Data):**
   | 행성 이름   | 거리 (AU) | 크기 (km) |
   |-------------|-----------|-----------|
   | 머큐리아(Mercuria) | 0.4       | 4879      |
   | 어스시아(Earthia)  | 1.0       | 12742     |
   | 마르시아(Marsia)   | 1.5       | 6779      |
   | 비누시아(Venusia)  | 0.7       | 12104     |

2. **빛의 동역학 규칙(Light Dynamics Rules):**
   - 작은 행성이 큰 행성 뒤에 있음 = `None` (완전한 그림자)  
   - 큰 행성이 작은 행성 뒤에 있음 = `Partial` (부분적 빛)  
   - 여러 행성이 그림자를 드리움 = `None (Multiple Shadows)`  
   - 비슷한 크기의 행성이 가까이 있음 = 모두 `Full` 빛 받음  

3. **알고리즘 요구 사항(Algorithm Requirements):**
   - 행성을 태양으로부터 거리 순으로 정렬  
   - 각 행성에 대해, 태양에 더 가까운 행성을 확인  
   - 더 크거나 작은 행성이 몇 개 있는지 계산  
   - 규칙에 따라 빛의 강도를 결정  

### Agent Mode로 어드벤처 해결하기

#### 1단계: Agent Mode에 고수준 작업 지시하기

Chat 패널에서 "Agent" 모드를 선택하고 아래와 같은 프롬프트를 제공합니다:

```
루모리아 항성계를 위한 완전한 천체 빛 강도 계산 시스템을 만들어 주세요. 시스템은 다음을 포함해야 합니다:

1. JavaScript(또는 선호하는 언어)로 콘솔 애플리케이션을 생성한다.
2. 거리와 크기를 포함한 행성 데이터를 정의한다:
   - 머큐리아(Mercuria): 0.4 AU, 4,879 km
   - 어스시아(Earthia): 1 AU, 12,742 km
   - 마르시아(Marsia): 1.5 AU, 6,779 km
   - 비누시아(Venusia): 0.7 AU, 12,104 km
3. 빛의 강도 계산 로직을 구현한다:
   - 행성을 태양으로부터의 거리순으로 정렬
   - 각 행성에 대해, 태양에 더 가까운 더 큰/더 작은 행성의 개수를 계산
   - 그림자 규칙 적용: Full, Partial, None, 또는 None (Multiple Shadows)
4. 각 행성이 받는 빛의 강도를 명확히 표시하도록 결과를 출력한다.
5. 천체 테마의 아름다운 콘솔 출력을 포함한다.
6. 적절한 오류 처리와 문서를 포함한다.
7. 코드를 읽기 쉽고 유지보수 가능하게 작성한다.

프로젝트 구조를 생성하고, 코드를 작성하며, 테스트까지 수행해 주세요.
```

```
Create a complete celestial light intensity calculation system for the Lumoria star system. The system should:

1. Create a console application in JavaScript (or your preferred language)
2. Define the planetary data with distances and sizes:
   - Mercuria: 0.4 AU, 4879 km
   - Earthia: 1 AU, 12742 km  
   - Marsia: 1.5 AU, 6779 km
   - Venusia: 0.7 AU, 12104 km
3. Implement light intensity calculation logic:
   - Sort planets by distance from sun
   - For each planet, count how many larger/smaller planets are closer to sun
   - Apply shadow rules: Full, Partial, None, or None (Multiple Shadows)
4. Display results clearly showing each planet's light intensity
5. Include beautiful console output with celestial theme
6. Add proper error handling and documentation
7. Make the code readable and maintainable

Please create the project structure, write the code, and test it.
```

#### 2단계: Agent Mode 작업 지켜보기

Agent Mode는 자율적으로:

- 🔍 **요구사항 분석** 및 생성할 파일 결정  
- 📁 **필요한 프로젝트 구조 생성**  
- 💻 **완전한 애플리케이션 코드 작성**  
- 🧪 **애플리케이션 실행 및 테스트**  
- 🔧 **문제 발생 시 자동 수정**  

#### 3단계: 상호작용 및 개선

Agent Mode가 작업하는 동안, 당신은:

- **변경 승인 또는 수정 요청**  
- **개선 요구**: "행성 정렬의 SVG 시각화를 추가해줄래?"  
- **설명 요청**: "그림자 계산 알고리즘이 어떻게 작동하는지 설명해줘"  
- **기능 추가**: "사용자가 직접 행성 데이터를 입력할 수 있게 해줘"  

#### 4단계: 고급 기능 탐험

기본 시스템이 동작하면, Agent Mode에 다음과 같은 기능을 요청해 보세요:

```
다음 기능들로 천체 정렬 시스템을 향상해 주세요:
1. 행성 정렬을 시각적으로 표현하는 SVG를 생성
2. 정렬 과정에서 그림자가 어떻게 변하는지 보여주는 애니메이션 추가
3. 그림자 계산의 과학적 정확도를 높이기 위한 개선 사항 반영
4. 이 천체 현상에 대한 상세 보고서 생성
5. 빛 강도 계산 로직에 대한 유닛 테스트 작성
6. 사용자 정의 행성을 가진 다양한 항성계를 지원하도록 확장
```

```
Enhance the celestial alignment system with these features:
1. Create a visual SVG representation of the planetary alignment
2. Add animation showing how shadows change during alignment
3. Include scientific accuracy improvements for shadow calculations
4. Generate detailed reports about the celestial phenomenon
5. Create unit tests for the light intensity calculations
6. Add support for different star systems with custom planets
```


### 예상 출력 예시(Expected Output Example)

Agent Mode 구현이 완료되면, 애플리케이션 실행 시 다음과 유사한 결과가 나옵니다 (AI는 비결정적이므로 약간 다를 수 있음):

```
🌌 루모리아의 천체 정렬 - 빛 강도 분석 🌌

🔬 행성 위치와 그림자 효과 분석 중...

🌟 태양계 정렬:

🌟 루모리아 태양
────🪐 머큐리아 ☀️
───────🪐 비누시아 🌤️
──────────🪐 어스시아 🌤️
───────────────🪐 마르시아 🌑

📊 상세 빛 강도 결과:

행성        | 거리 (AU) | 크기 (km) | 빛 강도            | 설명
───────────────────────────────────────────────────────────────────────────────
머큐리아    | 0.4       | 4879      | Full               | 태양에 가장 가까움 - 그림자 없음
비누시아    | 0.7       | 12104     | Partial            | 작은 행성들이 부분적 그림자 생성
어스시아    | 1.0       | 12742     | Partial            | 작은 행성들이 부분적 그림자 생성
마르시아    | 1.5       | 6779      | None (Multiple Shadows) | 두 개의 큰 행성이 그림자 생성

📈 정렬 요약:
Full: 1개 행성
Partial: 2개 행성
None (Multiple Shadows): 1개 행성

🌑 가장 큰 영향을 받은 행성: 마르시아 (None - Multiple Shadows)

✨ 천체 정렬 분석이 완료되었습니다! ✨
```

```
🌌 Celestial Alignment of Lumoria - Light Intensity Analysis 🌌

🔬 Analyzing planetary positions and shadow effects...

🌟 Solar System Alignment:

🌟 Lumorian Sun
────🪐 Mercuria ☀️
───────🪐 Venusia 🌤️
──────────🪐 Earthia 🌤️
───────────────🪐 Marsia 🌑

📊 Detailed Light Intensity Results:

Planet      | Distance (AU) | Size (km) | Light Intensity | Explanation
──────────────────────────────────────────────────────────────────────────────────────────
Mercuria    | 0.4           | 4879      | Full            | Closest to sun - no shadows possible
Venusia     | 0.7           | 12104     | Partial         | Smaller planets create partial shadow
Earthia     | 1             | 12742     | Partial         | Smaller planets create partial shadow
Marsia      | 1.5           | 6779      | None (Multiple Shadows) | Multiple larger planets (2) create complete shadow

📈 Alignment Summary:
Full: 1 planet(s)
Partial: 2 planet(s)
None (Multiple Shadows): 1 planet(s)

🌑 Most affected planet: Marsia (None (Multiple Shadows))

✨ The celestial alignment analysis is complete! ✨
```

**검증 체크리스트(Verification Checklist):**
- ✅ 태양으로부터 거리순 정렬 확인  
- ✅ 그림자 규칙에 따라 빛 강도 계산  
- ✅ 마르시아가 "None (Multiple Shadows)"로 식별됨  
- ✅ 태양계 정렬 시각화 표시  
- ✅ 각 결과에 대한 상세 설명 제공  
- ✅ 종합 분석 통계 포함  

### Agent Mode 팁

<a href="#">
    <img src="../../../Images/agent-mode-tips.jpg"  style="width: 830px" />
</a>

#### 효과적인 프롬프트 전략

1. **맥락 충분히 제공** — Agent Mode에 전체 컨텍스트와 요구사항 제공  
2. **선호 사항 명시** — 선호 언어, 프레임워크, 패턴 언급  
3. **목표 명확화** — "완료(done)"의 정의 명시  
4. **모범 사례 요청** — 유지보수성 좋고 문서화된 코드 요청  

#### Agent Mode의 자율성 활용

1. **작업 맡기기** — 방해하지 않고 다단계 작업을 완료하게 두기  
2. **검토 및 승인** — 제안된 변경사항을 적용 전 확인  
3. **자연스러운 반복** — 필요 시 개선 또는 수정 요청  
4. **학습 기회** — Agent Mode가 문제를 구조화하고 해결하는 방식 관찰  

### 중요한 고려사항

**도구 확인 및 제한:**
- Agent Mode는 도구 호출/명령 실행 전에 **승인**이 필요합니다  
- 요청당 최대 128개 도구 사용 가능  
- 언제든 요청을 **중단/일시정지** 가능  
- 변경 사항은 항상 검토 후 적용  

### 문제 해결(Troubleshooting)

Agent Mode가 기대대로 작동하지 않을 경우:

**일반적인 문제 & 해결책:**

🔧 **파일이 생성되지 않음**
- 워크스페이스 권한 확인  
- 유효한 프로젝트 디렉터리인지 확인  
- 프롬프트 시 파일 생성 승인  

🔧 **불완전한 구현**
- 프롬프트에 더 많은 세부 사항 제공  
- 성공 기준 및 요구사항을 명확히 추가  
- 기대 동작 예시 포함  

🔧 **도구 승인 필요**
- 도구 사용 승인 필요  
- 파일 작업 시 "Allow" 클릭  
- 어떤 도구가 사용되는지 확인  

🔧 **작업 중단**
- 요청당 128개 도구 제한에 도달했을 수 있음  
- 복잡한 작업을 더 작은 단위로 나눔  
- 후속 프롬프트로 이어서 진행  

**설정 확인:**
1. **VS Code 버전 확인** — 최신 버전인지 확인  
2. **설정 검증** — `chat.agent.enabled` 체크 여부 확인  
3. **모드 선택** — Chat 드롭다운에서 "Agent" 모드 선택  
4. **GitHub 로그인** — Copilot 액세스 확인  
5. **도구 권한** — 승인 요청 시 반드시 확인  

**프로 팁(Pro Tips):**
- 작은 작업부터 시작해 Agent Mode에 익숙해지기  
- "완료(done)"의 정의를 구체적으로 작성  
- 프롬프트에 테스트 및 검증 요구 포함  

### 다음 단계(What's Next?)

이 어드벤처 후:  

1. **고급 어드벤처 시도** — 더 복잡한 시나리오 도전  
2. **사용자 정의 도구/확장 실험** — Agent Mode와 통합  
3. **실제 프로젝트 적용** — 완전한 애플리케이션 제작에 최적  
4. **경험 공유 및 피드백 제공** — Agent Mode 개선에 기여  

**기억하세요**: Agent Mode는 **자율적인 코딩 파트너**입니다.  
명확한 목표를 주고, 실행을 맡기며, 반복적으로 개선하여 놀라운 소프트웨어를 함께 만들어가세요!
