# QR UniPass — HTML + Supabase 버전

QR 하나로 캠퍼스(출석·식당·도서관·기숙사)를 통합 운영하는 스마트 대학 데모. **HTML 한 파일**(`index.html`)에
**Supabase**(무료 실시간 DB)를 붙여, **여러 기기 → 하나의 대시보드 실시간**으로 동작합니다.
호스팅은 **GitHub Pages**(무료·무제한).

- **라이브 주소**: https://chan026-normal.github.io/qr-unipass-web/
- **발표자(관리자) 주소**: https://chan026-normal.github.io/qr-unipass-web/?admin=chan2026 (Dashboard에 Reset 버튼 노출)

## 기능 (4개 모듈 + 대시보드)
1. **체크인(출석)** — 학번 또는 이름 → 색종이 + 성공 카드
2. **카페테리아** — ID/이름 + 메뉴 → Pay → 가상 잔액 차감
3. **도서관(Library)** — ID/이름 → Borrow / Return (대출·반납)
4. **기숙사(Dormitory)** — ID/이름 → Enter / Exit (입실·퇴실)
5. **라이브 대시보드** — 출석 카운트(펄스+축포), 체크인 QR, present 모드(프로젝터),
   시간대별 차트, **Campus activity 결합 그래프(4모듈 한눈에)**, 식당 매출. 모두 Supabase 실시간 공유.

## 구조
- 전부 `index.html` 한 파일 (HTML + CSS + JavaScript).
- 데이터: Supabase 테이블 `attendance`, `cafeteria`, `library`, `dormitory` (RLS + realtime).
- `index.html` 상단 `SUPABASE_URL` / `SUPABASE_KEY`로 연결 (publishable 키 — 공개 안전), `ADMIN_KEY = "chan2026"`.
- `qr.png` — 라이브 주소를 가리키는 체크인 QR (대시보드·슬라이드에서 사용).

## 배포 (자동)
- **GitHub Pages**: 공개 저장소의 `main` 브랜치에 push하면 자동 빌드·배포. 주소 고정이라 QR 안 바꿔도 됨.
- Netlify는 더 이상 필요 없음(백업/선택). 크레딧 아끼려면 Netlify 사이트는 나중에 정리 가능.

## 발표 전 체크리스트
- 전날/당일 아침에 라이브 주소를 한 번 열어 Supabase를 깨워두기 (무료 플랜은 7일 미사용 시 잠듦).
- 현장에서 폰으로 QR 1회 스캔 → 체크인 → 노트북 대시보드 숫자 확인.
- 발표 직전 `?admin=chan2026`에서 Reset(4모듈 전부 비움) 후 시작. 폰 핫스팟 백업 준비.
