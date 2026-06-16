# 네이버 커머스 API (스마트스토어)

네이버 스마트스토어·윈도 등 네이버 커머스 판매자용 API. 상품·주문·문의·정산을 프로그램으로 관리. 네이버 쇼핑 노출 최적화와 함께 사용.

> 커머스 API 스펙은 변경될 수 있으므로 연동 전 네이버 커머스 API 공식 문서를 확인합니다.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | 커머스 API (상품·주문·문의·정산) |
| MCP | - | 네이티브 MCP 없음 |
| CLI | - | API 스크립트 |
| SDK | - | 커뮤니티/직접 구현 |

## Authentication

- **Type**: OAuth2 (애플리케이션 ID/시크릿 → 액세스 토큰)
- **선행 조건**: 네이버 커머스 API 센터에서 애플리케이션 등록, 판매자 계정 연동
- **Headers**: `Authorization: Bearer {access_token}`

## Common Agent Operations

- **상품 관리**: 상품 등록·수정·재고/가격 변경 (상품명·카테고리·옵션·속성)
- **주문 관리**: 신규 주문 조회, 발송 처리, 클레임(반품/교환) 처리
- **문의/리뷰 조회**: 고객 문의 응대, 리뷰 확인
- **정산 조회**

## 메모

- 상품명·태그·카테고리·상세페이지 노출 최적화는 `naver-smartstore-seo`.
- 상품정보제공고시·표시 규제는 전자상거래법, 표현 점검은 `kr-ad-compliance`.

## 연관 skill

`naver-smartstore-seo` · `cro` · `kr-ad-compliance`
