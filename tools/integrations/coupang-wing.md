# 쿠팡 Open API (Wing)

쿠팡 판매자(Wing)용 Open API. 상품 등록·주문·반품·정산을 프로그램으로 관리. 쿠팡 리스팅 최적화와 함께 사용.

> API 스펙은 변경될 수 있으므로 연동 전 쿠팡 Wing Open API 공식 문서를 확인합니다.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | Wing Open API (상품·주문·반품·정산) |
| MCP | - | 네이티브 MCP 없음 |
| CLI | - | API 스크립트 |
| SDK | - | 커뮤니티/직접 구현 |

## Authentication

- **Type**: Access Key + Secret Key 기반 HMAC 서명
- **서명(HMAC-SHA256)**: `메서드 + URL경로 + 타임스탬프(+쿼리)` 를 시크릿 키로 서명
- **Headers**: `Authorization: CEA algorithm=HmacSHA256, access-key=..., signed-date=..., signature=...`
- 키 발급: 쿠팡 Wing > 판매자 정보 > Open API 키

## Common Agent Operations

- **상품 관리**: 상품 등록·수정(상품명·옵션·이미지·검색태그), 가격/재고 변경
- **주문 관리**: 발주서 조회, 출고 처리, 송장 등록
- **반품/교환·정산 조회**

## 메모

- 상품명·검색태그·아이템위너·랭킹 최적화는 `coupang-listing`.
- "최저가/1위" 등 표현은 실증 전제 → `kr-ad-compliance`.

## 연관 skill

`coupang-listing` · `cro` · `kr-ad-compliance`
