<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>المكتبة القانونية</title>
  <style>
    body {
      font-family: 'Arial', sans-serif;
      background-color: #e8f5e9;
      margin: 0;
      padding: 0;
      color: #1b5e20;
    }
    header, footer {
      background-color: #1b5e20;
      color: white;
      text-align: center;
      padding: 10px 0;
      position: fixed;
      width: 100%;
      z-index: 999;
    }
    header {
      top: 0;
      animation: marquee 15s linear infinite;
    }
    footer {
      bottom: 0;
      font-size: 14px;
      animation: marquee 30s linear infinite reverse;
    }
    @keyframes marquee {
      0% {transform: translateX(100%);}
      100% {transform: translateX(-100%);}
    }
    main {
      padding: 80px 20px 60px 20px;
    }
    .login-box, .section, .admin-panel, .contact-box, .upload-box {
      background: white;
      padding: 20px;
      margin-bottom: 20px;
      border-radius: 12px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    input, select, button, textarea {
      display: block;
      width: 100%;
      margin: 10px 0;
      padding: 10px;
      border: 1px solid #c8e6c9;
      border-radius: 8px;
    }
    button {
      background-color: #2e7d32;
      color: white;
      font-weight: bold;
      cursor: pointer;
    }
    h1, h2, h3 {
      text-align: center;
    }
    nav {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-around;
      margin-top: 20px;
    }
    .nav-button {
      background: #a5d6a7;
      padding: 30px;
      border-radius: 15px;
      text-align: center;
      width: 45%;
      margin: 10px 0;
      font-weight: bold;
      font-size: 20px;
      cursor: pointer;
    }
    .icon {
      font-size: 40px;
      display: block;
      margin-bottom: 10px;
    }
    .back-button {
      margin-top: 10px;
      background-color: #388e3c;
    }
  </style>
</head>
<body>
  <header id="header-text">مرحبًا بكم في مكتبة المهندس علي محسن الحاضري – مرجعكم القانوني الأول بين أيديكم</header>
  <footer id="footer-text">إعداد المهندس/ علي محسن الحاضري – ت/770892215 – نحن نعمل لأجلكم ولأجل تسهيل وصولكم للقانون</footer>
  <main>
    <section class="login-box">
      <h1>تسجيل الدخول</h1>
      <input type="text" id="username" placeholder="اسم المستخدم أو البريد">
      <input type="password" id="password" placeholder="كلمة المرور">
      <button onclick="login()">دخول</button>
      <button onclick="showRegister()">إنشاء حساب</button>
      <button onclick="forgotPassword()">نسيت كلمة المرور؟</button>
    </section>

    <section id="app" style="display:none">
      <nav>
        <div class="nav-button" onclick="openSection('القانون المدني')"><span class="icon">🏛️</span>القانون المدني</div>
        <div class="nav-button" onclick="openSection('القانون الجنائي')"><span class="icon">⚖️</span>القانون الجنائي</div>
        <div class="nav-button" onclick="openSection('القانون الجزائي')"><span class="icon">⛓️</span>القانون الجزائي</div>
        <div class="nav-button" onclick="openSection('القانون الشخصي')"><span class="icon">‍‍‍👤</span>القانون الشخصي</div>
        <div class="nav-button" onclick="openAdmin()"><span class="icon">🛠️</span>لوحة تحكم الأدمن</div>
        <div class="nav-button" onclick="openContact()"><span class="icon">✉️</span>التواصل</div>
      </nav>
      <section id="section-area" class="section"></section>
    </section>

    <section id="register-box" class="login-box" style="display:none">
      <h2>إنشاء حساب</h2>
      <input type="text" placeholder="الاسم الكامل">
      <input type="email" placeholder="البريد الإلكتروني">
      <input type="password" placeholder="كلمة المرور">
      <button onclick="registerUser()">تسجيل</button>
    </section>
  </main>

  <script>
    const ADMIN_PASSWORD = "123";
    let users = JSON.parse(localStorage.getItem('users') || '{}');

    function login() {
      const u = document.getElementById('username').value;
      const p = document.getElementById('password').value;
      if ((u === 'admin' && p === ADMIN_PASSWORD) || (users[u] && users[u].password === p)) {
        document.querySelector('.login-box').style.display = 'none';
        document.getElementById('app').style.display = 'block';
      } else {
        alert('بيانات الدخول غير صحيحة');
      }
    }

    function showRegister() {
      document.querySelector('.login-box').style.display = 'none';
      document.getElementById('register-box').style.display = 'block';
    }

    function registerUser() {
      const inputs = document.querySelectorAll('#register-box input');
      const name = inputs[0].value;
      const email = inputs[1].value;
      const pass = inputs[2].value;
      users[email] = { name: name, password: pass };
      localStorage.setItem('users', JSON.stringify(users));
      alert('تم إنشاء الحساب بنجاح');
      location.reload();
    }

    function forgotPassword() {
      alert('يرجى التواصل مع الإدارة لاستعادة كلمة المرور.');
    }

    function openSection(section) {
      document.getElementById('section-area').innerHTML = `
        <h2>${section}</h2>
        <input type='text' placeholder='ابحث عن نص أو مادة'>
        <p>هنا سيتم عرض المواد القانونية من قاعدة البيانات المحلية</p>
        <button class='back-button' onclick='goBack()'>رجوع</button>`;
    }

    function openAdmin() {
      document.getElementById('section-area').innerHTML = `
        <h2>لوحة تحكم الأدمن</h2>
        <div class='upload-box'>
          <h3>رفع أو حذف ملفات</h3>
          <input type='file' id='fileUpload'>
          <button onclick='uploadFile()'>رفع</button>
          <button onclick='deleteFile()'>حذف ملف</button>
        </div>
        <div>
          <h3>إدارة المستخدمين</h3>
          <button onclick='grantAdmin()'>إعطاء صلاحية أدمن</button>
          <button onclick='changePasswords()'>تغيير كلمة مرور</button>
        </div>
        <div>
          <h3>إعدادات عامة</h3>
          <input type='text' id='newHeaderText' placeholder='تعديل الشريط العلوي'>
          <input type='text' id='newFooterText' placeholder='تعديل الشريط السفلي'>
          <button onclick='updateHeaderFooter()'>حفظ التعديلات</button>
        </div>
        <button class='back-button' onclick='goBack()'>رجوع</button>
        <p>خيارات أخرى: إدارة المكتبة، إضافة أقسام، تغيير الأيقونة، الوضع الليلي (قريبًا)</p>`;
    }

    function openContact() {
      document.getElementById('section-area').innerHTML = `
        <div class='contact-box'>
          <h3>التواصل عبر البريد</h3>
          <p>راسلنا عبر: example@lawyer.com</p>
          <h3>أو أرسل رسالة مباشرة</h3>
          <textarea placeholder='اكتب رسالتك هنا'></textarea>
          <button>إرسال</button>
          <button class='back-button' onclick='goBack()'>رجوع</button>
        </div>`;
    }

    function updateHeaderFooter() {
      document.getElementById('header-text').innerText = document.getElementById('newHeaderText').value;
      document.getElementById('footer-text').innerText = document.getElementById('newFooterText').value;
    }

    function uploadFile() {
      alert('ميزة رفع الملفات قيد التطوير. سيتم دعم PDF و DOC و TXT قريبًا.');
    }

    function deleteFile() {
      alert('ميزة حذف الملفات قيد التطوير.');
    }

    function grantAdmin() {
      alert('صلاحيات الأدمن قيد التفعيل');
    }

    function changePasswords() {
      alert('ميزة تغيير كلمة المرور للمستخدمين ستُضاف قريبًا');
    }

    function goBack() {
      document.getElementById('section-area').innerHTML = '';
    }
  </script>
</body>
</html>
