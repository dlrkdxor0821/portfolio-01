# CLAUDE.md — 이강택 포트폴리오

**이강택 개발자 취업용 포트폴리오** 작업 공간. 최종 산출물은 `이강택_포트폴리오.html`(A4 가로 26슬라이드) — 브라우저 인쇄→PDF로 제출.

## 폴더 구조

```
포트폴리오관련내용/
├─ 이강택_포트폴리오.html   ← 최종 산출물 (26슬라이드, 단일 HTML)
├─ assets/                  ← 슬라이드에 삽입되는 다이어그램 PNG (상대경로 참조)
├─ resume/                  ← 이력서 원본 (입사지원서 odt/pdf) = 프로필 사실의 출처
├─ 규칙/규칙.md             ← 포트폴리오 작성 규칙 (톤·구조·디자인)
└─ 내용정리/                ← 프로젝트별 사실 기록 (HTML의 근거)
   ├─ 핑더가든/핑더가든_내용정리.md
   └─ 쑈삥끼/{프로젝트-내용정리, 추종-기술정리}.md
```

**외부 자료 출처** (HTML 이미지·내용의 근거):
- 핑더가든 레포·이미지: `/home/asd/pingdergarten/` (presentation/panel/assets/*.png)
- 쑈삥끼 레포·이미지: `/home/asd/shoppinkki/docs/*.png`
- ABA(리비) — 진행중: `/home/asd/personal_repo/presen/` — `img/*.png`, `jira_data.json`, `confluence_data.json`(78p), `ABA_Libi_상세설계.pdf`

**작업 원칙**: 사실은 위 자료에 근거해서만 쓴다. 없는 수치·성과는 지어내지 않고 placeholder + 사용자 확인.

## 규칙 요약 (`규칙/규칙.md`)

- 구조: 표지 → 목차 → 프로필 → 프로젝트 → 마무리
- 프로젝트 = 선택의 기록 (문제정의·전략·트레이드오프·회고), 문제해결은 STAR
- "무엇을"보다 **"왜"**, 수치로 근거, "참여했습니다" 금지
- **톤앤매너 일관성**(폰트·컬러·톤), 마감 점검(오탈자·이미지 깨짐·링크)

## 디자인 토큰 (`:root`, 톤 고정)

- 폰트 `--sans` Noto Sans CJK KR · `--mono` D2Coding
- 텍스트 `--ink #18181B` `--sub #52525B` `--faint #8A8A93` · 선 `--line #E4E4E7`
- 강조 teal `--accent #0E7C6B` `--accent-bg #ECF6F3` · 골드 `--gold #B8860B`(수상·진행중)
- 슬라이드 297×210mm, 패딩 20mm 24mm. 한글은 `class="kr"`.
- 이미지 슬라이드: `.imgwrap`(높이 인라인 지정)+`object-fit:contain`, `.twoimg`, `.imgtext`. 폴더구조: `.folder`(monospace, `<b>`=본인담당 강조).

## 슬라이드 구성 (26p)

01 표지 · 02 Index · 03–04 Profile(2p) · **05–11 핑더가든(대표작, 7p)** · 12–18 쑈삥끼(7p) · 19–25 ABA·리비(진행중, 7p) · 26 Closing.
프로젝트 7p = 소개·아키텍처·(동작/상태/시퀀스)·folder·구현·문제해결/협업·회고. 페이지 상단 도트 네비 + `NN / 07` 카운터.

## 남은 작업 (사용자 확인/보완)

1. **지원동기 `[회사명]`** — 프로필 04p, 지원 회사 확정 후 채움.
2. **프로필 사진** — 03p `.photo`는 SVG placeholder. 실제 사진 삽입(이력서 pdf에 있음).
3. **회고·문제해결 세부** — 일부는 git/자료 기반 초안. 본인 실제 경험으로 교정 권장(핑더가든 회고, 쑈삥끼 협업 등).
4. **ABA 링크/영상** — 진행중, 필요 시 데모·발표 링크 추가.

## 검증 방법 (실측)

```
google-chrome-stable --headless=new --print-to-pdf=out.pdf --no-pdf-header-footer file://.../이강택_포트폴리오.html
pdftoppm -f N -l N -r 70 -png out.pdf pg   # 페이지별 PNG로 눈 확인
```
확인 포인트: 26슬라이드·페이지 연번, `assets/` 이미지 전부 로드, 텍스트 오버플로우, teal 톤 유지, 오탈자·placeholder 잔여.

## 주의

- Git 커밋/푸시는 사용자 명시 승인 없이 하지 않음 (전역 규칙).
- 이미지는 `assets/` 상대경로 참조 — HTML과 `assets/`를 같은 폴더에 유지해야 인쇄 시 이미지가 나옴.
