# Boudiaf.html
<!DOCTYPE html><html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ثانوية محمد بوضياف - منصة تعليمية متكاملة</title>  <style>
    *{margin:0;padding:0;box-sizing:border-box;font-family:Arial;}
    body{background:#eef3fb;}

    header{
      background:linear-gradient(135deg,#0a4a8a,#2196f3);
      color:white;
      text-align:center;
      padding:35px;
    }

    header h1{font-size:36px;}

    nav{
      background:#083a6b;
      display:flex;
      justify-content:center;
      flex-wrap:wrap;
      position:sticky;
      top:0;
      z-index:10;
    }

    nav button{
      background:none;
      border:none;
      color:white;
      padding:12px 14px;
      cursor:pointer;
      font-size:14px;
    }

    nav button:hover{background:#2196f3;}

    section{display:none;padding:20px;max-width:1200px;margin:auto;}
    .active{display:block;}

    .grid{
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
      gap:15px;
      margin-top:15px;
    }

    .card{
      background:white;
      padding:20px;
      border-radius:12px;
      box-shadow:0 3px 10px rgba(0,0,0,0.1);
    }

    table{
      width:100%;
      background:white;
      border-collapse:collapse;
      margin-top:10px;
      border-radius:10px;
      overflow:hidden;
    }

    th,td{padding:10px;text-align:center;border-bottom:1px solid #ddd;}
    th{background:#2196f3;color:white;}

    input,select,button{
      padding:10px;
      margin-top:10px;
      width:100%;
    }

    button.action{
      background:#2196f3;
      color:white;
      border:none;
      cursor:pointer;
    }

    footer{
      background:#0a4a8a;
      color:white;
      text-align:center;
      padding:15px;
      margin-top:30px;
    }
  </style></head><body><header>
  <h1>ثانوية محمد بوضياف</h1>
  <p>منصة تعليمية ذكية متكاملة</p>
</header><nav>
  <button onclick="show('home')">الرئيسية</button>
  <button onclick="show('stats')">الإحصائيات</button>
  <button onclick="show('streams')">الشعب</button>
  <button onclick="show('schedule')">الدراسة</button>
  <button onclick="show('exams')">الاختبارات</button>
  <button onclick="show('dashboard')">لوحة التحكم</button>
</nav><section id="home" class="active">
  <div class="grid">
    <div class="card"><h2>2200</h2><p>تلميذ</p></div>
    <div class="card"><h2>90</h2><p>قسم</p></div>
    <div class="card"><h2>110</h2><p>أستاذ</p></div>
    <div class="card"><h2>5</h2><p>شعب</p></div>
  </div>
</section><section id="stats">
  <h2>📊 الإحصائيات</h2>
  <div class="grid">
    <div class="card">عدد التلاميذ: 2200</div>
    <div class="card">عدد الأساتذة: 110</div>
    <div class="card">عدد الأقسام: 90</div>
  </div>
</section><section id="streams">
  <h2>📚 الشعب الجزائرية</h2>
  <div class="grid">
    <div class="card">علوم تجريبية</div>
    <div class="card">رياضيات</div>
    <div class="card">تقني رياضي</div>
    <div class="card">آداب وفلسفة</div>
    <div class="card">تسيير واقتصاد</div>
  </div>
</section><section id="schedule">
  <h2>📅 جدول الدراسة</h2>
  <table>
    <tr><th>اليوم</th><th>المادة</th><th>التوقيت</th></tr>
    <tr><td>الأحد</td><td>رياضيات</td><td>08:00</td></tr>
    <tr><td>الاثنين</td><td>فيزياء</td><td>10:00</td></tr>
    <tr><td>الثلاثاء</td><td>فرنسية</td><td>08:00</td></tr>
    <tr><td>الأربعاء</td><td>إنجليزية</td><td>10:00</td></tr>
  </table>
</section><section id="exams">
  <h2>📝 الاختبارات</h2>
  <table>
    <tr><th>المادة</th><th>التاريخ</th><th>الساعة</th></tr>
    <tr><td>رياضيات</td><td>10-06</td><td>09:00</td></tr>
    <tr><td>فيزياء</td><td>12-06</td><td>09:00</td></tr>
    <tr><td>فرنسية</td><td>14-06</td><td>09:00</td></tr>
  </table>
</section><section id="dashboard">
  <h2>🛠 لوحة التحكم المتقدمة</h2>  <div class="card">
    <h3>إضافة تلميذ</h3>
    <input id="student" placeholder="اسم التلميذ">
    <button class="action" onclick="addStudent()">إضافة</button>
  </div>  <div class="card">
    <h3>إضافة علامة</h3>
    <input id="name" placeholder="اسم التلميذ">
    <input id="grade" placeholder="العلامة">
    <button class="action" onclick="addGrade()">حفظ</button>
  </div>  <div class="card">
    <h3>النتائج</h3>
    <table>
      <tr><th>التلميذ</th><th>العلامة</th></tr>
      <tbody id="results"></tbody>
    </table>
  </div>
</section><footer>
© 2026 ثانوية محمد بوضياف - منصة تعليمية متكاملة
</footer><script>
let students=[];
let grades={};

function show(id){
  document.querySelectorAll('section').forEach(s=>s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
}

function addStudent(){
  let v=document.getElementById('student').value;
  if(v){students.push(v);alert('تمت الإضافة');}
}

function addGrade(){
  let n=document.getElementById('name').value;
  let g=document.getElementById('grade').value;
  if(n){grades[n]=g;render();}
}

function render(){
  let t=document.getElementById('results');
  t.innerHTML='';
  for(let k in grades){
    t.innerHTML+=`<tr><td>${k}</td><td>${grades[k]}</td></tr>`;
  }
}

render();
</script></body>
</html>
