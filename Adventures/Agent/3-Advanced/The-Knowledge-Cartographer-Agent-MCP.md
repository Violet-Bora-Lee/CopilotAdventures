# 지식 지도 제작자(The Knowledge Cartographer) - Agent Mode + MCP 어드벤처

<a href="#">
    <img src="../../../Images/knowledge-cartographer.jpg" style="width: 830px" />
</a>

### 배경(Background)

광대한 **아카식 아카이브(Akashic Archives)**의 디지털 영역 속에는 고대 지식의 파편들이 수많은 웹 도메인에 흩어져 있습니다.  
이 파편들은 기사, 논문, 디지털 아카이브 속에 숨어 있으며, 당신은 **지식 지도 제작자(Knowledge Cartographer)**로 선택되어 이 조각들을 발견하고 추출하여, 개념과 아이디어, 지혜 사이의 숨겨진 연결을 드러내는 지식 그래프로 엮어야 합니다.

**대도서관 위원회(The Great Library's Council)**는 당신에게 **전지적 코드(Ominscient Codex)**를 구축하라는 임무를 내렸습니다.  
이 시스템은 웹을 탐험하고, 통찰을 수집하며, 이를 검색 가능한 지식 기반으로 정리하고, 모든 인간 이해를 연결하는 보이지 않는 실을 드러내야 합니다.

### 목표(Objective)

당신의 임무는 **웹 탐색의 힘과 지능적인 로컬 지식 조직을 결합한 종합적인 지식 발견 및 매핑 시스템**을 만드는 것입니다.  
여러 출처에서 정보를 수집하고, 개념 사이의 관계를 식별하며, 탐색 가능한 지식 그래프를 만드는 **자율형 연구 어시스턴트**를 구축해야 합니다.

**이 어드벤처에서는 GitHub Copilot Agent Mode와 MCP(Model Control Protocol) 도구**를 함께 사용하는 법을 배우게 됩니다.  
즉, 웹 검색 및 파일 시스템 작업을 위해 외부 MCP 도구와 AI 기능을 확장합니다!

### 사전 준비(Prerequisites)

시작하기 전에 다음 단계를 완료하세요:

1. **VS Code 설치** — [VS Code](https://code.visualstudio.com/) 최신 버전 다운로드  
2. **VS Code에서 GitHub Copilot 설정** — [설정 가이드](https://code.visualstudio.com/docs/copilot/setup) 참고  
3. **MCP 서버 구성** — 확장 기능을 위한 MCP 서버 설정:  
   - **Web Search MCP 서버** — 웹 전반의 지식을 발견. [MCP 갤러리](https://code.visualstudio.com/mcp)에서 `MCP FireCrawl` 서버 설치  
   - **File System MCP 서버** — 로컬 지식 정리 및 저장. `MCP File System` 서버 설치  

### 학습 성과(Learning Outcomes)

이 어드벤처를 통해 배우는 것:

- ✅ MCP 도구와 AI 개발 통합 방법  
- ✅ 웹 탐색과 로컬 지식 관리 결합 시스템 설계  
- ✅ 지식 그래프와 관계 매핑 생성 방법  
- ✅ 자율 연구 워크플로우 설계  
- ✅ MCP 통합 및 오류 처리 모범 사례  

### Agent Mode + MCP 설정하기

1. **VS Code 열기** 및 GitHub 로그인 확인  
2. **MCP 서버 구성** — 3가지 방법 중 선택:  

   **방법 A: 큐레이션된 목록에서 직접 설치**  
   - GitHub Copilot 열고 "Agent" 모드 선택  
   - 채팅 뷰에서 🛠️ 아이콘 클릭  
   - "Add More Tools..." → "Add MCP Server" 선택  
   - `Firecrawl` 설치 후, `File System MCP Server`도 설치  

   **방법 B: 워크스페이스 구성**  
   - 루트 디렉토리에 `.vscode/mcp.json` 생성  
   - 서버 설정 추가 (예시는 아래 `샘플 MCP 설정` 참조)  

   **방법 C: 사용자 구성(User Configuration)**  
   - 명령 팔레트(`Ctrl+Shift+P`/`Cmd+Shift+P`) → "MCP: Open User Configuration" 실행  
   - 전역 MCP 서버 구성  

3. **MCP 통합 확인**  
   - Copilot 아이콘 클릭 후 "Agent" 모드 선택  
   - MCP 도구 목록에서 `Firecrawl`과 `File System` 확인  
   - 보이지 않는다면 MCP 서버가 실행 중인지 확인  

### 필요한 MCP 도구

🔍 **FireCrawl MCP Server**  
- 목적: 고급 웹 스크래핑 및 콘텐츠 추출  
- 기능: 다중 URL 처리, 데이터 구조화, 병렬 처리  
- 활용: 리서치, 웹 데이터 추출, 소스 분석  
- 패키지: `firecrawl-mcp` (Mendable AI 유지보수)  

📁 **File System MCP Server**  
- 목적: 로컬 지식 파일 관리  
- 기능: 파일 생성, 읽기, 쓰기, 디렉토리 관리  
- 활용: 지식 베이스 저장, 그래프 데이터 보관  
- 패키지: `@modelcontextprotocol/server-filesystem`  

#### 샘플 MCP 설정 (.vscode/mcp.json)

Firecrawl API 키 발급: [https://www.firecrawl.dev/app/api-keys](https://www.firecrawl.dev/app/api-keys)

```json
{
  "servers": {
      "firecrawl": {
         "command": "npx",
         "args": ["-y", "firecrawl-mcp"],
         "env": {
            "FIRECRAWL_API_KEY": "${input:fireCrawlApiKey}"
         }
      },
      "filesystem": {
         "command": "npx",
         "args": ["-y", "@modelcontextprotocol/server-filesystem", "${workspaceFolder}"]
      }
   },
   "inputs": [
      {
         "type": "promptString",
         "id": "fireCrawlApiKey",
         "description": "Firecrawl API Key",
         "password": true
      }
   ]
}
```

**보안 참고**: API 키 같은 민감 데이터는 하드코딩하지 말고 `${input:variableName}` 입력 플레이스홀더 사용.

### 요구 사항(Specifications)

**지식 지도 제작자 시스템**은 다음 기능을 포함해야 합니다:

1. **지식 발견 엔진**  
   - FireCrawl MCP를 통한 웹 스크래핑  
   - 다중 URL 처리 및 배치 스크래핑  
   - 주제 관계 식별 및 소스 분석  

2. **지식 그래프 빌더**  
   - 콘텐츠에서 개체 추출  
   - 개념 관계 매핑  
   - 그래프 데이터 구조 구현  
   - 시각화 기능  

3. **로컬 지식 베이스**  
   - File System MCP로 파일 관리  
   - JSON/Markdown 등 구조화된 저장  
   - 검색 및 검색 기능 지원  

4. **탐색 인터페이스**  
   - CLI 기반 탐색 기능  
   - 그래프 탐색 및 관계 조회  
   - 원본 소스와 메타데이터 표시  
   - 다양한 포맷으로 내보내기  

### Agent Mode + MCP로 문제 해결하기

#### 1단계: MCP 통합 작업 프롬프트 제공

```
GitHub Copilot Agent Mode와 MCP 도구를 사용해 완전한 Knowledge Cartographer 시스템을 만들어 주세요. 이 작업은 두 개의 단계(Phase)로 진행됩니다:

PHASE 1: MCP 도구로 지식 수집 및 정리
먼저, 구성해 둔 Firecrawl 및 server-filesystem MCP 서버와 함께 Agent Mode를 사용하여 지식 데이터를 수집·정리하세요.

1. FireCrawl MCP Server 도구 사용:
   - "양자 컴퓨팅(quantum computing)", "인공지능(artificial intelligence)" 같은 주제에 대한 웹 콘텐츠를 스크래핑한다.
   - 스크래핑한 콘텐츠에서 핵심 엔터티, 개념, 관계를 추출한다.
   - 콘텐츠 품질 및 출처 신뢰도를 분석한다.

2. File System MCP Server 도구 사용:
   - 워크스페이스 루트에 구조화된 지식 베이스 디렉터리 `./akashic-archives-demo`를 생성한다.
   - 데이터를 `topics/`와 `indexes/` 하위 디렉터리로 조직한다.
   - 엔터티, 관계, 출처를 JSON(`entities.json`, `relationships.json`, `sources.json`)으로 저장한다.
   - 각 지식 도메인에 대한 메타데이터와 인덱스 파일을 생성한다.

PHASE 2: 지식 베이스 탐색 애플리케이션 만들기
조직된 데이터를 읽고 분석하는 Node.js/JavaScript 애플리케이션을 만든다. Node.js의 `fs`, `path`, `readline` 모듈만 사용하고, 외부 라이브러리나 프레임워크는 사용하지 않는다.

3. 지식 베이스 리더(Reader) 구축:
   - MCP 도구가 만든 구조화된 JSON 파일을 읽는다.
   - `./akashic-archives-demo`에서 엔터티, 관계, 출처 정보를 로드한다.
   - 복수의 지식 도메인/토픽을 지원한다.

4. 지식 그래프 분석 구현:
   - 엔터티 간 관계를 분석한다.
   - 연결 패턴과 강도를 식별한다.
   - 개념 클러스터와 연관성을 탐색한다.

5. 대화형 탐색 인터페이스 만들기:
   - 지식 도메인을 탐색하는 커맨드라인 인터페이스(CLI)를 제공한다.
   - 토픽 로드, 엔터티 연결 찾기, 관계 탐색 등의 명령을 제공한다.
   - 원본 출처 자료와 메타데이터를 표시한다.
   - 신비로운(mystical) 테마의 보기 좋은 콘솔 출력을 제공한다.

6. 포괄적인 오류 처리와 문서화를 추가한다.

핵심 아키텍처: MCP Tools → Structured Files → Your Application
- MCP 도구: 외부 작업(웹 스크래핑, 파일 조직) 담당
- 애플리케이션: 데이터 읽기, 분석, 탐색에 집중

샘플 지식 도메인을 포함해 이 전체 시스템을 구현하고, 탐색 워크플로우를 시연해 주세요.
```

```
Create a complete Knowledge Cartographer system using GitHub Copilot Agent Mode with MCP tools. This should be a two-phase process:

PHASE 1: Use MCP Tools to Gather and Organize Knowledge
First, use Agent Mode with the configured Firecrawl and server-filesystem MCP servers to collect and organize knowledge data:

1. Use FireCrawl MCP Server tools to:
   - Scrape web content about topics like "quantum computing" and "artificial intelligence".
   - Extract key entities, concepts, and relationships from the scraped content
   - Analyze content quality and source credibility

2. Use File System MCP Server tools to:
   - Create a structured knowledge base directory ./akashic-archives-demo. Place the directory in the root of your workspace.
   - Organize data into topics/ and indexes/ subdirectories
   - Save entities, relationships, and sources as JSON files (entities.json, relationships.json, sources.json)
   - Create metadata and index files for each knowledge domain

PHASE 2: Create Application to Explore the Knowledge Base
Create a Node.js/JavaScript application that reads and analyzes the organized data. Only use the fs, path, and readline modules from Node.js. Do not use any external libraries or frameworks.

3. Build a Knowledge Base Reader:
   - Read the structured JSON files created by MCP tools
   - Load entities, relationships, and source information from ./akashic-archives-demo
   - Support multiple knowledge domains/topics

4. Implement Knowledge Graph Analysis:
   - Analyze relationships between entities
   - Identify connection patterns and strengths  
   - Explore concept clusters and associations

5. Create Interactive Exploration Interface:
   - Command-line interface for browsing knowledge domains
   - Commands to load topics, find entity connections, explore relationships
   - Show original source materials and metadata
   - Beautiful mystical-themed console output

6. Add comprehensive error handling and documentation

The key architecture: MCP Tools → Structured Files → Your Application
- MCP tools handle external operations (web scraping, file organization)
- Your application focuses on reading, analyzing, and exploring the data

Please implement this complete system with sample knowledge domains and demonstrate the exploration workflow.
```

#### 2단계: Agent Mode 작업 확인  

- 🔗 MCP 서버 연결  
- 📁 **1단계**: 파일 시스템 MCP로 디렉토리 생성  
- 🕷️ **1단계**: FireCrawl MCP로 웹 콘텐츠 스크래핑 후 파일 저장  
- 💻 **2단계**: Node.js 앱으로 데이터 읽기 및 분석  
- 🧠 지식 그래프 탐색 기능 구현  
- 🧪 전체 워크플로우 테스트  

#### 3단계: 상호작용 및 개선  

- 기능 요청: "FireCrawl로 학술 논문도 스크래핑 지원 추가"  
- 출력 탐색: "방금 조사한 주제의 지식 그래프 보여줘"  
- 기능 확장: "HTML 지식 그래프 내보내기 기능 추가"  

#### 4단계: 고급 기능 탐험  

```
Enhance the Knowledge Cartographer with these advanced MCP integrations:
1. 다중 소스 지식 그래프 병합
2. 자동 지식 업데이트 워크플로우
3. 멀티미디어 콘텐츠 지원
4. 지식 공유/내보내기 파이프라인
5. 고급 그래프 분석 및 통찰
6. 추천 시스템
7. 외부 지식 베이스/API 통합
```

### 예상 출력(Expected Output)

```
🗺️  지식 지도 제작자에 오신 것을 환영합니다! 🗺️

당신은 아카식 아카이브를 탐험하고 있습니다 — 
웹의 MCP 정령들이 발견하고 정리한 신비로운 지식 베이스입니다.

FireCrawl 정령들이 디지털 영역 전반에서 지식을 모았고,
File System 정령들이 그것을 신성한 두루마리로 정리했습니다.

당신의 임무: 서로 연결된 지혜의 보물창고를 항해하세요.

🔮 아카이브 탐색 시스템 초기화 중...
        
✅ 아카식 아카이브 감지: ./akashic-archives
📚 사용 가능한 지식 도메인: 2개의 토픽 발견
🌟 아카이브가 탐색 준비를 마쳤습니다!

📖 지식 도메인 로딩: quantum-computing
✅ 5개의 엔터티 로드 완료
✅ 4개의 관계 로드 완료
✅ 3개의 소스 로드 완료
🔮 지식 도메인이 탐색 준비되었습니다!

🌟 지식 도메인: QUANTUM COMPUTING
📊 개요:
   • 엔터티: 5
   • 관계: 4
   • 소스: 3
   • 생성일: 2025-07-15

🔍 출현 빈도 상위 엔터티:
   ├── quantum bit (3회 등장)
   │   └── 관련 개념: quantum mechanics, computation
   ├── superposition (2회 등장)
   │   └── 관련 개념: quantum mechanics
   ├── entanglement (2회 등장)
   │   └── 관련 개념: quantum mechanics
   ├── Shor's algorithm (2회 등장)
   │   └── 관련 개념: cryptography, algorithms
   └── quantum gate (1회 등장)
       └── 관련 개념: computation, quantum mechanics
```

```
🗺️  Welcome to the Knowledge Cartographer! 🗺️

You are exploring the Akashic Archives - a mystical knowledge base
that has been discovered and organized by the MCP spirits of the web.

The FireCrawl spirits have gathered knowledge from across the digital realm,
while the File System spirits have organized it into sacred scrolls.

Your task: Navigate this treasure trove of interconnected wisdom.

🔮 Initializing archive exploration systems...
        
✅ Akashic Archives detected at: ./akashic-archives
📚 Available knowledge domains: 2 topics discovered
🌟 Archives ready for exploration!

📖 Loading knowledge domain: quantum-computing
✅ Loaded 5 entities
✅ Loaded 4 relationships
✅ Loaded 3 sources
🔮 Knowledge domain ready for exploration!

🌟 Knowledge Domain: QUANTUM COMPUTING
📊 Overview:
   • Entities: 5
   • Relationships: 4
   • Sources: 3
   • Created: 7/15/2025

🔍 Top Entities by Frequency:
   ├── quantum bit (appears 3 times)
   │   └── concepts: quantum mechanics, computation
   ├── superposition (appears 2 times)
   │   └── concepts: quantum mechanics
   ├── entanglement (appears 2 times)
   │   └── concepts: quantum mechanics
   ├── Shor's algorithm (appears 2 times)
   │   └── concepts: cryptography, algorithms
   └── quantum gate (appears 1 times)
       └── concepts: computation, quantum mechanics
```

### MCP 고려사항

- 🔐 API 키는 안전하게 관리  
- ⚖️ 웹 스크래핑 시 윤리적 고려 (속도 제한, 데이터 정제)  

### 문제 해결(Troubleshooting)

1. VS Code 최신 버전 확인  
2. GitHub Copilot 활성화 여부 확인  
3. MCP 서버 설정 점검  

### 다음 단계(What's Next)

1. 다른 MCP 서버 탐색 — [MCP 갤러리](https://code.visualstudio.com/mcp)  
2. MCP 기반 워크플로우 구축  
3. MCP 생태계에 기여 — 맞춤 MCP 서버 개발  

🗺️ 즐거운 지식 지도 제작 되시길 바랍니다! 🗺️
