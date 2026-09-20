# LifeMedi SEO 작업 상태

기준 브랜치: `seo/technical-seo-v28`

## P0 — 색인/크롤링

- [x] Blogger 기본 `all-head-content` 유지
- [x] canonical 재작성/삭제 없음
- [x] 테마 XML 내 강제 `noindex` 없음
- [x] 홈 JS Feed 섹션에 초기 HTML fallback 링크 추가
- [x] 관련글 영역에 초기 HTML fallback 링크 추가
- [x] 게시글 제목은 상세에서 H1, 목록에서 H2 구조 확인
- [x] 본문 내부 H1은 런타임에서 H2로 변환하는 기존 로직 유지
- [ ] 게시글 원본 HTML의 중복 H1 전수 점검 — Blogger 게시물 데이터 필요
- [ ] Search Console URL 검사 — Search Console 연결 필요

## P1 — On-page SEO

- [x] 홈 전용 title 적용
- [x] 홈 meta description fallback 적용
- [x] 게시글 breadcrumb UI 추가
- [x] 건강정보 이용 안내(YMYL 고지) 추가
- [x] 관련글 내부링크 fallback 추가
- [x] Hero/카드 이미지 크기 지정 및 첫 Hero 우선 로딩
- [ ] 게시글별 Search Description 전수 점검 — Blogger 게시물 데이터 필요
- [ ] 본문 contextual internal link 전수 점검 — Blogger 게시물 데이터 필요

## P1 — Structured Data

- [x] 기존 `postMeta`에서 Blogger 네이티브 `postMetadataJSON` 호출 확인
- [x] 별도 Article JSON-LD를 중복 삽입하지 않음
- [ ] 운영 렌더링에서 실제 BlogPosting 필드 검증
- [ ] BreadcrumbList 추가 여부는 Rich Results 검증 후 결정

## P1 — 중복 콘텐츠

- [ ] 본문 similarity 전수 분석 — Blogger 게시물 export/feed 필요
- [ ] 대표 URL 선정 및 통합 대상 확정
- [ ] 기존 URL 처리(유지/리디렉션/비공개)는 Search Console 유입 확인 후 결정

기존 점검에서 알려진 우선 후보:
- `눈 건강을 위한 루테인과 오메가-3의 시너지 효과`
- `루테인과 오메가-3를 함께 섭취해야 하는 이유`

## P2 — 성능

- [x] 홈 Hero 첫 이미지 `fetchpriority=high`
- [x] 카드 이미지 width/height 지정
- [x] 사이드 이미지 width/height 지정
- [ ] 운영 적용 후 PageSpeed Insights LCP/CLS/INP 확인
- [ ] 실제 AdSense 로딩 후 CLS 영향 확인

## 외부 확인 필요

Search Console에서:
- 페이지 색인
- URL 검사
- 발견됨 - 현재 색인이 생성되지 않음
- 크롤링됨 - 현재 색인이 생성되지 않음
- 중복, Google이 다른 표준 선택
- Sitemap
- Core Web Vitals
- 수동 조치

## 다음 순서

1. PR 적용 전 XML/렌더링 확인
2. Blogger에 테스트 적용
3. Search Console 연결 후 색인 데이터 점검
4. 게시물 export 또는 feed 확보
5. 중복 H1 / Search Description / 중복 콘텐츠 전수 분석
6. 2차 SEO PR
