# 카카오모먼트 (Kakao Moment)

카카오 비즈니스의 디스플레이·메시지 광고 플랫폼. 카카오톡 비즈보드, 디스플레이, 채널 메시지 광고를 집행. 대규모 도달·리타기팅에 사용.

> API 스펙은 변경될 수 있으므로 집행 전 카카오모먼트 공식 API 문서를 재확인합니다.

## Capabilities

| Integration | Available | Notes |
|-------------|-----------|-------|
| API | ✓ | 카카오모먼트 API (캠페인·광고그룹·소재·리포트) |
| MCP | - | 네이티브 MCP 없음 |
| CLI | - | API 스크립트 사용 |
| SDK | - | 커뮤니티/직접 구현 |

## Authentication

- **Type**: OAuth 2.0 (카카오 계정 + 광고계정 권한)
- **필수**: 앱 등록(카카오 디벨로퍼스), 광고계정(adAccountId) 접근 권한, 액세스 토큰
- **Headers**: `Authorization: Bearer {access_token}`, `adAccountId`

## Common Agent Operations

- **캠페인/광고그룹 관리**: 생성·수정·상태 변경 (목표·예산·입찰)
- **소재(크리에이티브) 관리**: 비즈보드/이미지/메시지 소재 등록
- **타깃 설정**: 데모/관심사/맞춤타깃(픽셀·고객파일)/유사타깃
- **리포트 조회**: 노출·클릭·비용·전환 지표 (기간·차원별)

## 규제 메모

- 채널 메시지(광고형)는 정보통신망법(옵트인·(광고)·야간·수신거부) 적용 → `kakao-biz-message` 및 `kr-ad-compliance` 참고.
- 소재 카피의 과장·미입증 표현은 `kr-ad-compliance` 점검.

## 연관 skill

`kr-performance-ads` · `ads` · `kr-ad-compliance`
