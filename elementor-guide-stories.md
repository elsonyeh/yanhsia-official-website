# 埕中大小事（stories）— Elementor 匯入指南

> **做法：** CSS 寫在第一個 HTML 元件的 `<style>` 內，後續元件直接貼 HTML 即可。

---

## 元件 1 — CSS 全域樣式 + Page Hero（必須第一個放）

```html
```

> **Elementor 步驟：** 此為第一個 HTML 元件，包含全頁 CSS + Hero。

---

## 元件 2 — 鹽埕產業發展史

```html
<section class="yh-s-history">
  <div class="yh-s-history-eyebrow">INDUSTRY HISTORY</div>
  <div class="yh-s-history-title">鹽埕產業發展史｜<em>Industry History</em></div>

  <div class="yh-s-tl-wrap">

    <!-- 清朝 -->
    <div class="yh-s-tl-item">
      <div class="yh-s-tl-left">
        <div class="yh-s-tl-era">清朝</div>
        <div class="yh-s-tl-era-sub">最開始</div>
      </div>
      <div class="yh-s-tl-track">
        <div class="yh-s-tl-dot"></div>
        <div class="yh-s-tl-line"></div>
      </div>
      <div class="yh-s-tl-right">
        <div class="yh-s-tl-industry">製鹽產業</div>
        <p class="yh-s-tl-body">「鹽埔曉鷺」曾是傳說中的打狗八景。一百多年以前的鹽埕，清晨時的朝陽照映著鹽田閃閃發光，還有許多白鷺鷥飛翔其上。這樣的景象，一直到十九世紀末都沒有太大的改變，當時瀨南鹽場的產量佔全臺灣最大，甚至供過於求。</p>
      </div>
    </div>

    <!-- 日治時期 -->
    <div class="yh-s-tl-item">
      <div class="yh-s-tl-left">
        <div class="yh-s-tl-era">日治時期</div>
      </div>
      <div class="yh-s-tl-track">
        <div class="yh-s-tl-dot"></div>
        <div class="yh-s-tl-line"></div>
      </div>
      <div class="yh-s-tl-right">
        <div class="yh-s-tl-wave">第一波繁榮</div>
        <div class="yh-s-tl-industry">輕工業・商場百貨業</div>
        <div class="yh-s-tl-sub-list">
          <div>
            <div class="yh-s-tl-sub-label">輕工業</div>
            <p class="yh-s-tl-body">日治時代，鹽埕就因港口運輸之便，陸陸續續有輕工業設立於此，如化學廠、油漆廠、機械廠。</p>
          </div>
          <div>
            <div class="yh-s-tl-sub-label">商場百貨業</div>
            <p class="yh-s-tl-body">高雄第一間百貨公司也在鹽埕誕生，樓高五層的吉井百貨店俗稱「五層樓仔」，1938 年開幕時是臺灣建坪面積最大的百貨公司。</p>
          </div>
        </div>
      </div>
    </div>

    <!-- 美軍來台 -->
    <div class="yh-s-tl-item">
      <div class="yh-s-tl-left">
        <div class="yh-s-tl-era">美軍來台</div>
      </div>
      <div class="yh-s-tl-track">
        <div class="yh-s-tl-dot"></div>
        <div class="yh-s-tl-line"></div>
      </div>
      <div class="yh-s-tl-right">
        <div class="yh-s-tl-wave">第二波繁榮</div>
        <div class="yh-s-tl-industry">美式飲食產業（酒吧・西餐廳）</div>
        <p class="yh-s-tl-body">1950 年韓戰爆發之際，大批美軍艦隊以高雄港為補給據點。美軍為鹽埕帶來另一波繁榮，鹽埕因此誕生很多美式西餐廳、酒吧等娛樂場所。沿街開設的酒吧全盛時期有近六十家業者，陪酒的吧女數量更居全臺之冠，造就鹽埕繁榮的高峰，開放的風氣還曾譜出不少異國戀曲。</p>
      </div>
    </div>

    <!-- 戰後時期 -->
    <div class="yh-s-tl-item">
      <div class="yh-s-tl-left">
        <div class="yh-s-tl-era">戰後時期</div>
      </div>
      <div class="yh-s-tl-track">
        <div class="yh-s-tl-dot"></div>
        <div class="yh-s-tl-line"></div>
      </div>
      <div class="yh-s-tl-right">
        <div class="yh-s-tl-industry">各種產業專業街出現</div>
      </div>
    </div>

  </div>
</section>
<script>
  setTimeout(function(){
    if(window._yhSInitReveals) window._yhSInitReveals();
  }, 300);
</script>
```

> **Elementor 步驟：** 在元件 1 下方新增 HTML 元件，貼上上方程式碼。

---

## 元件 3 — Tab 導覽列

```html
<style>
  .yh-s-nav-fixed{position:fixed!important;top:0!important;left:0!important;right:0!important;z-index:9999!important;box-shadow:0 2px 12px rgba(26,38,64,.18);}
  .yh-s-nav-placeholder{display:none;}
  .yh-s-nav-placeholder.active{display:block;}
  .yh-s-tab-nav{background:var(--surface);display:flex;justify-content:center;border-bottom:2px solid rgba(242,190,92,.2);}
  .yh-s-tab-btn{padding:18px 48px;background:none;border:none;outline:none;color:var(--gray);font-family:'Noto Serif TC',serif;font-size:16px;font-weight:700;cursor:pointer;transition:color .2s;letter-spacing:.08em;position:relative;}
  .yh-s-tab-btn::after{content:'';position:absolute;bottom:-2px;left:0;right:0;height:2px;background:var(--gold);transform:scaleX(0);transition:transform .3s;}
  .yh-s-tab-btn:hover{color:var(--rose);background:none;}
  .yh-s-tab-btn:focus,.yh-s-tab-btn:focus-visible{outline:none;background:none;}
  .yh-s-tab-btn.active{color:var(--gold);}
  .yh-s-tab-btn.active::after{transform:scaleX(1);}
  .yh-s-tab-panel{display:none;}
  .yh-s-tab-panel.active{display:block;}
  @media(max-width:600px){.yh-s-tab-btn{padding:14px 18px;font-size:13px;}}
</style>

<div class="yh-s-nav-placeholder"></div>
<div class="yh-s-tab-nav">
  <button class="yh-s-tab-btn active" data-tab="story">小埕故事</button>
  <button class="yh-s-tab-btn" data-tab="observer">小埕觀察家</button>
  <button class="yh-s-tab-btn" data-tab="travel">小埕遊記</button>
</div>

<script>
(function(){
  /* Tab switching */
  function switchTab(name){
    document.querySelectorAll('.yh-s-tab-btn').forEach(function(b){b.classList.remove('active');});
    document.querySelectorAll('.yh-s-tab-panel').forEach(function(p){p.classList.remove('active');});
    var btn = document.querySelector('.yh-s-tab-btn[data-tab="'+name+'"]');
    var panel = document.getElementById('yh-s-tab-'+name);
    if(btn) btn.classList.add('active');
    if(panel){
      panel.classList.add('active');
      setTimeout(function(){if(window._yhSInitReveals) window._yhSInitReveals();},50);
    }
  }
  document.querySelectorAll('.yh-s-tab-btn').forEach(function(btn){
    btn.addEventListener('click',function(){switchTab(btn.dataset.tab);});
  });

  /* Sticky nav */
  var nav = document.querySelector('.yh-s-tab-nav');
  var ph  = document.querySelector('.yh-s-nav-placeholder');
  if(!nav || !ph) return;
  var triggerY = 0;
  function measure(){
    if(!nav.classList.contains('yh-s-nav-fixed')){
      triggerY = nav.getBoundingClientRect().top + window.scrollY;
      ph.style.height = nav.offsetHeight + 'px';
    }
  }
  window.addEventListener('scroll', function(){
    if(!triggerY) measure();
    var shouldFix = window.scrollY >= triggerY;
    nav.classList.toggle('yh-s-nav-fixed', shouldFix);
    ph.classList.toggle('active', shouldFix);
  }, {passive:true});
  setTimeout(measure, 400);
})();
</script>
```

> **Elementor 步驟：** 在元件 2 下方新增 HTML 元件。Tab 按鈕點擊後會控制元件 4、5、6 的面板顯示/隱藏。

---

## 元件 4 — 小埕故事（人物專訪）

```html
<div id="yh-s-tab-story" class="yh-s-tab-panel active" style="background:var(--bg);">
  <div class="yh-s-stories">
    <div class="yh-s-label">STORIES 小埕故事</div>
    <h2 class="yh-s-section-title">鹽埕的人與故事</h2>
    <p class="yh-s-stories-intro">人，是一個地方的回憶傳遞者，藉由人的口耳相傳將地方的故事一代一代地傳承下來，鹽埕作為高雄最早發展的區域，歷經繁華盛衰，但依然有一群人選擇留下，同時新的人決定加入，為鹽埕注入新的氣息，小埕故事集結在鹽埕深耕的各式職人，透過他們的故事，用新的角度認識鹽埕舊城區。</p>

    <div class="yh-s-interview-heading">人物專訪｜<em>Interview</em></div>
    <div class="yh-s-interview-list">

      <a href="https://yenhsiapuyehchen.com/%e5%b0%8f%e5%9f%95%e6%95%85%e4%ba%8b%ef%bc%bf%e5%bc%b5%e5%ae%b6%e8%88%96%e4%ba%ba%e7%89%a9%e5%b0%88%e6%ac%8420230307/" target="_blank" class="yh-s-card">
        <img src="https://yenhsiapuyehchen.com/wp-content/uploads/2023/03/張家鋪-11-scaled.jpg" class="yh-s-card-img" alt="EP.1 古物 Mix 咖啡" style="object-position:left center">
        <div class="yh-s-card-body">
          <div class="yh-s-badges"><span class="yh-s-cat">人物專訪</span><span class="yh-s-ep">EP.1</span></div>
          <div class="yh-s-card-title">古物 Mix 咖啡・不一般的咖啡廳</div>
          <div class="yh-s-hook">在一杯咖啡的時間裡 駐足腳步也收穫了故事</div>
          <div class="yh-s-date">— 2023.03.07</div>
          <div class="yh-s-excerpt">走在鹽埕的府北路上，你會發現，一家被植物圍繞的店面，望眼過去，老闆娘正悠閒地一邊製作咖啡，一邊和客人聊天。店內洋溢著慵懶隨和的氣息和老闆娘精選的老物，這就是「張家鋪老物咖啡」的日常……</div>
          <span class="yh-s-read">閱讀全文 →</span>
        </div>
      </a>

      <a href="https://yenhsiapuyehchen.com/%e5%b0%8f%e5%9f%95%e6%95%85%e4%ba%8b-ep-2/" target="_blank" class="yh-s-card">
        <img src="https://yenhsiapuyehchen.com/wp-content/uploads/2023/03/咖啡打擾了茶-02-scaled.jpg" class="yh-s-card-img" alt="EP.2 咖啡Ｘ印度奶茶" style="object-position:left center">
        <div class="yh-s-card-body">
          <div class="yh-s-badges"><span class="yh-s-cat">人物專訪</span><span class="yh-s-ep">EP.2</span></div>
          <div class="yh-s-card-title">咖啡Ｘ印度奶茶 ⁍ 巷弄裡的特色咖啡店</div>
          <div class="yh-s-hook">用一杯鍋煮奶茶的時間，打擾你的生活步調</div>
          <div class="yh-s-date">— 2023.03.12</div>
          <div class="yh-s-excerpt">說到巷弄咖啡店，或許你會立刻聯想到台南。但其實在鹽埕沙多宮旁的巷弄裡，有一家充滿獨特風格的咖啡店，它是——「咖啡打擾了茶」……</div>
          <span class="yh-s-read">閱讀全文 →</span>
        </div>
      </a>

      <a href="https://yenhsiapuyehchen.com/%e5%b0%8f%e5%9f%95%e6%95%85%e4%ba%8b-ep-3/" target="_blank" class="yh-s-card">
        <img src="https://yenhsiapuyehchen.com/wp-content/uploads/2023/04/HotBox-1.jpeg" class="yh-s-card-img" alt="EP.3 美式煙燻烤肉 HotBox">
        <div class="yh-s-card-body">
          <div class="yh-s-badges"><span class="yh-s-cat">人物專訪</span><span class="yh-s-ep">EP.3</span></div>
          <div class="yh-s-card-title">美式煙燻烤肉Ｘ團聚 ⁍ 愛河畔的特色餐廳</div>
          <div class="yh-s-hook">和喜歡的人一起做喜歡的事，到 HotBox 感受相聚氛圍</div>
          <div class="yh-s-date">— 2023.04.11</div>
          <div class="yh-s-excerpt">漫步在河畔的步道上，帶著香味四溢的煙燻烤肉的氣息，再搭配上一杯清涼的啤酒，簡直是人生一大享受。這樣的體驗現在可以在 Hot Box 實現……</div>
          <span class="yh-s-read">閱讀全文 →</span>
        </div>
      </a>

      <a href="https://yenhsiapuyehchen.com/%e5%b0%8f%e5%9f%95%e6%95%85%e4%ba%8b-ep-2-2/" target="_blank" class="yh-s-card">
        <img src="https://yenhsiapuyehchen.com/wp-content/uploads/2023/04/油飯-02-scaled.jpg" class="yh-s-card-img" alt="EP.4 油飯兒時記憶" style="object-position:left center">
        <div class="yh-s-card-body">
          <div class="yh-s-badges"><span class="yh-s-cat">人物專訪</span><span class="yh-s-ep">EP.4</span></div>
          <div class="yh-s-card-title">油飯。兒時舌尖記憶</div>
          <div class="yh-s-hook">一碗手工油飯，憶起傳統滋味</div>
          <div class="yh-s-date">— 2023.04.17</div>
          <div class="yh-s-excerpt">隱藏在鹽埕街的巷弄裡，文青風的招牌、小巧的店面，不時飄來陣陣的油飯香。店內，老闆娘正專注的分裝油飯，後頭的廚房也正忙碌著……</div>
          <span class="yh-s-read">閱讀全文 →</span>
        </div>
      </a>

      <a href="https://yenhsiapuyehchen.com/%e5%b0%8f%e5%9f%95%e6%95%85%e4%ba%8bep-5/" target="_blank" class="yh-s-card">
        <img src="https://yenhsiapuyehchen.com/wp-content/uploads/2023/04/AAC7681D-0A7D-49A5-97F2-12E9F0361624.jpg" class="yh-s-card-img" alt="EP.5 皮革與回憶">
        <div class="yh-s-card-body">
          <div class="yh-s-badges"><span class="yh-s-cat">人物專訪</span><span class="yh-s-ep">EP.5</span></div>
          <div class="yh-s-card-title">皮革與回憶 ❖ 從興趣到專業</div>
          <div class="yh-s-hook">只做喜歡的事，只走自己的路</div>
          <div class="yh-s-date">— 2023.04.25</div>
          <div class="yh-s-excerpt">皮革在大眾的印象裡，常常與文青、手作劃上等號，但今天當我們把皮革與回憶做結合，一塊冰冷的皮革似乎就多了點溫度，夢想鞄製所就是這一類的手作皮革店……</div>
          <span class="yh-s-read">閱讀全文 →</span>
        </div>
      </a>

      <a href="https://yenhsiapuyehchen.com/%E5%B0%8F%E5%9F%95%E6%95%85%E4%BA%8B-ep-6/" target="_blank" class="yh-s-card">
        <img src="https://yenhsiapuyehchen.com/wp-content/uploads/2024/04/百工百事-1.png" class="yh-s-card-img" alt="EP.6 百工百事 葉大哥">
        <div class="yh-s-card-body">
          <div class="yh-s-badges"><span class="yh-s-cat">百工百事</span><span class="yh-s-ep">EP.6</span></div>
          <div class="yh-s-card-title">百工百事｜葉大哥</div>
          <div class="yh-s-hook">一位府北居民的凝望與告白</div>
          <div class="yh-s-date">— 2023.04.28</div>
          <div class="yh-s-excerpt">在駁二、網路媒體時代等因素的影響下，鹽埕儼然是大眾熟悉的老城區，但很多人其實並不熟悉在高雄歷史博物館後方的「府北里」……</div>
          <span class="yh-s-read">閱讀全文 →</span>
        </div>
      </a>

      <a href="https://yenhsiapuyehchen.com/%e5%b0%8f%e5%9f%95%e6%95%85%e4%ba%8b-ep-7/" target="_blank" class="yh-s-card">
        <img src="https://yenhsiapuyehchen.com/wp-content/uploads/2024/05/百工百事_-_4.png" class="yh-s-card-img" alt="EP.7 百工百事 阿桃姐">
        <div class="yh-s-card-body">
          <div class="yh-s-badges"><span class="yh-s-cat">百工百事</span><span class="yh-s-ep">EP.7</span></div>
          <div class="yh-s-card-title">百工百事｜阿桃姐</div>
          <div class="yh-s-hook">府北在地商家的真情流露</div>
          <div class="yh-s-date">— 2023.05.05</div>
          <div class="yh-s-excerpt">再美的花，都會有凋謝的一天；這是人生百態，是萬物運行的規則。鹽埕商圈也是如此，府北曾經的繁榮，是每個在地商家的驕傲……</div>
          <span class="yh-s-read">閱讀全文 →</span>
        </div>
      </a>

      <a href="https://yenhsiapuyehchen.com/%e5%b0%8f%e5%9f%95%e6%95%85%e4%ba%8b-ep8/" target="_blank" class="yh-s-card">
        <img src="https://yenhsiapuyehchen.com/wp-content/uploads/2024/05/百工百事-3.png" class="yh-s-card-img" alt="EP.8 百工百事 施大哥">
        <div class="yh-s-card-body">
          <div class="yh-s-badges"><span class="yh-s-cat">百工百事</span><span class="yh-s-ep">EP.8</span></div>
          <div class="yh-s-card-title">百工百事｜施大哥</div>
          <div class="yh-s-hook">七福商場與跑單幫的興衰</div>
          <div class="yh-s-date">— 2024.05.27</div>
          <div class="yh-s-excerpt">七福商場（又稱七福商店街）是鹽埕全盛時期重要的舶來品交易所，店家老闆常常出國帶回許多「外國貨」，並在這裡販售……</div>
          <span class="yh-s-read">閱讀全文 →</span>
        </div>
      </a>

      <a href="https://yenhsiapuyehchen.com/%E5%B0%8F%E5%9F%95%E6%95%85%E4%BA%8B-ep-9/" target="_blank" class="yh-s-card">
        <img src="https://yenhsiapuyehchen.com/wp-content/uploads/2024/06/百工百事-5.png" class="yh-s-card-img" alt="EP.9 百工百事 李大哥">
        <div class="yh-s-card-body">
          <div class="yh-s-badges"><span class="yh-s-cat">百工百事</span><span class="yh-s-ep">EP.9</span></div>
          <div class="yh-s-card-title">百工百事｜李大哥</div>
          <div class="yh-s-hook">被淹沒在時間洪流的人</div>
          <div class="yh-s-date">— 2024.06.11</div>
          <div class="yh-s-excerpt">這次的訪談中，我們找到了曾經在外漂泊數十年，歷經風風雨雨，最終落腳在鹽埕這塊土地的人……</div>
          <span class="yh-s-read">閱讀全文 →</span>
        </div>
      </a>

      <a href="https://yenhsiapuyehchen.com/%E5%B0%8F%E5%9F%95%E6%95%85%E4%BA%8B-ep-10/" target="_blank" class="yh-s-card">
        <img src="https://yenhsiapuyehchen.com/wp-content/uploads/2025/05/1.jpg" class="yh-s-card-img" alt="EP.10 Cosmos of Liam 連恩宇宙">
        <div class="yh-s-card-body">
          <div class="yh-s-badges"><span class="yh-s-cat">店鋪故事</span><span class="yh-s-ep">EP.10</span></div>
          <div class="yh-s-card-title">店鋪故事｜Cosmos of Liam 連恩宇宙</div>
          <div class="yh-s-hook">一杯咖啡沖出來的夢</div>
          <div class="yh-s-date">— 2025.05.28</div>
          <div class="yh-s-excerpt">走在鹽埕的街頭，一不小心就會錯過街角那間不起眼的小咖啡店。沒有引人注目的招牌牆、沒有打卡點，甚至在 Google Map 上都找不到……</div>
          <span class="yh-s-read">閱讀全文 →</span>
        </div>
      </a>

      <a href="https://yenhsiapuyehchen.com/%E5%B0%8F%E5%9F%95%E6%95%85%E4%BA%8B-ep-11/" target="_blank" class="yh-s-card">
        <img src="https://yenhsiapuyehchen.com/wp-content/uploads/2025/05/未命名-簡報-43.jpg" class="yh-s-card-img" alt="EP.11 柒菓煎餅菓子">
        <div class="yh-s-card-body">
          <div class="yh-s-badges"><span class="yh-s-cat">店鋪故事</span><span class="yh-s-ep">EP.11</span></div>
          <div class="yh-s-card-title">店鋪故事｜柒菓煎餅菓子</div>
          <div class="yh-s-hook">一口熟悉，一份心意</div>
          <div class="yh-s-date">— 2025.05.28</div>
          <div class="yh-s-excerpt">走在鹽埕的鹽埕街上，一不小心就會錯過街角那台低調的小餐車。沒有醒目的招牌，卻總是有陣陣香味在空氣中飄散……</div>
          <span class="yh-s-read">閱讀全文 →</span>
        </div>
      </a>

      <a href="https://yenhsiapuyehchen.com/%E5%B0%8F%E5%9F%95%E6%95%85%E4%BA%8B-ep-12/" target="_blank" class="yh-s-card">
        <img src="https://yenhsiapuyehchen.com/wp-content/uploads/2025/05/3.jpg" class="yh-s-card-img" alt="EP.12 肉粽泰 Thai">
        <div class="yh-s-card-body">
          <div class="yh-s-badges"><span class="yh-s-cat">店鋪故事</span><span class="yh-s-ep">EP.12</span></div>
          <div class="yh-s-card-title">店鋪故事｜肉粽泰 Thai</div>
          <div class="yh-s-hook">一顆粽子，一條回家的路</div>
          <div class="yh-s-date">— 2025.05.28</div>
          <div class="yh-s-excerpt">鹽埕區的街頭，有間肉粽老店，香氣伴著這座城市走過六、七十個年頭，陪著無數人從童年走到成家立業，再到含飴弄孫……</div>
          <span class="yh-s-read">閱讀全文 →</span>
        </div>
      </a>

      <a href="https://yenhsiapuyehchen.com/%E5%B0%8F%E5%9F%95%E6%95%85%E4%BA%8B-ep-13/" target="_blank" class="yh-s-card">
        <img src="https://yenhsiapuyehchen.com/wp-content/uploads/2025/05/4.jpg" class="yh-s-card-img" alt="EP.13 時光商行">
        <div class="yh-s-card-body">
          <div class="yh-s-badges"><span class="yh-s-cat">店鋪故事</span><span class="yh-s-ep">EP.13</span></div>
          <div class="yh-s-card-title">店鋪故事｜時光商行</div>
          <div class="yh-s-hook">四個年輕人的夢想交匯</div>
          <div class="yh-s-date">— 2025.05.28</div>
          <div class="yh-s-excerpt">故事的開端來自四個年輕人的心聲，雖然他們來自不同的背景，卻因為對創業的熱情和對未來的憧憬走到了一起……</div>
          <span class="yh-s-read">閱讀全文 →</span>
        </div>
      </a>

    </div>
  </div>
</div>

<script>
  setTimeout(function(){ if(window._yhSInitReveals) window._yhSInitReveals(); }, 300);
</script>
```

> **Elementor 步驟：** 此面板預設顯示（`active`），點擊「小埕故事」tab 時顯示。

---

## 元件 5 — 小埕觀察家

> **⚠️ 圖片前置：** 照片推上 GitHub Pages 後，CDN 路徑如下（注意已改為新資料夾結構）：
> - 花葉印布：`https://elsonyeh.github.io/yanhsia-official-website/%E5%B0%8F%E5%9F%95%E8%A7%80%E5%AF%9F%E5%AE%B6/%E9%B9%BD%E5%9F%95%E5%9C%8B%E5%B0%8F%E8%A6%AA%E5%AD%90%E6%97%A5_%E8%8A%B1%E8%91%89%E5%8D%B0%E5%B8%83/%E7%85%A7%E7%89%87/`
> - 花落成流：`https://elsonyeh.github.io/yanhsia-official-website/%E5%B0%8F%E5%9F%95%E8%A7%80%E5%AF%9F%E5%AE%B6/%E8%8A%B1%E8%90%BD%E6%88%90%E6%B5%81%E5%B7%A5%E4%BD%9C%E5%9D%8A/%E7%85%A7%E7%89%87/`
> - SEL 工作坊：`https://elsonyeh.github.io/yanhsia-official-website/%E5%B0%8F%E5%9F%95%E8%A7%80%E5%AF%9F%E5%AE%B6/%E9%B9%BD%E5%9F%95%E5%9C%8B%E4%B8%AD%E8%8A%B1%E8%97%9D%E8%9E%8D%E5%85%A5SEL%E6%95%99%E8%82%B2%E5%B7%A5%E4%BD%9C%E5%9D%8A/%E7%85%A7%E7%89%87/`（檔名格式：`鹽埕國中花藝融入SEL教育工作坊_N.png`）
> - 花框留映：`https://elsonyeh.github.io/yanhsia-official-website/%E5%B0%8F%E5%9F%95%E8%A7%80%E5%AF%9F%E5%AE%B6/%E3%80%8A%E8%8A%B1%E6%A1%86%E7%95%99%E6%98%A0%E3%80%8B%E5%B7%A5%E4%BD%9C%E5%9D%8A/%E7%85%A7%E7%89%87/`（檔名：`花框留映_1.jpg`、`花框留映_2.jpg`）

> **設計說明：** 各篇文章預設**收合**（只顯示標題、日期、摘要、3 張縮圖預覽），點擊「展開閱讀」才展開全文。新增文章時照下方格式複製貼上即可。

```html

```

> **Elementor 步驟：** 預設隱藏，點擊「小埕觀察家」tab 時顯示。新增文章時，複製其中一個 `<article>` 區塊，更新標題、日期、圖片 URL 及文字即可；最新文章放在最上面。

---

## 元件 6 — 小埕遊記

> **⚠️ 圖片前置：** 照片推上 GitHub Pages 後，CDN 路徑如下：
> - 走入鹽東：`https://elsonyeh.github.io/yanhsia-official-website/%E5%B0%8F%E5%9F%95%E9%81%8A%E8%A8%98/%E8%B7%9F%E8%91%97%E9%B9%BD%E5%A4%8F%E8%B5%B0%E5%85%A5%E9%B9%BD%E6%9D%B1/%E7%85%A7%E7%89%87/`

> **設計說明：** 採用與小埕觀察家相同的折疊式文章設計，CSS 已在元件 5 定義，直接使用相同 class。

```html
<div id="yh-s-tab-travel" class="yh-s-tab-panel" style="background:var(--bg);">
  <div class="yh-s-observer">
    <div class="yh-s-label">TRAVEL DIARY 小埕遊記</div>
    <h2 class="yh-s-section-title">在鹽埕漫遊<br>留下你的足跡</h2>
    <p class="yh-s-observer-intro yh-s-reveal">跟著鹽夏的腳步，走進這座城市的肌理。小埕遊記記錄鹽埕的歷史脈絡、街區風景與在地故事，讓每一次漫步都成為一場有溫度的相遇。</p>

    <!-- ── 文章：走入鹽東 ── -->
    <article class="yh-s-article yh-s-reveal">
      <div class="yh-s-article-header">
        <div class="yh-s-article-meta">
          <span class="yh-s-obs-tag">街區誌</span>
          <span class="yh-s-obs-date">2026.05</span>
        </div>
        <h3 class="yh-s-article-title">跟著鹽夏一起花轟，一起走入「鹽東」</h3>
        <p class="yh-s-article-hook">從日治時代的榮町到今日的福容大飯店，鹽東的每條街道都藏著高雄最濃縮的城市記憶</p>
      </div>
      <div class="yh-s-article-preview">
        <img src="https://elsonyeh.github.io/yanhsia-official-website/%E5%B0%8F%E5%9F%95%E9%81%8A%E8%A8%98/%E8%B7%9F%E8%91%97%E9%B9%BD%E5%A4%8F%E8%B5%B0%E5%85%A5%E9%B9%BD%E6%9D%B1/%E7%85%A7%E7%89%87/1.jpg" alt="">
        <img src="https://elsonyeh.github.io/yanhsia-official-website/%E5%B0%8F%E5%9F%95%E9%81%8A%E8%A8%98/%E8%B7%9F%E8%91%97%E9%B9%BD%E5%A4%8F%E8%B5%B0%E5%85%A5%E9%B9%BD%E6%9D%B1/%E7%85%A7%E7%89%87/2.jpg" alt="">
        <img src="https://elsonyeh.github.io/yanhsia-official-website/%E5%B0%8F%E5%9F%95%E9%81%8A%E8%A8%98/%E8%B7%9F%E8%91%97%E9%B9%BD%E5%A4%8F%E8%B5%B0%E5%85%A5%E9%B9%BD%E6%9D%B1/%E7%85%A7%E7%89%87/1.jpg" alt="" style="object-position:right center;">
      </div>
      <button class="yh-s-obs-toggle" onclick="yhsObsToggle(this)">
        <span class="yh-s-obs-toggle-label">展開閱讀</span>
        <span class="yh-s-obs-toggle-arrow">↓</span>
      </button>
      <div class="yh-s-article-body">
        <div class="yh-s-obs-hero">
          <img src="https://elsonyeh.github.io/yanhsia-official-website/%E5%B0%8F%E5%9F%95%E9%81%8A%E8%A8%98/%E8%B7%9F%E8%91%97%E9%B9%BD%E5%A4%8F%E8%B5%B0%E5%85%A5%E9%B9%BD%E6%9D%B1/%E7%85%A7%E7%89%87/1.jpg" alt="鹽東街景" style="object-position:center 40%;">
        </div>
        <div class="yh-s-obs-body">
          <p>本屆「鹽夏不夜埕」選擇了鹽埕東側（後文稱「鹽東」）作為舉辦地，以育仁里、沙地里、南端里為我們的主要場域，希望帶領民眾更加認識該區域。</p>
        </div>
        <div class="yh-s-obs-body">
          <div class="yh-s-obs-label">日治時期的鹽東</div>
          <p>鹽東最早開發的階段可追溯自日治時期，今日的育仁里當時稱「榮町」，為當時日本人居住之地區，並有良好的商業機能，甚至亦有蓬勃的風化區（遊廓），那時的貸座敷主要是由旗后遷移過來。沙地里與南端里早年為荒涼的海沙埔，俗稱沙仔地，日治時期命名為「入船町」。根據日日新報記載，1933 年這裡曾有跑馬場舉辦當時的賽馬活動。綜合來講，「鹽東」可以說從日治時期就已經是當時高雄人重要的休憩中心。</p>
        </div>
        <div class="yh-s-photo-pair">
          <img src="https://elsonyeh.github.io/yanhsia-official-website/%E5%B0%8F%E5%9F%95%E9%81%8A%E8%A8%98/%E8%B7%9F%E8%91%97%E9%B9%BD%E5%A4%8F%E8%B5%B0%E5%85%A5%E9%B9%BD%E6%9D%B1/%E7%85%A7%E7%89%87/1.jpg" alt="鹽東街景一">
          <img src="https://elsonyeh.github.io/yanhsia-official-website/%E5%B0%8F%E5%9F%95%E9%81%8A%E8%A8%98/%E8%B7%9F%E8%91%97%E9%B9%BD%E5%A4%8F%E8%B5%B0%E5%85%A5%E9%B9%BD%E6%9D%B1/%E7%85%A7%E7%89%87/2.jpg" alt="鹽東街景二">
        </div>
        <div class="yh-s-obs-body">
          <div class="yh-s-obs-label">光復後的街區轉型</div>
          <p>國民政府來台後，曾經的遊廓區被拆除，1957 年今日鹽埕國中的位置上改建起圓山大飯店，並於 1970 年停止營運移至澄清湖畔。今日的新樂街綠廊過去是從 1940 年代即存在的「竹仔市」，以竹籬笆蓋起的印象至今仍為當地人所記得。該市場在 1951 年改建成為大智公有市場，成為當地人重要的購物餐飲空間，但於 2008 年因為市容整頓而拆除。相較於鹽埕區其他區域，今日鹽東的連棟式建築多建於 1960 年代之後，反映了當時建築觀念與技術的變化，強調理性、效率的風格成為這裡的景觀基調。五福路南側靠近公園路段，則保留了船舶五金產業，連結了入船町的歷史。</p>
        </div>
        <div class="yh-s-obs-body">
          <div class="yh-s-obs-label">五福四路的商業脈動</div>
          <p>受到越戰與美援的影響，五福四路上許多知名商業空間在 1960 年代開幕，見證了當時該區域的快速變化。1967 年新統一牛排館開幕，自此成為高雄民眾享受美式高端餐飲的新選擇。1968 年華王大飯店開幕，其建築見證了鹽埕區的輝煌歷史，也成為高雄民眾結婚、宴客的重要空間。1970 年代開業的瑞士大飯店，雖然名稱洋氣，但多以中式餐點為主，其中的芋頭香酥鴨至今仍為許多老饕所懷念。華王大飯店雖在 2019 年停業拆除，但 2010 年從「城市毒瘤」宜民大樓搖身一變的福容大飯店，則成為在地最重要的景觀地標之一。</p>
        </div>
        <div class="yh-s-obs-body">
          <div class="yh-s-obs-label">飲品文化</div>
          <p>五福四路上的飲品文化也非常值得體驗。已經營業 45 年的友加友咖啡，可能是高雄最早開始自烘咖啡豆的咖啡店，其飲品也成為高雄咖啡愛好者的共同回憶。在七賢路酒吧沒落之後，該區成為酒吧最密集的區段，貓頭鷹酒館、流浪者酒館、牛津啤酒屋 Oxford 等，均是今日高雄酒吧文化的重要代表與推手。</p>
        </div>
        <div class="yh-s-obs-body">
          <p class="yh-s-obs-quote">鹽東雖然在高雄文史上並不顯赫有名，但其商業、休憩之功能不能被忽略。2020 年後，伴隨著市府對於愛河出海口段的規劃整治、輕軌通車、高雄流行音樂中心開幕、各項在真愛碼頭區舉辦的活動，促成了觀光遊客數量快速成長，鹽東的重要性值得被看見。</p>
          <p style="font-size:13px;color:#999;margin-top:8px;">文：宋世祥｜國立中山大學人文暨科技跨領域學士學位學程主任 專任副教授</p>
        </div>
        <button class="yh-s-obs-close" onclick="yhsObsClose(this)">收合 ↑</button>
      </div>
    </article>

  </div>
</div>
```

> **Elementor 步驟：** 預設隱藏，點擊「小埕遊記」tab 時顯示。新增文章時，複製 `<article>` 區塊，更新標題、日期、CDN 圖片 URL 及文字即可；最新文章放在最上面。JS 函式 `yhsObsToggle` / `yhsObsClose` 已在元件 5 定義，無需重複加入。

---

## 元件 7 — Footer

```html
<footer>
  <div class="yh-s-footer-pre">
    <div class="yh-s-footer-pre-title">更多花轟體驗<br>等你來發現</div>
    <div class="yh-s-footer-pre-sub">5/16—5/23 新樂街綠廊　每日 17:00–21:00</div>
    <a href="/hanabomb" class="yh-s-footer-pre-btn">回到花轟 →</a>
  </div>
  <div class="yh-s-footer-bottom">
    <div class="yh-s-footer-logo">
      <img src="https://elsonyeh.github.io/yanhsia-official-website/%E9%B9%BD%E5%A4%8Flogo%E5%80%91-20260416T013432Z-3-001/%E9%B9%BD%E5%A4%8Flogo%E5%80%91/%E8%B3%87%E7%94%A2%202.png" alt="鹽夏不夜埕">
    </div>
    <div class="yh-s-footer-social">
      <a href="https://www.facebook.com/dontsleepinyancheng">Facebook</a>
      <a href="https://www.instagram.com/dont_sleep_in_yancheng/">Instagram</a>
      <a href="https://line.me/R/ti/p/@235chemh">LINE 官方帳號</a>
      <a href="mailto:dont.sleep.in.yancheng@gmail.com">Mail</a>
    </div>
    <div class="yh-s-footer-copy">© 2026 鹽夏不夜埕 All Rights Reserved</div>
  </div>
</footer>
```

---

## 注意事項

| 項目 | 說明 |
|------|------|
| Tab 切換 JS | 寫在元件 3，會抓取整頁的 `.yh-s-tab-panel`，因此元件 4、5、6 必須在元件 3 **之後** 放置 |
| Reveal 動畫 | 切換 tab 時自動重新觸發，隱藏面板裡的元素在顯示後也會有入場動畫 |
| 觀察家照片 | 照片結構改為 `小埕觀察家/[活動名稱]/照片/` — 推上 GitHub Pages 後 CDN 路徑前綴見元件 5 說明 |
| 折疊文章 JS | `yhsObsToggle` / `yhsObsClose` 寫在元件 5 末尾；新增文章時不需額外 JS |
| 人物專訪圖片 | 各卡片的 `<img src="【填入圖片連結】">` 換成實際圖片 URL 即可顯示；無圖時顯示淡褐色底色 |
