<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>منصة التجارب العملية | نواة العلوم التعليمية</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@600;700;800&family=Tajawal:wght@400;500;700&display=swap" rel="stylesheet">
<style>
  :root{
    --turquoise:#14B8A6;
    --turquoise-dark:#0D9488;
    --blue-deep:#1B4B66;
    --bg:#F3FDFB;
    --card:#FFFFFF;
    --ink:#0B2B2E;
    --ink-soft:#4F7072;
    --gold:#F3B94D;
    --coral:#FF6B4A;
    --coral-dark:#E4502F;
    --violet:#8B5CF6;
    --ring: rgba(20,184,166,.16);
    --border: rgba(27,75,102,.12);
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  html{scroll-behavior:smooth;}
  body{font-family:'Tajawal', sans-serif; background:var(--bg); color:var(--ink); line-height:1.8;}
  h1,h2,h3,.brand{font-family:'Cairo', sans-serif;}
  a{text-decoration:none; color:inherit;}
  .container{max-width:1180px; margin:0 auto; padding:0 28px;}
  .eyebrow{
    display:inline-flex; align-items:center; gap:8px; font-family:'Cairo'; font-weight:700; font-size:.85rem;
    color:var(--turquoise-dark); background:var(--ring); padding:6px 16px; border-radius:999px; margin-bottom:16px;
  }
  header{position:sticky; top:0; z-index:100; background:rgba(243,253,251,.9); backdrop-filter:blur(10px); border-bottom:1px solid var(--border);}
  .nav-wrap{display:flex; align-items:center; justify-content:space-between; padding:16px 28px; max-width:1180px; margin:0 auto;}
  .brand{display:flex; align-items:center; gap:10px; font-weight:800; font-size:1.15rem; color:var(--blue-deep);}
  .brand small{display:block; font-family:'Tajawal'; font-weight:500; font-size:.68rem; color:var(--ink-soft);}
  .nav-cta{background:linear-gradient(90deg, var(--turquoise), var(--coral)); color:#fff; padding:11px 22px; border-radius:10px; font-weight:700; font-size:.9rem; border:none; cursor:pointer; font-family:'Cairo';}
  .user-chip{display:none; align-items:center; gap:10px; background:var(--ring); padding:8px 8px 8px 18px; border-radius:999px; font-weight:700; font-size:.9rem; color:var(--blue-deep); cursor:pointer; border:none; font-family:'Tajawal';}
  .user-avatar{width:32px; height:32px; border-radius:50%; background:var(--turquoise); color:#fff; display:flex; align-items:center; justify-content:center; font-family:'Cairo'; font-weight:800; font-size:.9rem;}

  section{padding:56px 0;}
  .sec-head{max-width:680px; margin-bottom:36px;}
  .sec-head h2{font-size:clamp(1.5rem, 3vw, 2rem); color:var(--blue-deep); font-weight:800;}
  .sec-head p{color:var(--ink-soft); margin-top:10px;}

  .hero{padding:64px 0 40px; text-align:center;}
  .hero h1{font-size:clamp(2rem, 4vw, 3rem); font-weight:800; color:var(--blue-deep); margin-bottom:16px;}
  .hero h1 span{color:var(--coral);}
  .hero p{color:var(--ink-soft); font-size:1.05rem; max-width:600px; margin:0 auto;}

  .courses-grid{display:grid; grid-template-columns:repeat(auto-fit, minmax(280px,1fr)); gap:24px;}
  .course-card{background:var(--card); border:1px solid var(--border); border-radius:20px; padding:26px; transition:.2s;}
  .course-card:hover{box-shadow:0 16px 32px rgba(255,107,74,.12); border-color:var(--coral);}
  .course-card h3{color:var(--blue-deep); font-size:1.2rem; font-weight:800; margin-bottom:16px; display:flex; align-items:center; gap:10px;}
  .course-icon{width:38px; height:38px; border-radius:10px; background:var(--ring); display:flex; align-items:center; justify-content:center; font-size:1.2rem; flex-shrink:0;}
  .category-grid{display:grid; grid-template-columns:repeat(2, 1fr); gap:10px;}
  .category-btn{
    background:var(--bg); border:1.5px solid var(--border); border-radius:12px; padding:14px 8px; text-align:center;
    cursor:pointer; font-family:'Cairo'; font-weight:700; font-size:.8rem; color:var(--blue-deep); transition:.2s;
  }
  .category-btn:hover{border-color:var(--coral); background:#fff; color:var(--coral-dark);}
  .category-icon{font-size:1.4rem; display:block; margin-bottom:6px;}

  .modal-overlay{position:fixed; inset:0; background:rgba(11,43,46,.55); backdrop-filter:blur(3px); display:none; align-items:center; justify-content:center; z-index:1000; padding:20px;}
  .modal-overlay.open{display:flex;}
  .modal-box{background:#fff; width:100%; max-width:460px; border-radius:20px; padding:28px; position:relative; max-height:90vh; overflow-y:auto; box-shadow:0 24px 60px rgba(11,43,46,.3);}
  .modal-close{position:absolute; top:14px; left:14px; background:var(--bg); border:none; width:32px; height:32px; border-radius:50%; cursor:pointer; color:var(--ink-soft);}
  .modal-brand{font-family:'Cairo'; font-weight:800; color:var(--blue-deep); font-size:1.05rem; margin-bottom:18px;}

  .field{margin-bottom:16px;}
  .field label{display:block; font-weight:700; font-size:.88rem; color:var(--blue-deep); margin-bottom:6px;}
  .field input, .field textarea, .field select{width:100%; padding:12px 14px; border-radius:10px; border:1.5px solid var(--border); font-family:'Tajawal'; background:var(--bg);}
  .btn-primary{background:linear-gradient(90deg, var(--turquoise), var(--coral)); color:#fff; padding:13px 26px; border-radius:10px; font-weight:700; border:none; cursor:pointer; font-family:'Cairo'; width:100%;}
  .btn-secondary{background:#fff; color:var(--blue-deep); padding:12px 22px; border-radius:10px; font-weight:700; border:2px solid var(--border); cursor:pointer; font-family:'Cairo'; width:100%;}
  .auth-error{display:none; background:#FEF2F2; color:#B42318; border:1px solid #FECACA; padding:10px 14px; border-radius:10px; font-size:.85rem; font-weight:700; margin-bottom:12px;}
  .auth-success{display:none; background:var(--ring); color:var(--turquoise-dark); padding:10px 14px; border-radius:10px; font-size:.85rem; font-weight:700; margin-bottom:12px;}
  .auth-tabs{display:flex; background:var(--bg); border-radius:12px; padding:4px; margin-bottom:18px;}
  .auth-tab{flex:1; text-align:center; padding:10px; border:none; background:none; border-radius:9px; font-family:'Cairo'; font-weight:700; font-size:.9rem; color:var(--ink-soft); cursor:pointer;}
  .auth-tab.active{background:#fff; color:var(--turquoise-dark);}
  .auth-form{display:none; flex-direction:column; gap:12px;}
  .auth-form.active{display:flex;}

  .item-row{display:flex; align-items:center; justify-content:space-between; gap:10px; background:var(--bg); border:1px solid var(--border); border-radius:10px; padding:10px 14px; margin-bottom:8px; font-size:.88rem;}
  .item-row a{color:var(--turquoise-dark); font-weight:700;}
  .item-row button{background:none; border:none; color:#B42318; font-weight:700; cursor:pointer; font-size:.8rem;}
  .admin-step{display:none; flex-direction:column; gap:12px;}
  .admin-step.active{display:flex;}
  hr{border:none; border-top:1px solid var(--border); margin:16px 0;}

  footer{background:var(--blue-deep); color:#fff; padding:36px 0; text-align:center; font-size:.85rem; opacity:.85;}
</style>
</head>
<body>

<header>
  <div class="nav-wrap">
    <div class="brand">منصة التجارب العملية<small>نواة العلوم التعليمية</small></div>
    <button class="nav-cta" id="navAuthBtn" onclick="openAuth('signup')">سجلي الآن</button>
    <button class="user-chip" id="userChip" onclick="toggleUserMenu()">
      <span class="user-avatar" id="userAvatar">م</span>
      <span id="userNameLabel">مرحبًا</span>
    </button>
  </div>
</header>

<div class="modal-overlay" id="authOverlay" onclick="if(event.target===this) closeAuth()">
  <div class="modal-box">
    <button class="modal-close" onclick="closeAuth()">✕</button>
    <div class="modal-brand">منصة التجارب العملية</div>
    <div class="auth-tabs">
      <button class="auth-tab" id="tabSignup" onclick="switchTab('signup')">إنشاء حساب</button>
      <button class="auth-tab" id="tabLogin" onclick="switchTab('login')">تسجيل الدخول</button>
    </div>
    <div class="auth-error" id="authError"></div>
    <div class="auth-success" id="authSuccess"></div>
    <form class="auth-form" id="signupForm" onsubmit="return handleSignup(event)">
      <div class="field"><label>الاسم</label><input type="text" id="suName" required placeholder="اكتبي اسمك"></div>
      <div class="field"><label>اسم المستخدم</label><input type="text" id="suUsername" required placeholder="بدون مسافات"></div>
      <div class="field"><label>كلمة المرور</label><input type="password" id="suPass" required minlength="6" placeholder="٦ أحرف على الأقل"></div>
      <button type="submit" class="btn-primary">إنشاء الحساب</button>
    </form>
    <form class="auth-form" id="loginForm" onsubmit="return handleLogin(event)">
      <div class="field"><label>اسم المستخدم</label><input type="text" id="liUsername" required></div>
      <div class="field"><label>كلمة المرور</label><input type="password" id="liPass" required></div>
      <button type="submit" class="btn-primary">دخول</button>
    </form>
  </div>
</div>

<div class="modal-overlay" id="contentModal" onclick="if(event.target===this) closeContentModal()">
  <div class="modal-box">
    <button class="modal-close" onclick="closeContentModal()">✕</button>
    <div class="modal-brand" id="contentModalTitle">العنوان</div>
    <div id="contentModalLoggedOut" style="display:none; text-align:center; color:var(--ink-soft);">
      <p style="margin-bottom:14px;">سجّلي الدخول أولًا لعرض هذا المحتوى.</p>
      <button class="btn-primary" onclick="closeContentModal(); openAuth('login')">تسجيل الدخول</button>
    </div>
    <div id="contentModalBody"></div>
  </div>
</div>

<div class="modal-overlay" id="taskModal" onclick="if(event.target===this) closeTaskModal()">
  <div class="modal-box">
    <button class="modal-close" onclick="closeTaskModal()">✕</button>
    <div class="modal-brand" id="taskModalTitle">المهام الأدائية</div>
    <div id="taskLoggedOut" style="display:none; text-align:center; color:var(--ink-soft);">
      <p style="margin-bottom:14px;">سجّلي الدخول أولًا لتسليم تقريرك.</p>
      <button class="btn-primary" onclick="closeTaskModal(); openAuth('login')">تسجيل الدخول</button>
    </div>
    <div id="taskBody" style="display:none;">
      <div id="taskCurrentStatus" style="margin-bottom:14px;"></div>
      <div class="field">
        <label>ارفعي ملف تقريرك (أي صيغة)</label>
        <input type="file" id="taskFileInput">
      </div>
      <button class="btn-primary" onclick="submitTask()">تسليم التقرير</button>
      <div class="auth-success" id="taskSuccess" style="display:none; margin-top:12px;"></div>
      <div class="auth-error" id="taskError" style="display:none; margin-top:12px;"></div>
    </div>
  </div>
</div>

<div class="modal-overlay" id="adminOverlay" onclick="if(event.target===this) closeAdmin()">
  <div class="modal-box">
    <button class="modal-close" onclick="closeAdmin()">✕</button>
    <div class="modal-brand">لوحة إدارة منصة التجارب</div>

    <div class="admin-step active" id="adminGateStep">
      <div style="text-align:center; color:var(--ink-soft);">
        <p style="margin-bottom:16px;">لوحة الإدارة متاحة فقط لحساب المعلمة. سجّلي الدخول باسم المستخدم <b>admin</b>.</p>
        <button class="btn-primary" onclick="closeAdmin(); openAuth('login');">تسجيل الدخول كمعلمة</button>
      </div>
    </div>

    <div class="admin-step" id="adminFormStep">
      <h3 style="font-size:1rem; color:var(--blue-deep);">إضافة محتوى (تقرير / مصدر / فيديو)</h3>
      <div class="field">
        <label>المقرر</label>
        <select id="admCourseSelect">
          <option value="c1">كيمياء 1</option>
          <option value="c21">كيمياء 2-1</option>
          <option value="c22">كيمياء 2-2</option>
          <option value="c3">كيمياء 3</option>
        </select>
      </div>
      <div class="field">
        <label>النوع</label>
        <select id="admCategorySelect">
          <option value="reports">📊 التقارير</option>
          <option value="resources">🗂️ مصادر وخرائط</option>
          <option value="videos">🎥 عرض التجارب (فيديو)</option>
        </select>
      </div>
      <div class="field"><label>عنوان العنصر</label><input type="text" id="admItemTitle" placeholder="مثال: تجربة قياس الكثافة"></div>
      <div class="field"><label>رابط مباشر (اختياري)</label><input type="url" id="admItemUrl" placeholder="https://..."></div>
      <div class="field"><label>أو ارفعي ملفًا من جهازك — معاينة مؤقتة فقط</label><input type="file" id="admItemFile"></div>
      <button class="btn-secondary" onclick="addContentItem()">إضافة العنصر</button>
      <div class="auth-success" id="admItemSuccess" style="display:none;"></div>

      <hr>
      <h3 style="font-size:1rem; color:var(--blue-deep);">تسليمات المهام الأدائية</h3>
      <p style="font-size:.82rem; color:var(--ink-soft); margin-bottom:10px;">اختاري المقرر لعرض تقارير الطالبات المُسلَّمة.</p>
      <div class="field">
        <label>المقرر</label>
        <select id="admTaskCourseSelect">
          <option value="c1">كيمياء 1</option>
          <option value="c21">كيمياء 2-1</option>
          <option value="c22">كيمياء 2-2</option>
          <option value="c3">كيمياء 3</option>
        </select>
      </div>
      <button class="btn-secondary" onclick="renderTaskSubmissions()">عرض التسليمات</button>
      <div id="taskSubmissionsWrap" style="margin-top:12px;"></div>
    </div>
  </div>
</div>

<section class="hero">
  <div class="container">
    <span class="eyebrow">🧪 منصة تفاعلية للتجارب العملية</span>
    <h1>تجارب الكيمياء <span>بين يديكِ</span></h1>
    <p>تقارير، مهام أدائية، مصادر إثرائية، ومقاطع فيديو لكل تجربة — منظّمة حسب كل مقرر من مقررات الكيمياء الأربعة.</p>
  </div>
</section>

<section id="courses">
  <div class="container">
    <div class="sec-head">
      <span class="eyebrow">المقررات</span>
      <h2>اختاري مقررك وابدئي</h2>
      <p>كل مقرر يحتوي تقارير التجارب، مهامك الأدائية، مصادر إثرائية، ومقاطع فيديو للتجارب.</p>
    </div>
    <div class="courses-grid" id="coursesGrid"></div>
  </div>
</section>

<footer>
  <div class="container">© 2026 نواة العلوم التعليمية — منصة التجارب العملية. إشراف: المعلمة شيخة المطيري</div>
</footer>

<script type="module">
  import { initializeApp } from "https://www.gstatic.com/firebasejs/12.16.0/firebase-app.js";
  import {
    getFirestore, doc, getDoc, setDoc, collection, getDocs
  } from "https://www.gstatic.com/firebasejs/12.16.0/firebase-firestore.js";
  import {
    getAuth, createUserWithEmailAndPassword, signInWithEmailAndPassword,
    signOut, onAuthStateChanged
  } from "https://www.gstatic.com/firebasejs/12.16.0/firebase-auth.js";

  const firebaseConfig = {
    apiKey: "AIzaSyCcpntSQe5AIi66F5EshrP5rNStK0k9x1A",
    authDomain: "chem-simple.firebaseapp.com",
    projectId: "chem-simple",
    storageBucket: "chem-simple.firebasestorage.app",
    messagingSenderId: "966845874289",
    appId: "1:966845874289:web:f9b8e9a6777972f66adbd0"
  };

  const app = initializeApp(firebaseConfig);
  const db = getFirestore(app);
  const auth = getAuth(app);

  window.fbDB = db;
  window.fbDoc = doc;
  window.fbGetDoc = getDoc;
  window.fbSetDoc = setDoc;
  window.fbCollection = collection;
  window.fbGetDocs = getDocs;

  window.fbAuth = auth;
  window.fbCreateUser = createUserWithEmailAndPassword;
  window.fbSignIn = signInWithEmailAndPassword;
  window.fbSignOut = signOut;
  window.fbCurrentUser = null;
  window.fbAuthReady = false;

  onAuthStateChanged(auth, (user) => {
    window.fbCurrentUser = user;
    window.fbAuthReady = true;
    window.dispatchEvent(new Event('firebase-auth-changed'));
  });

  window.fbReady = true;
  window.dispatchEvent(new Event('firebase-ready'));
</script>

<script>
  // ===== رادع بسيط (مو حماية حقيقية): تعطيل الزر الأيمن واختصارات أدوات المطورين =====
  document.addEventListener('contextmenu', e => e.preventDefault());
  document.addEventListener('keydown', e => {
    const key = e.key.toUpperCase();
    if(key === 'F12') e.preventDefault();
    if(e.ctrlKey && e.shiftKey && (key === 'I' || key === 'J' || key === 'C')) e.preventDefault();
    if(e.ctrlKey && key === 'U') e.preventDefault();
  });

  // ===== Cloudinary config (used for student report uploads — no billing card required) =====
  const CLOUDINARY_CLOUD_NAME = 'bck0limu';
  const CLOUDINARY_UPLOAD_PRESET = 'srultsia';

  function waitForFirebase(){
    return new Promise(resolve => {
      if(window.fbReady) return resolve();
      window.addEventListener('firebase-ready', () => resolve(), {once:true});
    });
  }
  function waitForAuthReady(){
    return new Promise(resolve => {
      if(window.fbAuthReady) return resolve();
      window.addEventListener('firebase-auth-changed', () => resolve(), {once:true});
    });
  }

  const TEACHER_UID = 'KEZbGTEV3xT0e5G8JGjKsZvxf3u2';
  function usernameToEmail(username){
    if(username === 'admin') return 'admin@alkeemiya-albasita.com';
    return username + '@students.alkeemiya-albasita.com';
  }
  function isCurrentUserTeacher(){
    return !!(window.fbCurrentUser && window.fbCurrentUser.uid === TEACHER_UID);
  }
  function getCurrentUid(){
    return window.fbCurrentUser ? window.fbCurrentUser.uid : null;
  }

  async function fsGetDoc(collectionName, docId){
    await waitForFirebase();
    const snap = await window.fbGetDoc(window.fbDoc(window.fbDB, collectionName, docId));
    return snap.exists() ? snap.data() : null;
  }
  async function fsSetDoc(collectionName, docId, data){
    await waitForFirebase();
    await window.fbSetDoc(window.fbDoc(window.fbDB, collectionName, docId), data, {merge:true});
  }
  async function fsGetAllDocs(collectionName){
    await waitForFirebase();
    const snap = await window.fbGetDocs(window.fbCollection(window.fbDB, collectionName));
    const result = {};
    snap.forEach(d => { result[d.id] = d.data(); });
    return result;
  }

  const LAB_SETTINGS_DOC = 'site';
  async function getLabSettings(){
    return (await fsGetDoc('lab_settings', LAB_SETTINGS_DOC)) || {};
  }
  async function updateLabSettings(patch){
    await fsSetDoc('lab_settings', LAB_SETTINGS_DOC, patch);
  }

  async function saveProfile(uid, name, username){
    await fsSetDoc('profiles', uid, {name, username});
  }
  async function getProfile(uid){
    return await fsGetDoc('profiles', uid);
  }
  async function getAllProfiles(){
    return await fsGetAllDocs('profiles');
  }

  const COURSES = [
    {id:'c1', title:'كيمياء 1'},
    {id:'c21', title:'كيمياء 2-1'},
    {id:'c22', title:'كيمياء 2-2'},
    {id:'c3', title:'كيمياء 3'}
  ];
  const CATEGORIES = {
    reports: {title:'التقارير', icon:'📊'},
    tasks: {title:'المهام الأدائية', icon:'📝'},
    resources: {title:'مصادر وخرائط', icon:'🗂️'},
    videos: {title:'عرض التجارب', icon:'🎥'}
  };

  function renderCoursesGrid(){
    const grid = document.getElementById('coursesGrid');
    grid.innerHTML = '';
    COURSES.forEach(course => {
      const card = document.createElement('div');
      card.className = 'course-card';
      let catsHtml = '';
      Object.keys(CATEGORIES).forEach(catId => {
        const cat = CATEGORIES[catId];
        const action = catId === 'tasks' ? `openTaskModal('${course.id}')` : `openContentModal('${course.id}','${catId}')`;
        catsHtml += `<button class="category-btn" onclick="${action}"><span class="category-icon">${cat.icon}</span>${cat.title}</button>`;
      });
      card.innerHTML = `<h3><span class="course-icon">⚗️</span>${course.title}</h3><div class="category-grid">${catsHtml}</div>`;
      grid.appendChild(card);
    });
  }

  // ===== Auth =====
  function openAuth(tab){ document.getElementById('authOverlay').classList.add('open'); switchTab(tab || 'signup'); }
  function closeAuth(){ document.getElementById('authOverlay').classList.remove('open'); hideAuthMessages(); }
  function switchTab(tab){
    hideAuthMessages();
    const isSignup = tab === 'signup';
    document.getElementById('tabSignup').classList.toggle('active', isSignup);
    document.getElementById('tabLogin').classList.toggle('active', !isSignup);
    document.getElementById('signupForm').classList.toggle('active', isSignup);
    document.getElementById('loginForm').classList.toggle('active', !isSignup);
  }
  function showAuthError(msg){ const el = document.getElementById('authError'); el.textContent = msg; el.style.display='block'; document.getElementById('authSuccess').style.display='none'; }
  function showAuthSuccess(msg){ const el = document.getElementById('authSuccess'); el.textContent = msg; el.style.display='block'; document.getElementById('authError').style.display='none'; }
  function hideAuthMessages(){ document.getElementById('authError').style.display='none'; document.getElementById('authSuccess').style.display='none'; }

  function firebaseAuthErrorToArabic(err){
    const code = (err && err.code) || '';
    if(code.includes('email-already-in-use')) return 'اسم المستخدم هذا مسجّل مسبقًا. جرّبي تسجيل الدخول.';
    if(code.includes('weak-password')) return 'كلمة المرور ضعيفة (٦ أحرف على الأقل).';
    if(code.includes('invalid-credential') || code.includes('wrong-password') || code.includes('user-not-found')) return 'اسم المستخدم أو كلمة المرور غير صحيحة.';
    if(code.includes('invalid-email')) return 'اسم المستخدم يحتوي رموزًا غير مقبولة.';
    return 'حدث خطأ غير متوقع، حاولي مرة أخرى.';
  }

  async function handleSignup(e){
    e.preventDefault();
    const name = document.getElementById('suName').value.trim();
    const username = document.getElementById('suUsername').value.trim().toLowerCase().replace(/\s+/g, '');
    const pass = document.getElementById('suPass').value;
    if(!username || username === 'admin'){ showAuthError('الرجاء كتابة اسم مستخدم صالح.'); return false; }
    if(pass.length < 6){ showAuthError('كلمة المرور يجب أن تكون ٦ أحرف على الأقل.'); return false; }
    showAuthSuccess('جارٍ إنشاء الحساب...');
    await waitForFirebase();
    try{
      const cred = await window.fbCreateUser(window.fbAuth, usernameToEmail(username), pass);
      await saveProfile(cred.user.uid, name, username);
      showAuthSuccess('تم إنشاء حسابك بنجاح ✓'); setTimeout(closeAuth, 900);
    }catch(err){ showAuthError(firebaseAuthErrorToArabic(err)); }
    return false;
  }
  async function handleLogin(e){
    e.preventDefault();
    const username = document.getElementById('liUsername').value.trim().toLowerCase().replace(/\s+/g, '');
    const pass = document.getElementById('liPass').value;
    showAuthSuccess('جارٍ التحقق...');
    await waitForFirebase();
    try{
      await window.fbSignIn(window.fbAuth, usernameToEmail(username), pass);
      showAuthSuccess('تم تسجيل الدخول بنجاح ✓'); setTimeout(closeAuth, 900);
    }catch(err){ showAuthError(firebaseAuthErrorToArabic(err)); }
    return false;
  }
  async function logout(){ await waitForFirebase(); await window.fbSignOut(window.fbAuth); }
  function toggleUserMenu(){ if(confirm('تسجيل الخروج من حسابك؟')) logout(); }

  async function renderAuthState(){
    const navBtn = document.getElementById('navAuthBtn');
    const chip = document.getElementById('userChip');
    const uid = getCurrentUid();
    if(uid){
      const profile = await getProfile(uid);
      const displayName = (profile && profile.name) || 'م';
      navBtn.style.display = 'none'; chip.style.display = 'inline-flex';
      document.getElementById('userAvatar').textContent = displayName.trim().charAt(0) || 'م';
      document.getElementById('userNameLabel').textContent = 'مرحبًا، ' + displayName.split(' ')[0];
    }else{
      navBtn.style.display = 'inline-block'; chip.style.display = 'none';
    }
  }
  window.addEventListener('firebase-auth-changed', () => { renderAuthState(); });

  // ===== Content viewing (reports / resources / videos) =====
  async function openContentModal(courseId, categoryId){
    const uid = getCurrentUid();
    document.getElementById('contentModal').classList.add('open');
    const cat = CATEGORIES[categoryId];
    const course = COURSES.find(c => c.id === courseId);
    document.getElementById('contentModalTitle').textContent = cat.icon + ' ' + cat.title + ' — ' + course.title;

    const loggedOut = document.getElementById('contentModalLoggedOut');
    const body = document.getElementById('contentModalBody');
    if(!uid){ loggedOut.style.display = 'block'; body.innerHTML = ''; return; }
    loggedOut.style.display = 'none';

    body.innerHTML = '<p style="color:var(--ink-soft); font-size:.9rem;">جارٍ التحميل...</p>';
    const settings = await getLabSettings();
    const items = ((settings[categoryId] || {})[courseId]) || [];
    if(!items.length){
      body.innerHTML = '<p style="color:var(--ink-soft); font-size:.9rem;">لم يُضف محتوى لهذا القسم بعد.</p>';
      return;
    }
    let html = '';
    items.forEach(item => {
      html += `<div class="item-row"><span>${item.title}</span><a href="${item.url}" target="_blank" rel="noopener">فتح ›</a></div>`;
    });
    body.innerHTML = html;
  }
  function closeContentModal(){ document.getElementById('contentModal').classList.remove('open'); }

  // ===== Performance tasks (student submissions) =====
  let currentTaskCourseId = null;
  async function openTaskModal(courseId){
    currentTaskCourseId = courseId;
    const uid = getCurrentUid();
    const course = COURSES.find(c => c.id === courseId);
    document.getElementById('taskModal').classList.add('open');
    document.getElementById('taskModalTitle').textContent = '📝 المهام الأدائية — ' + course.title;
    document.getElementById('taskSuccess').style.display = 'none';
    document.getElementById('taskError').style.display = 'none';

    const loggedOut = document.getElementById('taskLoggedOut');
    const body = document.getElementById('taskBody');
    if(!uid){ loggedOut.style.display = 'block'; body.style.display = 'none'; return; }
    loggedOut.style.display = 'none'; body.style.display = 'block';

    const data = await fsGetDoc('lab_submissions', uid);
    const sub = data ? data[courseId] : null;
    const statusEl = document.getElementById('taskCurrentStatus');
    if(sub){
      statusEl.innerHTML = `<div class="auth-success" style="display:block;">تم تسليم تقرير سابقًا: <a href="${sub.fileUrl}" target="_blank" rel="noopener">عرض الملف المُسلَّم</a></div>`;
    }else{
      statusEl.innerHTML = '<p style="color:var(--ink-soft); font-size:.85rem;">لم يتم تسليم أي تقرير لهذا المقرر بعد.</p>';
    }
  }
  function closeTaskModal(){ document.getElementById('taskModal').classList.remove('open'); }

  async function submitTask(){
    const uid = getCurrentUid();
    if(!uid) return;
    const fileInput = document.getElementById('taskFileInput');
    const errEl = document.getElementById('taskError');
    const okEl = document.getElementById('taskSuccess');
    if(!fileInput.files || !fileInput.files[0]){
      errEl.textContent = 'الرجاء اختيار ملف أولًا.'; errEl.style.display = 'block'; okEl.style.display = 'none';
      return;
    }
    errEl.style.display = 'none';
    okEl.textContent = 'جارٍ الرفع...'; okEl.style.display = 'block';
    try{
      const file = fileInput.files[0];
      const formData = new FormData();
      formData.append('file', file);
      formData.append('upload_preset', CLOUDINARY_UPLOAD_PRESET);

      const uploadRes = await fetch('https://api.cloudinary.com/v1_1/' + CLOUDINARY_CLOUD_NAME + '/auto/upload', {
        method: 'POST', body: formData
      });
      const uploadData = await uploadRes.json();
      if(!uploadRes.ok || !uploadData.secure_url){
        throw new Error(uploadData.error ? uploadData.error.message : 'فشل الرفع');
      }
      const url = uploadData.secure_url;

      await waitForFirebase();
      const profile = await getProfile(uid);
      const current = await fsGetDoc('lab_submissions', uid);
      const merged = Object.assign({}, current || {});
      merged[currentTaskCourseId] = {
        fileUrl: url, fileName: file.name, submittedAt: new Date().toISOString(),
        name: profile ? profile.name : '', username: profile ? profile.username : ''
      };
      await fsSetDoc('lab_submissions', uid, merged);

      okEl.textContent = 'تم تسليم التقرير بنجاح ✓';
      fileInput.value = '';
    }catch(err){
      okEl.style.display = 'none';
      errEl.textContent = 'حدث خطأ أثناء الرفع، حاولي مرة أخرى.'; errEl.style.display = 'block';
    }
  }

  // ===== Admin panel =====
  function openAdmin(){
    const isTeacher = isCurrentUserTeacher();
    document.getElementById('adminOverlay').classList.add('open');
    document.getElementById('adminGateStep').classList.toggle('active', !isTeacher);
    document.getElementById('adminFormStep').classList.toggle('active', isTeacher);
  }
  function closeAdmin(){ document.getElementById('adminOverlay').classList.remove('open'); }

  async function addContentItem(){
    const courseId = document.getElementById('admCourseSelect').value;
    const categoryId = document.getElementById('admCategorySelect').value;
    const title = document.getElementById('admItemTitle').value.trim();
    const url = document.getElementById('admItemUrl').value.trim();
    const fileInput = document.getElementById('admItemFile');
    const successEl = document.getElementById('admItemSuccess');

    if(!title){ successEl.style.display = 'none'; return; }
    let finalUrl = url;
    if(fileInput.files && fileInput.files[0]){
      finalUrl = URL.createObjectURL(fileInput.files[0]);
    }
    if(!finalUrl){ successEl.style.display = 'none'; return; }

    const settings = await getLabSettings();
    settings[categoryId] = settings[categoryId] || {};
    settings[categoryId][courseId] = settings[categoryId][courseId] || [];
    settings[categoryId][courseId].push({id: Date.now().toString(), title, url: finalUrl});
    await updateLabSettings({[categoryId]: settings[categoryId]});

    document.getElementById('admItemTitle').value = '';
    document.getElementById('admItemUrl').value = '';
    successEl.textContent = 'تمت إضافة العنصر بنجاح ✓'; successEl.style.display = 'block';
  }

  async function renderTaskSubmissions(){
    const courseId = document.getElementById('admTaskCourseSelect').value;
    const wrap = document.getElementById('taskSubmissionsWrap');
    wrap.innerHTML = '<p style="color:var(--ink-soft); font-size:.85rem;">جارٍ التحميل...</p>';
    const allSubs = await fsGetAllDocs('lab_submissions');
    const rows = [];
    Object.keys(allSubs).forEach(uid => {
      const sub = allSubs[uid][courseId];
      if(sub) rows.push(sub);
    });
    if(!rows.length){
      wrap.innerHTML = '<p style="color:var(--ink-soft); font-size:.85rem;">لا توجد تسليمات لهذا المقرر بعد.</p>';
      return;
    }
    rows.sort((a,b) => (a.name||'').localeCompare(b.name||'', 'ar'));
    let html = '';
    rows.forEach(sub => {
      html += `<div class="item-row"><span>${sub.name} (${sub.username})</span><a href="${sub.fileUrl}" target="_blank" rel="noopener">عرض الملف ›</a></div>`;
    });
    wrap.innerHTML = html;
  }

  async function init(){
    await waitForFirebase();
    await waitForAuthReady();
    renderCoursesGrid();
    renderAuthState();
  }
  init();
</script>

</body>
</html>
