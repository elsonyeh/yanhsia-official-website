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
  @import url("https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@400;700;900&family=Noto+Sans+TC:wght@300;400;700;900&display=swap");

  :root {
    --primary: #1a2640;
    --surface: #374e7e;
    --secondary: #c0546c;
    --bg: #f2d9d0;
    --gold: #f2be5c;
    --peach: #f2a488;
    --blue: #5b7ba6;
    --pink: #f27e93;
    --red: #cb5661;
    --lavender: #c7a4c3;
    --gray: #cfc9cc;
    --rose: #e9abab;
    --white: #ffffff;
  }
  /* ── HERO（banner + 吉祥物，無其他內容） ── */
  .yh-hero {
    position: relative;
    width: 100%;
    aspect-ratio: 3418/1301;
    min-height: 280px;
    overflow: hidden;
  }
  /* Elementor widget container 補丁（移除預設 padding，避免 banner 上下被截） */
  .elementor-widget-html .elementor-widget-container {
    padding: 0 !important;
  }
  .yh-hero-bg {
    position: absolute;
    inset: 0;
    background: url("https://elsonyeh.github.io/yanhsia-official-website/%E9%B9%BD%E5%A4%8Fbanner%20%E7%84%A1%E5%90%89%E7%A5%A5%E7%89%A9%E7%89%88%E6%9C%AC.png")
      center/cover no-repeat;
  }
  /* 吉祥物 — 位置對應 banner 構圖 */
  .yh-mascot {
    position: absolute;
    pointer-events: none;
    z-index: 6;
  }
  /* 孤挺花：左側建築旁下偏中 */
  .yh-m-amary {
    top: 69%;
    left: 18%;
    width: 9%;
    max-width: 130px;
    min-width: 52px;
    animation: yh-floatB 4s ease-in-out infinite 0.8s;
  }
  /* 向日葵：中央偏左上，浮在空中 */
  .yh-m-sunf {
    top: 22%;
    left: 25%;
    width: 15%;
    max-width: 150px;
    min-width: 60px;
    animation: yh-floatB 3.2s ease-in-out infinite 0.4s;
  }
  /* 百合：左下方轟字旁 */
  .yh-m-lily {
    top: 55%;
    left: 30%;
    width: 8%;
    max-width: 120px;
    min-width: 48px;
    animation: yh-floatA 3.8s ease-in-out infinite;
  }
  /* 薰衣草：右下靠中 */
  .yh-m-lav {
    top: 60%;
    right: 25%;
    width: 10%;
    max-width: 130px;
    min-width: 52px;
    animation: yh-floatA 3.5s ease-in-out infinite 0.2s;
  }
  /* 藍玫瑰：右上靠中 */
  .yh-m-blue {
    top: 20%;
    right: 25%;
    width: 12%;
    max-width: 120px;
    min-width: 48px;
    animation: yh-floatB 5s ease-in-out infinite 1s;
  }
  .yh-marquee-strip {
    background: var(--gold);
    color: var(--primary);
    padding: 13px 0;
    overflow: hidden;
  }
  .yh-marquee-inner {
    display: flex;
    white-space: nowrap;
    animation: yh-marquee 22s linear infinite;
  }
  .yh-marquee-text {
    font-family: "Noto Sans TC", sans-serif;
    font-weight: 900;
    font-size: 17px;
    letter-spacing: 0.1em;
    padding-right: 64px;
    flex-shrink: 0;
  }
  .yh-section-label {
    font-family: "Noto Sans TC", sans-serif;
    font-size: 11px;
    letter-spacing: 0.45em;
    color: var(--gold);
    margin-bottom: 14px;
    text-transform: uppercase;
  }
  .yh-section-title {
    font-family: "Noto Serif TC", serif;
    font-size: clamp(32px, 5vw, 60px);
    font-weight: 900;
    line-height: 1.1;
    color: var(--primary);
  }
  .yh-features {
    background: var(--bg);
    padding: 100px 48px;
  }
  .yh-features-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 20px;
    max-width: 1080px;
    margin: 0 auto;
  }
  .yh-feat-card {
    border-radius: 24px;
    padding: 40px 24px;
    text-align: center;
    transition:
      transform 0.3s,
      box-shadow 0.3s;
  }
  .yh-feat-card:hover {
    transform: translateY(-8px);
    box-shadow: 0 16px 40px rgba(55,78,126, 0.12);
  }
  .yh-feat-card.white {
    background: var(--white);
    color: var(--primary);
  }
  .yh-feat-card.dark-red {
    background: var(--secondary);
    color: var(--white);
  }
  .yh-feat-card.primary {
    background: var(--surface);
    color: var(--white);
  }
  .yh-feat-card img {
    width: 80px;
    margin: 0 auto 16px;
    display: block;
  }
  .yh-feat-num {
    font-family: "Noto Serif TC", serif;
    font-size: 48px;
    font-weight: 900;
    color: var(--gold);
    line-height: 1;
    margin-bottom: 6px;
  }
  .yh-feat-title {
    font-family: "Noto Serif TC", serif;
    font-size: 20px;
    font-weight: 700;
    margin-bottom: 12px;
  }
  .yh-feat-desc {
    font-family: "Noto Sans TC", sans-serif;
    font-size: 13px;
    line-height: 1.9;
    opacity: 0.78;
  }
  .yh-cta-link {
    display: inline-block;
    padding: 13px 44px;
    background: var(--secondary);
    color: var(--white);
    text-decoration: none;
    font-family: "Noto Sans TC", sans-serif;
    font-weight: 700;
    font-size: 14px;
    border-radius: 50px;
    letter-spacing: 0.08em;
    transition:
      transform 0.2s,
      box-shadow 0.2s;
  }
  .yh-cta-link:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 24px rgba(55,78,126, 0.2);
  }
  .yh-hana-teaser-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 64px;
    align-items: center;
  }
  .yh-hana-teaser-badge {
    width: 320px;
    height: 320px;
    border-radius: 50%;
    background: rgba(192, 84, 108, 0.15);
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow:
      0 0 0 16px rgba(192, 84, 108, 0.08),
      0 0 80px rgba(192, 84, 108, 0.2);
  }
  .yh-hana-btn {
    display: inline-block;
    padding: 15px 52px;
    background: var(--secondary);
    color: var(--white);
    text-decoration: none;
    font-weight: 900;
    font-size: 15px;
    border-radius: 50px;
    letter-spacing: 0.08em;
    transition:
      transform 0.2s,
      box-shadow 0.2s;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.25);
  }
  .yh-hana-btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.35);
  }
  .yh-digital-xp {
    background: linear-gradient(150deg, #f2d9d0 0%, #e9abab 55%, #c7a4c3 100%);
    padding: 100px 48px;
    position: relative;
    overflow: hidden;
  }
  .yh-digital-xp-inner {
    max-width: 860px;
    margin: 0 auto;
    position: relative;
    z-index: 2;
  }
  .yh-digital-xp-layout {
    display: grid;
    grid-template-columns: 200px 1fr;
    gap: 44px;
    align-items: center;
  }
  .yh-digital-xp-badge-wrap {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .yh-digital-xp-badge {
    width: 180px;
    height: 180px;
    border-radius: 50%;
    background: #fff;
    border: 3px solid rgba(192, 84, 108, 0.25);
    display: flex;
    align-items: center;
    justify-content: center;
    box-shadow:
      0 0 0 12px rgba(192, 84, 108, 0.1),
      0 8px 40px rgba(192, 84, 108, 0.2);
  }
  .yh-digital-xp-badge img {
    width: 144px;
  }
  .yh-digital-xp-card {
    background: #fff;
    border-radius: 28px;
    padding: 48px 52px;
    box-shadow:
      0 12px 60px rgba(55,78,126, 0.12),
      0 0 0 1px rgba(192, 84, 108, 0.1);
  }
  .yh-digital-xp-btn {
    display: inline-block;
    margin-top: 28px;
    padding: 13px 40px;
    background: var(--surface);
    color: #fff;
    text-decoration: none;
    font-family: "Noto Sans TC", sans-serif;
    font-weight: 700;
    font-size: 14px;
    border-radius: 50px;
    letter-spacing: 0.06em;
    transition:
      transform 0.2s,
      box-shadow 0.2s;
    box-shadow: 0 4px 20px rgba(55,78,126, 0.22);
  }
  .yh-digital-xp-btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 28px rgba(55,78,126, 0.3);
  }
  .yh-founders {
    background: var(--surface);
    color: var(--white);
    padding: 100px 48px;
    position: relative;
    overflow: hidden;
  }
  .yh-video-label {
    font-family: "Noto Sans TC", sans-serif;
    font-size: 11px;
    letter-spacing: 0.4em;
    color: var(--gold);
    margin-bottom: 12px;
  }
  .yh-video-title {
    font-family: "Noto Serif TC", serif;
    font-size: 28px;
    font-weight: 700;
    color: var(--white);
    margin-bottom: 28px;
  }
  .yh-video-wrap {
    position: relative;
    padding-bottom: 56.25%;
    border-radius: 16px;
    overflow: hidden;
    box-shadow:
      0 0 0 1px rgba(255, 255, 255, 0.1),
      0 24px 60px rgba(0, 0, 0, 0.4);
  }
  .yh-video-wrap iframe {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    border: none;
  }
  .yh-line-cta {
    background: var(--gold);
    padding: 80px 48px;
    text-align: center;
  }
  .yh-line-title {
    font-family: "Noto Serif TC", serif;
    font-size: clamp(24px, 3.5vw, 40px);
    font-weight: 900;
    color: var(--primary);
    margin-bottom: 16px;
  }
  .yh-line-sub {
    font-family: "Noto Sans TC", sans-serif;
    font-size: 15px;
    line-height: 2;
    color: rgba(55,78,126, 0.68);
    margin-bottom: 32px;
    text-wrap: balance;
  }
  .yh-footer-pre {
    background: var(--secondary);
    padding: 80px 48px;
    text-align: center;
    color: var(--white);
  }
  .yh-footer-pre-title {
    font-family: "Noto Serif TC", serif;
    font-size: clamp(28px, 4vw, 48px);
    font-weight: 900;
    margin-bottom: 20px;
  }
  .yh-footer-pre-sub {
    font-family: "Noto Sans TC", sans-serif;
    font-size: 16px;
    opacity: 0.8;
    margin-bottom: 36px;
  }
  .yh-footer-pre-btn {
    display: inline-block;
    padding: 14px 52px;
    background: var(--gold);
    color: var(--primary);
    text-decoration: none;
    font-family: "Noto Sans TC", sans-serif;
    font-weight: 900;
    font-size: 16px;
    border-radius: 50px;
    transition: transform 0.2s;
  }
  .yh-footer-pre-btn:hover {
    transform: translateY(-3px);
  }
  .yh-footer-city {
    background: var(--bg);
    padding-top: 24px;
    overflow: hidden;
    line-height: 0;
  }
  .yh-footer-city img {
    width: 100%;
    display: block;
  }
  .yh-footer-bottom {
    background: var(--surface);
    color: var(--white);
    padding: 48px 48px 36px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
  }
  .yh-footer-logo img {
    height: 38px;
    filter: invert(1);
    mix-blend-mode: screen;
  }
  .yh-footer-social {
    display: flex;
    gap: 28px;
  }
  .yh-footer-social a {
    font-family: "Noto Sans TC", sans-serif;
    color: var(--gold);
    text-decoration: none;
    font-size: 13px;
    letter-spacing: 0.15em;
  }
  .yh-footer-copy {
    font-family: "Noto Sans TC", sans-serif;
    font-size: 12px;
    color: var(--gray);
    letter-spacing: 0.1em;
  }
  .yh-grass {
    position: relative;
    overflow: hidden;
    height: 100px;
    background: var(--bg);
  }
  .yh-grass img {
    position: absolute;
    bottom: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 100%;
    min-width: 900px;
    pointer-events: none;
  }
  /* 花轟頁 Hero */
  .yh-page-hero{min-height:100vh;display:flex;align-items:center;padding:0 48px;position:relative;overflow:hidden;}
  .yh-page-hero-bg{position:absolute;inset:0;background:url("https://elsonyeh.github.io/yanhsia-official-website/%E9%B9%BD%E5%A4%8Fbanner%20%E7%84%A1%E5%90%89%E7%A5%A5%E7%89%A9%E7%89%88%E6%9C%AC.png")center/cover no-repeat;}
  .yh-page-hero-overlay{position:absolute;inset:0;background:linear-gradient(105deg,rgba(26,38,64,.92) 0%,rgba(26,38,64,.65) 50%,rgba(26,38,64,.1) 100%);}
  .yh-page-hero-inner{position:relative;z-index:2;max-width:1080px;margin:0 auto;width:100%;display:grid;grid-template-columns:1fr 1fr;align-items:center;gap:40px;padding-top:80px;}
  .yh-page-eyebrow{font-size:10px;letter-spacing:.6em;color:var(--gold);margin-bottom:32px;display:flex;align-items:center;gap:14px;}
  .yh-page-eyebrow::before{content:'';display:block;width:36px;height:1px;background:var(--gold);flex-shrink:0;}
  .yh-page-title{font-family:'Noto Serif TC',serif;font-size:clamp(72px,11vw,148px);font-weight:900;color:var(--white);line-height:.95;letter-spacing:-.02em;margin-bottom:12px;}
  .yh-hero-title-en{font-size:clamp(13px,1.8vw,18px);letter-spacing:.55em;color:var(--gold);margin-bottom:36px;text-transform:uppercase;}
  .yh-hero-rule{width:56px;height:2px;background:var(--secondary);margin-bottom:28px;}
  .yh-page-sub{font-size:15px;color:rgba(242,217,208,.9);line-height:2;letter-spacing:.06em;margin-bottom:40px;}
  .yh-hero-meta{display:flex;gap:18px;align-items:center;font-size:11px;letter-spacing:.3em;color:var(--rose);}
  .yh-hero-meta-sep{color:var(--secondary);font-size:16px;}
  .yh-hero-mascot{position:relative;z-index:2;display:flex;justify-content:flex-end;align-items:center;}
  .yh-hero-mascot img{width:clamp(200px,34vw,460px);filter:drop-shadow(0 0 60px rgba(192,84,108,.5));animation:yh-float-mascot 4s ease-in-out infinite;}
  .yh-hero-deco-char{position:absolute;font-family:'Noto Serif TC',serif;font-size:clamp(280px,38vw,560px);font-weight:900;color:rgba(255,255,255,.03);line-height:1;right:-40px;top:50%;transform:translateY(-50%);user-select:none;pointer-events:none;z-index:1;}
  .yh-hero-scroll{position:absolute;bottom:36px;left:50%;transform:translateX(-50%);z-index:2;font-size:10px;letter-spacing:.4em;color:rgba(242,217,208,.45);animation:yh-fade-bob 2.2s ease-in-out infinite;}
  @keyframes yh-float-mascot{0%,100%{transform:translateY(0);}50%{transform:translateY(-18px);}}
  @keyframes yh-fade-bob{0%,100%{opacity:.45;transform:translateX(-50%) translateY(0);}50%{opacity:.9;transform:translateX(-50%) translateY(7px);}}
  .yh-curatorial {
    background: var(--surface);
    color: var(--white);
    padding: 100px 48px;
  }
  .yh-curatorial-inner {
    max-width: 860px;
    margin: 0 auto;
  }
  .yh-quote-block {
    font-family: "Noto Serif TC", serif;
    font-size: 17px;
    line-height: 2.3;
    border-left: 3px solid var(--secondary);
    padding-left: 28px;
    margin-bottom: 24px;
    color: var(--white);
  }
  .yh-sub-text {
    font-family: "Noto Sans TC", sans-serif;
    font-size: 16px;
    line-height: 2.2;
    color: var(--rose);
    margin-bottom: 24px;
  }
  .yh-note-text {
    font-family: "Noto Sans TC", sans-serif;
    font-size: 14px;
    line-height: 2;
    opacity: 0.6;
    margin-bottom: 64px;
    color: var(--white);
  }
  .yh-trio-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 2px;
    border-radius: 20px;
    overflow: hidden;
  }
  .yh-trio-card {
    padding: 44px 28px;
    color: var(--white);
  }
  .yh-trio-title {
    font-family: "Noto Serif TC", serif;
    font-size: 28px;
    font-weight: 900;
    color: var(--gold);
    margin-bottom: 8px;
  }
  .yh-trio-en {
    font-family: "Noto Sans TC", sans-serif;
    font-size: 11px;
    letter-spacing: 0.2em;
    opacity: 0.55;
    margin-bottom: 20px;
  }
  .yh-trio-body {
    font-family: "Noto Sans TC", sans-serif;
    font-size: 13px;
    line-height: 2.1;
    opacity: 0.88;
  }
  /* 裝置藝術 */
  .yh-install-section{background:#F8F4EF;padding:100px 48px;}
  .yh-install-inner{max-width:1080px;margin:0 auto;}
  .yh-install-tabs{display:flex;gap:0;border-bottom:1px solid rgba(26,38,64,.15);margin-bottom:36px;}
  .yh-install-tab-btn{flex:1;text-align:center;background:none;border:none;color:rgba(26,38,64,.4);font-family:'Noto Sans TC',sans-serif;font-size:12px;letter-spacing:.22em;padding:12px 16px;cursor:pointer;border-bottom:2px solid transparent;margin-bottom:-1px;transition:color .2s,border-color .2s;}
  .yh-install-tab-btn.active{color:var(--secondary);border-bottom-color:var(--secondary);}
  .yh-install-tab-btn:hover{color:var(--primary);}
  .yh-install-pane{display:none;}
  .yh-install-pane.active{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;}
  .yh-install-card{background:var(--bg);border:1px solid rgba(26,38,64,.08);border-radius:16px;padding:28px 24px;transition:background .25s;}
  .yh-install-card:hover{background:#EDD0C6;}
  .yh-install-num{font-size:10px;letter-spacing:.35em;color:var(--secondary);margin-bottom:10px;font-weight:700;}
  .yh-install-title{font-family:'Noto Serif TC',serif;font-size:17px;font-weight:700;color:var(--primary);line-height:1.45;margin-bottom:14px;}
  .yh-install-school{font-size:11px;letter-spacing:.08em;color:rgba(26,38,64,.5);margin-bottom:6px;}
  .yh-install-location{font-size:12px;color:rgba(26,38,64,.65);line-height:1.6;}
  @media(max-width:768px){
    .yh-install-section{padding:80px 24px;}
    .yh-install-pane.active{display:flex;overflow-x:auto;gap:14px;scroll-snap-type:x mandatory;-webkit-overflow-scrolling:touch;padding-bottom:14px;}
    .yh-install-pane.active::-webkit-scrollbar{display:none;}
    .yh-install-card{flex-shrink:0;width:72vw;scroll-snap-align:start;}
  }

  .yh-schedule {
    background: var(--bg);
    padding: 56px 48px;
  }
  .yh-schedule-img {
    display: block;
    width: 100%;
    max-width: 1080px;
    margin: 0 auto;
    border-radius: 20px;
    box-shadow: 0 8px 48px rgba(55,78,126, 0.14);
  }
  /* Lightbox */
  [data-lb] {
    cursor: zoom-in;
  }
  .yh-lb-overlay {
    display: none;
    position: fixed;
    inset: 0;
    z-index: 9999;
    background: rgba(0, 0, 0, 0.45);
    backdrop-filter: blur(18px);
    -webkit-backdrop-filter: blur(18px);
    overflow: auto;
    -webkit-overflow-scrolling: touch;
  }
  .yh-lb-overlay.open {
    display: block;
  }
  .yh-lb-inner {
    min-height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 60px 16px 40px;
    box-sizing: border-box;
  }
  .yh-lb-overlay .yh-lb-img {
    display: block;
    width: 100%;
    max-width: 960px;
    height: auto;
    touch-action: pan-x pan-y;
    border-radius: 12px;
  }
  .yh-lb-close {
    position: fixed;
    top: 14px;
    right: 14px;
    width: 44px;
    height: 44px;
    background: rgba(255, 255, 255, 0.18);
    border: none;
    border-radius: 50%;
    color: #fff;
    font-size: 20px;
    cursor: pointer;
    z-index: 10000;
    display: flex;
    align-items: center;
    justify-content: center;
    backdrop-filter: blur(4px);
  }
  .yh-lb-close:hover {
    background: rgba(255, 255, 255, 0.3);
  }
  .yh-lb-hint {
    position: fixed;
    bottom: 18px;
    left: 50%;
    transform: translateX(-50%);
    color: rgba(255, 255, 255, 0.45);
    font-size: 11px;
    letter-spacing: 0.14em;
    white-space: nowrap;
    pointer-events: none;
    font-family: "Noto Sans TC", sans-serif;
  }
  .yh-xp {
    background: #F8F4EF;
    padding: 100px 48px;
    position: relative;
    overflow: hidden;
  }
  .yh-xp-inner {
    max-width: 900px;
    margin: 0 auto;
    position: relative;
    z-index: 2;
  }
  .yh-xp-deco {
    position: absolute;
    pointer-events: none;
    z-index: 1;
  }
  @keyframes yh-xp-float {
    0%,
    100% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-14px);
    }
  }
  @keyframes yh-xp-float-r {
    0%,
    100% {
      transform: translateY(0) rotate(4deg);
    }
    50% {
      transform: translateY(-12px) rotate(-3deg);
    }
  }
  .yh-xp-card {
    background: var(--white);
    border-radius: 20px;
    padding: 32px 36px;
    display: flex;
    flex-wrap: wrap;
    gap: 28px;
    align-items: flex-start;
    margin-bottom: 20px;
  }
  .yh-xp-meta {
    flex-shrink: 0;
    min-width: 160px;
  }
  .yh-xp-title {
    font-family: "Noto Serif TC", serif;
    font-size: 20px;
    font-weight: 700;
    color: var(--primary);
    margin-bottom: 8px;
  }
  .yh-xp-date {
    font-family: "Noto Sans TC", sans-serif;
    font-size: 11px;
    font-weight: 700;
    color: var(--white);
    background: var(--secondary);
    border-radius: 50px;
    padding: 3px 12px;
    display: inline-block;
    margin-bottom: 8px;
  }
  .yh-xp-where {
    font-family: "Noto Sans TC", sans-serif;
    font-size: 12px;
    color: #999;
    line-height: 1.9;
  }
  .yh-xp-body {
    flex: 1;
    min-width: 200px;
    font-family: "Noto Sans TC", sans-serif;
    font-size: 14px;
    line-height: 2.1;
    color: #555;
  }
  .yh-xp-perf {
    background: var(--secondary);
    border-radius: 20px;
    padding: 40px;
    margin-top: 16px;
  }
  .yh-xp-perf-row {
    display: flex;
    align-items: flex-start;
    gap: 20px;
    padding: 16px 20px;
    background: rgba(255, 255, 255, 0.12);
    border-radius: 12px;
    margin-bottom: 12px;
  }
  .yh-xp-perf-time {
    font-family: "Noto Sans TC", sans-serif;
    font-weight: 900;
    font-size: 14px;
    color: var(--gold);
    min-width: 110px;
    flex-shrink: 0;
    padding-top: 2px;
  }
  .yh-xp-perf-name {
    font-family: "Noto Serif TC", serif;
    font-size: 17px;
    font-weight: 700;
    color: var(--white);
    margin-bottom: 4px;
  }
  .yh-xp-perf-desc {
    font-family: "Noto Sans TC", sans-serif;
    font-size: 13px;
    color: rgba(255, 255, 255, 0.75);
  }
  .yh-event-info {
    background: var(--surface);
    color: var(--white);
    padding: 100px 48px;
  }
  .yh-event-info-inner {
    max-width: 1080px;
    margin: 0 auto;
  }
  .yh-info-top {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
    margin-bottom: 20px;
  }
  .yh-info-box {
    background: rgba(242, 190, 92, 0.12);
    border: 1px solid rgba(242, 190, 92, 0.3);
    border-radius: 14px;
    padding: 30px 28px;
  }
  .yh-info-box-label {
    font-family: "Noto Sans TC", sans-serif;
    color: var(--gold);
    font-size: 11px;
    letter-spacing: 0.35em;
    margin-bottom: 10px;
  }
  .yh-info-box-value {
    font-family: "Noto Serif TC", serif;
    font-size: 20px;
    font-weight: 700;
    line-height: 1.8;
    color: var(--white);
  }
  .yh-info-box-value span {
    font-family: "Noto Sans TC", sans-serif;
    font-size: 15px;
    font-weight: 400;
    opacity: 0.75;
  }
  .yh-info-bottom {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
  }
  .yh-info-card {
    background: rgba(255, 255, 255, 0.06);
    border-radius: 14px;
    padding: 28px;
  }
  .yh-info-card-label {
    font-family: "Noto Sans TC", sans-serif;
    color: var(--gold);
    font-size: 11px;
    letter-spacing: 0.35em;
    margin-bottom: 14px;
  }
  .yh-info-list {
    display: flex;
    flex-direction: column;
    gap: 10px;
  }
  .yh-info-list-item {
    font-family: "Noto Sans TC", sans-serif;
    display: flex;
    gap: 10px;
    font-size: 13px;
    line-height: 1.8;
    color: var(--white);
  }
  .yh-info-list-num {
    color: var(--secondary);
    flex-shrink: 0;
  }
  .yh-info-plain {
    font-family: "Noto Sans TC", sans-serif;
    font-size: 13px;
    line-height: 2.2;
    opacity: 0.85;
    color: var(--white);
  }
  .yh-reveal.visible {
    animation: yh-fadeUp 0.7s ease forwards;
  }
  @keyframes yh-floatA {
    0%,
    100% {
      transform: translateY(0) rotate(-4deg);
    }
    50% {
      transform: translateY(-22px) rotate(4deg);
    }
  }
  @keyframes yh-floatB {
    0%,
    100% {
      transform: translateY(0) rotate(4deg);
    }
    50% {
      transform: translateY(-18px) rotate(-4deg);
    }
  }
  @keyframes yh-marquee {
    0% {
      transform: translateX(0);
    }
    100% {
      transform: translateX(-50%);
    }
  }
  @keyframes yh-pulse-ring {
    0%,
    100% {
      box-shadow:
        0 0 0 10px rgba(242, 126, 147, 0.18),
        0 0 60px rgba(192, 84, 108, 0.35);
    }
    50% {
      box-shadow:
        0 0 0 18px rgba(242, 126, 147, 0.08),
        0 0 80px rgba(192, 84, 108, 0.22);
    }
  }
  @keyframes yh-fadeUp {
    from {
      opacity: 0;
      transform: translateY(36px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }
  @media (max-width: 900px) {
    .yh-features-grid {
      grid-template-columns: repeat(2, 1fr);
    }
    .yh-hana-teaser-grid {
      grid-template-columns: 1fr;
      gap: 40px;
    }
    .yh-hana-teaser-badge {
      width: 220px;
      height: 220px;
    }
    .yh-hana-teaser-badge img {
      width: 180px !important;
    }
    .yh-digital-xp {
      padding: 80px 20px !important;
    }
    .yh-digital-xp-layout {
      display: block;
    }
    .yh-digital-xp-badge-wrap {
      justify-content: center;
      margin-bottom: -64px;
      position: relative;
      z-index: 3;
    }
    .yh-digital-xp-card {
      padding: 88px 28px 44px;
      text-align: center;
    }
    .yh-trio-grid {
      grid-template-columns: 1fr;
    }
    .yh-info-top,
    .yh-info-bottom {
      grid-template-columns: 1fr;
    }
  }
  @media (max-width: 560px) {
    .yh-features-grid {
      grid-template-columns: 1fr;
    }
    .yh-hero {
      min-height: 0;
    }
    .yh-m-amary {
      top: 52%;
      width: 10%;
      min-width: 0;
    }
    .yh-m-sunf {
      width: 12%;
      min-width: 0;
    }
    .yh-m-lily {
      top: 50%;
      width: 8%;
      min-width: 0;
    }
    .yh-m-lav {
      top: 58%;
      width: 10%;
      min-width: 0;
    }
    .yh-m-blue {
      width: 10%;
      min-width: 0;
    }
    .yh-features,
    .yh-founders,
    .yh-curatorial,
    .yh-schedule,
    .yh-xp,
    .yh-event-info,
    .yh-line-cta,
    [class*="yh-hana"] {
      padding-left: 20px !important;
      padding-right: 20px !important;
    }
    .yh-xp-card {
      gap: 16px;
    }
    .yh-xp-meta {
      min-width: 100%;
    }
    .yh-page-hero{min-height:100svh;padding:0 24px;}
    .yh-page-hero-overlay{background:linear-gradient(180deg,rgba(26,38,64,.85) 0%,rgba(26,38,64,.5) 60%,rgba(26,38,64,.2) 100%);}
    .yh-page-hero-inner{grid-template-columns:1fr;padding-top:110px;padding-bottom:40px;}
    .yh-hero-mascot{justify-content:center;margin-top:8px;}
    .yh-hero-mascot img{width:clamp(160px,55vw,240px);}
    .yh-feat-card {
      padding: 28px 18px;
    }
  }
</style>

<section class="yh-hero">
  <!-- Banner 背景 -->
  <div class="yh-hero-bg"></div>

  <!-- 五朵花吉祥物（位置對應 banner 構圖，動態飄浮） -->
  <img
    class="yh-mascot yh-m-lily"
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E7%99%BE%E5%90%88.png"
    alt=""
  />
  <img
    class="yh-mascot yh-m-sunf"
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%90%91%E6%97%A5%E8%91%B5.png"
    alt=""
  />
  <img
    class="yh-mascot yh-m-amary"
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%AD%A4%E6%8C%BA%E8%8A%B1.png"
    alt=""
  />
  <img
    class="yh-mascot yh-m-lav"
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%96%B0%E8%A1%A3%E8%8D%89.png"
    alt=""
  />
  <img
    class="yh-mascot yh-m-blue"
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%97%8D%E7%8E%AB%E7%91%B0.png"
    alt=""
  />
</section>

<script>
  (function () {
    function _yhInit() {
      if (window._yhDone) return;
      window._yhDone = true;
      const obs = new IntersectionObserver(
        (entries) => {
          entries.forEach((e) => {
            if (e.isIntersecting) {
              e.target.classList.add("visible");
              obs.unobserve(e.target);
            }
          });
        },
        { threshold: 0.12 },
      );
      document.querySelectorAll(".yh-reveal").forEach((el) => obs.observe(el));
      const ms = document.querySelectorAll(".yh-mascot");
      window.addEventListener(
        "scroll",
        () => {
          const y = window.scrollY;
          ms.forEach((m, i) => {
            m.style.transform = `translateY(${y * (i % 2 === 0 ? 0.08 : 0.05)}px)`;
          });
        },
        { passive: true },
      );
    }
    if (document.readyState === "loading")
      document.addEventListener("DOMContentLoaded", _yhInit);
    else _yhInit();
  })();
</script>
```

---

### 元件 2 — Marquee 跑馬燈

```html
<div class="yh-marquee-strip">
  <div class="yh-marquee-inner">
    <span class="yh-marquee-text"
      >2026 鹽夏不夜埕 × 花轟 ✦ 高雄新樂街綠廊 ✦
      開幕式・裝置藝術・踩街遊行・特色市集 ✦ 05.16—05.23 每日 17:00–21:00 ✦
      YANHSIA NIGHT × HANABOMB ✦ 花朵不睡覺 ✦&ensp;</span
    >
    <span class="yh-marquee-text"
      >2026 鹽夏不夜埕 × 花轟 ✦ 高雄新樂街綠廊 ✦
      開幕式・裝置藝術・踩街遊行・特色市集 ✦ 05.16—05.23 每日 17:00–21:00 ✦
      YANHSIA NIGHT × HANABOMB ✦ 花朵不睡覺 ✦&ensp;</span
    >
  </div>
</div>
```

---

### 元件 3 — 花轟 Teaser

```html
<section
  style="background:var(--surface);padding:90px 48px;position:relative;overflow:hidden;"
>
  <div
    style="position:absolute;inset:0;background:url('https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91-20260416T013420Z-3-001/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91/%E8%B3%87%E7%94%A2%20114.png')center/cover;opacity:.05;pointer-events:none;"
  ></div>
  <div
    class="yh-hana-teaser-grid"
    style="max-width:1080px;margin:0 auto;position:relative;z-index:2;"
  >
    <div>
      <h2
        style="font-family:'Noto Serif TC',serif;font-size:clamp(36px,5vw,64px);font-weight:900;color:#fff;line-height:1.1;margin-bottom:20px;"
      >
        以花的綻放<br />回應情緒的<br />張力與流動
      </h2>
      <p
        style="font-family:'Noto Sans TC',sans-serif;font-size:15px;line-height:2.2;color:var(--gray);margin-bottom:36px;max-width:420px;"
      >
        2026
        鹽夏不夜埕年度主題展覽。開幕式・踩街遊行・裝置藝術・特色市集，用八天把高雄的夏夜染得更鮮豔。
      </p>
      <a href="/hanabomb" class="yh-hana-btn">進入花轟世界 →</a>
    </div>
    <div style="display:flex;justify-content:center;align-items:center;">
      <div style="position:relative;">
        <div class="yh-hana-teaser-badge">
          <img
            src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%8A%B1%E8%BD%9F.png"
            style="width:260px;"
            alt="花轟"
          />
        </div>
        <img
          src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%90%91%E6%97%A5%E8%91%B5.png"
          style="position:absolute;top:-24px;right:-16px;width:72px;animation:yh-floatB 3.5s ease-in-out infinite;"
          alt=""
        />
        <img
          src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%96%B0%E8%A1%A3%E8%8D%89.png"
          style="position:absolute;bottom:-12px;left:-12px;width:62px;animation:yh-floatA 4s ease-in-out infinite .5s;"
          alt=""
        />
        <img
          src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E7%99%BE%E5%90%88.png"
          style="position:absolute;top:40%;right:-52px;width:50px;animation:yh-floatA 3.8s ease-in-out infinite 1s;"
          alt=""
        />
      </div>
    </div>
  </div>
</section>
```

---

### 元件 4 — 四大特色

```html
<section class="yh-features">
  <div style="max-width:1080px;margin:0 auto;">
    <div style="text-align:center;margin-bottom:60px;">
      <div class="yh-section-label">FEATURES</div>
      <h2 class="yh-section-title">鹽夏四大特色｜Features</h2>
    </div>
    <div class="yh-features-grid">
      <div class="yh-feat-card white">
        <img
          src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%96%B0%E8%A1%A3%E8%8D%89.png"
          alt=""
        />
        <div class="yh-feat-num">01</div>
        <div class="yh-feat-title">裝置藝術</div>
        <div class="yh-feat-desc">
          鹽埕埕區展示一系列光影裝置藝術作品，合作來源包含中山大學「跨領域創新專選（一）」課程學生、高雄高中生科技藝術競賽，以及社區共創工作坊，共同點亮鹽埕夜夜。
        </div>
      </div>
      <div class="yh-feat-card dark-red">
        <img
          src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%AD%A4%E6%8C%BA%E8%8A%B1.png"
          alt=""
        />
        <div class="yh-feat-num">02</div>
        <div class="yh-feat-title">表演藝術</div>
        <div class="yh-feat-desc">
          邀請高雄在地劇團、街頭藝人等表演團體，在街廊進行演出，沈浸在藝術表演與歷史文化交融出的鹽埕記憶。
        </div>
      </div>
      <div class="yh-feat-card white">
        <img
          src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%90%91%E6%97%A5%E8%91%B5.png"
          alt=""
        />
        <div class="yh-feat-num">03</div>
        <div class="yh-feat-title">特色市集</div>
        <div class="yh-feat-desc">
          在展期的跨週六，邀請高雄在地商家或是學生創業品牌，配合每年的不同主題企劃，打造出獨一無二的鹽夏特色市集。
        </div>
      </div>
      <div class="yh-feat-card primary">
        <img
          src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E7%99%BE%E5%90%88.png"
          alt=""
        />
        <div class="yh-feat-num">04</div>
        <div class="yh-feat-title">周邊活動</div>
        <div class="yh-feat-desc">
          舉辦「前導工作坊」作為策展的暖身，與鹽埕在地企業合作推出各種「鹽夏限定活動」，活動當日則有美食、歷史等導覽。
        </div>
      </div>
    </div>
  </div>
</section>
```

---

### 元件 5 — 介紹影片

```html
<section class="yh-founders">
  <div
    style="max-width:800px;margin:0 auto;position:relative;z-index:2;text-align:center;"
  >
    <div class="yh-video-label">FILM</div>
    <h3 class="yh-video-title">介紹影片</h3>
    <div class="yh-video-wrap">
      <iframe
        src="https://www.youtube.com/embed/25naLda_-jo"
        title="介紹影片"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        allowfullscreen
      ></iframe>
    </div>
  </div>
</section>
```

---

### 元件 6 — LINE CTA

```html
<section class="yh-line-cta">
  <div style="max-width:600px;margin:0 auto;">
    <div class="yh-section-label" style="color:rgba(55,78,126,.55);">
      OFFICIAL LINE
    </div>
    <h2 class="yh-line-title">加入【鹽夏不夜埕】<br />官方 LINE 好友</h2>
    <p class="yh-line-sub">
      加入 LINE
      好友集點趣！提升觀展體驗，第一時間掌握花轟最新消息、活動通知與限定優惠。
    </p>
    <a
      href="https://line.me/R/ti/p/@235chemh"
      class="yh-cta-link"
      style="background:#243554;color:#fff;"
      >加入 LINE 好友 →</a
    >
  </div>
</section>
```

---

### 元件 7 — Footer

```html
<div
  style="height:120px;background:#F2D9D0 url('https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%8F%AF%E6%84%9B%E7%9A%84%E8%8D%89%E5%8F%A2.png') center bottom/auto 100% no-repeat;"
></div>
<footer>
  <div class="yh-footer-pre">
    <div class="yh-footer-pre-title">
      2026 鹽夏不夜埕 × 花轟<br />5/16—5/23 新樂街綠廊見！
    </div>
    <div class="yh-footer-pre-sub">
      裝置藝術・表演藝術・特色市集・周邊活動　免費入場
    </div>
    <a href="/hanabomb" class="yh-footer-pre-btn">了解更多 →</a>
  </div>
  <div
    class="yh-footer-city"
    style="background:var(--bg);padding:56px 48px 48px;"
  >
    <div style="max-width:860px;margin:0 auto;">
      <div style="text-align:center;margin-bottom:24px;">
        <div
          style="font-size:11px;letter-spacing:.45em;color:var(--secondary);margin-bottom:8px;font-family:'Noto Sans TC',sans-serif;font-weight:700;"
        >
          MAP 活動地圖
        </div>
        <h2
          style="font-family:'Noto Serif TC',serif;font-size:clamp(24px,3vw,36px);font-weight:900;color:var(--primary);line-height:1.2;"
        >
          花轟 × 鹽埕地圖
        </h2>
      </div>
      <img
        src="https://elsonyeh.github.io/yanhsia-official-website/map.png"
        alt="活動地圖"
        style="display:block;width:100%;box-shadow:0 8px 40px rgba(55,78,126,.12);"
        data-lb
      />
    </div>
  </div>
  <div class="yh-footer-bottom">
    <div class="yh-footer-logo">
      <img
        src="https://elsonyeh.github.io/yanhsia-official-website/%E9%B9%BD%E5%A4%8Flogo%E5%80%91-20260416T013432Z-3-001/%E9%B9%BD%E5%A4%8Flogo%E5%80%91/%E8%B3%87%E7%94%A2%202.png"
        alt="鹽夏不夜埕"
      />
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

### 元件 — Lightbox（首頁最後一個 HTML 元件底部加入）

> 地圖點擊後放大。在首頁最後一個 HTML 元件末尾加入此段。

```html
<div class="yh-lb-overlay" id="yh-lb">
  <button class="yh-lb-close" id="yh-lb-close">✕</button>
  <div class="yh-lb-inner">
    <img class="yh-lb-img" id="yh-lb-img" src="" alt="" />
  </div>
  <div class="yh-lb-hint">雙指縮放・點擊空白處關閉</div>
</div>
<script>
  (function () {
    var lb = document.getElementById("yh-lb"),
      lbImg = document.getElementById("yh-lb-img");
    function lbOpen(src) {
      lbImg.src = src;
      lb.classList.add("open");
      document.body.style.overflow = "hidden";
      lb.scrollTop = 0;
    }
    function lbClose() {
      lb.classList.remove("open");
      document.body.style.overflow = "";
    }
    document.querySelectorAll("[data-lb]").forEach(function (el) {
      el.addEventListener("click", function () {
        lbOpen(el.src);
      });
    });
    lb.addEventListener("click", function (e) {
      if (e.target !== lbImg) lbClose();
    });
    document.addEventListener("keydown", function (e) {
      if (e.key === "Escape") lbClose();
    });
  })();
</script>
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
  <div class="yh-hero-deco-char">花</div>

  <div class="yh-page-hero-inner">
    <!-- 左：文字 -->
    <div>
      <div class="yh-page-eyebrow">2026 YANHSIA NIGHT × HANABOMB</div>
      <div class="yh-page-title">花轟</div>
      <div class="yh-hero-title-en">Hanabomb</div>
      <div class="yh-hero-rule"></div>
      <div class="yh-page-sub">以花的綻放<br>回應情緒的張力與流動</div>
      <div class="yh-hero-meta">
        <span>5.16 &thinsp;/&thinsp; 5.17 &thinsp;/&thinsp; 5.23</span>
        <span class="yh-hero-meta-sep">·</span>
        <span>高雄 鹽埕</span>
      </div>
    </div>

    <!-- 右：吉祥物 -->
    <div class="yh-hero-mascot">
      <img
        src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%8A%B1%E8%BD%9F.png"
        alt="花轟"
      />
    </div>
  </div>

  <div class="yh-hero-scroll">SCROLL &darr;</div>
</section>

<script>
  if (!window._yhObsInit) {
    window._yhObsInit = true;
    const _obs = new IntersectionObserver(
      (entries) => {
        entries.forEach((e) => {
          if (e.isIntersecting) {
            e.target.classList.add("visible");
            _obs.unobserve(e.target);
          }
        });
      },
      { threshold: 0.12 },
    );
    document.querySelectorAll(".yh-reveal").forEach((el) => _obs.observe(el));
  }
</script>
```

---

### 元件 2 — 策展論述

```html
<section class="yh-curatorial">
  <div class="yh-curatorial-inner">
    <div class="yh-section-label">CURATORIAL STATEMENT 策展論述</div>
    <h2 class="yh-section-title" style="color:var(--white);margin-bottom:28px;">
      花の宣言
    </h2>
    <div class="yh-quote-block">
      《花轟》以花的綻放，回應情緒的張力與流動。正如花朵終將撐開花萼、露出真實的姿態，情緒的包裝紙在拆封的瞬間被釋放與凝視，以當下最真實的樣貌綻放。
    </div>
    <div class="yh-sub-text">
      鹽埕將化身為一座「花園」，情緒在巷弄間自然生長；觀眾在花園中自由穿梭。透過「呼吸、蔓延、共生」三大面向，體驗情緒從個體到他者，從他者到群體網絡相互影響、轉化與共存的過程。
    </div>
    <div class="yh-note-text">
      《花轟》邀請觀眾進入這座花園，靠近那些正在發生的情緒。
    </div>
    <div class="yh-trio-grid">
      <div class="yh-trio-card" style="background:#C0546C;">
        <div class="yh-trio-title">呼吸</div>
        <div class="yh-trio-en">BREATHE</div>
        <div class="yh-trio-body">
          綻放前，個體在每一次吸吐中積累著綻放的能量。初來乍到的資訊在身體裡隱隱作祟，隨著個體微乎其微的擴張和收縮，為綻放蓄力。含苞待放的每一刻，這些自然被忽視的過程，不只是綻放的前奏，更是在觸碰內心的瞬間，覺察自我更深層的情緒。
        </div>
      </div>
      <div class="yh-trio-card" style="background:#CB5661;">
        <div class="yh-trio-title">蔓延</div>
        <div class="yh-trio-en">SPREAD</div>
        <div class="yh-trio-body">
          綻放的瞬間，花粉隨風飄散。允許情緒以最真實的樣貌綻放，肆意宣示著屬於自己的氣味、顏色、質感，表達著自我。盛開的情緒經由單向的釋放，將既有的能量於個體間傳遞與承接，在感知、轉化、擴散之中，不斷反覆。
        </div>
      </div>
      <div class="yh-trio-card" style="background:#5B7BA6;">
        <div class="yh-trio-title">共生</div>
        <div class="yh-trio-en">SYMBIOSIS</div>
        <div class="yh-trio-body">
          綻放後，個體、他者與環境彼此纏繞、相互依偎，在不斷的交互與回響間，重新定義彼此存在的方式。「共生」之時，情緒與世界產生共振，在這緩緩運行的生態圈內，引領我們感知、察覺並回應生活的宏觀脈絡，重新理解自己與周遭的連結。
        </div>
      </div>
    </div>
  </div>
</section>
```

---

### 元件 3 — 裝置藝術展演

> 三個 Tab（呼吸/蔓延/共生），手機為橫向滑動。JS 放在元件末尾。

```html
<section class="yh-install-section">
  <div class="yh-install-inner">
    <div style="margin-bottom:40px;">
      <div class="yh-section-label" style="color:var(--secondary);">INSTALLATION ART</div>
      <h2 class="yh-section-title" style="color:var(--primary);">裝置藝術展演</h2>
    </div>
    <div class="yh-install-tabs">
      <button class="yh-install-tab-btn active" data-itab="breathe">呼吸 BREATHE</button>
      <button class="yh-install-tab-btn" data-itab="spread">蔓延 SPREAD</button>
      <button class="yh-install-tab-btn" data-itab="coexist">共生 COEXIST</button>
    </div>

    <!-- 呼吸 -->
    <div class="yh-install-pane active" id="yh-install-breathe">
      <div class="yh-install-card"><div class="yh-install-num">A1</div><div class="yh-install-title">當我聽見我</div><div class="yh-install-school">鳳新高中</div><div class="yh-install-location">光榮國小外空地（三角形區域）</div></div>
      <div class="yh-install-card"><div class="yh-install-num">A2</div><div class="yh-install-title">一瞬花綻</div><div class="yh-install-school">中山大學</div><div class="yh-install-location">光榮國小陶壺後空地</div></div>
      <div class="yh-install-card"><div class="yh-install-num">A3</div><div class="yh-install-title">炎赫</div><div class="yh-install-school">中山大學</div><div class="yh-install-location">千葉素食館 2F</div></div>
      <div class="yh-install-card"><div class="yh-install-num">A4</div><div class="yh-install-title">關於情緒的棲息方式</div><div class="yh-install-school">中山大學 × 鹽埕國小</div><div class="yh-install-location">國小國中外草地（綠廊）</div></div>
      <div class="yh-install-card"><div class="yh-install-num">A5</div><div class="yh-install-title">流金歲月</div><div class="yh-install-school">中山大學</div><div class="yh-install-location">光榮國小建築物空隙</div></div>
    </div>

    <!-- 蔓延 -->
    <div class="yh-install-pane" id="yh-install-spread">
      <div class="yh-install-card"><div class="yh-install-num">B1</div><div class="yh-install-title">花落成流</div><div class="yh-install-school">中山大學</div><div class="yh-install-location">欄杆旁樹木</div></div>
      <div class="yh-install-card"><div class="yh-install-num">B2</div><div class="yh-install-title">情緒共振實驗室</div><div class="yh-install-school">鹽埕國中</div><div class="yh-install-location">鹽埕國中外牆花圃</div></div>
      <div class="yh-install-card"><div class="yh-install-num">B3</div><div class="yh-install-title">這裡有很多按鈕</div><div class="yh-install-school">中山大學</div><div class="yh-install-location">克朗德美術館騎樓</div></div>
      <div class="yh-install-card"><div class="yh-install-num">B4</div><div class="yh-install-title">Overblown 盛放失序—花花失控中！</div><div class="yh-install-school">中山大學 × 鹽埕國小</div><div class="yh-install-location">巴黎花紙行</div></div>
      <div class="yh-install-card"><div class="yh-install-num">B5</div><div class="yh-install-title">花鹽</div><div class="yh-install-school">前鎮高中</div><div class="yh-install-location">雍之川流古董師交易館</div></div>
    </div>

    <!-- 共生 -->
    <div class="yh-install-pane" id="yh-install-coexist">
      <div class="yh-install-card"><div class="yh-install-num">C1</div><div class="yh-install-title">聽見花開：聲與光的共存</div><div class="yh-install-school">中山大學</div><div class="yh-install-location">沙地里空屋一樓</div></div>
      <div class="yh-install-card"><div class="yh-install-num">C2</div><div class="yh-install-title">鹽晶．緣進</div><div class="yh-install-school">道明中學</div><div class="yh-install-location">老房間（里長）</div></div>
      <div class="yh-install-card"><div class="yh-install-num">C3</div><div class="yh-install-title">起家 Khí-ke：紮根</div><div class="yh-install-school">中山高中</div><div class="yh-install-location">老房間（居民）</div></div>
      <div class="yh-install-card"><div class="yh-install-num">C4</div><div class="yh-install-title">聲綻</div><div class="yh-install-school">中山大學</div><div class="yh-install-location">福容飯店門口</div></div>
      <div class="yh-install-card"><div class="yh-install-num">C5</div><div class="yh-install-title">日常的封存</div><div class="yh-install-school">中山大學</div><div class="yh-install-location">岸等</div></div>
    </div>
  </div>
</section>
<script>
(function(){
  document.querySelectorAll('.yh-install-tab-btn').forEach(function(btn){
    btn.addEventListener('click',function(){
      document.querySelectorAll('.yh-install-tab-btn').forEach(function(b){b.classList.remove('active');});
      document.querySelectorAll('.yh-install-pane').forEach(function(p){p.classList.remove('active');});
      btn.classList.add('active');
      document.getElementById('yh-install-'+btn.dataset.itab).classList.add('active');
    });
  });
})();
</script>
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
      <img
        src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%96%B0%E8%A1%A3%E8%8D%89.png"
        alt=""
      />
      <div class="yh-feat-num">01</div>
      <div class="yh-feat-title">開幕式</div>
      <div class="yh-feat-desc">
        5/16（六）17:00–19:00，主舞台。揭開 2026
        鹽夏不夜埕序幕，同步頒發高雄高中生科技藝術競賽獎項，邀請觀眾一同感受盛夏慶典的到來。
      </div>
    </div>
    <div class="yh-feat-card dark-red">
      <img
        src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%AD%A4%E6%8C%BA%E8%8A%B1.png"
        alt=""
      />
      <div class="yh-feat-num">02</div>
      <div class="yh-feat-title">踩街遊行</div>
      <div class="yh-feat-desc">
        5/16（六）19:00–21:00，主舞台 /
        整個街廊。結合高中時裝作品展與在地小學社團表演，攜手手工共創藝術，邀請大家一同花行上街！
      </div>
    </div>
    <div class="yh-feat-card white">
      <img
        src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%90%91%E6%97%A5%E8%91%B5.png"
        alt=""
      />
      <div class="yh-feat-num">03</div>
      <div class="yh-feat-title">裝置藝術</div>
      <div class="yh-feat-desc">
        5/16–5/23，每日 19:30–20:30
        作品導覽，服務台出發。中山大學生、高中科技競賽與社區共創，以「呼吸・蔓延・共生」呈現情緒綻放的旅程。
      </div>
    </div>
    <div class="yh-feat-card primary">
      <img
        src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E7%99%BE%E5%90%88.png"
        alt=""
      />
      <div class="yh-feat-num">04</div>
      <div class="yh-feat-title">特色市集</div>
      <div class="yh-feat-desc">
        5/16–5/23，每日
        17:00–21:00，新樂街大智路口至愛文店口路段。花圃般的創意市集，飲食、手作、花香一次擁有。
      </div>
    </div>
  </div>
</section>
```

---

### 元件 5 — 數位體驗

```html
<section class="yh-digital-xp">
  <div
    style="position:absolute;inset:0;background:url('https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91-20260416T013420Z-3-001/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91/%E8%B3%87%E7%94%A2%20114.png')center/cover;opacity:.06;pointer-events:none;"
  ></div>

  <!-- 浮動花朵裝飾 -->
  <img
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%90%91%E6%97%A5%E8%91%B5.png"
    style="position:absolute;top:32px;left:6%;width:80px;opacity:.75;animation:yh-floatB 3.8s ease-in-out infinite;pointer-events:none;"
    alt=""
  />
  <img
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E7%99%BE%E5%90%88.png"
    style="position:absolute;bottom:40px;left:4%;width:70px;opacity:.7;animation:yh-floatA 4.2s ease-in-out infinite .6s;pointer-events:none;"
    alt=""
  />
  <img
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%AD%A4%E6%8C%BA%E8%8A%B1.png"
    style="position:absolute;top:24px;right:5%;width:72px;opacity:.75;animation:yh-floatA 3.5s ease-in-out infinite .3s;pointer-events:none;"
    alt=""
  />
  <img
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%96%B0%E8%A1%A3%E8%8D%89.png"
    style="position:absolute;bottom:36px;right:6%;width:66px;opacity:.7;animation:yh-floatB 4s ease-in-out infinite 1s;pointer-events:none;"
    alt=""
  />

  <div class="yh-digital-xp-inner">
    <div class="yh-digital-xp-layout">
      <!-- 左：吉祥物（電腦版）/ 上方溢出（手機版） -->
      <div class="yh-digital-xp-badge-wrap">
        <div class="yh-digital-xp-badge">
          <img
            src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%8A%B1%E8%BD%9F.png"
            alt="花轟"
          />
        </div>
      </div>

      <!-- 右（電腦）/ 下（手機）：白色卡片 -->
      <div class="yh-digital-xp-card">
        <div
          style="font-size:11px;letter-spacing:.45em;color:var(--secondary);margin-bottom:12px;font-family:'Noto Sans TC',sans-serif;font-weight:700;"
        >
          DIGITAL EXPERIENCE 數位體驗
        </div>
        <h2
          style="font-family:'Noto Serif TC',serif;font-size:clamp(24px,3vw,36px);font-weight:900;color:var(--primary);margin-bottom:16px;line-height:1.2;"
        >
          埕花｜情緒解籤 × 花語體驗
        </h2>
        <p
          style="font-family:'Noto Sans TC',sans-serif;font-size:15px;line-height:2.1;color:rgba(55,78,126,.65);"
        >
          不知從何逛起？網站透過面部識別，即時捕捉你的表情並解讀情緒，轉化為專屬花語祝福卡，點擊花攤獲得路線指引。花語卡中還藏有鹽夏的神秘小驚喜，等你來發現屬於自己的花朵緣分。
        </p>
        <a
          href="https://drawing-flower-fortunes.vercel.app/"
          target="_blank"
          class="yh-digital-xp-btn"
          >立即體驗 →</a
        >
      </div>
    </div>
  </div>
</section>
```

---

### 元件 6 — 展覽資訊

```html
<section class="yh-event-info" style="position:relative;overflow:hidden;">
  <div
    style="position:absolute;right:-80px;bottom:40px;opacity:.06;pointer-events:none;z-index:0;transform:rotate(-15deg);"
  >
    <img
      src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E8%8A%B1%E8%BD%9F.png"
      alt=""
      style="width:380px;"
    />
  </div>
  <div class="yh-event-info-inner" style="position:relative;z-index:1;">
    <div style="text-align:center;margin-bottom:56px;">
      <div class="yh-section-label">EVENT INFO 展覽資訊</div>
      <h2 class="yh-section-title" style="color:var(--white);">活動資訊</h2>
      <div
        style="width:40px;height:3px;background:var(--gold);margin:20px auto 0;border-radius:2px;"
      ></div>
    </div>
    <div
      style="display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:20px;margin-bottom:20px;"
    >
      <div class="yh-info-box">
        <div class="yh-info-box-label">活動時間</div>
        <div class="yh-info-box-value">
          2026 / 5.16 — 5.23<br /><span>每日 17:00 – 21:00</span>
        </div>
      </div>
      <div class="yh-info-box">
        <div class="yh-info-box-label">活動地點</div>
        <div class="yh-info-box-value">
          新樂街綠廊<br /><span>大智路 – 大成街路段</span>
        </div>
      </div>
      <div
        class="yh-info-box"
        style="background:rgba(242,190,92,.18);border-color:rgba(242,190,92,.6);"
      >
        <div class="yh-info-box-label">入場費用</div>
        <div class="yh-info-box-value" style="color:var(--gold);">
          全程免費<br /><span style="color:rgba(255,255,255,.7);"
            >Free Admission</span
          >
        </div>
      </div>
    </div>
    <div class="yh-info-bottom">
      <div style="display:flex;flex-direction:column;gap:16px;">
        <div class="yh-info-card">
          <div class="yh-info-card-label">主辦單位</div>
          <div class="yh-info-list">
            <div class="yh-info-list-item">
              <span class="yh-info-list-num">①</span>國立中山大學
              USR「鹽埕創意街區實驗室計畫」
            </div>
            <div class="yh-info-list-item">
              <span class="yh-info-list-num">②</span
              >高教深耕「以社會設計、社會策展與跨域創新打造幸福鹽埕」計畫
            </div>
            <div class="yh-info-list-item">
              <span class="yh-info-list-num">③</span
              >國立中山大學 人文暨科技跨領域學士學位學程
            </div>
          </div>
        </div>
        <div class="yh-info-card">
          <div class="yh-info-card-label">共同主辦</div>
          <div class="yh-info-plain">鹽埕區公所</div>
        </div>
        <div class="yh-info-card">
          <div class="yh-info-card-label">協辦單位</div>
          <div class="yh-info-plain">
            育仁里里長辦公室・光明里里長辦公室・南端里里長辦公室・沙地里里長辦公室<br />鹽埕國中・鹽埕國小・光榮國小・忠孝國小<br />揚帆主婦社・微熟成文創有限公司
          </div>
        </div>
      </div>
      <div style="display:flex;flex-direction:column;gap:16px;">
        <div class="yh-info-card">
          <div class="yh-info-card-label">贊助單位</div>
          <div class="yh-info-list">
            <div class="yh-info-list-item">
              <span class="yh-info-list-num">①</span>財團法人瑞儀教育基金會
            </div>
            <div class="yh-info-list-item">
              <span class="yh-info-list-num">②</span>翰品酒店 高雄
            </div>
            <div class="yh-info-list-item">
              <span class="yh-info-list-num">③</span>福容大飯店 高雄
            </div>
            <div class="yh-info-list-item">
              <span class="yh-info-list-num">④</span>台灣福興工業股份有限公司
            </div>
            <div class="yh-info-list-item">
              <span class="yh-info-list-num">⑤</span
              >南區社會情緒學習與教育創新中心
            </div>
          </div>
        </div>
        <div class="yh-info-card">
          <div class="yh-info-card-label">交通資訊</div>
          <div class="yh-info-list">
            <div class="yh-info-list-item">
              <svg width="26" height="26" viewBox="0 0 26 26" style="flex-shrink:0;vertical-align:middle;" xmlns="http://www.w3.org/2000/svg">
                <circle cx="13" cy="13" r="13" fill="#5B7BA6"/>
                <rect x="7.5" y="6" width="11" height="8.5" rx="2.2" fill="white"/>
                <rect x="9.5" y="8" width="2.5" height="2.2" rx="0.8" fill="#5B7BA6"/>
                <rect x="14" y="8" width="2.5" height="2.2" rx="0.8" fill="#5B7BA6"/>
                <rect x="7.5" y="11.5" width="11" height="0.8" fill="#5B7BA6" opacity="0.25"/>
                <rect x="9.5" y="14.5" width="2" height="4" rx="1" fill="white"/>
                <rect x="14.5" y="14.5" width="2" height="4" rx="1" fill="white"/>
                <rect x="7.5" y="14" width="11" height="1.2" rx="0.6" fill="white" opacity="0.55"/>
              </svg>
              捷運鹽埕埔站（R9）步行約 5 分鐘
            </div>
            <div class="yh-info-list-item">
              <svg width="26" height="26" viewBox="0 0 26 26" style="flex-shrink:0;vertical-align:middle;" xmlns="http://www.w3.org/2000/svg">
                <circle cx="13" cy="13" r="13" fill="#C7A4C3"/>
                <rect x="4.5" y="7.5" width="17" height="9" rx="2.2" fill="white"/>
                <rect x="6.5" y="9.5" width="4" height="2.8" rx="1" fill="#C7A4C3"/>
                <rect x="15.5" y="9.5" width="4" height="2.8" rx="1" fill="#C7A4C3"/>
                <rect x="12" y="9.5" width="0.8" height="2.8" fill="#C7A4C3" opacity="0.3"/>
                <rect x="4.5" y="14.5" width="17" height="1.2" fill="#C7A4C3" opacity="0.2"/>
                <circle cx="8.5" cy="18.2" r="2.2" fill="white"/>
                <circle cx="17.5" cy="18.2" r="2.2" fill="white"/>
              </svg>
              公車 新樂街站、鹽埕區公所站
            </div>
            <div class="yh-info-list-item">
              <svg width="26" height="26" viewBox="0 0 26 26" style="flex-shrink:0;vertical-align:middle;" xmlns="http://www.w3.org/2000/svg">
                <circle cx="13" cy="13" r="13" fill="#E9ABAB"/>
                <text x="13" y="18.5" text-anchor="middle" font-family="Arial, sans-serif" font-size="17" font-weight="900" fill="#243554">P</text>
              </svg>
              鹽埕地下停車場、哈瑪星停車場
            </div>
          </div>
        </div>
      </div>
    </div>
    <div style="text-align:center;margin-top:44px;">
      <a
        href="https://maps.google.com/?q=高雄市鹽埕區新樂街"
        target="_blank"
        style="display:inline-block;padding:13px 40px;border:1px solid rgba(242,190,92,.45);color:var(--gold);text-decoration:none;font-family:'Noto Sans TC',sans-serif;font-size:14px;letter-spacing:.1em;border-radius:50px;"
        >📍 查看活動地圖</a
      >
    </div>
  </div>
</section>
```

---

### 元件 7 — 活動排程

> 背景淡桃色 `var(--bg)`，四邊留白，圖片圓角加陰影，點擊圖片可放大（Lightbox）。

```html
<section class="yh-schedule">
  <div style="text-align:center;margin-bottom:28px;">
    <div class="yh-section-label">SCHEDULE</div>
    <h2 class="yh-section-title">活動排程</h2>
  </div>
  <img
    src="https://elsonyeh.github.io/yanhsia-official-website/手冊時刻表.png"
    alt="活動排程"
    class="yh-schedule-img"
    data-lb
  />
</section>
```

---

### 元件 7b — 鹽夏專屬體驗

> 背景 `var(--bg)`，列出所有專屬活動卡片 + 表演活動區塊。

```html
<section class="yh-xp">
  <img
    class="yh-xp-deco"
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91-20260416T013420Z-3-001/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91/%E8%B3%87%E7%94%A2%20114.png"
    alt=""
    style="inset:0;width:100%;height:100%;object-fit:cover;opacity:.09;"
  />
  <img
    class="yh-xp-deco"
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91-20260416T013420Z-3-001/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91/%E8%B3%87%E7%94%A2%2096.png"
    alt=""
    style="top:56px;left:28px;width:72px;opacity:.7;animation:yh-xp-float-r 3.6s ease-in-out infinite;"
  />
  <img
    class="yh-xp-deco"
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91-20260416T013420Z-3-001/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91/%E8%B3%87%E7%94%A2%20105.png"
    alt=""
    style="top:48px;right:36px;width:64px;opacity:.75;animation:yh-xp-float 4s ease-in-out infinite .5s;"
  />
  <img
    class="yh-xp-deco"
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91-20260416T013420Z-3-001/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91/%E8%B3%87%E7%94%A2%20109.png"
    alt=""
    style="top:156px;right:62px;width:44px;opacity:.6;animation:yh-xp-float-r 3s ease-in-out infinite 1.2s;"
  />
  <img
    class="yh-xp-deco"
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91-20260416T013420Z-3-001/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91/%E8%B3%87%E7%94%A2%20101.png"
    alt=""
    style="top:42%;left:12px;width:62px;opacity:.55;animation:yh-xp-float 4.2s ease-in-out infinite .3s;"
  />
  <img
    class="yh-xp-deco"
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91-20260416T013420Z-3-001/%E9%BB%9E%E7%B6%B4%E7%89%A9%E5%80%91/%E8%B3%87%E7%94%A2%20113.png"
    alt=""
    style="top:48%;right:10px;width:72px;opacity:.6;animation:yh-xp-float-r 3.8s ease-in-out infinite .8s;"
  />
  <img
    class="yh-xp-deco"
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%AD%A4%E6%8C%BA%E8%8A%B1.png"
    alt=""
    style="bottom:-24px;left:-16px;width:148px;opacity:.45;"
  />
  <img
    class="yh-xp-deco"
    src="https://elsonyeh.github.io/yanhsia-official-website/%E9%BB%9E%E7%B6%B4%E7%89%A9/%E5%90%91%E6%97%A5%E8%91%B5.png"
    alt=""
    style="bottom:-8px;right:-8px;width:128px;opacity:.4;transform:scaleX(-1);"
  />
  <div class="yh-xp-inner">
    <div style="text-align:center;margin-bottom:56px;">
      <div class="yh-section-label">EXCLUSIVE EXPERIENCE</div>
      <h2 class="yh-section-title">鹽夏專屬體驗</h2>
    </div>

    <div class="yh-xp-card">
      <div class="yh-xp-meta">
        <div class="yh-xp-title">情緒花粉投遞站</div>
        <div class="yh-xp-date">5/16 · 17</div>
        <div class="yh-xp-where">
          17:00–21:00<br />5/16 服務台<br />5/17 主舞台<br />移動式投遞站
        </div>
      </div>
      <div class="yh-xp-body">
        不只是分享，還能被演出來？透過情緒花粉投遞站把想分享的事、想大喊的話，傳達出去吧！投遞的回覆將成為《開港來花轟》喜劇演出題材！
      </div>
    </div>

    <div class="yh-xp-card">
      <div class="yh-xp-meta">
        <div class="yh-xp-title">花舞之際</div>
        <div class="yh-xp-date">5/16</div>
        <div class="yh-xp-where">17:00–17:30<br />主舞台</div>
      </div>
      <div class="yh-xp-body">
        現場舉辦呼啦舞互動演出！本活動與「快樂藝術空間」合作，帶領「鹽埕老人活動站」長輩舞動鹽埕活力。
      </div>
    </div>

    <div class="yh-xp-card">
      <div class="yh-xp-meta">
        <div class="yh-xp-title">花轟時裝秀</div>
        <div class="yh-xp-date">5/16</div>
        <div class="yh-xp-where">18:40–19:00<br />主舞台</div>
      </div>
      <div class="yh-xp-body">
        小學生模特兒雲集！鹽埕國小與國立中山大學劇藝系服裝設計組學生共同創作服飾，並在時裝秀中由小學生走上秀台，展示共創服飾！
      </div>
    </div>

    <div class="yh-xp-card">
      <div class="yh-xp-meta">
        <div class="yh-xp-title">開港來花轟</div>
        <div class="yh-xp-date">5/17</div>
        <div class="yh-xp-where">17:00–18:30<br />19:30–21:00<br />主舞台</div>
      </div>
      <div class="yh-xp-body">
        高雄在地喜劇品牌——喜劇開港，透過觀眾互動創作即興喜劇，帶來充滿驚喜的《花轟》演出！
      </div>
    </div>

    <div class="yh-xp-card">
      <div class="yh-xp-meta">
        <div class="yh-xp-title">聽！花兒在說什麼？</div>
        <div class="yh-xp-date">5/17</div>
        <div class="yh-xp-where">18:30–19:30<br />鹽埕國中大會議室</div>
      </div>
      <div class="yh-xp-body">
        以鋼琴三重奏與弦樂重奏，將指尖音符化作初夏花語。共賞一場細膩優雅、如花綻放的室內樂饗宴。
      </div>
    </div>

    <div class="yh-xp-card">
      <div class="yh-xp-meta">
        <div class="yh-xp-title">
          花聚共感餐桌<br /><span style="font-size:12px;color:var(--secondary);"
            >邀請制</span
          >
        </div>
        <div class="yh-xp-date">5/23</div>
        <div class="yh-xp-where">17:00–19:30<br />市集互動區</div>
      </div>
      <div class="yh-xp-body">
        以食物為入口、故事為情感、情緒為核心，青銀共食的體驗活動。邀請翰品酒店、在地店家、民眾一同享用暖心美食。
      </div>
    </div>

    <div class="yh-xp-card">
      <div class="yh-xp-meta">
        <div class="yh-xp-title">從手機至 AI：數位時代鹽埕長輩的情緒故事</div>
        <div class="yh-xp-date">5/16 · 17 · 23</div>
        <div class="yh-xp-where">17:00–21:00<br />克朗德美術館</div>
      </div>
      <div class="yh-xp-body">
        本展覽由中山大學《數位文化與人類學：理論與實踐》課程同學策劃：透過訪談與工作坊，深入鹽埕區老人活動站實地調查，探討手機等數位設備如何影響了在地長輩們的日常生活與社交活動，進而成為牽動情緒的重要載體，也將探討長輩面對
        AI 發展的複雜情緒與隱藏期待。
      </div>
    </div>

    <div class="yh-xp-perf">
      <div style="margin-bottom:28px;">
        <div
          style="font-family:'Noto Sans TC',sans-serif;font-size:11px;letter-spacing:.4em;color:rgba(255,255,255,.6);margin-bottom:6px;"
        >
          LIVE PERFORMANCE 表演活動
        </div>
        <div
          style="font-family:'Noto Serif TC',serif;font-size:26px;font-weight:700;color:var(--white);"
        >
          表演活動
        </div>
        <div
          style="font-family:'Noto Sans TC',sans-serif;font-size:13px;color:rgba(255,255,255,.75);margin-top:6px;"
        >
          5/23・鹽埕國中大門口前廣場
        </div>
      </div>
      <div class="yh-xp-perf-row">
        <div class="yh-xp-perf-time">17:30–18:30</div>
        <div>
          <div class="yh-xp-perf-name">魚皮</div>
          <div class="yh-xp-perf-desc">
            用音樂與大家交流情感，唱出動人旋律。
          </div>
        </div>
      </div>
      <div class="yh-xp-perf-row">
        <div class="yh-xp-perf-time">18:45–19:45</div>
        <div>
          <div class="yh-xp-perf-name">小丑呀咪</div>
          <div class="yh-xp-perf-desc">
            來自小丑島的呀咪，帶你拋開憂愁大笑。
          </div>
        </div>
      </div>
      <div class="yh-xp-perf-row">
        <div class="yh-xp-perf-time">20:00–21:00</div>
        <div>
          <div class="yh-xp-perf-name">WiKi</div>
          <div class="yh-xp-perf-desc">Wiki 以吉他與合唱，唱出動人故事。</div>
        </div>
      </div>
    </div>
  </div>
</section>
```

> **Elementor 步驟：** 在元件 7 下方新增一個 HTML 元件，貼上上方程式碼。

---

### 元件 7c — 集章活動

```html
<!-- STAMP RALLY -->
<style>
  .yh-stamp-layout{display:grid;grid-template-columns:1fr 1fr;gap:80px;align-items:start;}
  .yh-stamp-cols{display:flex;flex-direction:column;gap:36px;}
  .yh-stamp-col{display:flex;align-items:flex-start;gap:20px;padding:0;}
  .yh-stamp-col-body{flex:1;}
  .yh-stamp-redeem{display:flex;flex-direction:column;gap:28px;}
  .yh-stamp-redeem-prize{width:100%;}
  .yh-stamp-redeem-label{font-size:16px;letter-spacing:.3em;color:var(--secondary);margin-bottom:12px;font-weight:700;}
  .yh-stamp-prize-text{font-family:'Noto Serif TC',serif;font-size:clamp(18px,2vw,24px);font-weight:900;color:var(--primary);line-height:1.5;text-align:center;margin:0 !important;padding:0;}
  @media(max-width:768px){
    .yh-stamp-layout{display:block;}
    .yh-stamp-cols{gap:36px;margin-bottom:48px;}
    .yh-stamp-col{flex-direction:column;}
    .yh-stamp-redeem{gap:28px;}
    .yh-stamp-redeem-prize{width:100%;}
    .yh-stamp-prize-text{font-size:16px;}
    .yh-stamp-redeem-label{font-size:13px;}
  }
</style>
<section style="background:linear-gradient(145deg,#F2D9D0 0%,#E9ABAB 50%,#C7A4C3 100%);padding:100px 48px;position:relative;overflow:hidden;">
  <div style="position:absolute;top:32px;left:48px;font-size:28px;color:var(--secondary);opacity:.5;line-height:1;">✦</div>
  <div style="position:absolute;top:32px;right:48px;font-size:28px;color:var(--secondary);opacity:.5;line-height:1;">✦</div>
  <div style="max-width:1080px;margin:0 auto;position:relative;">

    <!-- 標題 -->
    <div class="reveal" style="margin-bottom:64px;">
      <div style="display:flex;align-items:center;gap:20px;margin-bottom:20px;">
        <div class="yh-section-label" style="color:var(--primary);opacity:.6;white-space:nowrap;">STAMP RALLY</div>
        <div style="flex:1;height:1px;background:rgba(55,78,126,.15);"></div>
      </div>
      <h2 style="font-family:'Noto Serif TC',serif;font-size:clamp(36px,5vw,60px);font-weight:900;color:var(--primary);line-height:1.1;margin-bottom:16px;">集章活動 <span style="font-size:clamp(14px,1.8vw,20px);font-weight:400;letter-spacing:.2em;color:var(--secondary);border:1px solid var(--secondary);border-radius:4px;padding:3px 10px;vertical-align:middle;font-family:'Noto Sans TC',sans-serif;">服務台</span></h2>
      <p style="font-size:14px;color:var(--primary);opacity:.7;line-height:2;">手冊地圖頁設有 <strong>5 個貼紙空位</strong>，透過以下 3 種方式蒐集貼紙</p>
    </div>

    <!-- 左右佈局 -->
    <div class="yh-stamp-layout">

      <!-- 左：三種集章方式（垂直） -->
      <div class="yh-stamp-cols reveal">

        <div class="yh-stamp-col">
          <svg viewBox="0 0 80 80" width="64" height="64" style="flex-shrink:0;">
            <circle cx="40" cy="40" r="36" fill="rgba(255,255,255,.7)" stroke="#C0546C" stroke-width="2" stroke-dasharray="6 3"/>
            <text x="40" y="46" text-anchor="middle" font-family="Noto Serif TC,serif" font-size="20" font-weight="900" fill="#C0546C">01</text>
          </svg>
          <div class="yh-stamp-col-body">
            <div style="font-family:'Noto Serif TC',serif;font-size:17px;font-weight:700;color:var(--primary);margin-bottom:10px;line-height:1.4;">裝置藝術展區</div>
            <p style="font-size:13px;line-height:2.1;color:var(--primary);opacity:.75;">前往「呼吸」「蔓延」「共生」三大展區指定裝置藝術區 <strong style="opacity:1;">A2、B3、C4</strong>，各獲得 <mark style="background:rgba(242,190,92,.6);padding:1px 5px;border-radius:3px;">1 張展區貼紙</mark></p>
          </div>
        </div>

        <div class="yh-stamp-col">
          <svg viewBox="0 0 80 80" width="64" height="64" style="flex-shrink:0;">
            <circle cx="40" cy="40" r="36" fill="rgba(255,255,255,.7)" stroke="#F2A488" stroke-width="2" stroke-dasharray="6 3"/>
            <text x="40" y="46" text-anchor="middle" font-family="Noto Serif TC,serif" font-size="20" font-weight="900" fill="#F2A488">02</text>
          </svg>
          <div class="yh-stamp-col-body">
            <div style="font-family:'Noto Serif TC',serif;font-size:17px;font-weight:700;color:var(--primary);margin-bottom:10px;line-height:1.4;">特色市集</div>
            <p style="font-size:13px;line-height:2.1;color:var(--primary);opacity:.75;">於市集任一攤位消費，獲得 <mark style="background:rgba(242,190,92,.6);padding:1px 5px;border-radius:3px;">1 張貼紙</mark></p>
          </div>
        </div>

        <div class="yh-stamp-col">
          <svg viewBox="0 0 80 80" width="64" height="64" style="flex-shrink:0;">
            <circle cx="40" cy="40" r="36" fill="rgba(255,255,255,.7)" stroke="#C7A4C3" stroke-width="2" stroke-dasharray="6 3"/>
            <text x="40" y="46" text-anchor="middle" font-family="Noto Serif TC,serif" font-size="20" font-weight="900" fill="#C7A4C3">03</text>
          </svg>
          <div class="yh-stamp-col-body">
            <div style="font-family:'Noto Serif TC',serif;font-size:17px;font-weight:700;color:var(--primary);margin-bottom:10px;line-height:1.4;">數位體驗〈埕花〉</div>
            <p style="font-size:13px;line-height:2.1;color:var(--primary);opacity:.75;">參與〈埕花〉數位體驗並出示，獲得 <mark style="background:rgba(242,190,92,.6);padding:1px 5px;border-radius:3px;">1 張貼紙</mark></p>
          </div>
        </div>

      </div>

      <!-- 右：兌換規則 -->
      <div class="yh-stamp-redeem reveal">
        <div class="yh-stamp-redeem-text">
          <p class="yh-stamp-redeem-label">集滿 5 張後</p>
          <p style="font-size:15px;color:var(--primary);line-height:2;">
            於 Instagram、Threads、Facebook 任一平台打卡，至服務台出示手冊及打卡頁面，即可兌換
          </p>
        </div>
        <div class="yh-stamp-redeem-prize">
          <div style="background:var(--gold);border-radius:20px;padding:36px 40px;margin-bottom:14px;display:flex;align-items:center;justify-content:center;min-height:100px;">
            <p class="yh-stamp-prize-text">🎉 鹽夏不夜埕<br>專屬環保吸管杯 乙個 🎉</p>
          </div>
          <p style="font-size:11px;color:rgba(26,38,64,.55);line-height:2;letter-spacing:.05em;">
            ※ 於 5/16、5/17、5/23 發送，每日限量 60 份，每人限換一份，送完為止
          </p>
        </div>
      </div>

    </div>

  </div>
</section>
```

> **Elementor 步驟：** 在元件 7b 下方新增一個 HTML 元件，貼上上方程式碼。

---

### 元件 8 — Footer

> **Lightbox 提醒：** 在此頁最後一個 HTML 元件末尾加入首頁「Lightbox 元件」的 HTML/JS 程式碼（參考首頁段落），地圖與活動排程圖片已有 `data-lb` 屬性，加入後即可觸發放大功能。

```html
<footer>
  <div
    class="yh-footer-city"
    style="background:var(--bg);padding:56px 48px 48px;"
  >
    <div style="max-width:860px;margin:0 auto;">
      <div style="text-align:center;margin-bottom:24px;">
        <div
          style="font-size:11px;letter-spacing:.45em;color:var(--secondary);margin-bottom:8px;font-family:'Noto Sans TC',sans-serif;font-weight:700;"
        >
          MAP 活動地圖
        </div>
        <h2
          style="font-family:'Noto Serif TC',serif;font-size:clamp(24px,3vw,36px);font-weight:900;color:var(--primary);line-height:1.2;"
        >
          花轟 × 鹽埕地圖
        </h2>
      </div>
      <img
        src="https://elsonyeh.github.io/yanhsia-official-website/map.png"
        alt="活動地圖"
        style="display:block;width:100%;box-shadow:0 8px 40px rgba(55,78,126,.12);"
        data-lb
      />
    </div>
  </div>
  <div class="yh-footer-bottom">
    <div class="yh-footer-logo">
      <img
        src="https://elsonyeh.github.io/yanhsia-official-website/%E9%B9%BD%E5%A4%8Flogo%E5%80%91-20260416T013432Z-3-001/%E9%B9%BD%E5%A4%8Flogo%E5%80%91/%E8%B3%87%E7%94%A2%202.png"
        alt="鹽夏不夜埕"
      />
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
