# QR UniPass — HTML + Supabase 버전

QR 하나로 캠퍼스(출석·식당)를 통합 운영하는 스마트 대학 데모. **HTML 한 파일**(`index.html`)에
**Supabase**(무료 실시간 DB)를 붙여, **여러 기기 → 하나의 대시보드 실시간**으로 동작합니다.

- **라이브 주소**: https://qr-unipass.netlify.app
- **발표자(관리자) 주소**: https://qr-unipass.netlify.app/?admin=gybm2026 (Dashboard에 Reset 버튼 노출)

## 기능
1. **체크인** — 학번 또는 이름 입력 → 색종이 + 성공 카드
2. **카페테리아** — 이름/ID + 메뉴 선택 → Pay → 가상 잔액 차감
3. **라이브 대시보드** — 출석 카운트(체크인 시 펄스+축포), 체크인 QR, 시간대별 차트,
   식당 매출 실시간 집계. 데이터는 Supabase에 영구 저장되고 여러 기기에서 실시간 공유됨.

## 구조
- 전부 `index.html` 한 파일 (HTML + CSS + JavaScript).
- 데이터: Supabase 테이블 `attendance`, `cafeteria` (RLS + realtime).
- `index.html` 상단 `SUPABASE_URL` / `SUPABASE_KEY`로 연결 (publishable 키 — 공개 안전).
- `qr.png` — 라이브 주소를 가리키는 체크인 QR (대시보드와 슬라이드에서 사용).

## 배포 (자동)
이 저장소는 Netlify와 연결돼 있어, **main 브랜치에 push하면 자동 배포**됩니다.
사이트 이름(주소)은 고정이라 QR은 다시 만들 필요 없음.

## 발표 전 체크리스트
- 전날/당일 아침에 라이브 주소를 한 번 열어 Supabase를 깨워두기 (무료 플랜은 7일 미사용 시 잠듦).
- 현장에서 폰으로 QR 1회 스캔 → 체크인 → 노트북 대시보드 숫자 확인.
- 발표 직전 `?admin=gybm2026`에서 Reset으로 비우고 시작. 폰 핫스팟 백업 준비.
