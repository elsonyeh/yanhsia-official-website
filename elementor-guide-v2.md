# 鹽夏不夜埕 — Elementor 匯入指南 v2（免付費版）

> **做法：** CSS 直接寫在第一個 HTML 元件的 `<style>` 標籤內，不需使用 WordPress 額外 CSS 功能。
> 圖片使用 GitHub Pages CDN，不需上傳到 WordPress。
>
> **貼法：** Elementor 編輯頁面 → 拖入「HTML」元件 → 貼上對應區塊的完整程式碼 → 儲存。

---

## 首頁（index）

### 元件 1 — CSS 全域樣式 + Hero（必須第一個放）

```html
<style>
@import url('https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@400;700;900&family=Noto+Sans+TC:wght@300;400;700;900&display=swap');

:root {
  --primary:#330609; --secondary:#C0546C; --bg:#F2D9D0;
  --gold:#F2BE5C; --peach:#F2A488; --blue:#5B7BA6;
  --pink:#F27E93; --red:#CB5661; --lavender:#C7A4C3;
  --gray:#CFC9CC; --rose:#E9ABAB; --white:#FFFFFF;
}
.yh-hero{position:relative;min-height:100vh;display:flex;align-items:center;justify-content:center;overflow:hidden;background:var(--primary);padding:80px 24px 220px;}
.yh-hero-bg{position:absolute;inset:0;background:url('https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%83%8C%E6%99%AF.png')center/cover no-repeat;opacity:.55;mix-blend-mode:screen;}
.yh-hero-overlay{position:absolute;inset:0;background:radial-gradient(ellipse 80% 70% at 50% 40%,rgba(192,84,108,.25) 0%,rgba(51,6,9,.75) 68%);}
.yh-hero-content{position:relative;z-index:10;display:flex;flex-direction:column;align-items:center;gap:22px;text-align:center;}
.yh-hero-eyebrow{font-family:'Noto Sans TC',sans-serif;font-size:12px;letter-spacing:.5em;color:var(--gold);border:1px solid rgba(242,190,92,.35);padding:6px 20px;border-radius:50px;}
.yh-hero-logos{display:flex;align-items:center;gap:48px;flex-wrap:wrap;justify-content:center;}
.yh-hero-main-logo{height:260px;filter:invert(1);mix-blend-mode:screen;}
.yh-hero-bomb-badge{background:var(--bg);border-radius:50%;width:210px;height:210px;display:flex;align-items:center;justify-content:center;box-shadow:0 0 0 8px rgba(242,126,147,.25),0 0 60px rgba(192,84,108,.4);animation:yh-pulse-ring 3s ease-in-out infinite;}
.yh-hero-bomb-badge img{width:175px;}
.yh-hero-tagline{font-family:'Noto Serif TC',serif;font-size:20px;color:var(--rose);letter-spacing:.25em;}
.yh-hero-dates{display:flex;align-items:center;gap:14px;}
.yh-date-pill{background:var(--gold);color:var(--primary);font-family:'Noto Sans TC',sans-serif;font-weight:900;font-size:17px;padding:8px 22px;border-radius:6px;letter-spacing:.05em;}
.yh-date-dash{color:var(--white);font-size:20px;}
.yh-hero-location{font-family:'Noto Sans TC',sans-serif;font-size:13px;letter-spacing:.22em;color:var(--gray);}
.yh-hero-cta{margin-top:6px;display:inline-block;padding:14px 52px;background:var(--secondary);color:var(--white);text-decoration:none;font-family:'Noto Sans TC',sans-serif;font-weight:700;font-size:15px;letter-spacing:.12em;border-radius:50px;transition:background .2s,transform .2s;box-shadow:0 4px 24px rgba(192,84,108,.4);}
.yh-hero-cta:hover{background:var(--pink);transform:translateY(-3px);}
.yh-mascot{position:absolute;pointer-events:none;z-index:6;}
.yh-m-lily{top:24%;left:5%;width:130px;animation:yh-floatA 3.8s ease-in-out infinite;}
.yh-m-sunf{bottom:24%;left:7%;width:140px;animation:yh-floatB 3.2s ease-in-out infinite .4s;}
.yh-m-amary{top:28%;right:5%;width:115px;animation:yh-floatB 4s ease-in-out infinite .8s;}
.yh-m-lav{bottom:26%;right:8%;width:120px;animation:yh-floatA 3.5s ease-in-out infinite .2s;}
.yh-m-blue{top:50%;left:16%;width:90px;animation:yh-floatB 5s ease-in-out infinite 1s;}
.yh-hero-city{position:absolute;bottom:0;left:50%;transform:translateX(-50%);width:100%;max-width:980px;z-index:7;pointer-events:none;}
.yh-marquee-strip{background:var(--gold);color:var(--primary);padding:13px 0;overflow:hidden;}
.yh-marquee-inner{display:flex;white-space:nowrap;animation:yh-marquee 22s linear infinite;}
.yh-marquee-text{font-family:'Noto Sans TC',sans-serif;font-weight:900;font-size:17px;letter-spacing:.1em;padding-right:64px;flex-shrink:0;}
.yh-section-label{font-family:'Noto Sans TC',sans-serif;font-size:11px;letter-spacing:.45em;color:var(--gold);margin-bottom:14px;text-transform:uppercase;}
.yh-section-title{font-family:'Noto Serif TC',serif;font-size:clamp(32px,5vw,60px);font-weight:900;line-height:1.1;color:var(--primary);}
.yh-features{background:var(--bg);padding:100px 48px;}
.yh-features-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:20px;max-width:1080px;margin:0 auto;}
.yh-feat-card{border-radius:24px;padding:40px 24px;text-align:center;transition:transform .3s,box-shadow .3s;}
.yh-feat-card:hover{transform:translateY(-8px);box-shadow:0 16px 40px rgba(51,6,9,.12);}
.yh-feat-card.white{background:var(--white);color:var(--primary);}
.yh-feat-card.dark-red{background:var(--secondary);color:var(--white);}
.yh-feat-card.primary{background:var(--primary);color:var(--white);}
.yh-feat-card img{width:80px;margin:0 auto 16px;display:block;}
.yh-feat-num{font-family:'Noto Serif TC',serif;font-size:48px;font-weight:900;color:var(--gold);line-height:1;margin-bottom:6px;}
.yh-feat-title{font-family:'Noto Serif TC',serif;font-size:20px;font-weight:700;margin-bottom:12px;}
.yh-feat-desc{font-family:'Noto Sans TC',sans-serif;font-size:13px;line-height:1.9;opacity:.78;}
.yh-cta-link{display:inline-block;padding:13px 44px;background:var(--secondary);color:var(--white);text-decoration:none;font-family:'Noto Sans TC',sans-serif;font-weight:700;font-size:14px;border-radius:50px;letter-spacing:.08em;transition:transform .2s,box-shadow .2s;}
.yh-cta-link:hover{transform:translateY(-3px);box-shadow:0 8px 24px rgba(51,6,9,.2);}
.yh-founders{background:var(--primary);color:var(--white);padding:100px 48px;position:relative;overflow:hidden;}
.yh-founders-inner{max-width:1080px;margin:0 auto;position:relative;z-index:2;}
.yh-founder-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:32px;max-width:800px;margin:0 auto 80px;}
.yh-founder-card{text-align:center;}
.yh-founder-avatar{width:140px;height:140px;border-radius:50%;margin:0 auto 24px;display:flex;align-items:center;justify-content:center;}
.yh-founder-avatar img{width:100px;}
.yh-founder-name{font-family:'Noto Serif TC',serif;font-size:26px;font-weight:900;margin-bottom:6px;color:var(--white);}
.yh-founder-role{font-family:'Noto Sans TC',sans-serif;font-size:12px;letter-spacing:.18em;color:var(--gold);margin-bottom:16px;}
.yh-founder-bio{font-family:'Noto Sans TC',sans-serif;font-size:14px;line-height:2.1;color:var(--gray);}
.yh-book-badge{display:inline-block;background:rgba(242,190,92,.12);border:1px solid rgba(242,190,92,.3);border-radius:12px;padding:18px 36px;margin-bottom:80px;}
.yh-book-badge span{font-family:'Noto Serif TC',serif;font-size:16px;color:var(--gold);}
.yh-video-label{font-family:'Noto Sans TC',sans-serif;font-size:11px;letter-spacing:.4em;color:var(--gold);margin-bottom:12px;}
.yh-video-title{font-family:'Noto Serif TC',serif;font-size:28px;font-weight:700;color:var(--white);margin-bottom:28px;}
.yh-video-wrap{position:relative;padding-bottom:56.25%;border-radius:16px;overflow:hidden;box-shadow:0 0 0 1px rgba(255,255,255,.1),0 24px 60px rgba(0,0,0,.4);}
.yh-video-wrap iframe{position:absolute;inset:0;width:100%;height:100%;border:none;}
.yh-line-cta{background:var(--gold);padding:80px 48px;text-align:center;}
.yh-line-title{font-family:'Noto Serif TC',serif;font-size:clamp(24px,3.5vw,40px);font-weight:900;color:var(--primary);margin-bottom:16px;}
.yh-line-sub{font-family:'Noto Sans TC',sans-serif;font-size:15px;line-height:2;color:rgba(51,6,9,.68);margin-bottom:32px;}
.yh-footer-pre{background:var(--secondary);padding:80px 48px;text-align:center;color:var(--white);}
.yh-footer-pre-title{font-family:'Noto Serif TC',serif;font-size:clamp(28px,4vw,48px);font-weight:900;margin-bottom:20px;}
.yh-footer-pre-sub{font-family:'Noto Sans TC',sans-serif;font-size:16px;opacity:.8;margin-bottom:36px;}
.yh-footer-pre-btn{display:inline-block;padding:14px 52px;background:var(--gold);color:var(--primary);text-decoration:none;font-family:'Noto Sans TC',sans-serif;font-weight:900;font-size:16px;border-radius:50px;transition:transform .2s;}
.yh-footer-pre-btn:hover{transform:translateY(-3px);}
.yh-footer-city{background:var(--bg);padding-top:24px;overflow:hidden;line-height:0;}
.yh-footer-city img{width:100%;display:block;}
.yh-footer-bottom{background:var(--primary);color:var(--white);padding:48px 48px 36px;display:flex;flex-direction:column;align-items:center;gap:20px;}
.yh-footer-logo img{height:38px;filter:invert(1);mix-blend-mode:screen;}
.yh-footer-social{display:flex;gap:28px;}
.yh-footer-social a{font-family:'Noto Sans TC',sans-serif;color:var(--gold);text-decoration:none;font-size:13px;letter-spacing:.15em;}
.yh-footer-copy{font-family:'Noto Sans TC',sans-serif;font-size:12px;color:var(--gray);letter-spacing:.1em;}
.yh-grass{position:relative;overflow:hidden;height:100px;background:var(--bg);}
.yh-grass img{position:absolute;bottom:0;left:50%;transform:translateX(-50%);width:100%;min-width:900px;pointer-events:none;}
/* 花轟頁 */
.yh-page-hero{background:var(--primary);padding:160px 48px 80px;text-align:center;position:relative;overflow:hidden;}
.yh-page-hero-bg{position:absolute;inset:0;background:url('https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%83%8C%E6%99%AF.png')center/cover no-repeat;opacity:.3;mix-blend-mode:screen;}
.yh-page-hero-overlay{position:absolute;inset:0;background:radial-gradient(ellipse 70% 60% at 50% 40%,rgba(192,84,108,.2) 0%,rgba(51,6,9,.8) 70%);}
.yh-page-hero-inner{position:relative;z-index:2;}
.yh-page-eyebrow{font-family:'Noto Sans TC',sans-serif;font-size:11px;letter-spacing:.5em;color:var(--gold);margin-bottom:16px;}
.yh-page-title{font-family:'Noto Serif TC',serif;font-size:clamp(48px,7vw,96px);font-weight:900;color:var(--white);line-height:1;}
.yh-page-sub{font-family:'Noto Sans TC',sans-serif;margin-top:16px;font-size:15px;color:var(--rose);letter-spacing:.2em;}
.yh-hero-badge{display:inline-flex;align-items:center;justify-content:center;background:var(--bg);border-radius:50%;width:160px;height:160px;margin:32px auto 0;box-shadow:0 0 0 10px rgba(242,126,147,.2),0 0 60px rgba(192,84,108,.35);}
.yh-hero-badge img{width:130px;}
.yh-curatorial{background:var(--primary);color:var(--white);padding:100px 48px;}
.yh-curatorial-inner{max-width:860px;margin:0 auto;}
.yh-quote-block{font-family:'Noto Serif TC',serif;font-size:17px;line-height:2.3;border-left:3px solid var(--secondary);padding-left:28px;margin-bottom:24px;color:var(--white);}
.yh-sub-text{font-family:'Noto Sans TC',sans-serif;font-size:16px;line-height:2.2;color:var(--rose);margin-bottom:24px;}
.yh-note-text{font-family:'Noto Sans TC',sans-serif;font-size:14px;line-height:2;opacity:.6;margin-bottom:64px;color:var(--white);}
.yh-trio-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:2px;border-radius:20px;overflow:hidden;}
.yh-trio-card{padding:44px 28px;color:var(--white);}
.yh-trio-title{font-family:'Noto Serif TC',serif;font-size:28px;font-weight:900;color:var(--gold);margin-bottom:8px;}
.yh-trio-en{font-family:'Noto Sans TC',sans-serif;font-size:11px;letter-spacing:.2em;opacity:.55;margin-bottom:20px;}
.yh-trio-body{font-family:'Noto Sans TC',sans-serif;font-size:13px;line-height:2.1;opacity:.88;}
.yh-schedule{background:var(--bg);padding:100px 48px;}
.yh-schedule-inner{max-width:860px;margin:0 auto;}
.yh-schedule-day{margin-bottom:48px;}
.yh-schedule-day-label{font-family:'Noto Serif TC',serif;font-size:22px;font-weight:700;color:var(--secondary);border-bottom:2px solid var(--secondary);padding-bottom:10px;margin-bottom:18px;}
.yh-schedule-row{display:flex;align-items:center;gap:24px;padding:16px 0;border-bottom:1px solid rgba(51,6,9,.1);}
.yh-schedule-time{font-family:'Noto Sans TC',sans-serif;font-weight:900;font-size:15px;color:var(--primary);min-width:80px;}
.yh-schedule-name{font-family:'Noto Sans TC',sans-serif;font-weight:700;font-size:16px;margin-bottom:3px;}
.yh-schedule-stage{font-family:'Noto Sans TC',sans-serif;font-size:12px;letter-spacing:.12em;color:var(--secondary);}
.yh-event-info{background:var(--primary);color:var(--white);padding:100px 48px;}
.yh-event-info-inner{max-width:1080px;margin:0 auto;}
.yh-info-top{display:grid;grid-template-columns:1fr 1fr;gap:20px;margin-bottom:20px;}
.yh-info-box{background:rgba(242,190,92,.12);border:1px solid rgba(242,190,92,.3);border-radius:14px;padding:30px 28px;}
.yh-info-box-label{font-family:'Noto Sans TC',sans-serif;color:var(--gold);font-size:11px;letter-spacing:.35em;margin-bottom:10px;}
.yh-info-box-value{font-family:'Noto Serif TC',serif;font-size:20px;font-weight:700;line-height:1.8;color:var(--white);}
.yh-info-box-value span{font-family:'Noto Sans TC',sans-serif;font-size:15px;font-weight:400;opacity:.75;}
.yh-info-bottom{display:grid;grid-template-columns:1fr 1fr;gap:20px;}
.yh-info-card{background:rgba(255,255,255,.06);border-radius:14px;padding:28px;}
.yh-info-card-label{font-family:'Noto Sans TC',sans-serif;color:var(--gold);font-size:11px;letter-spacing:.35em;margin-bottom:14px;}
.yh-info-list{display:flex;flex-direction:column;gap:10px;}
.yh-info-list-item{font-family:'Noto Sans TC',sans-serif;display:flex;gap:10px;font-size:13px;line-height:1.8;color:var(--white);}
.yh-info-list-num{color:var(--secondary);flex-shrink:0;}
.yh-info-plain{font-family:'Noto Sans TC',sans-serif;font-size:13px;line-height:2.2;opacity:.85;color:var(--white);}
.yh-reveal{opacity:0;}
.yh-reveal.visible{animation:yh-fadeUp .7s ease forwards;}
@keyframes yh-floatA{0%,100%{transform:translateY(0) rotate(-4deg);}50%{transform:translateY(-22px) rotate(4deg);}}
@keyframes yh-floatB{0%,100%{transform:translateY(0) rotate(4deg);}50%{transform:translateY(-18px) rotate(-4deg);}}
@keyframes yh-marquee{0%{transform:translateX(0);}100%{transform:translateX(-50%);}}
@keyframes yh-pulse-ring{0%,100%{box-shadow:0 0 0 10px rgba(242,126,147,.18),0 0 60px rgba(192,84,108,.35);}50%{box-shadow:0 0 0 18px rgba(242,126,147,.08),0 0 80px rgba(192,84,108,.22);}}
@keyframes yh-fadeUp{from{opacity:0;transform:translateY(36px);}to{opacity:1;transform:translateY(0);}}
@media(max-width:900px){
  .yh-features-grid{grid-template-columns:repeat(2,1fr);}
  .yh-founder-grid{grid-template-columns:1fr;}
  .yh-hero-logos{flex-direction:column;gap:20px;}
  .yh-hero-main-logo{height:180px;}
  .yh-hero-bomb-badge{width:160px;height:160px;}
  .yh-hero-bomb-badge img{width:130px;}
  .yh-m-lily,.yh-m-blue,.yh-m-lav{display:none;}
  .yh-trio-grid{grid-template-columns:1fr;}
  .yh-info-top,.yh-info-bottom{grid-template-columns:1fr;}
}
@media(max-width:560px){.yh-features-grid{grid-template-columns:1fr;}}
</style>

<section class="yh-hero">
  <div class="yh-hero-bg"></div>
  <div class="yh-hero-overlay"></div>
  <img class="yh-mascot yh-m-lily"  src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E7%99%BE%E5%90%88.png" alt="">
  <img class="yh-mascot yh-m-sunf"  src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%90%91%E6%97%A5%E8%91%B5.png" alt="">
  <img class="yh-mascot yh-m-amary" src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%AD%A4%E6%8C%BA%E8%8A%B1.png" alt="">
  <img class="yh-mascot yh-m-lav"   src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%96%B0%E8%A1%A3%E8%8D%89.png" alt="">
  <img class="yh-mascot yh-m-blue"  src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%97%8D%E7%8E%AB%E7%91%B0.png" alt="">
  <div class="yh-hero-content">
    <div class="yh-hero-eyebrow">2026 × 高雄新樂街綠廊 × YANHSIA NIGHT</div>
    <div class="yh-hero-logos">
      <img class="yh-hero-main-logo" src="https://elsonyeh.github.io/yanhsia-official-website/%E9%B9%BD%E5%A4%8Flogo%E5%80%91-20260416T013432Z-3-001/%E9%B9%BD%E5%A4%8Flogo%E5%80%91/%E8%B3%87%E7%94%A2%201.png" alt="鹽夏不夜埕">
      <div class="yh-hero-bomb-badge">
        <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%8A%B1%E8%BD%9F.png" alt="花轟">
      </div>
    </div>
    <div class="yh-hero-tagline">夏夜盛開，花の祭典</div>
    <div class="yh-hero-dates">
      <div class="yh-date-pill">05.16</div>
      <span class="yh-date-dash">—</span>
      <div class="yh-date-pill">05.23</div>
      <span style="color:#F2BE5C;font-size:14px;letter-spacing:.1em">2026</span>
    </div>
    <div class="yh-hero-location">高雄市 新樂街綠廊</div>
    <a href="/hanabomb" class="yh-hero-cta">探索花轟</a>
  </div>
  <img class="yh-hero-city" src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%8F%AF%E6%84%9B%E7%9A%84%E8%A1%97%E5%8D%80.png" alt="">
</section>

<script>
  const _obs = new IntersectionObserver((entries) => {
    entries.forEach(e => { if(e.isIntersecting){ e.target.classList.add('visible'); _obs.unobserve(e.target); } });
  }, { threshold: 0.12 });
  document.querySelectorAll('.yh-reveal').forEach(el => _obs.observe(el));
  const _mascots = document.querySelectorAll('.yh-mascot');
  window.addEventListener('scroll', () => {
    const y = window.scrollY;
    _mascots.forEach((m, i) => { m.style.transform = `translateY(${y*(i%2===0?.08:.05)}px)`; });
  }, { passive: true });
</script>
```

---

### 元件 2 — Marquee 跑馬燈

```html
<div class="yh-marquee-strip">
  <div class="yh-marquee-inner">
    <span class="yh-marquee-text">2026 鹽夏不夜埕 × 花轟 ✦ 高雄新樂街綠廊 ✦ 裝置藝術・表演藝術・特色市集・周邊活動 ✦ 05.16—05.23 每日 17:00–21:00 ✦ YANHSIA NIGHT × HANABOMB ✦ 花朵不睡覺 ✦&ensp;</span>
    <span class="yh-marquee-text">2026 鹽夏不夜埕 × 花轟 ✦ 高雄新樂街綠廊 ✦ 裝置藝術・表演藝術・特色市集・周邊活動 ✦ 05.16—05.23 每日 17:00–21:00 ✦ YANHSIA NIGHT × HANABOMB ✦ 花朵不睡覺 ✦&ensp;</span>
  </div>
</div>
```

---

### 元件 3 — 四大特色

```html
<section class="yh-features">
  <div style="max-width:1080px;margin:0 auto;">
    <div style="text-align:center;margin-bottom:60px;">
      <div class="yh-section-label">FEATURES</div>
      <h2 class="yh-section-title yh-reveal">鹽夏四大特色｜Features</h2>
    </div>
    <div class="yh-features-grid">
      <div class="yh-feat-card white yh-reveal">
        <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%96%B0%E8%A1%A3%E8%8D%89.png" alt="">
        <div class="yh-feat-num">01</div>
        <div class="yh-feat-title">裝置藝術</div>
        <div class="yh-feat-desc">鹽埕埕區中展示一系列由中山大學「跨領域創新專選（一）」課程學生與藝術家所創作之光影裝置藝術作品，共同點亮鹽埕夜夜。</div>
      </div>
      <div class="yh-feat-card dark-red yh-reveal">
        <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%AD%A4%E6%8C%BA%E8%8A%B1.png" alt="">
        <div class="yh-feat-num">02</div>
        <div class="yh-feat-title">表演藝術</div>
        <div class="yh-feat-desc">邀請高雄在地劇團、樂團等表演團體，在街廊進行演出，沈浸在藝術表演與歷史文化交融出的鹽埕記憶。</div>
      </div>
      <div class="yh-feat-card white yh-reveal">
        <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%90%91%E6%97%A5%E8%91%B5.png" alt="">
        <div class="yh-feat-num">03</div>
        <div class="yh-feat-title">特色市集</div>
        <div class="yh-feat-desc">在展期的跨週六，邀請高雄在地商家或是學生創業品牌，配合每年的不同主題企劃，打造出獨一無二的鹽夏特色市集。</div>
      </div>
      <div class="yh-feat-card primary yh-reveal">
        <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E7%99%BE%E5%90%88.png" alt="">
        <div class="yh-feat-num">04</div>
        <div class="yh-feat-title">周邊活動</div>
        <div class="yh-feat-desc">舉辦「前導工作坊」作為策展的暖身，與鹽埕在地企業合作推出各種「鹽夏限定活動」，活動當日則有美食、歷史等導覽。</div>
      </div>
    </div>
    <div style="text-align:center;margin-top:48px;">
      <a href="/hanabomb" class="yh-cta-link">查看完整活動資訊 →</a>
    </div>
  </div>
</section>
```

---

### 元件 4 — 創始人 + 影片

```html
<section class="yh-founders">
  <div class="yh-founders-inner">
    <div style="text-align:center;margin-bottom:64px;">
      <div class="yh-section-label">FOUNDERS</div>
      <h2 class="yh-section-title yh-reveal" style="color:#fff;">鹽夏創始人們｜Founders</h2>
    </div>
    <div class="yh-founder-grid">
      <div class="yh-founder-card yh-reveal">
        <div class="yh-founder-avatar" style="background:#C0546C;box-shadow:0 0 0 8px rgba(192,84,108,.2),0 0 48px rgba(192,84,108,.25);">
          <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%AD%A4%E6%8C%BA%E8%8A%B1.png" alt="">
        </div>
        <div class="yh-founder-name">劉雯婷</div>
        <div class="yh-founder-role">鹽夏不夜埕 共同創辦人</div>
        <div class="yh-founder-bio">以社會設計為核心，長期深耕鹽埕街區的文化活化與社區共創，致力用藝術讓老街區重新被看見。</div>
      </div>
      <div class="yh-founder-card yh-reveal" style="animation-delay:.12s">
        <div class="yh-founder-avatar" style="background:#5B7BA6;box-shadow:0 0 0 8px rgba(91,123,166,.2),0 0 48px rgba(91,123,166,.25);">
          <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%97%8D%E7%8E%AB%E7%91%B0.png" alt="">
        </div>
        <div class="yh-founder-name">宋世祥</div>
        <div class="yh-founder-role">鹽夏不夜埕 共同創辦人</div>
        <div class="yh-founder-bio">中山大學社會學系，推動地方設計與社會策展。著有《在街區走著走著》｜設計讀吧，持續以書寫記錄台灣街區的生命力。</div>
      </div>
    </div>
    <div style="text-align:center;">
      <div class="yh-book-badge"><span>《在街區走著走著》｜設計讀吧</span></div>
    </div>
    <div class="yh-reveal" style="max-width:800px;margin:0 auto;text-align:center;">
      <div class="yh-video-label">FILM</div>
      <h3 class="yh-video-title">創始人介紹影片</h3>
      <div class="yh-video-wrap">
        <iframe src="https://www.youtube.com/embed/25naLda_-jo" title="創始人介紹影片"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen></iframe>
      </div>
    </div>
  </div>
</section>
```

---

### 元件 5 — LINE CTA

```html
<section class="yh-line-cta">
  <div style="max-width:600px;margin:0 auto;">
    <div class="yh-section-label" style="color:rgba(51,6,9,.55);">OFFICIAL LINE</div>
    <h2 class="yh-line-title">加入【鹽夏不夜埕】<br>官方 LINE 好友</h2>
    <p class="yh-line-sub">加入 LINE 好友集點趣！提升觀展體驗，第一時間掌握花轟最新消息、活動通知與限定優惠。</p>
    <a href="#" class="yh-cta-link" style="background:#330609;color:#fff;">加入 LINE 好友 →</a>
  </div>
</section>
```

---

### 元件 6 — Footer

```html
<div class="yh-grass">
  <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%8F%AF%E6%84%9B%E7%9A%84%E8%8D%89%E5%8F%A2.png" alt="">
</div>
<footer>
  <div class="yh-footer-pre">
    <div class="yh-footer-pre-title">2026 鹽夏不夜埕 × 花轟<br>5/16—5/23 新樂街綠廊見！</div>
    <div class="yh-footer-pre-sub">裝置藝術・表演藝術・特色市集・周邊活動　免費入場</div>
    <a href="/hanabomb" class="yh-footer-pre-btn">了解更多 →</a>
  </div>
  <div class="yh-footer-city">
    <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%8F%AF%E6%84%9B%E7%9A%84%E8%A1%97%E5%8D%80.png" alt="">
  </div>
  <div class="yh-footer-bottom">
    <div class="yh-footer-logo">
      <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%B9%BD%E5%A4%8Flogo%E5%80%91-20260416T013432Z-3-001/%E9%B9%BD%E5%A4%8Flogo%E5%80%91/%E8%B3%87%E7%94%A2%202.png" alt="鹽夏不夜埕">
    </div>
    <div class="yh-footer-social">
      <a href="#">Facebook</a>
      <a href="#">Instagram</a>
      <a href="#">LINE 官方帳號</a>
    </div>
    <div class="yh-footer-copy">© 2026 鹽夏不夜埕 All Rights Reserved</div>
  </div>
</footer>
```

---

## 花轟頁（hanabomb）

> **注意：** 花轟頁的元件 1 同樣包含完整 CSS，如果首頁已載入過（同網站），CSS 已在 DOM 中，可省略 `<style>` 區塊只保留 HTML。但若是獨立頁面，請保留完整元件 1。

### 元件 1 — CSS（同首頁，複製首頁元件 1 的 `<style>` 區塊貼在此即可）+ Page Hero

```html
<style>
/* 貼上首頁元件 1 的完整 <style> 內容 */
</style>

<section class="yh-page-hero">
  <div class="yh-page-hero-bg"></div>
  <div class="yh-page-hero-overlay"></div>
  <div class="yh-page-hero-inner">
    <div class="yh-page-eyebrow">2026 YANHSIA NIGHT × HANABOMB</div>
    <div class="yh-page-title">花轟</div>
    <div class="yh-page-sub">以花的綻放，回應情緒的張力與流動</div>
    <div class="yh-hero-badge">
      <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%8A%B1%E8%BD%9F.png" alt="花轟">
    </div>
  </div>
</section>

<script>
  if(!window._yhObsInit){
    window._yhObsInit = true;
    const _obs = new IntersectionObserver((entries) => {
      entries.forEach(e => { if(e.isIntersecting){ e.target.classList.add('visible'); _obs.unobserve(e.target); } });
    }, { threshold: 0.12 });
    document.querySelectorAll('.yh-reveal').forEach(el => _obs.observe(el));
  }
</script>
```

---

### 元件 2 — 關於花轟

```html
<section style="background:var(--primary);color:var(--white);padding:100px 48px;">
  <div style="max-width:1080px;margin:0 auto;display:grid;grid-template-columns:1fr 1fr;gap:80px;align-items:center;">
    <div class="yh-reveal">
      <div class="yh-section-label">ABOUT 關於花轟</div>
      <h2 class="yh-section-title" style="color:var(--white);margin-bottom:28px;">什麼是<br>花轟？</h2>
      <p style="font-family:'Noto Sans TC',sans-serif;font-size:16px;line-height:2.1;color:var(--gray);">
        夏夜裡，花朵不睡覺。<br><br>
        花轟是一場屬於夏天的街區派對，讓每一朵花都在鹽埕的巷弄間盡情綻放。我們相信藝術就在生活裡，音樂就在街角上，而你就是這個夏天最美的風景。<br><br>
        2026 年，鹽夏不夜埕帶著全新能量回來。開幕式、踩街遊行、裝置藝術、特色市集，用八天的時間把高雄的夏夜染得更鮮豔，更不羈，更屬於你。
      </p>
    </div>
    <div class="yh-reveal" style="display:flex;justify-content:center;">
      <div style="background:var(--bg);border-radius:50%;width:280px;height:280px;display:flex;align-items:center;justify-content:center;box-shadow:0 0 0 12px rgba(242,126,147,.15),0 0 80px rgba(192,84,108,.3);animation:yh-pulse-ring 3s ease-in-out infinite;">
        <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%8A%B1%E8%BD%9F.png" style="width:220px;" alt="花轟">
      </div>
    </div>
  </div>
</section>
```

---

### 元件 3 — 策展論述

```html
<section class="yh-curatorial">
  <div class="yh-curatorial-inner">
    <div class="yh-section-label">CURATORIAL STATEMENT 策展論述</div>
    <h2 class="yh-section-title yh-reveal" style="color:var(--white);margin-bottom:28px;">花の宣言</h2>
    <div class="yh-quote-block yh-reveal">《花轟》以花的綻放，回應情緒的張力與流動。正如花朵終將撐開花萼、露出真實的姿態，情緒的包裝紙在拆封的瞬間被釋放與凝視，以當下最真實的樣貌綻放。</div>
    <div class="yh-sub-text yh-reveal">鹽埕將化身為一座「花園」，情緒在巷弄間自然生長；觀眾在花園中自由穿梭。透過「呼吸、蔓延、共生」三大面向，體驗情緒從個體到他者，從他者到群體網絡相互影響、轉化與共存的過程。</div>
    <div class="yh-note-text yh-reveal">1st《花轟》邀請觀眾進入這座花園，靠近那些正在發生的情緒。</div>
    <div class="yh-trio-grid yh-reveal">
      <div class="yh-trio-card" style="background:#C0546C;">
        <div class="yh-trio-title">呼吸</div>
        <div class="yh-trio-en">BREATHE</div>
        <div class="yh-trio-body">綻放前，個體在每一次吸吐中積累著綻放的能量。初來乍到的資訊在身體裡隱隱作祟，隨著個體微乎其微的擴張和收縮，為綻放蓄力。含苞待放的每一刻，這些自然被忽視的過程，不只是綻放的前奏，更是在觸碰內心的瞬間，覺察自我更深層的情緒。</div>
      </div>
      <div class="yh-trio-card" style="background:#CB5661;">
        <div class="yh-trio-title">蔓延</div>
        <div class="yh-trio-en">SPREAD</div>
        <div class="yh-trio-body">綻放的瞬間，花粉隨風飄散。允許情緒以最真實的樣貌綻放，肆意宣示著屬於自己的氣味、顏色、質感，表達著自我。盛開的情緒經由單向的釋放，將既有的能量於個體間傳遞與承接，在感知、轉化、擴散之中，不斷反覆。</div>
      </div>
      <div class="yh-trio-card" style="background:#5B7BA6;">
        <div class="yh-trio-title">共生</div>
        <div class="yh-trio-en">SYMBIOSIS</div>
        <div class="yh-trio-body">綻放後，個體、他者與環境彼此纏繞、相互依偎，在不斷的交互與回響間，重新定義彼此存在的方式。「共生」之時，情緒與世界產生共振，在這緩緩運行的生態圈內，引領我們感知、察覺並回應生活的宏觀脈絡，重新理解自己與周遭的連結。</div>
      </div>
    </div>
  </div>
</section>
```

---

### 元件 4 — 四大主要活動

```html
<section style="background:var(--bg);padding:100px 48px;">
  <div style="text-align:center;margin-bottom:56px;" class="yh-reveal">
    <div class="yh-section-label">FEATURES 四大主要活動</div>
    <h2 class="yh-section-title">今年花轟</h2>
  </div>
  <div class="yh-features-grid">
    <div class="yh-feat-card white yh-reveal">
      <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%96%B0%E8%A1%A3%E8%8D%89.png" alt="">
      <div class="yh-feat-num">01</div>
      <div class="yh-feat-title">開幕式</div>
      <div class="yh-feat-desc">5/16（六）17:00–19:00，主舞台。揭開 2026 鹽夏不夜埕序幕，同步頒發高雄高中生科技藝術競賽獎項，邀請觀眾一同感受盛夏慶典的到來。</div>
    </div>
    <div class="yh-feat-card dark-red yh-reveal">
      <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%AD%A4%E6%8C%BA%E8%8A%B1.png" alt="">
      <div class="yh-feat-num">02</div>
      <div class="yh-feat-title">踩街遊行</div>
      <div class="yh-feat-desc">5/16（六）19:00–21:00，主舞台 / 整個街廊。結合高中時裝作品展與在地小學社團表演，攜手手工共創藝術，邀請大家一同花行上街！</div>
    </div>
    <div class="yh-feat-card white yh-reveal">
      <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%90%91%E6%97%A5%E8%91%B5.png" alt="">
      <div class="yh-feat-num">03</div>
      <div class="yh-feat-title">裝置藝術</div>
      <div class="yh-feat-desc">5/16–5/23，每日 19:30–20:30 作品導覽，服務台出發。中山大學生、高中科技競賽與社區共創，以「呼吸・蔓延・共生」呈現情緒綻放的旅程。</div>
    </div>
    <div class="yh-feat-card primary yh-reveal">
      <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E7%99%BE%E5%90%88.png" alt="">
      <div class="yh-feat-num">04</div>
      <div class="yh-feat-title">特色市集</div>
      <div class="yh-feat-desc">5/16–5/23，每日 17:00–21:00，新樂街大智路口至愛文店口路段。花圃般的創意市集，飲食、手作、花香一次擁有。</div>
    </div>
  </div>
</section>
```

---

### 元件 5 — 活動排程

```html
<section class="yh-schedule">
  <div class="yh-schedule-inner">
    <div style="text-align:center;margin-bottom:56px;" class="yh-reveal">
      <div class="yh-section-label">SCHEDULE 活動時程</div>
      <h2 class="yh-section-title">活動排程</h2>
    </div>
    <div class="yh-schedule-day yh-reveal">
      <div class="yh-schedule-day-label">5/16（六）開幕式 × 踩街遊行</div>
      <div class="yh-schedule-row"><div class="yh-schedule-time">17:00</div><div><div class="yh-schedule-name">🎉 開幕式 × 高中科技藝術競賽頒獎</div><div class="yh-schedule-stage">主舞台</div></div></div>
      <div class="yh-schedule-row"><div class="yh-schedule-time">17:00</div><div><div class="yh-schedule-name">特色市集 開市</div><div class="yh-schedule-stage">新樂街大智路口—愛文店口</div></div></div>
      <div class="yh-schedule-row"><div class="yh-schedule-time">19:00</div><div><div class="yh-schedule-name">🌸 踩街遊行 ── 花行上街！</div><div class="yh-schedule-stage">主舞台出發 / 新樂街全廊</div></div></div>
      <div class="yh-schedule-row"><div class="yh-schedule-time">19:30</div><div><div class="yh-schedule-name">裝置藝術 作品導覽</div><div class="yh-schedule-stage">服務台集合出發</div></div></div>
      <div class="yh-schedule-row"><div class="yh-schedule-time">21:00</div><div><div class="yh-schedule-name">踩街收隊 / 市集收攤</div><div class="yh-schedule-stage">新樂街綠廊</div></div></div>
    </div>
    <div class="yh-schedule-day yh-reveal">
      <div class="yh-schedule-day-label">5/17（日）— 5/22（五）常態展期</div>
      <div class="yh-schedule-row"><div class="yh-schedule-time">17:00</div><div><div class="yh-schedule-name">特色市集 開市</div><div class="yh-schedule-stage">新樂街大智路口—愛文店口</div></div></div>
      <div class="yh-schedule-row"><div class="yh-schedule-time">19:30</div><div><div class="yh-schedule-name">裝置藝術 作品導覽</div><div class="yh-schedule-stage">服務台集合出發</div></div></div>
      <div class="yh-schedule-row"><div class="yh-schedule-time">21:00</div><div><div class="yh-schedule-name">市集收攤</div><div class="yh-schedule-stage">新樂街綠廊</div></div></div>
    </div>
    <div class="yh-schedule-day yh-reveal">
      <div class="yh-schedule-day-label">5/22（五）特別場 × 邀演活動</div>
      <div class="yh-schedule-row"><div class="yh-schedule-time">全日</div><div><div class="yh-schedule-name">邀演活動 × 高雄市中央公園商圈</div><div class="yh-schedule-stage">高雄市中央公園商圈</div></div></div>
    </div>
    <div class="yh-schedule-day yh-reveal">
      <div class="yh-schedule-day-label">5/23（六）最終日 × 閉幕</div>
      <div class="yh-schedule-row"><div class="yh-schedule-time">17:00</div><div><div class="yh-schedule-name">特色市集 最終場</div><div class="yh-schedule-stage">新樂街大智路口—愛文店口</div></div></div>
      <div class="yh-schedule-row"><div class="yh-schedule-time">19:30</div><div><div class="yh-schedule-name">裝置藝術 最終導覽</div><div class="yh-schedule-stage">服務台集合出發</div></div></div>
      <div class="yh-schedule-row"><div class="yh-schedule-time">21:00</div><div><div class="yh-schedule-name">花轟閉幕 · 花朵歸巢</div><div class="yh-schedule-stage">新樂街綠廊</div></div></div>
    </div>
  </div>
</section>
```

---

### 元件 6 — 展覽資訊 + Footer

```html
<section class="yh-event-info">
  <div class="yh-event-info-inner">
    <div style="text-align:center;margin-bottom:56px;" class="yh-reveal">
      <div class="yh-section-label">EVENT INFO 展覽資訊</div>
      <h2 class="yh-section-title" style="color:var(--white);">活動資訊</h2>
    </div>
    <div class="yh-info-top yh-reveal">
      <div class="yh-info-box">
        <div class="yh-info-box-label">活動時間</div>
        <div class="yh-info-box-value">2026 / 5.16 — 5.23<br><span>每日 17:00 – 21:00</span></div>
      </div>
      <div class="yh-info-box">
        <div class="yh-info-box-label">活動地點</div>
        <div class="yh-info-box-value">新樂街綠廊<br><span>大智路 – 大成街路段</span></div>
      </div>
    </div>
    <div class="yh-info-bottom yh-reveal">
      <div style="display:flex;flex-direction:column;gap:16px;">
        <div class="yh-info-card">
          <div class="yh-info-card-label">主辦單位</div>
          <div class="yh-info-list">
            <div class="yh-info-list-item"><span class="yh-info-list-num">①</span>中山大學 USR「鹽埕創意街區實驗室計畫」計畫</div>
            <div class="yh-info-list-item"><span class="yh-info-list-num">②</span>高教深耕「以社會設計、社會策展與跨域創新打造幸福鹽埕」計畫</div>
            <div class="yh-info-list-item"><span class="yh-info-list-num">③</span>人文暨科技跨領域學士學位學程</div>
          </div>
        </div>
        <div class="yh-info-card">
          <div class="yh-info-card-label">共同主辦</div>
          <div class="yh-info-plain">鹽埕區公所</div>
        </div>
        <div class="yh-info-card">
          <div class="yh-info-card-label">協辦單位</div>
          <div class="yh-info-plain">育仁里里長辦公室・光明里里長辦公室・南端里里長辦公室・沙地里里長辦公室<br>鹽埕國中・鹽埕國小・光榮國小・忠孝國小<br>揚帆主婦社</div>
        </div>
      </div>
      <div class="yh-info-card">
        <div class="yh-info-card-label">贊助單位</div>
        <div class="yh-info-list">
          <div class="yh-info-list-item"><span class="yh-info-list-num">①</span>財團法人瑞儀教育基金會</div>
          <div class="yh-info-list-item"><span class="yh-info-list-num">②</span>翰品酒店 高雄</div>
          <div class="yh-info-list-item"><span class="yh-info-list-num">③</span>福容大飯店 高雄</div>
          <div class="yh-info-list-item"><span class="yh-info-list-num">④</span>南區社會情緒學習與教育創新中心</div>
        </div>
      </div>
    </div>
  </div>
</section>

<footer>
  <div class="yh-footer-pre">
    <div class="yh-footer-pre-title">2026 鹽夏不夜埕 × 花轟<br>5/16—5/23 新樂街綠廊見！</div>
    <div class="yh-footer-pre-sub">開幕式・踩街遊行・裝置藝術・特色市集　免費入場</div>
    <a href="/stories" class="yh-footer-pre-btn">埕中大小事 →</a>
  </div>
  <div class="yh-footer-city">
    <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%8F%AF%E6%84%9B%E7%9A%84%E8%A1%97%E5%8D%80.png" alt="">
  </div>
  <div class="yh-footer-bottom">
    <div class="yh-footer-logo">
      <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%B9%BD%E5%A4%8Flogo%E5%80%91-20260416T013432Z-3-001/%E9%B9%BD%E5%A4%8Flogo%E5%80%91/%E8%B3%87%E7%94%A2%202.png" alt="鹽夏不夜埕">
    </div>
    <div class="yh-footer-social">
      <a href="#">Facebook</a>
      <a href="#">Instagram</a>
      <a href="#">LINE 官方帳號</a>
    </div>
    <div class="yh-footer-copy">© 2026 鹽夏不夜埕 All Rights Reserved</div>
  </div>
</footer>
```
