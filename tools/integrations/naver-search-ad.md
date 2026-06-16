# 네이버 검색광고 (Naver Search Ad)

네이버 검색 영역(파워링크·쇼핑검색·파워콘텐츠·브랜드검색) 광고 운영 플랫폼. 검색 의도 수요 확보에 사용.

> API 스펙·엔드포인트는 변경될 수 있으므로 집행 전 네이버 검색광고 공식 API 문서를 재확인합니다. GFA(성과형 디스플레이)는 별도 플랫폼입니다.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | 검색광고 API (캠페인·키워드·입찰·통계) |
| MCP | - | 네이티브 MCP 없음 (직접 API 또는 Composio 검토) |
| CLI | - | API 스크립트 사용 |
| SDK | - | 커뮤니티 라이브러리(파이썬 등) 존재 |

## Authentication

- **Type**: API Key 기반 (액세스 라이선스 + 시크릿 키)
- **필수 값**: `X-API-KEY`(액세스 라이선스), `X-Customer`(CUSTOMER_ID), 서명(`X-Signature`)
- **서명**: 타임스탬프 + HTTP 메서드 + URI 를 시크릿 키로 HMAC-SHA256 서명 후 Base64
- 키 발급: 네이버 검색광고 > 도구 > API 사용 관리

## Common Agent Operations

- **캠페인/광고그룹 조회**: `GET /ncc/campaigns`, `GET /ncc/adgroups`
- **키워드 등록·입찰 조정**: `POST /ncc/keywords`, `PUT /ncc/keywords` (입찰가 bidAmt)
- **연관 키워드·검색량 조회**: 키워드도구 API (`GET /keywordstool`)
- **성과 리포트**: StatReport 생성 후 다운로드 (`POST /stat-reports`, `GET /stat-reports/{id}`)

## 규제 메모

- 소재·확장 문구의 과장·미입증·절대적 표현은 표시광고법 + 매체 심사 대상 → `kr-ad-compliance` 로 사전 점검.

## 연관 skill

`kr-performance-ads` · `ads` · `kr-ad-compliance`
