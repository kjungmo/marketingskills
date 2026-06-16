# LOCALIZATION_PLAN.md — 한국 시장 마케팅 Skill 재구성 계획

> 베이스 저장소: `coreyhaines31/marketingskills` (MIT) 를 fork 하여 한국 시장 전용 마케팅 skill 저장소로 재구성하기 위한 Phase 1 현황 분석 문서입니다.
> 본 문서는 **분류 결과**이며, 실제 보정·신규 제작은 후속 Phase에서 진행합니다.
> 규제·검색 로직 관련 모든 단정 표현은 "추정/검증 필요" 주석을 유지하며, 실제 캠페인 집행 전 최신 법령 재검증을 전제로 합니다.

---

## 0. 분류 기준 (Bucketing Rule)

핵심 전략은 모든 skill이 가장 먼저 읽는 `product-marketing.md` 컨텍스트 파일에 한국 시장·검색 환경·규제를 주입하여, 다수의 글로벌 skill이 **자동으로** 한국 맥락을 따르게 하는 것입니다. 따라서 분류 기준은 다음과 같습니다.

| 버킷 | 정의 | 판정 규칙 |
|------|------|-----------|
| **REUSE** | 수정 없이 사용 가능 | 보편적 원리·프레임워크 중심이며, 한국에서 오해를 부를 외국 전용 채널/규제/통화/표기가 하드코딩되어 있지 **않음**. 톤·언어는 `product-marketing.md` 주입으로 자동 보정됨. |
| **ADAPT** | 한국 보정 필요 | 외국 전용 채널·플랫폼 규격·규제·통화·언어 관용 표현이 **구조적으로 하드코딩**되어 있어, 한국 컨텍스트 섹션 또는 채널 분기를 추가해야 함. |
| **NEW** | 신규 제작 | 네이버·카카오·쿠팡·당근 등 국내 전용 채널로, 베이스 저장소에 존재하지 않음. |

> **보정 방식**: 원본 파일을 통째로 덮어쓰지 않고, `product-marketing.md` 컨텍스트를 키로 삼는 **조건부 한국 섹션**을 추가합니다. 이 방식은 원저장소가 이미 `ads` skill에 적용한 선례(`skills/ads/SKILL.md` 의 "Medical / CFM compliance (when product context indicates pt-BR medical practice)" 조건부 섹션)와 동일한 패턴이므로, 베이스와의 호환성과 cross-agent 호환성을 유지합니다.

---

## 1. product-marketing 의존 관계 분석

### 구조

- `skills/product-marketing/SKILL.md` 는 대화형 워크플로로 `.agents/product-marketing.md` 파일을 생성·갱신합니다.
- 캡처 섹션 12개: 제품 개요 / 타깃 / 페르소나 / 문제·페인포인트 / 경쟁 환경 / 차별화 / 반론·안티페르소나 / 전환 동인(JTBD 4 Forces) / 고객 언어 / 브랜드 보이스 / 증거 자료 / 목표.
- 산출물 경로(정규): `.agents/product-marketing.md` (구버전 `.claude/product-marketing.md`, 레거시 `product-marketing-context.md` 도 탐색).

### 다른 skill의 참조 방식 (의존성)

- 분석 결과, **43개 skill 전부**가 본문 상단에 동일한 참조 구문을 보유합니다.
  > "Check for product marketing context first: If `.agents/product-marketing.md` exists ... read it before asking questions."
- 즉 `product-marketing.md` 는 저장소 전체의 **단일 컨텍스트 허브**이며, 여기에 한국 시장 컨텍스트를 주입하면 모든 skill이 별도 수정 없이 한국 톤·규제·채널 기본값을 상속합니다.
- **결론**: Phase 2(`product-marketing.md` 재작성)가 전체 현지화의 레버리지 지점이며 최우선(P0)입니다. ADAPT/NEW 작업은 이 컨텍스트만으로 해결되지 않는 **구조적 채널·규제·표기**만 추가하면 됩니다.

---

## 2. 전체 분류 표 (44개 skill)

> 우선순위: **P0** = 즉시(레버리지 큼) / **P1** = 핵심 채널·톤 / **P2** = 선택·후속(구조적 보정이 있으나 영향 범위 한정)

| skill명 | 버킷 | 보정 포인트 | 우선순위 |
|---|---|---|---|
| product-marketing | ADAPT | **[Phase 2 핵심]** 시장 컨텍스트(네이버·카카오·커머스), 규제 가드레일(표시광고법·정보통신망법·PIPA), 톤·카피 가이드 섹션 주입 | **P0** |
| seo-audit | ADAPT | 구글 + 네이버(블로그·플레이스·쇼핑·지식iN) 이원 점검 항목 추가 | **P0** |
| copywriting | ADAPT | 한국어 톤(합쇼체/해요체), 영어 직역투 금지, 국내 관용 표현 우선 규칙 | **P0** |
| emails | ADAPT | 카카오 알림톡/친구톡 분기 + 정보통신망법 옵트인·(광고)표기·야간(21~08시)전송 규칙 | **P0** |
| pricing | ADAPT | 원화·부가세(VAT) 표기, 국내 간편결제(네이버페이/카카오페이/토스) 반영 | **P0** |
| ads | ADAPT | 네이버 GFA·검색광고, 카카오모먼트 채널 구조·입찰·소재 규격 분기 | P1 |
| ad-creative | ADAPT | 네이버/카카오 소재 규격 + 한국어 광고 카피 톤, 표시광고법 표현 가드 | P1 |
| copy-editing | ADAPT | 한국어 교정 기준(직역투·번역체 제거, 맞춤법·띄어쓰기, 관용 표현) | P1 |
| sms | ADAPT | SMS/LMS/MMS + 카카오 알림톡 분기, 정보통신망법·(광고)·080 무료수신거부 (A2P 10DLC/TCPA는 미국 한정 → 한국 분기로 대체) | P1 |
| cold-email | ADAPT | 영리목적 광고성 정보 = 정보통신망법 (광고) 표기·옵트인 고려, 국내 B2B 이메일 톤 | P2 |
| cro | ADAPT | 한국 신뢰 요소(사업자등록번호·통신판매업신고·네이버페이 배지), 전자상거래법 표기 | P2 |
| social | ADAPT | 국내 플랫폼 세트(인스타·유튜브·네이버 블로그·카카오·스레드) 반영 | P2 |
| analytics | ADAPT | 네이버 애널리틱스 추가 + PIPA 쿠키·추적 동의 고지 | P2 |
| aso | ADAPT | 원스토어(ONE store) 추가, 한국어 키워드 필드 특성 | P2 |
| community-marketing | ADAPT | 네이버 카페·카카오 오픈채팅 채널 분기 (Discord/Slack 보완) | P2 |
| customer-research | ADAPT | 국내 리서치 소스(네이버 카페·지식iN·블라인드·디시·클리앙) | P2 |
| directory-submissions | ADAPT | 국내 디렉터리(디스콰이엇·아웃스탠딩·플래텀 등) 추가 | P2 |
| launch | ADAPT | 국내 런치 채널(디스콰이엇·네이버 카페·카카오 오픈채팅) | P2 |
| popups | ADAPT | 이메일·전화 수집 시 정보통신망법·PIPA 동의 체크박스 | P2 |
| programmatic-seo | ADAPT | 네이버 저품질(대량 생성 페이지) 회피 주의 + 구글 타깃 한정 주석 | P2 |
| prospecting | ADAPT | 국내 데이터 소스(잡코리아·사람인·DART·카탈로그) (Apollo/ZoomInfo 보완) | P2 |
| public-relations | ADAPT | 국내 매체·배포(뉴스와이어·플래텀·아웃스탠딩·전자신문), 보도자료 양식 | P2 |
| signup | ADAPT | 카카오/네이버 소셜로그인, 휴대폰 본인인증, 만 14세 미만 동의(PIPA) | P2 |
| ab-testing | REUSE | 보편 통계·실험 프레임워크 (톤만 컨텍스트 상속) | — |
| marketing-psychology | REUSE | 보편 행동과학·심리 원리 | — |
| ai-seo | REUSE | 글로벌 AI 검색엔진 대상, 원리 동일 (네이버 Cue: 는 선택 주석) | — |
| churn-prevention | REUSE | 보편 리텐션 프레임워크 (카카오 윈백은 emails/kakao로 연계) | — |
| co-marketing | REUSE | 보편 파트너십 전략 | — |
| competitor-profiling | REUSE | 보편 경쟁사 리서치 방법론 | — |
| competitors | REUSE | 비교/대안 페이지 포맷 보편 (언어만 상속) | — |
| content-strategy | REUSE | 보편 토픽 클러스터·에디토리얼 방법 (네이버 채널은 컨텍스트 상속) | — |
| free-tools | REUSE | engineering-as-marketing 보편 원리 | — |
| image | REUSE | 글로벌 AI 이미지 툴·규격 보편 (한국어 텍스트 렌더링만 주의) | — |
| lead-magnets | REUSE | 게이티드 콘텐츠 보편 원리 | — |
| marketing-ideas | REUSE | 보편 아이디어 라이브러리 | — |
| marketing-plan | REUSE | AARRR 프레임워크 보편 (옵스 스택은 컨텍스트 상속) | — |
| onboarding | REUSE | 보편 활성화·TTV 원리 | — |
| paywalls | REUSE | 인앱 업그레이드 보편 원리 (결제수단은 컨텍스트 상속) | — |
| referrals | REUSE | 추천 프로그램 메커니즘 보편 | — |
| revops | REUSE | 리드 라이프사이클·CRM 보편 (HubSpot/Salesforce 국내도 사용) | — |
| sales-enablement | REUSE | 보편 세일즈 콜래터럴 (B2B 톤은 컨텍스트 상속) | — |
| schema | REUSE | 구글 리치결과용 JSON-LD 보편 (네이버는 schema.org 미사용 주석) | — |
| site-architecture | REUSE | 보편 IA·내비게이션·내부링크 원리 | — |
| video | REUSE | 글로벌 AI 영상 툴 보편 | — |
| **naver-blog-seo** | **NEW** | 네이버 검색 로직(C-Rank·D.I.A.+) 대응, 키워드 배치, 체류시간·이미지 최적화, 저품질 회피 | **P0** |
| **naver-smartstore-seo** | **NEW** | 스마트스토어 상품명·태그·상세페이지 최적화, 네이버 쇼핑 노출 | **P0** |
| **kakao-biz-message** | **NEW** | 알림톡/친구톡 템플릿 설계, 채널 친구 확보, 정보통신망법 옵트인 준수 | **P0** |
| **coupang-listing** | **NEW** | 쿠팡 상품명·검색태그·로켓배송 노출, 리뷰·랭킹 최적화 | P1 |
| **kr-performance-ads** | **NEW** | 네이버 GFA/검색광고·카카오모먼트·메타 한국 집행, 소재·타깃·예산 구조 | P1 |
| **kr-ad-compliance** | **NEW** | 표시광고법·정보통신망법 카피 사전 점검 체커 (다른 skill이 호출) | P1 |
| **danggn-local-ads** | **NEW** | 당근 지역 광고 등 로컬 비즈니스 | P2 |

### 버킷 요약

- **REUSE**: 21개 — 수정 불필요. `product-marketing.md` 주입으로 한국 톤·맥락 자동 상속.
- **ADAPT**: 23개 — 조건부 한국 섹션/채널 분기 추가 (P0 5개, P1 4개, P2 14개).
- **NEW**: 7개 — 국내 전용 신규 제작 (P0 3개, P1 3개, P2 1개).

---

## 3. 후속 Phase 실행 순서 (제안)

| Phase | 작업 | 산출물 |
|---|---|---|
| Phase 2 | `product-marketing.md` 한국 시장 컨텍스트 주입 (레버리지 P0) | `skills/product-marketing/SKILL.md` 보정 |
| Phase 3 | 국내 전용 NEW skill 제작 (naver-blog-seo → kakao-biz-message → …) | `skills/<신규>/SKILL.md` 7종 |
| Phase 4 | ADAPT P0→P1→P2 순으로 조건부 한국 섹션 추가 | seo-audit, copywriting, emails, pricing, ads … |
| Phase 5 | 마켓플레이스·README 한국어 재작성, 설치 검증, 라이선스·fork 출처 표기 | `marketplace.json`, `README.md` |

> 커밋은 Phase 단위로 분리합니다 (예: `feat(kr): naver-blog-seo skill 추가`).

---

## 4. 규제·검색 로직 면책 주석 (전 Phase 공통 유지)

- 표시광고법·정보통신망법·개인정보보호법 등 **법령은 개정될 수 있으므로**, skill 본문의 규제 항목에는 "현재 기준 확인 필요" 주석을 달고 실제 집행 전 최신 법령을 재검증하도록 명시합니다.
- 네이버 검색 로직(C-Rank·D.I.A.+) 등은 **공식 미공개·수시 변동 알고리즘**이므로, "추정 기반·정기 검증 필요"임을 명시하고 단정적 수치를 피합니다.
- 의료·건강기능식품·금융 등 업종은 별도 심의·광고 규제가 추가로 적용되므로 업종별 확인을 전제합니다.
