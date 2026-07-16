# 인노사 데일리 정보

인사·노무 리스크 데일리 리포트 아카이브. 매일 발행되는 리포트를 일자별로 모아 웹에서 보고, PDF로 내려받을 수 있는 정적 사이트입니다.

## 공개 주소 (GitHub Pages · 루트 서빙)

`https://cchulmin-steve.github.io/today-working/` 에서 공개됩니다.
(Settings → Pages → Source: `main` 브랜치 / `/ (root)`)

> 기존 "AI 교육 3일 정리" 페이지는 `ai-edu/` 로 옮겨 보존했습니다 →
> `https://cchulmin-steve.github.io/today-working/ai-edu/`

## 구조

```
index.html        홈 (일자별 리스트 + 본문 뷰어 + PDF 첨부)
reports.json      일자별 목록 (매일 항목 누적)
.nojekyll
reports/
├─ <날짜>.html     리포트 본문 (사이트 내 표시)
└─ <날짜>.pdf      리포트 첨부파일 (다운로드)
ai-edu/           기존 'AI 교육 3일 정리' 페이지 (보존)
```

## 새 리포트 추가 방법

1. `reports/<YYYY-MM-DD>.html` 와 `<YYYY-MM-DD>.pdf` 추가
2. `reports.json` 배열 **맨 앞**에 항목 추가:
   ```json
   { "date":"2026-07-17", "title":"인사노무 리스크·우선순위 리포트",
     "summary":"한 줄 요약", "tags":["태그1","태그2"],
     "html":"reports/2026-07-17.html", "pdf":"reports/2026-07-17.pdf" }
   ```
3. `index.html` 은 고정 — `reports.json` 을 읽어 리스트를 자동 렌더링합니다.

> 로컬 미리보기는 정적 서버가 필요합니다(브라우저로 파일 직접 열면 목록이 로드되지 않음).

## 주의

본 리포트는 고용노동부·대법원·한국노동연구원 등 1차 자료를 기준으로 정리한 **참고용** 자료이며, 법률 자문이 아닙니다.
