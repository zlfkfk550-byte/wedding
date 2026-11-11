[Uploading index (1).html…]()
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>모바일 청첩장</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Gowun+Batang:wght@400;700&family=Noto+Sans+KR:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#ffffff; --paper:#ffffff; --ink:#333333; --sub:#8e8e8e;
    --accent:#9a9a9a; --line:#eeeeee; --soft:#f7f7f7;
  }
  *{box-sizing:border-box;margin:0;padding:0}
  html{-webkit-text-size-adjust:100%}
  body{background:#f4f4f4;font-family:'Noto Sans KR',sans-serif;color:var(--ink);font-weight:300;line-height:1.8;-webkit-tap-highlight-color:transparent}
  .wrap{max-width:430px;margin:0 auto;background:var(--paper);min-height:100vh;overflow:hidden}
  section{padding:72px 28px;text-align:center;border-bottom:1px solid var(--line)}
  .serif{font-family:'Gowun Batang',serif}
  .eyebrow{font-size:11px;letter-spacing:.35em;color:var(--accent);margin-bottom:18px;text-transform:uppercase}
  h2{font-family:'Gowun Batang',serif;font-weight:400;font-size:20px;margin-bottom:28px}
  p{font-size:15px}
  .muted{color:var(--sub)}

  /* 사진 자리 */
  .photo{background:var(--soft);border:1.5px dashed #dddddd;border-radius:4px;display:flex;flex-direction:column;align-items:center;justify-content:center;color:var(--sub);font-size:12px;gap:6px}
  .photo svg{width:26px;height:26px;opacity:.55}

  /* 커버 */
  .cover{padding:0 0 56px;border:none}
  .cover .photo{aspect-ratio:3/4;border-radius:0;border-left:none;border-right:none;border-top:none}
  .cover .date-top{font-family:'Gowun Batang',serif;font-size:13px;letter-spacing:.3em;color:var(--accent);margin:40px 0 14px}
  .cover .names{font-family:'Gowun Batang',serif;font-size:26px;letter-spacing:.08em}
  .cover .names span{font-size:15px;color:var(--accent);margin:0 12px;vertical-align:middle}
  .cover .when{margin-top:16px;font-size:14px;color:var(--sub);line-height:1.7}

  /* 인사말 */
  .greeting p.serif{font-size:15.5px;line-height:2.15}
  .parents{margin-top:44px;display:grid;gap:10px;font-size:15px}
  .parents b{font-weight:500}
  .parents .rel{color:var(--sub);font-size:13px;margin:0 6px}

  /* 달력 */
  .cal{max-width:300px;margin:0 auto}
  .cal .month{font-family:'Gowun Batang',serif;font-size:17px;margin-bottom:18px}
  .cal table{width:100%;border-collapse:collapse;font-size:13.5px}
  .cal th{font-weight:400;color:var(--sub);padding:6px 0;font-size:12px}
  .cal td{padding:7px 0;height:36px}
  .cal .sun{color:#d08a8a}
  .cal .sat{color:#8aa0c0}
  .cal .day-on{display:inline-flex;width:32px;height:32px;border-radius:50%;background:var(--accent);color:#fff;align-items:center;justify-content:center;font-weight:500}
  .dday{margin-top:30px;font-size:14px}
  .dday b{color:var(--accent);font-weight:500}
  .count{display:flex;justify-content:center;gap:14px;margin-top:22px}
  .count div{min-width:56px}
  .count .n{font-family:'Gowun Batang',serif;font-size:24px}
  .count .u{font-size:10px;letter-spacing:.2em;color:var(--sub)}

  /* 갤러리 */
  .gallery{display:grid;grid-template-columns:repeat(3,1fr);gap:4px}
  .gallery .photo{aspect-ratio:1/1;font-size:10.5px}
  .gallery .photo svg{width:18px;height:18px}

  /* 오시는 길 */
  .venue-name{font-family:'Gowun Batang',serif;font-size:18px;margin-bottom:4px}
  .map{aspect-ratio:4/3;margin:24px 0 14px}
  .btns{display:grid;grid-template-columns:repeat(3,1fr);gap:6px}
  .btn{display:block;padding:11px 0;border:1px solid var(--line);border-radius:4px;background:#fff;color:var(--ink);font-size:13px;text-decoration:none;font-family:inherit;cursor:pointer}
  .btn:active{background:var(--soft)}
  .route{text-align:left;margin-top:34px;display:grid;gap:22px}
  .route h3{font-size:13px;font-weight:500;color:var(--accent);margin-bottom:4px}
  .route p{font-size:14px;color:var(--sub);line-height:1.7}

  /* 계좌 */
  .acc-group{border:1px solid var(--line);border-radius:6px;margin-bottom:10px;text-align:left;overflow:hidden}
  .acc-head{width:100%;background:var(--soft);border:none;padding:15px 18px;font-family:inherit;font-size:14px;color:var(--ink);display:flex;justify-content:space-between;align-items:center;cursor:pointer}
  .acc-head .arr{transition:transform .25s;color:var(--sub)}
  .acc-group.open .arr{transform:rotate(180deg)}
  .acc-body{display:none;padding:4px 18px}
  .acc-group.open .acc-body{display:block}
  .acc-row{display:flex;justify-content:space-between;align-items:center;padding:14px 0;border-bottom:1px solid var(--line);font-size:13.5px}
  .acc-row:last-child{border:none}
  .acc-row .who{color:var(--sub);font-size:12px}
  .copy{border:1px solid var(--line);background:#fff;border-radius:3px;padding:6px 12px;font-size:12px;font-family:inherit;color:var(--ink);cursor:pointer;flex-shrink:0;margin-left:10px}

  footer{padding:48px 28px 64px;text-align:center;font-size:12px;color:var(--sub)}
  .share{display:inline-block;margin-bottom:22px;padding:12px 28px;border:1px solid var(--accent);color:var(--accent);background:transparent;border-radius:30px;font-family:inherit;font-size:13px;cursor:pointer}

  .toast{position:fixed;left:50%;bottom:40px;transform:translateX(-50%) translateY(20px);background:rgba(51,51,51,.9);color:#fff;font-size:13px;padding:10px 20px;border-radius:20px;opacity:0;transition:all .3s;pointer-events:none}
  .toast.show{opacity:1;transform:translateX(-50%) translateY(0)}

  .reveal{opacity:0;transform:translateY(16px);transition:opacity .9s ease,transform .9s ease}
  .reveal.in{opacity:1;transform:none}
  @media (prefers-reduced-motion:reduce){.reveal{opacity:1;transform:none;transition:none}}
</style>
</head>
<body>
<div class="wrap">

  <!-- ===== 커버 ===== -->
  <section class="cover">
    <div class="photo" data-ph="메인 사진"></div>
    <div class="date-top" id="coverDate"></div>
    <div class="names"><span id="groomName1">신랑</span><span>&amp;</span><span id="brideName1">신부</span></div>
    <div class="when" id="coverWhen"></div>
  </section>

  <!-- ===== 인사말 ===== -->
  <section class="greeting reveal">
    <div class="eyebrow">Invitation</div>
    <h2>소중한 분들을 초대합니다</h2>
    <p class="serif">
      서로 다른 길을 걸어온 두 사람이<br>
      이제 같은 길을 함께 걸어가려 합니다.<br><br>
      저희의 새로운 시작을<br>
      가까이에서 축복해 주시면<br>
      더없는 기쁨으로 간직하겠습니다.
    </p>
    <div class="parents">
      <div><b id="gFather">신랑아버지</b> · <b id="gMother">신랑어머니</b><span class="rel">의 아들</span><b id="groomName2">신랑</b></div>
      <div><b id="bFather">신부아버지</b> · <b id="bMother">신부어머니</b><span class="rel">의 딸</span><b id="brideName2">신부</b></div>
    </div>
  </section>

  <!-- ===== 중간 사진 ===== -->
  <section class="reveal" style="padding:0;border:none">
    <div class="photo" style="aspect-ratio:4/5;border-radius:0;border-left:none;border-right:none" data-ph="서브 사진"></div>
  </section>

  <!-- ===== 날짜 / 달력 ===== -->
  <section class="reveal">
    <div class="eyebrow">Wedding Day</div>
    <div class="cal">
      <div class="month" id="calTitle"></div>
      <table>
        <thead><tr><th class="sun">일</th><th>월</th><th>화</th><th>수</th><th>목</th><th>금</th><th class="sat">토</th></tr></thead>
        <tbody id="calBody"></tbody>
      </table>
    </div>
    <div class="count" id="count"></div>
    <p class="dday" id="ddayText"></p>
  </section>

  <!-- ===== 갤러리 ===== -->
  <section class="reveal">
    <div class="eyebrow">Gallery</div>
    <h2>우리의 순간</h2>
    <div class="gallery" id="gallery"></div>
  </section>

  <!-- ===== 오시는 길 ===== -->
  <section class="reveal">
    <div class="eyebrow">Location</div>
    <h2>오시는 길</h2>
    <div class="venue-name" id="venueName"></div>
    <p class="muted" id="venueHall"></p>
    <p class="muted" id="venueAddr" style="font-size:13.5px"></p>
    <div class="photo map" data-ph="약도 이미지 자리"></div>
    <div class="btns">
      <a class="btn" id="naverMap" href="#">네이버 지도</a>
      <a class="btn" id="kakaoMap" href="#">카카오맵</a>
      <button class="btn" type="button" id="copyAddr">주소 복사</button>
    </div>
    <div class="route">
      <div><h3>지하철</h3><p id="rSubway"></p></div>
      <div><h3>버스</h3><p id="rBus"></p></div>
      <div><h3>주차</h3><p id="rParking"></p></div>
    </div>
  </section>

  <!-- ===== 마음 전하실 곳 ===== -->
  <section class="reveal">
    <div class="eyebrow">Account</div>
    <h2>마음 전하실 곳</h2>
    <p class="muted" style="font-size:13.5px;margin-bottom:26px">참석이 어려우신 분들을 위해<br>계좌번호를 안내드립니다.</p>
    <div id="accounts"></div>
  </section>

  <footer>
    <button class="share" type="button" id="shareBtn">청첩장 링크 복사</button>
    <div>Thank you for celebrating with us</div>
  </footer>
</div>
<div class="toast" id="toast"></div>

<script>
/* =========================================================
   ✏️ 여기만 수정하시면 전체 청첩장에 반영됩니다
   ========================================================= */
const INFO = {
  groom: "OOO",            // 신랑 이름
  bride: "OOO",            // 신부 이름
  groomParents: ["OOO", "OOO"],   // 신랑 아버지, 어머니
  brideParents: ["OOO", "OOO"],   // 신부 아버지, 어머니

  date: "2027-02-27T13:30:00",    // 예식 일시 (연-월-일T시:분)

  venue: "OOO 웨딩홀",
  hall: "O층 OOO홀",
  address: "서울특별시 OO구 OO로 000",
  subway: "O호선 OO역 O번 출구 도보 5분",
  bus: "OO정류장 하차 (간선 000, 지선 0000)",
  parking: "건물 내 지하주차장 이용 (2시간 무료)",

  photoCount: 9,           // 갤러리 사진 칸 수

  accounts: [
    { side: "신랑측", list: [
      { who: "신랑", name: "OOO", bank: "OO은행", num: "000-0000-0000" },
      { who: "신랑 아버지", name: "OOO", bank: "OO은행", num: "000-0000-0000" },
      { who: "신랑 어머니", name: "OOO", bank: "OO은행", num: "000-0000-0000" }
    ]},
    { side: "신부측", list: [
      { who: "신부", name: "OOO", bank: "OO은행", num: "000-0000-0000" },
      { who: "신부 아버지", name: "OOO", bank: "OO은행", num: "000-0000-0000" },
      { who: "신부 어머니", name: "OOO", bank: "OO은행", num: "000-0000-0000" }
    ]}
  ]
};
/* ========================================================= */

const $ = id => document.getElementById(id);
const set = (id, t) => { const el = $(id); if (el) el.textContent = t; };
const camIcon = '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="6" width="18" height="14" rx="2"/><circle cx="12" cy="13" r="3.5"/><path d="M8 6l1.5-2h5L16 6"/></svg>';

// 사진 자리 표시
document.querySelectorAll('.photo').forEach(el => {
  el.innerHTML = camIcon + '<span>' + (el.dataset.ph || '사진') + '</span>';
});

// 이름
['groomName1','groomName2'].forEach(id => set(id, INFO.groom));
['brideName1','brideName2'].forEach(id => set(id, INFO.bride));
set('gFather', INFO.groomParents[0]); set('gMother', INFO.groomParents[1]);
set('bFather', INFO.brideParents[0]); set('bMother', INFO.brideParents[1]);

// 날짜
const d = new Date(INFO.date);
const days = ['일','월','화','수','목','금','토'];
const pad = n => String(n).padStart(2,'0');
const h = d.getHours(), m = d.getMinutes();
const timeKo = (h < 12 ? '오전 ' : '오후 ') + ((h % 12) || 12) + '시' + (m ? ' ' + m + '분' : '');
set('coverDate', d.getFullYear() + '. ' + pad(d.getMonth()+1) + '. ' + pad(d.getDate()) + '. ' + days[d.getDay()].toUpperCase());
$('coverWhen').innerHTML = d.getFullYear() + '년 ' + (d.getMonth()+1) + '월 ' + d.getDate() + '일 ' + days[d.getDay()] + '요일 ' + timeKo + '<br>' + INFO.venue + ' ' + INFO.hall;

// 달력
set('calTitle', d.getFullYear() + '년 ' + (d.getMonth()+1) + '월');
const first = new Date(d.getFullYear(), d.getMonth(), 1).getDay();
const last = new Date(d.getFullYear(), d.getMonth()+1, 0).getDate();
let html = '<tr>';
for (let i = 0; i < first; i++) html += '<td></td>';
for (let day = 1; day <= last; day++) {
  const col = (first + day - 1) % 7;
  const cls = col === 0 ? 'sun' : col === 6 ? 'sat' : '';
  html += '<td class="' + cls + '">' + (day === d.getDate() ? '<span class="day-on">' + day + '</span>' : day) + '</td>';
  if (col === 6 && day !== last) html += '</tr><tr>';
}
$('calBody').innerHTML = html + '</tr>';

// 카운트다운
function tick(){
  const diff = d - new Date();
  const c = $('count');
  if (diff <= 0) {
    c.innerHTML = '';
    $('ddayText').innerHTML = diff > -86400000 ? '오늘, 저희 결혼합니다' : INFO.groom + ' ♥ ' + INFO.bride + '의 결혼식이 있었습니다';
    return;
  }
  const s = Math.floor(diff/1000);
  const parts = [[Math.floor(s/86400),'DAYS'],[Math.floor(s%86400/3600),'HOUR'],[Math.floor(s%3600/60),'MIN'],[s%60,'SEC']];
  c.innerHTML = parts.map(p => '<div><div class="n">' + p[0] + '</div><div class="u">' + p[1] + '</div></div>').join('');
  const dd = Math.ceil(diff/86400000);
  $('ddayText').innerHTML = INFO.groom + ' ♥ ' + INFO.bride + '의 결혼식이 <b>' + dd + '일</b> 남았습니다';
}
tick(); setInterval(tick, 1000);

// 갤러리
$('gallery').innerHTML = Array.from({length: INFO.photoCount}, (_, i) =>
  '<div class="photo">' + camIcon + '<span>사진 ' + (i+1) + '</span></div>').join('');

// 오시는 길
set('venueName', INFO.venue); set('venueHall', INFO.hall); set('venueAddr', INFO.address);
set('rSubway', INFO.subway); set('rBus', INFO.bus); set('rParking', INFO.parking);
$('naverMap').href = 'https://map.naver.com/p/search/' + encodeURIComponent(INFO.venue);
$('kakaoMap').href = 'https://map.kakao.com/?q=' + encodeURIComponent(INFO.venue);
$('naverMap').target = $('kakaoMap').target = '_blank';
$('naverMap').rel = $('kakaoMap').rel = 'noopener';

// 계좌
$('accounts').innerHTML = INFO.accounts.map((g, gi) =>
  '<div class="acc-group"><button class="acc-head" type="button" data-g="' + gi + '">' + g.side + ' 계좌번호<span class="arr">▾</span></button><div class="acc-body">' +
  g.list.map(a => '<div class="acc-row"><div><div class="who">' + a.who + ' ' + a.name + '</div>' + a.bank + ' ' + a.num + '</div><button class="copy" type="button" data-copy="' + a.bank + ' ' + a.num + ' ' + a.name + '">복사</button></div>').join('') +
  '</div></div>').join('');
document.querySelectorAll('.acc-head').forEach(b => b.addEventListener('click', () => b.parentElement.classList.toggle('open')));

// 복사 / 토스트
function toast(msg){ const t = $('toast'); t.textContent = msg; t.classList.add('show'); clearTimeout(t._t); t._t = setTimeout(() => t.classList.remove('show'), 1800); }
async function copy(text, msg){
  try { await navigator.clipboard.writeText(text); toast(msg); }
  catch(e){ toast('복사가 지원되지 않는 환경입니다'); }
}
document.addEventListener('click', e => {
  const b = e.target.closest('[data-copy]');
  if (b) copy(b.dataset.copy, '계좌번호가 복사되었습니다');
});
$('copyAddr').addEventListener('click', () => copy(INFO.address, '주소가 복사되었습니다'));
$('shareBtn').addEventListener('click', () => copy(location.href.split('#')[0], '청첩장 링크가 복사되었습니다'));

// 스크롤 등장 효과
const io = new IntersectionObserver(es => es.forEach(en => { if (en.isIntersecting) { en.target.classList.add('in'); io.unobserve(en.target); } }), {threshold:.15});
document.querySelectorAll('.reveal').forEach(el => io.observe(el));
</script>
</body>
</html>
