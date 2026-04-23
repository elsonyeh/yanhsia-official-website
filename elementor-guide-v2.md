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
/* ── HERO（banner + 吉祥物，無其他內容） ── */
.yh-hero{position:relative;width:100%;aspect-ratio:3418/1301;min-height:280px;overflow:hidden;}
/* Elementor widget container 補丁（移除預設 padding，避免 banner 上下被截） */
.elementor-widget-html .elementor-widget-container{padding:0!important;}
.yh-hero-bg{position:absolute;inset:0;background:url('https://elsonyeh.github.io/yanhsia-official-website/%E9%B9%BD%E5%A4%8Fbanner%20%E7%84%A1%E5%90%89%E7%A5%A5%E7%89%A9%E7%89%88%E6%9C%AC.png')center/cover no-repeat;}
/* 吉祥物 — 位置對應 banner 構圖 */
.yh-mascot{position:absolute;pointer-events:none;z-index:6;}
/* 孤挺花：左側建築旁下偏中 */
.yh-m-amary{top:69%;left:18%; width:9%;max-width:130px;min-width:52px;animation:yh-floatB 4s   ease-in-out infinite .8s;}
/* 向日葵：中央偏左上，浮在空中 */
.yh-m-sunf {top:22%;left:25%; width:15%;max-width:150px;min-width:60px;animation:yh-floatB 3.2s ease-in-out infinite .4s;}
/* 百合：左下方轟字旁 */
.yh-m-lily {top:55%;left:30%; width:8%;max-width:120px;min-width:48px;animation:yh-floatA 3.8s ease-in-out infinite;}
/* 薰衣草：右下靠中 */
.yh-m-lav  {top:60%;right:25%;width:10%;max-width:130px;min-width:52px;animation:yh-floatA 3.5s ease-in-out infinite .2s;}
/* 藍玫瑰：右上靠中 */
.yh-m-blue {top:20%;right:25%;width:12%;max-width:120px;min-width:48px;animation:yh-floatB 5s   ease-in-out infinite 1s;}
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
.yh-line-sub{font-family:'Noto Sans TC',sans-serif;font-size:15px;line-height:2;color:rgba(51,6,9,.68);margin-bottom:32px;text-wrap:balance;}
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
/* 花轟關於區塊 */
.yh-about-grid{max-width:1080px;margin:0 auto;display:grid;grid-template-columns:1fr 1fr;gap:80px;align-items:center;}
.yh-about-badge{background:var(--bg);border-radius:50%;width:280px;height:280px;display:flex;align-items:center;justify-content:center;box-shadow:0 0 0 12px rgba(242,126,147,.15),0 0 80px rgba(192,84,108,.3);animation:yh-pulse-ring 3s ease-in-out infinite;}
.yh-about-badge img{width:220px;}
/* 花轟頁 */
.yh-page-hero{background:var(--primary);padding:160px 48px 80px;text-align:center;position:relative;overflow:hidden;}
.yh-page-hero-bg{position:absolute;inset:0;background:url('https://elsonyeh.github.io/yanhsia-official-website/%E9%B9%BD%E5%A4%8Fbanner%20%E7%84%A1%E5%90%89%E7%A5%A5%E7%89%A9%E7%89%88%E6%9C%AC.png')center/cover no-repeat;}
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
.yh-schedule{background:var(--primary);padding:100px 48px;}
.yh-schedule-inner{max-width:900px;margin:0 auto;}
.yh-schedule-img{display:block;width:100%;border-radius:20px;box-shadow:0 16px 64px rgba(0,0,0,.35);}
.yh-xp{background:var(--bg);padding:100px 48px;}
.yh-xp-inner{max-width:900px;margin:0 auto;}
.yh-xp-card{background:var(--white);border-radius:20px;padding:32px 36px;display:flex;flex-wrap:wrap;gap:28px;align-items:flex-start;margin-bottom:20px;}
.yh-xp-meta{flex-shrink:0;min-width:160px;}
.yh-xp-title{font-family:'Noto Serif TC',serif;font-size:20px;font-weight:700;color:var(--primary);margin-bottom:8px;}
.yh-xp-date{font-family:'Noto Sans TC',sans-serif;font-size:11px;font-weight:700;color:var(--white);background:var(--secondary);border-radius:50px;padding:3px 12px;display:inline-block;margin-bottom:8px;}
.yh-xp-where{font-family:'Noto Sans TC',sans-serif;font-size:12px;color:#999;line-height:1.9;}
.yh-xp-body{flex:1;min-width:200px;font-family:'Noto Sans TC',sans-serif;font-size:14px;line-height:2.1;color:#555;}
.yh-xp-perf{background:var(--secondary);border-radius:20px;padding:40px;margin-top:16px;}
.yh-xp-perf-row{display:flex;align-items:flex-start;gap:20px;padding:16px 20px;background:rgba(255,255,255,.12);border-radius:12px;margin-bottom:12px;}
.yh-xp-perf-time{font-family:'Noto Sans TC',sans-serif;font-weight:900;font-size:14px;color:var(--gold);min-width:110px;flex-shrink:0;padding-top:2px;}
.yh-xp-perf-name{font-family:'Noto Serif TC',serif;font-size:17px;font-weight:700;color:var(--white);margin-bottom:4px;}
.yh-xp-perf-desc{font-family:'Noto Sans TC',sans-serif;font-size:13px;color:rgba(255,255,255,.75);}
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
.yh-reveal.visible{animation:yh-fadeUp .7s ease forwards;}
@keyframes yh-floatA{0%,100%{transform:translateY(0) rotate(-4deg);}50%{transform:translateY(-22px) rotate(4deg);}}
@keyframes yh-floatB{0%,100%{transform:translateY(0) rotate(4deg);}50%{transform:translateY(-18px) rotate(-4deg);}}
@keyframes yh-marquee{0%{transform:translateX(0);}100%{transform:translateX(-50%);}}
@keyframes yh-pulse-ring{0%,100%{box-shadow:0 0 0 10px rgba(242,126,147,.18),0 0 60px rgba(192,84,108,.35);}50%{box-shadow:0 0 0 18px rgba(242,126,147,.08),0 0 80px rgba(192,84,108,.22);}}
@keyframes yh-fadeUp{from{opacity:0;transform:translateY(36px);}to{opacity:1;transform:translateY(0);}}
@media(max-width:900px){
  .yh-features-grid{grid-template-columns:repeat(2,1fr);}
  .yh-founder-grid{grid-template-columns:1fr;}
  .yh-trio-grid{grid-template-columns:1fr;}
  .yh-info-top,.yh-info-bottom{grid-template-columns:1fr;}
  .yh-about-grid{grid-template-columns:1fr;gap:48px;}
  .yh-about-badge{width:220px;height:220px;}
  .yh-about-badge img{width:180px;}
}
@media(max-width:560px){
  .yh-features-grid{grid-template-columns:1fr;}
  .yh-hero{min-height:0;}
  .yh-m-amary{top:52%;width:10%;min-width:0;}
  .yh-m-sunf{width:12%;min-width:0;}
  .yh-m-lily{top:50%;width:8%;min-width:0;}
  .yh-m-lav{top:58%;width:10%;min-width:0;}
  .yh-m-blue{width:10%;min-width:0;}
  .yh-features,.yh-founders,.yh-curatorial,.yh-schedule,.yh-xp,.yh-event-info,.yh-line-cta{padding-left:20px!important;padding-right:20px!important;}
  .yh-xp-card{gap:16px;}.yh-xp-meta{min-width:100%;}
  .yh-page-hero{padding-left:20px!important;padding-right:20px!important;padding-top:100px!important;}
  .yh-feat-card{padding:28px 18px;}
  .yh-about-badge{width:180px;height:180px;}
  .yh-about-badge img{width:150px;}
}
</style>

<section class="yh-hero">
  <!-- Banner 背景 -->
  <div class="yh-hero-bg"></div>

  <!-- 五朵花吉祥物（位置對應 banner 構圖，動態飄浮） -->
  <img class="yh-mascot yh-m-lily"  src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E7%99%BE%E5%90%88.png"   alt="">
  <img class="yh-mascot yh-m-sunf"  src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%90%91%E6%97%A5%E8%91%B5.png" alt="">
  <img class="yh-mascot yh-m-amary" src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%AD%A4%E6%8C%BA%E8%8A%B1.png" alt="">
  <img class="yh-mascot yh-m-lav"   src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%96%B0%E8%A1%A3%E8%8D%89.png" alt="">
  <img class="yh-mascot yh-m-blue"  src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%97%8D%E7%8E%AB%E7%91%B0.png"  alt="">
</section>

<script>
  (function(){
    function _yhInit(){
      if(window._yhDone) return; window._yhDone=true;
      const obs = new IntersectionObserver((entries)=>{
        entries.forEach(e=>{ if(e.isIntersecting){ e.target.classList.add('visible'); obs.unobserve(e.target); } });
      },{threshold:0.12});
      document.querySelectorAll('.yh-reveal').forEach(el=>obs.observe(el));
      const ms = document.querySelectorAll('.yh-mascot');
      window.addEventListener('scroll',()=>{
        const y=window.scrollY;
        ms.forEach((m,i)=>{ m.style.transform=`translateY(${y*(i%2===0?.08:.05)}px)`; });
      },{passive:true});
    }
    if(document.readyState==='loading') document.addEventListener('DOMContentLoaded',_yhInit);
    else _yhInit();
  })();
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
      <h2 class="yh-section-title">鹽夏四大特色｜Features</h2>
    </div>
    <div class="yh-features-grid">
      <div class="yh-feat-card white">
        <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%96%B0%E8%A1%A3%E8%8D%89.png" alt="">
        <div class="yh-feat-num">01</div>
        <div class="yh-feat-title">裝置藝術</div>
        <div class="yh-feat-desc">鹽埕埕區中展示一系列由中山大學「跨領域創新專選（一）」課程學生與藝術家所創作之光影裝置藝術作品，共同點亮鹽埕夜夜。</div>
      </div>
      <div class="yh-feat-card dark-red">
        <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%AD%A4%E6%8C%BA%E8%8A%B1.png" alt="">
        <div class="yh-feat-num">02</div>
        <div class="yh-feat-title">表演藝術</div>
        <div class="yh-feat-desc">邀請高雄在地劇團、樂團等表演團體，在街廊進行演出，沈浸在藝術表演與歷史文化交融出的鹽埕記憶。</div>
      </div>
      <div class="yh-feat-card white">
        <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%90%91%E6%97%A5%E8%91%B5.png" alt="">
        <div class="yh-feat-num">03</div>
        <div class="yh-feat-title">特色市集</div>
        <div class="yh-feat-desc">在展期的跨週六，邀請高雄在地商家或是學生創業品牌，配合每年的不同主題企劃，打造出獨一無二的鹽夏特色市集。</div>
      </div>
      <div class="yh-feat-card primary">
        <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E7%99%BE%E5%90%88.png" alt="">
        <div class="yh-feat-num">04</div>
        <div class="yh-feat-title">周邊活動</div>
        <div class="yh-feat-desc">舉辦「前導工作坊」作為策展的暖身，與鹽埕在地企業合作推出各種「鹽夏限定活動」，活動當日則有美食、歷史等導覽。</div>
      </div>
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
      <h2 class="yh-section-title" style="color:#fff;">鹽夏創始人們｜Founders</h2>
    </div>
    <div class="yh-founder-grid">
      <div class="yh-founder-card">
        <div class="yh-founder-avatar" style="background:#C0546C;box-shadow:0 0 0 8px rgba(192,84,108,.2),0 0 48px rgba(192,84,108,.25);">
          <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%AD%A4%E6%8C%BA%E8%8A%B1.png" alt="">
        </div>
        <div class="yh-founder-name">劉雯婷</div>
        <div class="yh-founder-role">鹽夏不夜埕 共同創辦人</div>
        <div class="yh-founder-bio">以社會設計為核心，長期深耕鹽埕街區的文化活化與社區共創，致力用藝術讓老街區重新被看見。</div>
      </div>
      <div class="yh-founder-card" style="animation-delay:.12s">
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
    <div style="max-width:800px;margin:0 auto;text-align:center;">
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
    <a href="https://line.me/R/ti/p/@235chemh" class="yh-cta-link" style="background:#330609;color:#fff;">加入 LINE 好友 →</a>
  </div>
</section>
```

---

### 元件 6 — Footer

```html
<div style="height:120px;background:#F2D9D0 url('https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%8F%AF%E6%84%9B%E7%9A%84%E8%8D%89%E5%8F%A2.png') center bottom/auto 100% no-repeat;"></div>
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
      <a href="https://www.facebook.com/dontsleepinyancheng">Facebook</a>
      <a href="https://www.instagram.com/dont_sleep_in_yancheng/">Instagram</a>
      <a href="https://line.me/R/ti/p/@235chemh">LINE 官方帳號</a>
      <a href="mailto:dont.sleep.in.yancheng@gmail.com">Mail</a>
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
<section class="yh-founders">
  <div class="yh-about-grid">
    <div>
      <div class="yh-section-label">ABOUT 關於花轟</div>
      <h2 class="yh-section-title" style="color:var(--white);margin-bottom:28px;">什麼是<br>花轟？</h2>
      <p style="font-family:'Noto Sans TC',sans-serif;font-size:16px;line-height:2.1;color:var(--gray);">
        夏夜裡，花朵不睡覺。<br><br>
        花轟是一場屬於夏天的街區派對，讓每一朵花都在鹽埕的巷弄間盡情綻放。我們相信藝術就在生活裡，音樂就在街角上，而你就是這個夏天最美的風景。<br><br>
        2026 年，鹽夏不夜埕帶著全新能量回來。開幕式、踩街遊行、裝置藝術、特色市集，用八天的時間把高雄的夏夜染得更鮮豔，更不羈，更屬於你。
      </p>
    </div>
    <div style="display:flex;justify-content:center;">
      <div class="yh-about-badge">
        <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%8A%B1%E8%BD%9F.png" alt="花轟">
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
    <h2 class="yh-section-title" style="color:var(--white);margin-bottom:28px;">花の宣言</h2>
    <div class="yh-quote-block">《花轟》以花的綻放，回應情緒的張力與流動。正如花朵終將撐開花萼、露出真實的姿態，情緒的包裝紙在拆封的瞬間被釋放與凝視，以當下最真實的樣貌綻放。</div>
    <div class="yh-sub-text">鹽埕將化身為一座「花園」，情緒在巷弄間自然生長；觀眾在花園中自由穿梭。透過「呼吸、蔓延、共生」三大面向，體驗情緒從個體到他者，從他者到群體網絡相互影響、轉化與共存的過程。</div>
    <div class="yh-note-text">《花轟》邀請觀眾進入這座花園，靠近那些正在發生的情緒。</div>
    <div class="yh-trio-grid">
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
<section class="yh-features">
  <div style="text-align:center;margin-bottom:56px;">
    <div class="yh-section-label">FEATURES 四大主要活動</div>
    <h2 class="yh-section-title">今年花轟</h2>
  </div>
  <div class="yh-features-grid">
    <div class="yh-feat-card white">
      <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%96%B0%E8%A1%A3%E8%8D%89.png" alt="">
      <div class="yh-feat-num">01</div>
      <div class="yh-feat-title">開幕式</div>
      <div class="yh-feat-desc">5/16（六）17:00–19:00，主舞台。揭開 2026 鹽夏不夜埕序幕，同步頒發高雄高中生科技藝術競賽獎項，邀請觀眾一同感受盛夏慶典的到來。</div>
    </div>
    <div class="yh-feat-card dark-red">
      <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%AD%A4%E6%8C%BA%E8%8A%B1.png" alt="">
      <div class="yh-feat-num">02</div>
      <div class="yh-feat-title">踩街遊行</div>
      <div class="yh-feat-desc">5/16（六）19:00–21:00，主舞台 / 整個街廊。結合高中時裝作品展與在地小學社團表演，攜手手工共創藝術，邀請大家一同花行上街！</div>
    </div>
    <div class="yh-feat-card white">
      <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%90%91%E6%97%A5%E8%91%B5.png" alt="">
      <div class="yh-feat-num">03</div>
      <div class="yh-feat-title">裝置藝術</div>
      <div class="yh-feat-desc">5/16–5/23，每日 19:30–20:30 作品導覽，服務台出發。中山大學生、高中科技競賽與社區共創，以「呼吸・蔓延・共生」呈現情緒綻放的旅程。</div>
    </div>
    <div class="yh-feat-card primary">
      <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E7%99%BE%E5%90%88.png" alt="">
      <div class="yh-feat-num">04</div>
      <div class="yh-feat-title">特色市集</div>
      <div class="yh-feat-desc">5/16–5/23，每日 17:00–21:00，新樂街大智路口至愛文店口路段。花圃般的創意市集，飲食、手作、花香一次擁有。</div>
    </div>
  </div>
</section>
```

---

### 元件 5 — 數位體驗

```html
<section style="background:var(--primary);padding:80px 48px;">
  <div style="max-width:1080px;margin:0 auto;">
    <div style="display:flex;flex-wrap:wrap;gap:48px;align-items:center;justify-content:space-between;">
      <div style="flex:1;min-width:260px;">
        <div style="font-size:11px;letter-spacing:.45em;color:var(--gold);margin-bottom:12px;font-family:'Noto Sans TC',sans-serif;font-weight:700;">DIGITAL EXPERIENCE 數位體驗</div>
        <h2 style="font-family:'Noto Serif TC',serif;font-size:clamp(24px,3vw,38px);font-weight:900;color:var(--white);margin-bottom:24px;line-height:1.35;">埕花｜情緒解籤 × 花語體驗</h2>
        <p style="font-family:'Noto Sans TC',sans-serif;font-size:15px;line-height:2.2;color:rgba(255,255,255,.75);margin:0;">不知從何逛起？網站透過面部識別，即時捕捉你的表情並解讀情緒，轉化為專屬花語祝福卡，點擊花攤獲得路線指引。每張花卡都承載祝福與鹽夏故事，邀請你與埕花一同探索街區。花語卡中還藏有鹽夏的神秘小驚喜，等你來發現屬於自己的花朵緣分。</p>
        <a href="https://drawing-flower-fortunes.vercel.app/" target="_blank" style="display:inline-block;margin-top:28px;padding:12px 36px;background:var(--secondary);color:#fff;text-decoration:none;font-family:'Noto Sans TC',sans-serif;font-weight:700;font-size:14px;border-radius:50px;letter-spacing:.06em;">立即體驗 →</a>
      </div>
      <div style="flex-shrink:0;text-align:center;">
        <img src="https://api.qrserver.com/v1/create-qr-code/?size=160x160&data=https%3A%2F%2Fdrawing-flower-fortunes.vercel.app%2F" alt="埕花 QR Code" style="width:160px;height:160px;border-radius:12px;padding:8px;background:#fff;display:block;box-shadow:0 4px 20px rgba(0,0,0,.3);">
        <div style="font-family:'Noto Sans TC',sans-serif;font-size:11px;letter-spacing:.2em;color:rgba(255,255,255,.45);margin-top:8px;">掃碼體驗</div>
      </div>
    </div>
  </div>
</section>
```

---

### 元件 6 — 展覽資訊

```html
<section class="yh-event-info" style="position:relative;overflow:hidden;">
  <div style="position:absolute;right:-80px;bottom:40px;opacity:.06;pointer-events:none;z-index:0;transform:rotate(-15deg);">
    <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%8A%B1%E8%BD%9F.png" alt="" style="width:380px;">
  </div>
  <div class="yh-event-info-inner" style="position:relative;z-index:1;">
    <div style="text-align:center;margin-bottom:56px;">
      <div class="yh-section-label">EVENT INFO 展覽資訊</div>
      <h2 class="yh-section-title" style="color:var(--white);">活動資訊</h2>
      <div style="width:40px;height:3px;background:var(--gold);margin:20px auto 0;border-radius:2px;"></div>
    </div>
    <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:20px;margin-bottom:20px;">
      <div class="yh-info-box">
        <div class="yh-info-box-label">活動時間</div>
        <div class="yh-info-box-value">2026 / 5.16 — 5.23<br><span>每日 17:00 – 21:00</span></div>
      </div>
      <div class="yh-info-box">
        <div class="yh-info-box-label">活動地點</div>
        <div class="yh-info-box-value">新樂街綠廊<br><span>大智路 – 大成街路段</span></div>
      </div>
      <div class="yh-info-box" style="background:rgba(242,190,92,.18);border-color:rgba(242,190,92,.6);">
        <div class="yh-info-box-label">入場費用</div>
        <div class="yh-info-box-value" style="color:var(--gold);">全程免費<br><span style="color:rgba(255,255,255,.7);">Free Admission</span></div>
      </div>
    </div>
    <div class="yh-info-bottom">
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
          <div class="yh-info-plain">育仁里里長辦公室・光明里里長辦公室・南端里里長辦公室・沙地里里長辦公室<br>鹽埕國中・鹽埕國小・光榮國小・忠孝國小<br>揚帆主婦社・微熟成文創有限公司</div>
        </div>
      </div>
      <div style="display:flex;flex-direction:column;gap:16px;">
        <div class="yh-info-card">
          <div class="yh-info-card-label">贊助單位</div>
          <div class="yh-info-list">
            <div class="yh-info-list-item"><span class="yh-info-list-num">①</span>財團法人瑞儀教育基金會</div>
            <div class="yh-info-list-item"><span class="yh-info-list-num">②</span>翰品酒店 高雄</div>
            <div class="yh-info-list-item"><span class="yh-info-list-num">③</span>福容大飯店 高雄</div>
            <div class="yh-info-list-item"><span class="yh-info-list-num">④</span>台灣福興工業股份有限公司</div>
            <div class="yh-info-list-item"><span class="yh-info-list-num">⑤</span>南區社會情緒學習與教育創新中心</div>
          </div>
        </div>
        <div class="yh-info-card">
          <div class="yh-info-card-label">交通資訊</div>
          <div class="yh-info-list">
            <div class="yh-info-list-item"><span class="yh-info-list-num" style="background:var(--blue);">捷</span>捷運鹽埕埔站（R9）步行約 5 分鐘</div>
            <div class="yh-info-list-item"><span class="yh-info-list-num" style="background:var(--lavender);">公</span>公車 新樂街站、鹽埕區公所站</div>
            <div class="yh-info-list-item"><span class="yh-info-list-num" style="background:var(--rose);color:var(--primary);">停</span>鹽埕地下停車場、哈瑪星停車場</div>
          </div>
        </div>
      </div>
    </div>
    <div style="text-align:center;margin-top:44px;">
      <a href="https://maps.google.com/?q=高雄市鹽埕區新樂街" target="_blank" style="display:inline-block;padding:13px 40px;border:1px solid rgba(242,190,92,.45);color:var(--gold);text-decoration:none;font-family:'Noto Sans TC',sans-serif;font-size:14px;letter-spacing:.1em;border-radius:50px;">📍 查看活動地圖</a>
    </div>
  </div>
</section>
```

---

### 元件 7 — 活動排程

> 背景改為深色 `var(--primary)`，內容只顯示活動排程圖 + 標題。

```html
<section class="yh-schedule">
  <div class="yh-schedule-inner">
    <div style="text-align:center;margin-bottom:48px;">
      <div class="yh-section-label" style="color:var(--gold);">SCHEDULE 活動時程</div>
      <h2 class="yh-section-title" style="color:var(--white);">活動排程</h2>
    </div>
    <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%B9%BD%E5%A4%8F%E6%B4%BB%E5%8B%95%E6%8E%92%E7%A8%8B.png" alt="活動排程" class="yh-schedule-img">
  </div>
</section>
```

---

### 元件 7b — 鹽夏專屬體驗

> 背景 `var(--bg)`，列出所有專屬活動卡片 + 表演活動區塊。

```html
<section class="yh-xp">
  <div class="yh-xp-inner">
    <div style="text-align:center;margin-bottom:56px;">
      <div class="yh-section-label">EXCLUSIVE EXPERIENCE</div>
      <h2 class="yh-section-title">鹽夏專屬體驗</h2>
    </div>

    <div class="yh-xp-card">
      <div class="yh-xp-meta">
        <div class="yh-xp-title">情緒花粉投遞站</div>
        <div class="yh-xp-date">5/16 · 17</div>
        <div class="yh-xp-where">17:00–21:00<br>5/16 服務台<br>5/17 主舞台<br>移動式投遞站</div>
      </div>
      <div class="yh-xp-body">不只是分享，還能被演出來？透過情緒花粉投遞站把想分享的事、想大喊的話，傳達出去吧！投遞的回覆將成為《開港來花轟》喜劇演出題材！</div>
    </div>

    <div class="yh-xp-card">
      <div class="yh-xp-meta">
        <div class="yh-xp-title">花舞之際</div>
        <div class="yh-xp-date">5/16</div>
        <div class="yh-xp-where">17:00–17:30<br>主舞台</div>
      </div>
      <div class="yh-xp-body">現場舉辦呼啦舞互動演出！本活動與「快樂藝術空間」合作，帶領「鹽埕老人活動站」長輩舞動鹽埕活力。</div>
    </div>

    <div class="yh-xp-card">
      <div class="yh-xp-meta">
        <div class="yh-xp-title">花轟時裝秀</div>
        <div class="yh-xp-date">5/16</div>
        <div class="yh-xp-where">18:40–19:00<br>主舞台</div>
      </div>
      <div class="yh-xp-body">小學生模特兒雲集！鹽埕國小與國立中山大學劇藝系服裝設計組學生共同創作服飾，並在時裝秀中由小學生走上秀台，展示共創服飾！</div>
    </div>

    <div class="yh-xp-card">
      <div class="yh-xp-meta">
        <div class="yh-xp-title">開港來花轟</div>
        <div class="yh-xp-date">5/17</div>
        <div class="yh-xp-where">17:00–18:30<br>19:30–21:00<br>主舞台</div>
      </div>
      <div class="yh-xp-body">高雄在地喜劇品牌——喜劇開港，透過觀眾互動創作即興喜劇，帶來充滿驚喜的《花轟》演出！</div>
    </div>

    <div class="yh-xp-card">
      <div class="yh-xp-meta">
        <div class="yh-xp-title">聽！花兒在說什麼？</div>
        <div class="yh-xp-date">5/17</div>
        <div class="yh-xp-where">18:30–19:30<br>鹽埕國中大會議室</div>
      </div>
      <div class="yh-xp-body">以鋼琴三重奏與弦樂重奏，將指尖音符化作初夏花語。共賞一場細膩優雅、如花綻放的室內樂饗宴。</div>
    </div>

    <div class="yh-xp-card">
      <div class="yh-xp-meta">
        <div class="yh-xp-title">花聚共感餐桌<br><span style="font-size:12px;color:var(--secondary);">邀請制</span></div>
        <div class="yh-xp-date">5/23</div>
        <div class="yh-xp-where">17:00–19:30<br>市集互動區</div>
      </div>
      <div class="yh-xp-body">以食物為入口、故事為情感、情緒為核心，青銀共食的體驗活動。邀請翰品酒店、在地店家、民眾一同享用暖心美食。</div>
    </div>

    <div class="yh-xp-card">
      <div class="yh-xp-meta">
        <div class="yh-xp-title">從手機至 AI：數位時代鹽埕長輩的情緒故事</div>
        <div class="yh-xp-date">5/16 · 17 · 23</div>
        <div class="yh-xp-where">17:00–21:00<br>克朗德美術館</div>
      </div>
      <div class="yh-xp-body">本展覽由中山大學《數位文化與人類學：理論與實踐》課程同學策劃：透過訪談與工作坊，深入鹽埕區老人活動站實地調查，探討手機等數位設備如何影響了在地長輩們的日常生活與社交活動，進而成為牽動情緒的重要載體，也將探討長輩面對 AI 發展的複雜情緒與隱藏期待。</div>
    </div>

    <div class="yh-xp-perf">
      <div style="margin-bottom:28px;">
        <div style="font-family:'Noto Sans TC',sans-serif;font-size:11px;letter-spacing:.4em;color:rgba(255,255,255,.6);margin-bottom:6px;">LIVE PERFORMANCE 表演活動</div>
        <div style="font-family:'Noto Serif TC',serif;font-size:26px;font-weight:700;color:var(--white);">表演活動</div>
        <div style="font-family:'Noto Sans TC',sans-serif;font-size:13px;color:rgba(255,255,255,.75);margin-top:6px;">5/23・鹽埕國中大門口前廣場</div>
      </div>
      <div class="yh-xp-perf-row">
        <div class="yh-xp-perf-time">17:30–18:30</div>
        <div><div class="yh-xp-perf-name">魚皮</div><div class="yh-xp-perf-desc">用音樂與大家交流情感，唱出動人旋律。</div></div>
      </div>
      <div class="yh-xp-perf-row">
        <div class="yh-xp-perf-time">18:45–19:45</div>
        <div><div class="yh-xp-perf-name">小丑呀咪</div><div class="yh-xp-perf-desc">來自小丑島的呀咪，帶你拋開憂愁大笑。</div></div>
      </div>
      <div class="yh-xp-perf-row">
        <div class="yh-xp-perf-time">20:00–21:00</div>
        <div><div class="yh-xp-perf-name">WiKi</div><div class="yh-xp-perf-desc">Wiki 以吉他與合唱，唱出動人故事。</div></div>
      </div>
    </div>
  </div>
</section>
```

> **Elementor 步驟：** 在元件 7 下方新增一個 HTML 元件，貼上上方程式碼。

---

### 元件 8 — Footer

```html
<footer>
  <div class="yh-footer-city" style="background:var(--bg);padding:56px 48px 48px;">
    <div style="max-width:860px;margin:0 auto;">
      <div style="text-align:center;margin-bottom:24px;">
        <div style="font-size:11px;letter-spacing:.45em;color:var(--secondary);margin-bottom:8px;font-family:'Noto Sans TC',sans-serif;font-weight:700;">MAP 活動地圖</div>
        <h2 style="font-family:'Noto Serif TC',serif;font-size:clamp(24px,3vw,36px);font-weight:900;color:var(--primary);line-height:1.2;">花轟 × 鹽埕地圖</h2>
      </div>
      <img src="https://elsonyeh.github.io/yanhsia-official-website/map.png" alt="活動地圖" style="display:block;width:100%;box-shadow:0 8px 40px rgba(51,6,9,.12);">
    </div>
  </div>
  <div class="yh-footer-bottom">
    <div class="yh-footer-logo">
      <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%B9%BD%E5%A4%8Flogo%E5%80%91-20260416T013432Z-3-001/%E9%B9%BD%E5%A4%8Flogo%E5%80%91/%E8%B3%87%E7%94%A2%202.png" alt="鹽夏不夜埕">
    </div>
    <div class="yh-footer-social">
      <a href="https://www.facebook.com/dontsleepinyancheng">Facebook</a>
      <a href="https://www.instagram.com/dont_sleep_in_yancheng/">Instagram</a>
      <a href="https://line.me/R/ti/p/@235chemh">LINE 官方帳號</a>
      <a href="mailto:dont.sleep.in.yancheng@gmail.com">Mail</a>
    </div>
    <div class="yh-footer-copy">© 2026 鹽夏不夜埕 All Rights Reserved</div>
  </div>
</footer>
```
