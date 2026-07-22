# Tape Lounge

> A lounge for reading the tape — real-time crypto metrics, living order flow, and three resident strategists.
> 크립토 시장의 "보는 맛"을 모아둔 라운지 — 실시간 지표, 살아 움직이는 체결, 그리고 세 명의 전략가.

**Live** → https://tapelounge.com *(coming soon)* · https://giho919.github.io/tape-lounge/

A **single-file static site** that runs entirely on free public APIs in the browser (no backend; only chat & leaderboard use Supabase). The concept: a members' hideaway for people who like to *read the tape*.

*English below · 한국어는 아래에 있습니다 ↓*

---

## 🇬🇧 English

### 🥂 Lounge (main)

Read the market's *now* on a single screen.

**Top metric strip**
- **BTC / KRW·USDT** — live won & dollar prices
- **Kimchi Premium** — analog gauge; the Korean-market premium computed as Upbit KRW-BTC ÷ (Binance BTCUSDT × KRW-USDT)
- **Fear & Greed Index** — from alternative.me (0 = extreme fear ~ 100 = extreme greed)
- **BTC Dominance** — Bitcoin's share of total market cap
- **Funding Rate** — perpetual-futures 8h funding (a gauge of futures-market heat)

**Live charts (swipeable)**
- **Symbols**: BTC · ETH · BTC.D (dominance) · NASDAQ (QQQB, a Nasdaq-100 ETF token)
- **Timeframes**: 1m · 15m · 60m · 240m · daily · weekly · monthly
- **Moving averages**: MA 10 · 20 · 60 · 120 · 200 (live, on every chart)
- Countdown to candle close, split-flap price display

**Candle Deck 🃏** — each closed candle is dealt as a card. Body size sets its rarity (common → uncommon → rare → **epic / big candle**). The deck follows your selected chart & timeframe, with a `?` card holding the next slot.

**Rain of Fills 🌧** — every **real trade** happening on Binance right now falls as a raindrop. Left = sell, right = buy; drop size = trade value; gold ring = $500k+ whale; spreading ripples = futures liquidations; the bottom bar shows buy/sell pressure.

**Full-screen reactions** — big bullish/bearish candle bursts, 60-minute breakout / breakdown, neon flicker, spotlight — the whole screen responds when the market moves hard.

**Interactive**
- **Lounge Chat** — live visitor chat (nickname-based); the strategists' letters and news flow in alongside
- **Next-Candle Prediction** — call the next BTC 1-minute candle (UP/DOWN) in advance and build a win streak (locked when the candle opens, judged at close)
- **Leaderboard** — self-standing ranking by best streak & record

### 🎰 Blind Chart

You're dropped into a **real past crypto market** with its identity hidden — no symbol, no dates (start price indexed to 100, time axis removed). Trade a $10,000 stake day by day; after 200 days the identity is revealed and you're judged against **buy & hold over the same window**. Moving averages included.

### 🎩 The Strategists

Three resident characters. Each has an avatar, a style radar, an activity journal, and a daily-refreshed report.

| Strategist | Beat | Publishes |
|------------|------|-----------|
| **Madam Jeong** | Yeouido | Morning system-status letter + today's ledger (position direction, market regime, indicator charts) |
| **Andy** | Chicago | Evening altcoin-scan wire (breakout / trend / bottom-reversal candidates) |
| **Prof. Justin** | The Lab | Monthly regime-model opinion + a history-of-verdicts dashboard |

Reports are auto-generated daily and pushed to this repo's `reports/`.
> ⚠️ Public reports **never include sensitive figures** — no account balance, P&L amounts, or entry prices. Only informational content (market indicators, position direction, regime verdicts).

### Data sources
All public & free APIs, called directly from the browser:
- **Binance** — spot/futures WebSocket (trades, candles, liquidations, dominance index) + REST history
- **Upbit** — REST (KRW prices for the kimchi-premium calc)
- **alternative.me** — Fear & Greed
- **CoinGecko** — global dominance

### Tech
- Single HTML file (`index.html`) — only external deps are lightweight-charts and Supabase JS (via CDN)
- **Supabase** — live chat & leaderboard (Row Level Security; read/insert only)
- **Hosting** — GitHub Pages

### Disclaimer
This site is for informational purposes only and is not investment advice. All investment decisions and their consequences are the user's own.

---

## 🇰🇷 한국어

### 🥂 라운지 (메인)

한 화면에서 시장의 지금을 읽습니다.

**상단 지표 스트립**
- **BTC / KRW·USDT** — 원화·달러 실시간 가격
- **김치 프리미엄** — 아날로그 게이지. 업비트 KRW-BTC ÷ (바이낸스 BTCUSDT × KRW-USDT)로 산출한 한국 시장 프리미엄
- **공포·탐욕 지수** — alternative.me Fear & Greed (0=극단 공포 ~ 100=극단 탐욕)
- **BTC 도미넌스** — 전체 시총 중 비트코인 점유율
- **펀딩비** — 무기한 선물 8시간 펀딩 (선물 시장 과열 온도)

**라이브 차트 (넘겨보기)**
- **종목**: BTC · ETH · BTC.D(도미넌스) · NASDAQ(QQQB, 나스닥100 ETF 토큰)
- **타임프레임**: 1분 · 15분 · 60분 · 240분 · 일봉 · 주봉 · 월봉
- **이동평균선**: MA 10 · 20 · 60 · 120 · 200 (전 차트 실시간)
- 봉 마감까지 카운트다운, split-flap 가격 표시

**캔들 덱 🃏** — 마감된 캔들이 한 장씩 카드로 딜립니다. 몸통 크기에 따라 등급이 갈립니다 (일반 → 언커먼 → 레어 → **에픽/장대봉**). 선택한 차트·타임프레임을 그대로 따라가며, 맨 오른쪽 `?` 카드가 다음 봉 자리를 지킵니다.

**체결의 비 🌧** — 지금 이 순간 바이낸스에서 일어나는 **실제 체결**이 빗방울로 떨어집니다. 왼쪽=매도, 오른쪽=매수 / 방울 크기=체결 금액 / 금테=$50만+ 고래 / 퍼지는 파문=선물 강제 청산 / 하단 수급 바=매수·매도 압력 비율.

**전면 연출** — 장대양봉 분출 · 장대음봉 낙하 · 60분 고점 돌파 / 저점 붕괴 · 네온 점멸 · 스포트라이트. 시장이 크게 움직이는 순간을 화면 전체로 반응합니다.

**참여 요소**
- **라운지 채팅** — 방문자 실시간 채팅 (닉네임 기반) + 전략가들의 서신·소식이 함께 흐름
- **다음 캔들 예측** — BTC 1분봉의 다음 방향(UP/DOWN)을 미리 걸고 연승에 도전 (봉이 열리는 순간 잠금 → 마감 판정)
- **리더보드** — 예측 최고 연승·전적 기반 자율 순위

### 🎰 블라인드 차트

정체를 숨긴 **과거의 실제 코인 시장**에 던져집니다. 종목도 날짜도 비밀 (시작가 100 기준 지수화, 시간축 숨김). 밑천 $10,000으로 하루씩 넘기며 매매하고, 200일 뒤 정체가 공개되며 **같은 기간 존버(buy & hold) 대비 성적**으로 판정받습니다. 이동평균선도 함께 표시됩니다.

### 🎩 전략가들

라운지에 상주하는 세 명의 캐릭터. 각자 아바타·성향 레이더·활동 일지를 갖고, 매일 갱신되는 리포트를 발행합니다.

| 전략가 | 무대 | 발행물 |
|--------|------|--------|
| **鄭마담** | 여의도 | 매일 아침 시스템 현황 서신 + 오늘의 장부 (포지션 방향·시장 국면·지표 차트) |
| **Andy** | Chicago | 매일 저녁 알트코인 스캔 전보 (돌파·추세·바닥반전 3종 후보) |
| **Prof. Justin** | 연구실 | 매월 시장 국면 판정 모형 소견서 + 판정의 역사 대시보드 |

리포트는 서버가 매일 자동 생성해 이 저장소의 `reports/`로 push합니다.
> ⚠️ 공개 리포트에는 **계좌 잔고·수익 금액·진입가 등 민감 정보를 일절 담지 않습니다.** 시장 지표와 포지션 방향·국면 판정 등 정보 제공 목적의 내용만 게재합니다.

### 데이터 출처
전부 공개·무료 API, 브라우저에서 직접 호출:
- **Binance** — 현물/선물 WebSocket (체결·캔들·강제청산·도미넌스 지수), REST 과거 캔들
- **Upbit** — REST (김치 프리미엄 산출용 KRW 시세)
- **alternative.me** — 공포·탐욕 지수
- **CoinGecko** — 글로벌 도미넌스

### 기술
- 단일 HTML 파일 (`index.html`) — 외부 의존성은 lightweight-charts, Supabase JS(CDN)뿐
- **Supabase** — 라이브 채팅·리더보드 (Row Level Security 적용, 읽기·삽입만 허용)
- **호스팅** — GitHub Pages

### 면책
본 사이트는 정보 제공 목적이며 투자 권유가 아닙니다. 모든 투자 판단과 책임은 이용자 본인에게 있습니다.
