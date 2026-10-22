<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="theme-color" content="#151515">
  <title>قَلَم | منصّة الكتابة العربية</title>
  <style>
    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: Tahoma, Arial, sans-serif;
      background: #111;
      color: #f5f0e8;
    }
    header {
      padding: 20px;
      background: #191919;
      border-bottom: 1px solid #333;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    .logo { font-size: 27px; font-weight: bold; color: #ff962e; }
    .tagline { color: #bbb; font-size: 13px; margin-top: 5px; }
    main { max-width: 720px; margin: auto; padding: 20px; }
    .intro { padding: 25px 0; }
    h1 { font-size: 28px; line-height: 1.6; }
    .intro p { color: #bbb; line-height: 1.9; }
    .panel {
      background: #1b1b1b;
      border: 1px solid #333;
      border-radius: 14px;
      padding: 18px;
      margin-bottom: 18px;
    }
    input, textarea, select, button {
      width: 100%;
      padding: 13px;
      margin-top: 10px;
      border-radius: 9px;
      font: inherit;
    }
    input, textarea, select {
      color: #fff;
      background: #111;
      border: 1px solid #444;
    }
    textarea { min-height: 130px; resize: vertical; }
    button {
      background: #ff962e;
      color: #17110a;
      border: 0;
      font-weight: bold;
      cursor: pointer;
    }
    .hint { color: #aaa; font-size: 13px; line-height: 1.8; }
    footer { text-align: center; color: #888; padding: 30px 10px; }
  </style>
</head>
<body>
  <header>
    <div>
      <div class="logo">✒ قَلَم</div>
      <div class="tagline">مساحة لكل فكرة وكلمة</div>
    </div>
    <span>منصّة الكتابة العربية</span>
  </header>

  <main>
    <section class="intro">
      <h1>لكل إنسان حكاية، ولكل فكرة قلم.</h1>
      <p>اكتب مقالاتك وخواطرك وقصائدك، وشارك كلماتك مع القرّاء.</p>
    </section>

    <section class="panel">
      <h2>اكتب منشوراً</h2>
      <p class="hint">هذه واجهة أولية. النشر الفعلي وحفظ الكتابات سيُفعّلان بعد ربط قاعدة البيانات وتسجيل الدخول.</p>
      <form id="post-form">
        <input id="title" placeholder="عنوان الكتابة" maxlength="200" required>
        <select id="category">
          <option>مقالة</option>
          <option>خاطرة</option>
          <option>شعر</option>
          <option>قصة</option>
          <option>فلسفة</option>
          <option>علم نفس</option>
        </select>
        <textarea id="content" placeholder="اكتب ما يجول في خاطرك..." maxlength="30000" required></textarea>
        <button type="submit">معاينة الكتابة</button>
      </form>
      <div id="preview" aria-live="polite"></div>
    </section>

    <section>
      <h2>مساحة القرّاء</h2>
      <p class="hint">ستظهر الكتابات المنشورة هنا بعد ربط الموقع بقاعدة البيانات.</p>
    </section>
  </main>

  <footer>قَلَم © منصّة عربية للكلمة والفكرة</footer>

  <script>
    document.getElementById("post-form").addEventListener("submit", function(event) {
      event.preventDefault();
      const title = document.getElementById("title").value.trim();
      const category = document.getElementById("category").value;
      const content = document.getElementById("content").value.trim();
      const preview = document.getElementById("preview");
      preview.replaceChildren();

      const heading = document.createElement("h3");
      heading.textContent = title;
      const label = document.createElement("p");
      label.textContent = "التصنيف: " + category;
      const body = document.createElement("p");
      body.style.whiteSpace = "pre-wrap";
      body.textContent = content;

      preview.append(heading, label, body);
    });
  </script>
</body>
</html>
