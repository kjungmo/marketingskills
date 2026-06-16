---
name: product-marketing
description: "When the user wants to create or update their product marketing context document. Also use when the user mentions 'product context,' 'marketing context,' 'set up context,' 'positioning,' 'who is my target audience,' 'describe my product,' 'ICP,' 'ideal customer profile,' or wants to avoid repeating foundational information across marketing tasks. Use this at the start of any new project before using other marketing skills — it creates `.agents/product-marketing.md` that all other skills reference for product, audience, and positioning context."
metadata:
  version: 2.0.0
---

# Product Marketing Context

You help users create and maintain a product marketing context document. This captures foundational positioning and messaging information that other marketing skills reference, so users don't repeat themselves.

The document is stored at `.agents/product-marketing.md`.

## 한국 시장 기본값 (Korea Defaults)

이 저장소는 한국 시장용으로 현지화되어 있습니다. 제품이 **한국 시장을 타깃**으로 한다면(또는 사용자가 한국어로 작업하거나 한국 채널을 언급하면), 아래 **섹션 13(한국 시장 컨텍스트)** 을 반드시 채우고, 그 내용을 다운스트림 skill 전체의 기본값으로 삼습니다.

- `.agents/product-marketing.md` 에 한국 시장·채널·규제·톤이 기록되면, 다른 모든 skill(SEO·카피·이메일·광고·가격 등)이 이 컨텍스트를 읽어 **자동으로 한국 맥락**을 따릅니다.
- 규제 항목은 "현재 기준 확인 필요"를 전제로 기록하며, 실제 캠페인 집행 전 최신 법령(표시광고법·정보통신망법·개인정보보호법 등)을 재검증하도록 명시합니다. (법령은 개정될 수 있습니다.)
- 글로벌 제품이라면 이 섹션은 건너뛰어도 됩니다.

## Workflow

### Step 1: Check for Existing Context

First, check if `.agents/product-marketing.md` already exists. Also check `.claude/product-marketing.md` and the legacy filename `product-marketing-context.md` (in either `.agents/` or `.claude/`) for older setups — if found anywhere other than `.agents/product-marketing.md`, offer to move it to the canonical location.

**If it exists:**
- Read it and summarize what's captured
- Ask which sections they want to update
- Only gather info for those sections

**If it doesn't exist, offer two options:**

1. **Auto-draft from codebase** (recommended): You'll study the repo—README, landing pages, marketing copy, package.json, etc.—and draft a V1 of the context document. The user then reviews, corrects, and fills gaps. This is faster than starting from scratch.

2. **Start from scratch**: Walk through each section conversationally, gathering info one section at a time.

Most users prefer option 1. After presenting the draft, ask: "What needs correcting? What's missing?"

### Step 2: Gather Information

**If auto-drafting:**
1. Read the codebase: README, landing pages, marketing copy, about pages, meta descriptions, package.json, any existing docs
2. Draft all sections based on what you find
3. Present the draft and ask what needs correcting or is missing
4. Iterate until the user is satisfied

**If starting from scratch:**
Walk through each section below conversationally, one at a time. Don't dump all questions at once.

For each section:
1. Briefly explain what you're capturing
2. Ask relevant questions
3. Confirm accuracy
4. Move to the next

Push for verbatim customer language — exact phrases are more valuable than polished descriptions because they reflect how customers actually think and speak, which makes copy more resonant.

---

## Sections to Capture

### 1. Product Overview
- One-line description
- What it does (2-3 sentences)
- Product category (what "shelf" you sit on—how customers search for you)
- Product type (SaaS, marketplace, e-commerce, service, etc.)
- Business model and pricing

### 2. Target Audience
- Target company type (industry, size, stage)
- Target decision-makers (roles, departments)
- Primary use case (the main problem you solve)
- Jobs to be done (2-3 things customers "hire" you for)
- Specific use cases or scenarios

### 3. Personas (B2B only)
If multiple stakeholders are involved in buying, capture for each:
- User, Champion, Decision Maker, Financial Buyer, Technical Influencer
- What each cares about, their challenge, and the value you promise them

### 4. Problems & Pain Points
- Core challenge customers face before finding you
- Why current solutions fall short
- What it costs them (time, money, opportunities)
- Emotional tension (stress, fear, doubt)

### 5. Competitive Landscape
- **Direct competitors**: Same solution, same problem (e.g., Calendly vs SavvyCal)
- **Secondary competitors**: Different solution, same problem (e.g., Calendly vs Superhuman scheduling)
- **Indirect competitors**: Conflicting approach (e.g., Calendly vs personal assistant)
- How each falls short for customers

### 6. Differentiation
- Key differentiators (capabilities alternatives lack)
- How you solve it differently
- Why that's better (benefits)
- Why customers choose you over alternatives

### 7. Objections & Anti-Personas
- Top 3 objections heard in sales and how to address them
- Who is NOT a good fit (anti-persona)

### 8. Switching Dynamics
The JTBD Four Forces:
- **Push**: What frustrations drive them away from current solution
- **Pull**: What attracts them to you
- **Habit**: What keeps them stuck with current approach
- **Anxiety**: What worries them about switching

### 9. Customer Language
- How customers describe the problem (verbatim)
- How they describe your solution (verbatim)
- Words/phrases to use
- Words/phrases to avoid
- Glossary of product-specific terms

### 10. Brand Voice
- Tone (professional, casual, playful, etc.)
- Communication style (direct, conversational, technical)
- Brand personality (3-5 adjectives)

### 11. Proof Points
- Key metrics or results to cite
- Notable customers/logos
- Testimonial snippets
- Main value themes and supporting evidence

### 12. Goals
- Primary business goal
- Key conversion action (what you want people to do)
- Current metrics (if known)

### 13. 한국 시장 컨텍스트 (Korea) — 한국 타깃 제품만

한국 시장을 타깃으로 하는 경우 아래를 채웁니다. 다른 skill이 이 내용을 기본값으로 상속합니다.

- **시장 컨텍스트**: 주요 검색 환경(네이버/구글), 주요 광고 채널, 주요 커머스 채널, 메신저 마케팅(카카오), 결제 수단을 기록.
- **규제 가드레일**: 적용 업종의 표시광고법·정보통신망법·개인정보보호법 준수 사항과 업종별 추가 규제(의료/건기식/금융 등) 여부.
- **톤 & 카피 가이드**: 타깃 어조(합쇼체/해요체), 영어 직역투 금지 등 언어 규칙.

> 규제·검색 로직 항목은 단정하지 말고 "현재 기준 확인 필요" 주석을 유지합니다.

---

## Step 3: Create the Document

After gathering information, create `.agents/product-marketing.md` with this structure:

```markdown
# Product Marketing Context

*Last updated: [date]*

## Product Overview
**One-liner:**
**What it does:**
**Product category:**
**Product type:**
**Business model:**

## Target Audience
**Target companies:**
**Decision-makers:**
**Primary use case:**
**Jobs to be done:**
-
**Use cases:**
-

## Personas
| Persona | Cares about | Challenge | Value we promise |
|---------|-------------|-----------|------------------|
| | | | |

## Problems & Pain Points
**Core problem:**
**Why alternatives fall short:**
-
**What it costs them:**
**Emotional tension:**

## Competitive Landscape
**Direct:** [Competitor] — falls short because...
**Secondary:** [Approach] — falls short because...
**Indirect:** [Alternative] — falls short because...

## Differentiation
**Key differentiators:**
-
**How we do it differently:**
**Why that's better:**
**Why customers choose us:**

## Objections
| Objection | Response |
|-----------|----------|
| | |

**Anti-persona:**

## Switching Dynamics
**Push:**
**Pull:**
**Habit:**
**Anxiety:**

## Customer Language
**How they describe the problem:**
- "[verbatim]"
**How they describe us:**
- "[verbatim]"
**Words to use:**
**Words to avoid:**
**Glossary:**
| Term | Meaning |
|------|---------|
| | |

## Brand Voice
**Tone:**
**Style:**
**Personality:**

## Proof Points
**Metrics:**
**Customers:**
**Testimonials:**
> "[quote]" — [who]
**Value themes:**
| Theme | Proof |
|-------|-------|
| | |

## Goals
**Business goal:**
**Conversion action:**
**Current metrics:**

## 시장 컨텍스트 (Korea)
> 한국 타깃 제품만 작성. 글로벌 제품은 생략.
- 1차 검색 엔진: 네이버(블로그·카페·지식iN·플레이스) + 구글 이원 구조
- 주요 광고 채널: 네이버 GFA/검색광고, 카카오모먼트, 메타, 구글, (앱: 당근/토스 등)
- 주요 커머스: 네이버 스마트스토어, 쿠팡, 11번가, 무신사 등
- 메신저 마케팅: 카카오 알림톡/친구톡 (이메일보다 도달·열람률 우위)
- 결제·간편결제: 네이버페이, 카카오페이, 토스

## 규제 가드레일 (반드시 준수) — 현재 기준 확인 필요
> 법령은 개정될 수 있으므로 실제 집행 전 최신 법령을 재검증할 것.
- 표시·광고의 공정화에 관한 법률(표시광고법): 거짓·과장·기만·부당비교·비방 광고 금지. "최고/유일/100%" 등 절대적 표현, 미입증 효능·효과 표현 금지(실증 자료 보유 전제).
- 정보통신망법(영리 목적 광고성 정보 전송): 사전 수신 동의(옵트인) 필수, 야간(21시~익일 08시) 전송 별도 동의, 제목/본문에 '(광고)' 명시, 무료 수신거부 수단 안내.
- 개인정보보호법(PIPA): 개인정보 수집·이용 시 목적·항목·보유기간 고지 후 동의.
- 업종별 추가 규제: 의료/건강기능식품/금융 등은 별도 심의·광고 규제 별도 확인.

## 톤 & 카피 가이드 (Korea)
- 타깃 어조: [합쇼체 / 해요체 / 반말 등 명시]
- 영어 직역투 금지, 국내 관용 표현 우선.
- 네이버 노출용 텍스트는 키워드를 부자연스럽게 반복하지 않되 핵심 키워드는 도입부·소제목에 배치.
```

---

## Step 4: Confirm and Save

- Show the completed document
- Ask if anything needs adjustment
- Save to `.agents/product-marketing.md`
- Tell them: "Other marketing skills will now use this context automatically. Run `/product-marketing` anytime to update it."

---

## Tips

- **Be specific**: Ask "What's the #1 frustration that brings them to you?" not "What problem do they solve?"
- **Capture exact words**: Customer language beats polished descriptions
- **Ask for examples**: "Can you give me an example?" unlocks better answers
- **Validate as you go**: Summarize each section and confirm before moving on
- **Skip what doesn't apply**: Not every product needs all sections (e.g., Personas for B2C)
