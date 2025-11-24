## css 版面(flexbox,grid)

### display:flex的觀念

![](./images/魔法彈性搬家記.png)

### display:flex的思考流程

![](./images/flex視覺化決策路徑.png)

#### bakery.html

```html
<!doctype html>
<html>

<head>
  <meta charset="UTF-8">
  <title>黑鵝麵包店</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link href="https://fonts.googleapis.com/css?family=Stint+Ultra+Expanded" rel="stylesheet">
  <style>
    @import url(bakery-styles.css);
  </style>
</head>

<body>

  <header>
    <nav>
      <ul>
        <li><a href="">菜單</a></li>
        <li><a href="">新聞</a></li>
        <li><a href="">關於</a></li>
        <li><a href="">聯繫方式</a></li>
      </ul>
    </nav>
    <h1><img src="images/bgb_logo.png" alt="Black Goose Bakery"></h1>
    <p>您在 Black Goose Bistro 喜愛的美味烘焙食品......現在可以外賣了！</p>
  </header>

  <main>
    <h2>剛出爐</h2>
    <h3>麵包</h3>
    <p><img src="images/bread.png" alt="round loaf of bread on cutting board"> 我們的麵包每天由最優質的全麥麵粉、水、鹽和酵母或酵母發酵劑製成。
      簡單自然，從不添加任何防腐劑。 耐心是實現適當發酵水平和將每條麵包烘烤至完美的關鍵。 提供全麥、酵母、橄欖麵包、經典黑麥和土豆洋蔥。</p>
    <p class="more"><a href="">詳細了解我們的烘焙過程...</a></p>

    <h3>鬆餅</h3>
    <p><img src="images/muffin.png" alt="one chocolate chip muffin"> 每天，我們都會提供種類繁多的鬆餅，包括藍莓、多漿果、麩皮、玉米、檸檬罌粟籽和巧克力。
      我們的鬆餅每天都是從零開始製作的。 停下來看看我們的時令鬆餅口味！</p>
    <p class="more"><a href="">詳細了解我們如何製作鬆餅...</a></p>
  </main>

  <aside>
    <h2>營業時間</h2>
    <p><span class="day">星期一：</span>早上 5 點到下午 3 點</p>
    <p><span class="day">星期二：</span>早上 5 點到下午 3 點</p>
    <p><span class="day">星期三：</span>早上 5 點到下午 3 點</p>
    <p><span class="day">星期四：</span>早上 5 點到下午 3 點</p>
    <p><span class="day">星期五：</span>早上 5 點到下午 3 點</p>
    <p><span class="day">星期六：</span>早上 6 點到下午 4 點</p>
    <p><span class="day">週日：</span>早上 6 點到下午 4 點</p>
  </aside>

  <footer>
    所有內容版權&copy; 2017，黑鵝小酒館。
  </footer>

</body>

</html>
```

#### flexmenu.html

```html
<!doctype html>
<html>

<head>
  <meta charset="UTF-8">
  <title>Flexbox Product Listing Exercise</title>

  <style>
    html {
      box-sizing: border-box;
    }

    *,
    *:before,
    *:after {
      box-sizing: inherit;
    }

    body {
      font-family: Georgia, serif;
      line-height: 1.5em;
    }

    h1 {
      font-size: 4em;
      font-weight: normal;
    }

    h2 {
      font-size: 1.2em;
      margin-top: 0;
    }

    #menu {
      border: 3px solid #783F27;

    }

    section {
      background: #F6F3ED;
      margin: 10px;
      padding: 20px;
      border: 1px dotted maroon;
      width: 240px;
    }

    .title {
      background-color: #783F27;
      color: #F9AB33;
      line-height: 4em;
    }

    .price {
      font-weight: bold;
      background: #F9AB33;
      padding: 5px;
      width: 100%;
      text-align: center;
    }
  </style>

</head>

<body>
  <div id="menu">
    <section class="title">
      <h1>小酒館項目去</h1>
    </section>

    <section class="dish">
      <h2>1<br>黑豆錢包</h2>
      <p class="info">辣味黑豆和混合墨西哥奶酪，包裹在千層酥中，烘烤至金黃色。</p>
      <p class="photo"><img src="table.jpg" alt=""></p>
      <p class="price">$3.95</p>
    </section>

    <section class="dish">
      <h2>2<br>西南拿破崙</h2>
      <p class="info">層層疊疊的蟹肉塊、豆子和玉米莎莎醬，以及我們手工製作的麵粉玉米餅。</p>
      <p class="photo"><img src="table.jpg" alt=""></p>
      <p class="price">$7.95</p>
    </section>

    <section class="dish">
      <h2>3<br>椰子玉米濃湯</h2>
      <p class="info">這種在椰子湯中加入土豆和玉米的素食雜燴清淡可口。</p>
      <p class="photo"><img src="table.jpg" alt=""></p>
      <p class="price">$3.95</p>
    </section>

    <section class="dish">
      <h2>4<br>混蛋烤雞</h2>
      <p class="info">在烤肉架上慢烤的嫩雞肉，用香辣的肉乾醬調味，配以炸大蕉和芒果片。 <em>警告，非常辣！</em></p>
      <p class="photo"><img src="table.jpg" alt=""></p>
      <p class="price">$12.95</p>
    </section>

    <section class="dish">
      <h2>5<br>泰國蝦串</h2>
      <p class="info">用檸檬草、大蒜和魚露醃製的蝦串，然後烤至完美。</p>
      <p class="photo"><img src="table.jpg" alt=""></p>
      <p class="price">$12.95</p>
    </section>

    <section class="dish">
      <h2>6<br>麵食Puttanesca</h2>
      <p class="info">用大蒜、橄欖、刺山柑、鳳尾魚和大量紅辣椒片燉製而成的濃郁番茄醬。</p>
      <p class="photo"><img src="table.jpg" width="200" height="100" alt=""></p>
      <p class="price">$12.95</p>
    </section>


  </div>

</body>

</html>
```

#### grid.html

```html
<!doctype html>
<html>

<head>
  <meta charset="UTF-8">
  <title>Black Goose Bakery Grid</title>
  <link href="https://fonts.googleapis.com/css?family=Stint+Ultra+Expanded" rel="stylesheet">
  <style>
    html {
      box-sizing: border-box;
    }

    * {
      box-sizing: inherit;
    }

    body {
      font-family: Georgia, serif;
      font-size: 100%;
      background-color: white;
      margin: 0;
    }

    /* GRID STYLES START HERE */
    #layout {
      margin-left: 5%;
      margin-right: 5%;

    }



    /* VISUAL STYLES START HERE */

    /* link styles */
    a:link,
    a:visited {
      color: #DC6903;
    }

    a:focus,
    a:hover,
    a:active {
      color: #F9AB33;
    }

    a {
      text-decoration: none;
      border-bottom: 1px dotted;
      padding-bottom: .2em;
    }



    /* nav styles */
    nav,
    footer {
      font-family: verdana, sans-serif;
      background-color: #783F27;
    }

    nav ul li a:link,
    nav ul li a:visited {
      color: #F9AB33;
    }

    nav ul li a:focus,
    nav ul li a:hover,
    nav ul li a:active {
      color: #fff;
    }

    nav ul {
      margin: 0;
      padding: 0;
      list-style-type: none;
      display: flex;
      justify-content: center;
    }

    nav ul li {
      font-size: .8em;
      text-transform: uppercase;
      letter-spacing: .2em;
    }

    nav ul li a {
      display: block;
      border: 1px solid;
      border-radius: .5em;
      padding: .5em 1em;
      margin: .5em;
    }


    /* main styles */
    main {
      font-family: 'Stint Ultra Expanded', Georgia, serif;
      background-color: white;
      line-height: 1.8em;
      color: #555;
      padding: 1em;
      border: double 4px #EADDC4;
      border-radius: 25px;
    }


    /* misc styles */

    figure {
      margin: 0;
      padding: 0;
      '

      /* clears browser styles for figures */
    }

    footer {
      color: #EADDC4;
      text-align: center;
      font-size: .8em;
      padding: .5em;
    }
  </style>
</head>

<body>
  <div id="layout">

    <nav>
      <ul>
        <li><a href="">菜單</a></li>
        <li><a href="">新聞</a></li>
        <li><a href="">關於</a></li>
        <li><a href="">聯繫方式</a></li>
      </ul>
    </nav>

    <main>
      <h2>介紹：世界麵包！</h2>
      <p>似乎世界上每個地區對這種人類主食都有自己的特殊看法。 從硬皮法式長棍麵包到餐桌大小的阿富汗大扁麵包，麵包可以有各種形狀、大小和質地。</p>
      <p>每個月，我們都會推出一款代表特定文化或世界某個地區特色的麵包。 有些將由我們的麵包師在內部製作，他們周遊世界學習當地技術，以便將它們帶回來供您嘗試。 其他麵包將由當地幾代人為社區製作麵包的麵包店提供。</p>

      <p>當您在麵包店時，我們鼓勵您嘗試一下我們的特色麵包世界。 如果您無法前往商店，我們的許多麵包都可以在線購買。</p>
      <p>為您提供新鮮、獨特的麵包是 Black Goose Bakery 引以為豪的事情之一。</p>
      <!--
<p>我們的麵包每天由最優質的全麥麵粉、水、鹽和酵母或酵母發酵劑製成。 簡單自然，從不添加任何防腐劑。 耐心是實現適當發酵水平和將每條麵包烘烤至完美的關鍵。 提供全麥、酵母、橄欖麵包、經典黑麥和土豆洋蔥。</p>
-->
    </main>

    <figure id="figA"><img src="images/uzbek_150.jpg"></figure>
    <figure id="figB"><img src="images/bread_150.jpg"></figure>
    <figure id="figC"><img src="images/braided_150.jpg"></figure>

    <footer>
      <p><strong>黑鵝麵包店</strong> | Seekonk, MA <br>
        週一 &ndash; 星期五: 5am to 3pm | 週六 &amp; Sunday: 6am to 4pm</p>
    </footer>

  </div>
</body>

</html>
```