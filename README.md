<!doctype html>
<html lang="ko">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Twelve Fallen — Steam 상점 페이지(샘플)</title>
  <meta name="description" content="시간이 멈춘 신전에서 12거인을 쓰러뜨려 봉인을 완성하는 보스 중심 액션 어드벤처. 샘플 스토어 페이지입니다." />
  <style>
    :root {
      --bg: #0d1016;
      --bg-soft: #161a23;
      --panel: #131722;
      --panel-soft: #171b26;
      --accent: #c7a36a;
      --accent-soft: #2a3444;
      --text-muted: #9fa5b3;
      --steam-blue: #1b2a3c;
    }
    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Apple SD Gothic Neo", "Noto Sans KR", sans-serif;
      background: radial-gradient(circle at top center, #242b3b 0, #0b0d12 55%, #050609 100%);
      color: #eef2ff;
    }
    .page {
      max-width: 1120px;
      margin: 32px auto;
      padding: 0 24px 40px;
    }
    header {
      display: flex;
      gap: 18px;
      align-items: center;
    }
    .logo {
      width: 90px;
      height: 90px;
      border-radius: 12px;
      background: radial-gradient(circle at 30% 20%, #fff2 0, transparent 60%),
                  linear-gradient(145deg, #f5e1b2, #9b6232);
      display: flex;
      align-items: center;
      justify-content: center;
      color: #120b06;
      font-weight: 800;
      font-size: 22px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.6);
    }
    h1 {
      margin: 0;
      font-size: 28px;
    }
    .subtitle {
      margin-top: 6px;
      color: var(--text-muted);
      font-size: 14px;
    }

    .hero-wrap {
      margin-top: 20px;
      position: relative;
    }
    /* 양방향 그라데이션 오라 */
    .hero-wrap::before,
    .hero-wrap::after {
      content: "";
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
      width: 120%;
      max-width: 1400px;
      pointer-events: none;
      z-index: -1;
    }
    .hero-wrap::before {
      top: -120px;
      height: 260px;
      background: radial-gradient(circle at center, rgba(64,77,120,0.8) 0, transparent 60%);
      opacity: 0.85;
    }
    .hero-wrap::after {
      bottom: -180px;
      height: 320px;
      background: radial-gradient(circle at center, rgba(0,0,0,0.8) 0, transparent 60%);
      opacity: 0.7;
    }

    .hero {
      display: grid;
      grid-template-columns: minmax(0, 1.6fr) minmax(290px, 0.9fr);
      gap: 22px;
    }
    .hero-main {
      background: linear-gradient(180deg, rgba(255,255,255,0.015), rgba(0,0,0,0.35));
      border-radius: 14px;
      padding: 18px 18px 20px;
      box-shadow: 0 16px 40px rgba(0,0,0,0.55);
    }
    .banner {
      position: relative;
      height: 340px;
      border-radius: 12px;
      overflow: hidden;
      background-image: url("banner-placeholder.jpg");
      background-size: cover;
      background-position: center;
      display: flex;
      align-items: flex-end;
      isolation: isolate;
    }
    .banner::before {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(to top, rgba(3,6,10,0.95) 0, rgba(10,12,18,0.2) 55%, rgba(17,20,30,0.9) 100%);
      mix-blend-mode: multiply;
    }
    .banner-caption {
      position: relative;
      padding: 18px 20px;
      color: #f6f7ff;
      text-shadow: 0 6px 18px rgba(0,0,0,0.85);
    }
    .banner-caption-title {
      font-size: 18px;
      font-weight: 700;
    }
    .banner-caption-sub {
      margin-top: 4px;
      font-size: 13px;
      color: #e1e6ff;
    }

    .buy-panel {
      background: radial-gradient(circle at top, #263349 0, #10131b 60%);
      border-radius: 14px;
      padding: 18px 18px 16px;
      box-shadow: 0 16px 40px rgba(0,0,0,0.6);
      border: 1px solid rgba(255,255,255,0.04);
      display: flex;
      flex-direction: column;
      gap: 14px;
    }
    .buy-head {
      display: flex;
      justify-content: space-between;
      gap: 10px;
      align-items: flex-start;
    }
    .buy-head-meta-label {
      font-size: 12px;
      color: var(--text-muted);
      text-transform: uppercase;
      letter-spacing: 0.07em;
    }
    .buy-head-title {
      font-weight: 700;
    }
    .price {
      font-size: 26px;
      font-weight: 800;
      text-align: right;
    }
    .price-sub {
      font-size: 12px;
      color: var(--text-muted);
      text-align: right;
    }
    .btn-buy {
      margin-top: 6px;
      width: 100%;
      border-radius: 8px;
      border: none;
      background: linear-gradient(90deg, #d1b067, #f8e3a4);
      color: #221306;
      font-weight: 800;
      padding: 10px 14px;
      cursor: pointer;
      font-size: 15px;
    }
    .btn-buy:hover {
      filter: brightness(1.05);
    }
    .buy-small-meta {
      font-size: 12px;
      color: var(--text-muted);
    }

    .long-desc-wrap {
      margin-top: 18px;
      background: rgba(4,6,11,0.85);
      border-radius: 12px;
      padding: 14px 16px;
      border: 1px solid rgba(255,255,255,0.04);
    }
    .long-desc-title {
      font-size: 15px;
      font-weight: 600;
      margin-bottom: 8px;
    }
    .long-desc {
      max-height: 220px;
      overflow: hidden;
      position: relative;
      color: var(--text-muted);
      font-size: 14px;
      line-height: 1.65;
    }
    .long-desc.collapsed::after {
      content: "";
      position: absolute;
      left: 0;
      right: 0;
      bottom: 0;
      height: 70px;
      background: linear-gradient(to bottom, rgba(4,5,9,0), rgba(4,5,9,0.96));
    }
    .long-desc p {
      margin: 0 0 10px;
    }
    .toggle-desc-btn {
      margin-top: 6px;
      background: none;
      border: none;
      color: #d1e2ff;
      font-size: 13px;
      display: inline-flex;
      align-items: center;
      gap: 4px;
      cursor: pointer;
      padding: 4px 0 0;
    }

    .features {
      margin-top: 26px;
      display: grid;
      grid-template-columns: repeat(2, minmax(0,1fr));
      gap: 16px;
    }
    .feature {
      background: linear-gradient(145deg, rgba(18,23,35,0.98), rgba(11,15,23,0.98));
      border-radius: 12px;
      padding: 14px 15px 12px;
      border: 1px solid rgba(255,255,255,0.03);
    }
    .feature h3 {
      margin: 0 0 6px;
      font-size: 15px;
    }
    .feature p {
      margin: 0;
      color: var(--text-muted);
      font-size: 13px;
      line-height: 1.6;
    }

    /* 지원 정보 영역 */
    .support-section {
      margin-top: 30px;
      display: grid;
      grid-template-columns: minmax(0, 1.1fr) minmax(280px, 0.9fr);
      gap: 18px;
    }
    .support-panel {
      background: var(--panel);
      border-radius: 12px;
      padding: 14px 16px;
      border: 1px solid rgba(255,255,255,0.04);
    }
    .support-panel h2 {
      margin: 0 0 10px;
      font-size: 16px;
    }
    .support-row {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 6px 0;
      border-bottom: 1px solid rgba(255,255,255,0.04);
      font-size: 13px;
    }
    .support-row:last-child { border-bottom: none; }
    .support-row-label { color: var(--text-muted); }
    .support-row-value { font-weight: 600; }
    .support-row-value.positive { color: #87d38c; }

    .support-tags {
      margin-top: 10px;
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      font-size: 12px;
    }
    .support-tag {
      background: #1a2433;
      color: #dde7ff;
      padding: 4px 8px;
      border-radius: 4px;
    }

    .controller-panel {
      background: var(--panel-soft);
      border-radius: 12px;
      padding: 14px 16px 10px;
      border: 1px solid rgba(255,255,255,0.04);
      font-size: 13px;
    }
    .controller-title {
      font-weight: 600;
      margin-bottom: 6px;
    }
    .controller-highlight {
      color: #9ad18b;
      margin-top: 2px;
    }

    .language-panel {
      margin-top: 14px;
      background: #10131d;
      border-radius: 12px;
      border: 1px solid rgba(255,255,255,0.05);
    }
    .language-header {
      padding: 10px 14px;
      font-size: 14px;
      background: linear-gradient(180deg, #1d2636, #151926);
      border-radius: 12px 12px 0 0;
    }
    table.lang-table {
      width: 100%;
      border-collapse: collapse;
      font-size: 12px;
    }
    .lang-table th,
    .lang-table td {
      padding: 6px 10px;
      text-align: left;
    }
    .lang-table thead {
      background: #151926;
    }
    .lang-table tbody tr:nth-child(odd) {
      background: rgba(255,255,255,0.01);
    }
    .lang-table tbody tr:nth-child(even) {
      background: rgba(255,255,255,0.03);
    }
    .lang-table th {
      font-weight: 500;
      color: var(--text-muted);
    }
    .lang-table td.check {
      width: 70px;
      text-align: center;
    }

    .req-section {
      margin-top: 30px;
      background: var(--panel);
      border-radius: 12px;
      padding: 14px 16px 18px;
      border: 1px solid rgba(255,255,255,0.04);
      color: var(--text-muted);
      font-size: 13px;
    }
    .req-columns {
      display: grid;
      grid-template-columns: repeat(2, minmax(0,1fr));
      gap: 16px;
      margin-top: 10px;
    }
    .req-col-title {
      font-weight: 600;
      color: #e5e9f7;
      margin-bottom: 4px;
    }

    footer {
      margin-top: 30px;
      padding-top: 14px;
      border-top: 1px solid rgba(255,255,255,0.04);
      font-size: 12px;
      color: var(--text-muted);
      display: flex;
      justify-content: space-between;
      gap: 12px;
      flex-wrap: wrap;
    }

    @media (max-width: 960px) {
      .hero { grid-template-columns: minmax(0,1fr); }
      .support-section { grid-template-columns: minmax(0,1fr); }
    }
    @media (max-width: 640px) {
      .page { margin-top: 18px; padding: 0 14px 30px; }
      .banner { height: 260px; }
      .features { grid-template-columns: minmax(0,1fr); }
      header { align-items: flex-start; }
      .logo { width: 70px; height: 70px; font-size: 18px; }
    }
  </style>
</head>
<body>
  <div class="page">
    <header>
      <div class="logo">TF</div>
      <div>
        <h1>Twelve Fallen</h1>
        <div class="subtitle">129년의 침묵. 깨어난 악. 마지막 가드너의 봉인.</div>
      </div>
    </header>

    <div class="hero-wrap">
      <div class="hero">
        <main class="hero-main" aria-label="게임 정보">
          <section class="banner" aria-label="게임 대표 이미지">
            <div class="banner-caption">
              <div class="banner-caption-title">잊힌 신전, 정지한 시간</div>
              <div class="banner-caption-sub">열두 거인의 등 위에서 악을 봉인하는 미니멀리즘 보스 액션</div>
            </div>
          </section>

          <section class="long-desc-wrap">
            <div class="long-desc-title">게임 설명</div>
            <div class="long-desc collapsed" id="long-desc">
              <p>어느 날, 세계에 열두 구의 거인이 떨어졌다. 그들은 전쟁, 기아, 폭력, 차별… 인간이 쌓아 올린 모든 악을 흡수해 소멸시키는 존재였다. 사람들은 그것을 기적이라 불렀지만, 거인들이 삼킨 악이 언젠가 다시 세계에 풀려날지 모른다는 공포는 곧 기적을 두려움으로 바꾸었다.</p>
              <p>결국 인류는 열두 거인을 멸지(滅地)에 유폐하고 그 위에 봉인의 신전을 세운 뒤, 스스로 모든 기록을 지우고 모든 기억을 봉인했다. 오직 한 사람, 신전의 봉인을 관리하기 위해 남겨진 가드너(Gardener)만이 진실을 기억한 채 정지한 시간 속에서 129년을 홀로 보냈다.</p>
              <p>그러던 어느 날, 가드너는 신전 깊숙한 곳에서 불길한 전율을 느낀다. 거인들과 연결된 열두 개의 석상들이 모두 검게 물들어 무너져 있었고, 봉인은 이미 균열을 드러내고 있었다. 거인들은 악에 잠식되었고, 세계가 잊어버린 죄가 다시 꿈틀거리고 있었다.</p>
              <p>플레이어는 무기와 화려한 장비 대신, 몸 하나와 관찰력, 타이밍만으로 거대한 거인들을 오르고 약점을 찾아내야 한다. 각 거인은 서로 다른 형태의 ‘악’을 품고 있으며, 그 몸 자체가 하나의 거대한 던전이자 전장이 된다. 균열을 뛰어넘고, 기생하는 구조물을 피하고, 위험을 감수해 더 높은 곳으로 손을 뻗어야만 한다.</p>
              <p><strong>Twelve Fallen</strong>은 정지한 세계의 고독함과 신화적인 스케일의 보스전을 결합한 미니멀리즘 액션 어드벤처입니다. 과도한 UI와 설명을 걷어내고, 플레이어의 시선과 선택을 통해 서사가 서서히 드러나는 경험에 초점을 맞추었습니다. 당신은 열두 거인을 멸하고 악을 봉인할 것인가, 아니면 또 다른 선택을 할 것인가.</p>
            </div>
            <button class="toggle-desc-btn" id="toggle-desc" aria-expanded="false">
              <span>더 보기</span><span>▾</span>
            </button>
          </section>
        </main>

        <aside class="buy-panel" aria-label="구매 정보">
          <div class="buy-head">
            <div>
              <div class="buy-head-meta-label">장르</div>
              <div class="buy-head-title">액션, 어드벤처, 보스러시</div>
            </div>
            <div>
              <div class="price">₩19,800</div>
              <div class="price-sub">출시 예정 · 싱글 플레이</div>
            </div>
          </div>
          <button class="btn-buy">장바구니에 추가</button>
          <div class="buy-small-meta">플레이어 수: 싱글 플레이 · 비동기 소통 요소 포함</div>
        </aside>
      </div>
    </div>

    <section aria-label="주요 특징" style="margin-top:26px;">
      <div class="features">
        <article class="feature">
          <h3>・정지한 시간의 신전</h3>
          <p>외부 세계와 단절된 신전에서 시간은 흐르지 않습니다. 부서진 회랑과 봉인의 제단이 하나의 거대한 던전처럼 이어지며, 탐색 자체가 퍼즐이 됩니다.</p>
        </article>
        <article class="feature">
          <h3>・압도적인 거인과의 일대일 대면</h3>
          <p>12체의 거인은 각기 다른 구조와 약점을 지닌 보스로, 그 몸을 오르는 것부터가 전투의 일부입니다. 관찰과 등반, 과감한 점프로 공략 루트를 찾아내야 합니다.</p>
        </article>
        <article class="feature">
          <h3>・가드너의 기록으로 엮이는 신화</h3>
          <p>129년에 걸친 가드너의 기록과 신전에 남겨진 잔재들을 통해, 거인과 인류가 왜 망각을 선택했는지 서서히 드러납니다. 단편적인 조각이 모여 하나의 봉인 신화를 이룹니다.</p>
        </article>
        <article class="feature">
          <h3>・느슨하게 이어지는 세계</h3>
          <p>다른 플레이어의 발걸음과 선택이 비동기적으로 세계에 잔향을 남깁니다. 직접 만나지는 않지만, 서로의 존재를 은근히 느낄 수 있습니다.</p>
        </article>
      </div>
    </section>

    <section class="support-section" aria-label="지원 정보">
      <div class="support-panel">
        <h2>이 게임에 관심이 있나요?</h2>
        <div class="support-row">
          <div class="support-row-label">평균 플레이 시간</div>
          <div class="support-row-value">약 3시간 (메인 클리어 기준)</div>
        </div>
        <div class="support-row">
          <div class="support-row-label">사용자 평가</div>
          <div class="support-row-value positive">매우 긍정적 (예상)</div>
        </div>
        <div class="support-row">
          <div class="support-row-label">지원하는 게임 방식</div>
          <div class="support-row-value">싱글 플레이</div>
        </div>
        <div class="support-tags">
          <span class="support-tag">싱글 플레이어</span>
          <span class="support-tag">도전 과제</span>
          <span class="support-tag">클라우드 저장</span>
          <span class="support-tag">Remote Play</span>
          <span class="support-tag">가족 공유</span>
        </div>
      </div>

      <div>
        <div class="controller-panel">
          <div class="controller-title">컨트롤러 완벽 지원</div>
          <div class="controller-highlight">Xbox 컨트롤러</div>
          <div style="margin-top:4px; color: var(--text-muted);">다른 기기에 대한 지원 여부는 아직 알려져 있지 않습니다.</div>
        </div>

        <div class="language-panel" aria-label="언어 지원">
          <div class="language-header">언어</div>
          <table class="lang-table">
            <thead>
              <tr>
                <th>언어</th>
                <th class="check">인터페이스</th>
                <th class="check">음성</th>
                <th class="check">자막</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>한국어</td>
                <td class="check">✔</td>
                <td class="check">—</td>
                <td class="check">✔</td>
              </tr>
              <tr>
                <td>영어</td>
                <td class="check">✔</td>
                <td class="check">—</td>
                <td class="check">✔</td>
              </tr>
              <tr>
                <td>독일어</td>
                <td class="check">✔</td>
                <td class="check">—</td>
                <td class="check">✔</td>
              </tr>
              <tr>
                <td>프랑스어</td>
                <td class="check">✔</td>
                <td class="check">—</td>
                <td class="check">✔</td>
              </tr>
              <tr>
                <td>스페인어 - 스페인</td>
                <td class="check">✔</td>
                <td class="check">—</td>
                <td class="check">✔</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </section>

    <section class="req-section" aria-label="시스템 요구 사항">
      <div style="font-size:14px; color:#e2e6f5; font-weight:600; margin-bottom:4px;">시스템 요구 사항</div>
      <div class="req-columns">
        <div>
          <div class="req-col-title">최소 사양</div>
          <div>OS: Windows 10 64-bit<br>프로세서: Intel i5 4세대 또는 동급<br>메모리: 8 GB RAM<br>그래픽: NVIDIA GTX 970 / 동급<br>저장공간: 15 GB 여유 공간</div>
        </div>
        <div>
          <div class="req-col-title">권장 사양</div>
          <div>OS: Windows 10/11 64-bit<br>프로세서: Intel i7 / Ryzen 5 또는 상위<br>메모리: 16 GB RAM<br>그래픽: NVIDIA GTX 1660 / RTX 2060 또는 상위<br>저장공간: SSD 권장</div>
        </div>
      </div>
    </section>

    <footer>
      <div>
        <div style="font-weight:600; color:#dde3ff;">Twelve Fallen</div>
        <div style="margin-top:4px;">개발사: Your Studio · 퍼블리셔: Your Label</div>
      </div>
      <div>© Your Studio. All rights reserved.</div>
    </footer>
  </div>

  <script>
    (function(){
      var btn = document.getElementById('toggle-desc');
      var desc = document.getElementById('long-desc');
      if(!btn || !desc) return;
      btn.addEventListener('click', function(){
        var collapsed = desc.classList.toggle('collapsed');
        var labelSpan = btn.querySelector('span:first-child');
        var iconSpan = btn.querySelector('span:last-child');
        if(labelSpan && iconSpan){
          if(collapsed){
            labelSpan.textContent = '더 보기';
            iconSpan.textContent = '▾';
            btn.setAttribute('aria-expanded','false');
          } else {
            labelSpan.textContent = '접기';
            iconSpan.textContent = '▴';
            btn.setAttribute('aria-expanded','true');
          }
        }
      });
    })();
  </script>
</body>
</html>
