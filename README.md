# 한국 마케팅 Skills (Marketing Skills KR)

한국 시장에 바로 쓸 수 있는 마케팅 **AI Agent Skills** 모음입니다. 네이버·카카오·쿠팡·당근 등 국내 채널과 표시광고법·정보통신망법·개인정보보호법 등 국내 규제를 반영했습니다. Claude Code, OpenAI Codex, Cursor, Windsurf 등 [Agent Skills 스펙](https://agentskills.io)을 지원하는 모든 에이전트에서 동작합니다.

> **Fork 출처**: 본 저장소는 [Corey Haines](https://corey.co)의 [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) (MIT 라이선스)를 fork 하여 한국 시장용으로 재구성한 것입니다. 원저작권 표기는 [LICENSE](LICENSE)에 그대로 유지됩니다.

## 핵심 전략 — 컨텍스트 한 곳에 한국을 주입

모든 skill은 가장 먼저 `.agents/product-marketing.md` 컨텍스트 파일을 읽습니다. 이 파일에 **한국 시장·검색 환경·국내 규제·톤**을 주입해 두면, 나머지 글로벌 skill 다수가 별도 수정 없이 **자동으로 한국 맥락**을 따릅니다.

- `product-marketing` skill로 컨텍스트를 한 번 만들면(`시장 컨텍스트`·`규제 가드레일`·`톤 & 카피 가이드` 포함), SEO·카피·이메일·광고·가격 등 다른 skill이 이를 상속합니다.
- 국내 전용 채널(네이버·카카오·쿠팡·당근)은 별도 신규 skill로 제공합니다.

> ⚠️ **규제·검색 로직 면책**: 표시광고법·정보통신망법·개인정보보호법 등 **법령은 개정될 수 있으므로** 실제 캠페인 집행 전 최신 법령을 재검증하십시오. 네이버 C-Rank·D.I.A.+ 등 검색 로직은 **공식 미공개·수시 변동**이므로 본 저장소의 설명은 추정 기반이며 정기 검증이 필요합니다. 의료·건강기능식품·금융 등은 업종별 추가 규제를 별도 확인하십시오. 본 저장소는 법률 자문이 아닙니다.

## 한국화 분류 (REUSE / ADAPT / NEW)

전체 51개 skill을 세 갈래로 재구성했습니다. 상세 분류 근거는 [LOCALIZATION_PLAN.md](LOCALIZATION_PLAN.md)를 참고하세요.

### 🆕 NEW — 국내 전용 신규 skill (7종)

| Skill | 다루는 범위 |
|-------|-------------|
| [naver-blog-seo](skills/naver-blog-seo/) | 네이버 블로그·검색 상위노출(C-Rank·D.I.A.+ 추정 대응), 키워드 배치, 체류시간·저품질 회피 |
| [naver-smartstore-seo](skills/naver-smartstore-seo/) | 스마트스토어 상품명·태그·상세페이지, 네이버 쇼핑 노출 |
| [kakao-biz-message](skills/kakao-biz-message/) | 카카오 알림톡/친구톡 설계, 채널 친구 확보, 정보통신망법 옵트인 준수 |
| [coupang-listing](skills/coupang-listing/) | 쿠팡 상품명·검색태그·로켓배송 노출, 리뷰·랭킹 최적화 |
| [kr-performance-ads](skills/kr-performance-ads/) | 네이버 GFA/검색광고·카카오모먼트·메타 한국 집행, 소재·타깃·예산 구조 |
| [kr-ad-compliance](skills/kr-ad-compliance/) | 표시광고법·정보통신망법·PIPA 카피 사전 점검 체커 (다른 skill이 호출) |
| [danggn-local-ads](skills/danggn-local-ads/) | 당근 지역 광고 등 로컬 비즈니스 |

### 🔧 ADAPT — 한국 채널·톤·규제 보정 skill (23종)

각 skill 본문에 `## 한국 시장 보정 (Korea)` 섹션을 추가해 국내 채널 분기·규제·표기를 반영했습니다(원본은 유지).

| Skill | 한국 보정 포인트 |
|-------|------------------|
| [product-marketing](skills/product-marketing/) | **컨텍스트 허브** — 시장·규제·톤 가이드 주입 |
| [seo-audit](skills/seo-audit/) | 구글 + 네이버 이원 점검 (`references/naver-seo.md`) |
| [copywriting](skills/copywriting/) | 한국어 톤(합쇼체/해요체), 영어 직역투 금지 |
| [emails](skills/emails/) | 카카오 알림톡/친구톡 분기 + 정보통신망법 |
| [pricing](skills/pricing/) | 원화·부가세·네이버페이/카카오페이/토스 |
| [ads](skills/ads/) | 네이버 GFA·검색광고, 카카오모먼트 분기 |
| [ad-creative](skills/ad-creative/) | 네이버/카카오 소재 규격, 한국어 카피 톤 |
| [copy-editing](skills/copy-editing/) | 한국어 교정·번역체 제거 |
| [sms](skills/sms/) | SMS/LMS/MMS + 카카오 + 정보통신망법((광고)·080) |
| [cold-email](skills/cold-email/) | 국내 B2B 톤 + 정보통신망법 유의 |
| [cro](skills/cro/) | 국내 신뢰 요소(사업자번호·통신판매신고)·전자상거래법 |
| [social](skills/social/) | 국내 플랫폼 세트(인스타·유튜브·네이버·카카오) |
| [analytics](skills/analytics/) | 네이버 애널리틱스 + PIPA 추적 동의 |
| [aso](skills/aso/) | 원스토어(ONE store) + 한국어 키워드 |
| [community-marketing](skills/community-marketing/) | 네이버 카페·카카오 오픈채팅 |
| [customer-research](skills/customer-research/) | 국내 VOC 소스(카페·지식iN·블라인드) |
| [directory-submissions](skills/directory-submissions/) | 국내 디렉터리(디스콰이엇 등) |
| [launch](skills/launch/) | 국내 런치 채널(디스콰이엇·카페·오픈채팅) |
| [popups](skills/popups/) | 수집 동의(PIPA·옵트인) 체크박스 분리 |
| [programmatic-seo](skills/programmatic-seo/) | 네이버 저품질 회피·구글 타깃 주석 |
| [prospecting](skills/prospecting/) | 국내 데이터 소스(DART·잡코리아·사람인) |
| [public-relations](skills/public-relations/) | 국내 매체·보도자료(뉴스와이어·플래텀) |
| [signup](skills/signup/) | 카카오/네이버 로그인·본인인증·만14세 동의 |

### ♻️ REUSE — 수정 없이 사용 (21종)

보편 원리 중심으로, `product-marketing.md` 컨텍스트만으로 한국 톤·맥락을 자동 상속합니다.

| Skill | 범위 | Skill | 범위 |
|-------|------|-------|------|
| [ab-testing](skills/ab-testing/) | A/B 테스트·실험 설계 | [marketing-psychology](skills/marketing-psychology/) | 행동과학·설득 원리 |
| [ai-seo](skills/ai-seo/) | AI 검색(AEO/GEO/LLMO) | [churn-prevention](skills/churn-prevention/) | 이탈 방지·결제 복구 |
| [co-marketing](skills/co-marketing/) | 공동마케팅·협업 | [competitor-profiling](skills/competitor-profiling/) | 경쟁사 리서치 |
| [competitors](skills/competitors/) | 비교/대안 페이지 | [content-strategy](skills/content-strategy/) | 콘텐츠 전략·토픽 클러스터 |
| [free-tools](skills/free-tools/) | 무료 툴 기획 | [image](skills/image/) | 마케팅 이미지 생성 |
| [lead-magnets](skills/lead-magnets/) | 리드 마그넷 | [marketing-ideas](skills/marketing-ideas/) | 마케팅 아이디어 |
| [marketing-plan](skills/marketing-plan/) | AARRR 종합 플랜 | [onboarding](skills/onboarding/) | 온보딩·활성화 |
| [paywalls](skills/paywalls/) | 인앱 업그레이드 | [referrals](skills/referrals/) | 추천·제휴 프로그램 |
| [revops](skills/revops/) | 레브옵스·파이프라인 | [sales-enablement](skills/sales-enablement/) | 세일즈 콜래터럴 |
| [schema](skills/schema/) | 구조화 데이터(구글) | [site-architecture](skills/site-architecture/) | 사이트 IA·내비게이션 |
| [video](skills/video/) | AI 영상 제작 | | |

## 설치

### 방법 1: CLI 설치 (권장)

[npx skills](https://github.com/vercel-labs/skills)로 직접 설치합니다.

```bash
# 전체 skill 설치
npx skills add kjungmo/marketingskills

# 특정 skill만 설치
npx skills add kjungmo/marketingskills --skill naver-blog-seo kakao-biz-message

# 목록 보기
npx skills add kjungmo/marketingskills --list
```

`.agents/skills/` 디렉터리에 설치되며 Claude Code 호환을 위해 `.claude/skills/`로 심볼릭 링크됩니다.

### 방법 2: Claude Code 플러그인

```bash
# 마켓플레이스 추가
/plugin marketplace add kjungmo/marketingskills

# 전체 skill 설치
/plugin install marketing-skills-kr
```

### 방법 3: 클론 후 복사

```bash
git clone https://github.com/kjungmo/marketingskills.git
cp -r marketingskills/skills/* .agents/skills/
```

## 사용법

먼저 제품 컨텍스트를 만들어 한국 시장 기본값을 잡습니다.

```
"제품 마케팅 컨텍스트를 만들어줘"
→ product-marketing skill (한국 시장·규제·톤 섹션 포함)
```

이후 작업을 요청하면 적절한 skill이 한국 맥락으로 동작합니다.

```
"네이버 블로그 상위노출용 글을 써줘"      → naver-blog-seo
"카카오 알림톡 템플릿 만들어줘"            → kakao-biz-message
"스마트스토어 상품명 최적화해줘"           → naver-smartstore-seo
"이 광고 카피 법적으로 문제 없는지 봐줘"   → kr-ad-compliance
"랜딩페이지 전환율 개선해줘"               → cro (한국 신뢰 요소 반영)
"가격 페이지 만들어줘"                     → pricing (원화·부가세·간편결제)
```

직접 호출도 가능합니다.

```
/naver-blog-seo
/kakao-biz-message
/kr-ad-compliance
```

## Skills란?

Skills는 AI 에이전트에 특정 작업을 위한 전문 지식·워크플로를 부여하는 마크다운 파일입니다. 프로젝트에 추가하면 에이전트가 마케팅 작업을 인식하고 적절한 프레임워크·모범 사례를 적용합니다. 각 skill의 **연관 skill** 섹션에서 의존 관계를 확인할 수 있습니다.

## 기여

skill 개선이나 신규 제안은 PR·이슈로 환영합니다. [CONTRIBUTING.md](CONTRIBUTING.md)를 참고하세요.

## 라이선스

[MIT](LICENSE) — 원저작자 [Corey Haines](https://corey.co). 본 fork의 한국화 보정분도 동일하게 MIT로 제공합니다.
