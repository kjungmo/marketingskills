# SOLAPI (문자 · 알림톡 통합 발송)

SMS/LMS/MMS 및 카카오 알림톡·친구톡을 단일 API로 발송하는 국내 메시징 서비스. 개발자 친화적 API로 sms·kakao-biz-message 실행에 적합.

> 스펙은 변경될 수 있으므로 발송 전 SOLAPI 공식 문서를 확인합니다. (유사 대행사: 알리고, NHN Cloud, 비즈엠 등)

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | REST API (메시지 발송·조회·잔액) |
| MCP | - | 네이티브 MCP 없음 |
| CLI | - | API 스크립트 |
| SDK | ✓ | Node/Python/PHP 등 공식 SDK |

## Authentication

- **Type**: API Key + API Secret 기반 HMAC 서명
- **Headers**: `Authorization: HMAC-SHA256 apiKey=..., date=..., salt=..., signature=...`
- **선행 조건**: **발신번호 사전 등록**(전기통신사업법), 알림톡은 카카오 발신프로필·템플릿 등록

## Common Agent Operations

- **단건/대량 메시지 발송**: SMS(단문)·LMS(장문)·MMS(이미지) — `POST /messages/v4/send(-many)`
- **카카오 발송**: 알림톡(템플릿+변수), 친구톡 — 메시지 type 지정
- **발송 결과·통계 조회**, **잔액 조회**

## 규제 메모 (정보통신망법 — 현재 기준 확인 필요)

- 광고성 문자/메시지: 사전 수신 동의, 본문 처음 **(광고)**, 야간(21~08시) 별도 동의, **무료 수신거부(080 등)** 안내, 전송자 명시.
- 발신번호는 사전 등록된 번호만 사용 가능.
- 카피 점검은 `kr-ad-compliance`.

## 연관 skill

`sms` · `kakao-biz-message` · `kr-ad-compliance`
