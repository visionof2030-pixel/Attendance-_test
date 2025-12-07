<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>سجل متابعة الطلاب - فهد الخالدي</title>
<style>
body {
    font-family: "Tajawal", sans-serif;
    margin: 0;
    padding: 0;
    background: #f7f7f7;
}

header {
    background: linear-gradient(135deg, #1a5276, #2a9d8f);
    color: #fff;
    text-align: center;
    padding: 12px 0;
    box-shadow: 0px 4px 6px rgba(0,0,0,0.1);
}

.header-main {
    font-size: 22px;
    font-weight: bold;
    margin-bottom: 5px;
}

.header-sub {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 20px;
    font-size: 14px;
    margin-top: 5px;
}

.header-sub div {
    padding: 4px 10px;
    background: rgba(255,255,255,0.15);
    border-radius: 4px;
}

.current-date {
    background: rgba(38, 70, 83, 0.8) !important;
    transition: all 0.3s;
}

.date-info {
    font-size: 12px;
    color: #e0f7fa;
    margin-top: 2px;
}

.class-header {
    background: #2a9d8f;
    color: white;
    padding: 8px;
    margin: 15px 0 5px 0;
    border-radius: 5px;
    text-align: center;
    font-size: 16px;
}

.container {
    width: 95%;
    margin: 10px auto;
    background: white;
    padding: 15px;
    border-radius: 10px;
    box-shadow: 0px 4px 10px rgba(0,0,0,0.1);
}

table {
    width: 100%;
    border-collapse: collapse;
    font-size: 12px;
    margin-bottom: 15px;
}

th, td {
    border: 1px solid #ddd;
    padding: 8px;
    text-align: center;
}

th {
    background: #e9f5f4;
    color: #264653;
    font-size: 11px;
    font-weight: bold;
}

td {
    cursor: pointer;
    user-select: none;
}

button {
    margin: 5px;
    padding: 8px 15px;
    border: none;
    border-radius: 5px;
    background: #1a5276;
    color: white;
    font-weight: bold;
    cursor: pointer;
    transition: all 0.3s;
}

button:hover {
    background: #2a9d8f;
    transform: translateY(-2px);
}

.controls {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    margin-bottom: 15px;
    gap: 10px;
}

.admin-panel {
    display: none;
    margin-top: 15px;
    padding: 15px;
    border: 1px solid #1a5276;
    border-radius: 10px;
    background: #f0f8ff;
}

.star-cell {
    color: #ffd700;
    font-size: 16px;
    cursor: pointer;
}

.present {
    background-color: #e8f5e9;
}

.absent {
    background-color: #ffebee;
}

.status-filter {
    margin: 10px 0;
    text-align: center;
}

.status-filter button {
    background: #ddd;
    color: #333;
}

.status-filter button.active {
    background: #2a9d8f;
    color: white;
}

input[type="password"], input[type="text"], select {
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-family: "Tajawal", sans-serif;
}

.class-tabs {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 15px;
    gap: 5px;
}

.class-tab {
    padding: 8px 15px;
    background: #e0e0e0;
    border-radius: 5px;
    cursor: pointer;
    transition: all 0.3s;
}

.class-tab.active {
    background: #2a9d8f;
    color: white;
}

.class-tab:hover {
    background: #c0c0c0;
}

.student-count {
    text-align: center;
    margin: 10px 0;
    color: #264653;
    font-weight: bold;
}

.admin-section {
    margin: 15px 0;
    padding: 10px;
    background: #f9f9f9;
    border-radius: 8px;
    border: 1px solid #ddd;
}

.admin-section h4 {
    margin-top: 0;
    color: #1a5276;
    text-align: center;
    border-bottom: 1px solid #ddd;
    padding-bottom: 8px;
}

.admin-row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 10px 0;
    flex-wrap: wrap;
}

.admin-label {
    font-weight: bold;
    color: #264653;
    min-width: 150px;
}

.admin-input {
    flex: 1;
    min-width: 200px;
}

.semester-info {
    display: inline-block;
    padding: 4px 10px;
    background: #e8f5e9;
    border-radius: 4px;
    color: #2a9d8f;
    font-weight: bold;
    margin-left: 10px;
}

.starred-student {
    background-color: #fffde7 !important;
}

.week-buttons-container {
    display: flex;
    flex-direction: column;
    gap: 15px;
    margin: 15px 0;
}

.semester-weeks {
    background: white;
    border-radius: 8px;
    padding: 15px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.semester-title {
    background: linear-gradient(135deg, #1a5276, #2a9d8f);
    color: white;
    padding: 10px;
    border-radius: 5px;
    margin-bottom: 10px;
    text-align: center;
}

.week-buttons-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
    gap: 8px;
}

.week-button {
    padding: 10px 5px;
    background: #e0e0e0;
    border: 2px solid #ddd;
    border-radius: 5px;
    cursor: pointer;
    font-weight: bold;
    transition: all 0.3s;
    text-align: center;
    position: relative;
}

.week-button:hover {
    background: #d0d0d0;
    transform: translateY(-2px);
}

.week-button.selected {
    background: #4CAF50 !important;
    color: white !important;
    border-color: #388E3C !important;
    box-shadow: 0 2px 5px rgba(0,0,0,0.2);
}

.week-button.holiday {
    background: #ffcccc;
    color: #666;
    cursor: not-allowed;
    opacity: 0.6;
}

.week-button.empty {
    background: #f5f5f5;
    color: #999;
    cursor: not-allowed;
    border-style: dashed;
}

.selected-weeks-display {
    background: #e3f2fd;
    border: 1px solid #2196F3;
    border-radius: 5px;
    padding: 10px;
    margin: 10px 0;
    text-align: center;
}

.export-section {
    background: #fff8e1;
    border: 1px solid #ffb300;
    border-radius: 5px;
    padding: 15px;
    margin-top: 20px;
}

.week-controls {
    display: flex;
    justify-content: center;
    gap: 10px;
    margin-bottom: 15px;
    flex-wrap: wrap;
}

.week-number {
    font-size: 16px;
    font-weight: bold;
    display: block;
}

.week-dates {
    font-size: 10px;
    color: #666;
    display: block;
    margin-top: 2px;
}

.student-management {
    background: #f0f8ff;
    border: 1px solid #2196F3;
    border-radius: 5px;
    padding: 15px;
    margin-top: 20px;
}

.management-form {
    display: flex;
    flex-direction: column;
    gap: 10px;
    margin: 15px 0;
}

.management-form input,
.management-form select {
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-family: "Tajawal", sans-serif;
}

.form-buttons {
    display: flex;
    justify-content: center;
    gap: 10px;
    margin-top: 15px;
}

.loading-spinner {
    display: none;
    text-align: center;
    padding: 20px;
}

.spinner {
    border: 4px solid #f3f3f3;
    border-top: 4px solid #3498db;
    border-radius: 50%;
    width: 40px;
    height: 40px;
    animation: spin 1s linear infinite;
    margin: 0 auto 10px;
}

@keyframes spin {
    0% { transform: rotate(0deg); }
    100% { transform: rotate(360deg); }
}

.week-button:active {
    transform: scale(0.98);
}

@media print {
    button, .admin-panel, .status-filter, .class-tabs, .week-buttons-container, 
    .selected-weeks-display, .export-section, .student-management {
        display: none !important;
    }
    
    table {
        font-size: 10px;
    }
    
    .header-sub {
        background: white;
        color: black;
        border: 1px solid #ccc;
    }
    
    .current-date {
        background: white !important;
        color: black;
        border: 1px solid #ccc;
    }
}
</style>
<!-- مكتبة ummAlQura لحساب التاريخ الهجري -->
<script src="https://cdn.jsdelivr.net/npm/hijri-date/lib/simple.umd.min.js"></script>
</head>
<body>

<header>
    <div class="header-main">سجل متابعة الطلاب للمعلم / فهد الخالدي - المادة / اللغة الإنجليزية</div>
    <div class="header-sub">
        <div>المدرسة: سعيد بن العاص المتوسطة</div>
        <div class="current-date">
            <div>تاريخ اليوم:</div>
            <div id="gregorianDateText">تحميل...</div>
            <div class="date-info" id="hijriDateText">تحميل التاريخ الهجري...</div>
        </div>
    </div>
</header>

<div class="container">
    <div class="controls">
        <button onclick="exportToExcel()">📊 تصدير اليوم Excel</button>
        <button onclick="exportSelectedWeeks()">📅 تصدير الأسابيع المحددة</button>
        <button onclick="printPage()">🖨️ طباعة</button>
        <button onclick="showAllClasses()">👁️ عرض الكل</button>
        <button onclick="showTodayAttendance()">📅 عرض تحضير اليوم</button>
    </div>
    
    <div class="class-tabs" id="classTabs">
        <!-- سيتم إنشاء الألسنة ديناميكياً -->
    </div>
    
    <div class="status-filter">
        <button onclick="filterByStatus('all')" class="active">الكل</button>
        <button onclick="filterByStatus('present')">الحاضرون</button>
        <button onclick="filterByStatus('absent')">الغائبون</button>
        <button onclick="filterByStatus('star')">المتميزون ⭐</button>
    </div>
    
    <div id="tablesContainer">
        <!-- سيتم إنشاء الجداول ديناميكياً -->
    </div>
    
    <div class="student-count" id="studentCount">إجمالي الطلاب: 0</div>
    
    <div style="text-align: center; margin-top: 20px;">
        <input type="password" id="adminPass" placeholder="ادخل كلمة المرور للإدارة" style="width: 200px;">
        <button onclick="checkAdmin()">🔓 فتح الإدارة</button>
    </div>

    <div class="admin-panel" id="adminPanel">
        <h3 style="text-align:center; margin-top:0; color: #1a5276;">لوحة الإدارة - الخصائص الإدارية</h3>
        
        <div class="admin-section">
            <h4>🎓 إعدادات الفصل الدراسي</h4>
            <div class="admin-row">
                <div class="admin-label">الفصل الدراسي:</div>
                <div class="admin-input">
                    <select id="semesterSelect" onchange="updateSemester()" style="width: 100%;">
                        <option value="1">الترم الأول</option>
                        <option value="2" selected>الترم الثاني</option>
                    </select>
                </div>
            </div>
            <div class="admin-row">
                <div class="admin-label">السنة الدراسية:</div>
                <div class="admin-input">
                    <input type="text" id="academicYear" value="١٤٤٦-١٤٤٧هـ" style="width: 100%;">
                </div>
            </div>
            <div style="text-align: center; margin-top: 10px;">
                <button onclick="saveSemesterSettings()">💾 حفظ إعدادات الفصل</button>
                <span class="semester-info" id="currentSemesterInfo">الترم الثاني ١٤٤٦-١٤٤٧هـ</span>
            </div>
        </div>
        
        <div class="admin-section">
            <h4>📅 التحضير الأسبوعي (الأسابيع الدراسية الفعلية)</h4>
            
            <div class="selected-weeks-display" id="selectedWeeksDisplay">
                <strong>الأسابيع المحددة:</strong> <span id="selectedWeeksText">لا توجد أسابيع محددة</span>
                <br>
                <span id="selectedWeeksCount">0 أسبوع | 0 يوم</span>
            </div>
            
            <div class="week-controls">
                <button onclick="selectAllWeeks()">📋 تحديد الكل</button>
                <button onclick="clearSelectedWeeks()">🗑️ مسح الكل</button>
                <button onclick="selectFirstSemesterWeeks()">📚 الترم الأول (1-19)</button>
            </div>
            
            <div class="week-buttons-container">
                <div class="semester-weeks">
                    <div class="semester-title">الترم الأول (الأسابيع 1-19)</div>
                    <div class="week-buttons-grid" id="firstSemesterWeeks">
                        <!-- سيتم إنشاء أزرار الأسابيع 1-19 هنا -->
                    </div>
                </div>
                
                <div class="semester-weeks">
                    <div class="semester-title">الترم الثاني (سيتم إضافة الأسابيع لاحقاً)</div>
                    <div class="week-buttons-grid" id="secondSemesterWeeks">
                        <!-- سيتم إنشاء أزرار فارغة للترم الثاني -->
                        <div class="week-button empty" title="سيتم إضافة الأسابيع لاحقاً">قيد الإضافة</div>
                    </div>
                </div>
            </div>
            
            <div style="text-align: center; margin-top: 20px;">
                <button onclick="randomAttendanceForSelectedWeeks()" style="background: #4CAF50; padding: 12px 24px; font-size: 16px;">
                    🎲 تحضير عشوائي للأسابيع المحددة
                </button>
            </div>
        </div>
        
        <div class="export-section">
            <h4>📤 تصدير التقارير</h4>
            <div style="text-align: center; margin-top: 10px;">
                <button onclick="exportSelectedWeeks()" style="background: #4CAF50; padding: 12px 24px; font-size: 14px;">
                    📥 تصدير الأسابيع المحددة إلى Excel
                </button>
                <button onclick="exportAllWeeks()" style="background: #2196F3; padding: 12px 24px; font-size: 14px;">
                    📚 تصدير جميع أسابيع الترم الأول
                </button>
            </div>
        </div>
        
        <div class="student-management">
            <h4>👨‍🏫 إدارة الطلاب</h4>
            
            <div class="loading-spinner" id="loadingSpinner">
                <div class="spinner"></div>
                جاري المعالجة...
            </div>
            
            <div class="management-form">
                <h5>➕ إضافة طالب جديد</h5>
                <input type="text" id="newStudentName" placeholder="اسم الطالب الجديد" style="width: 100%;">
                
                <div class="admin-row">
                    <div class="admin-label">الصف:</div>
                    <div class="admin-input">
                        <select id="newStudentClass" style="width: 100%;">
                            <option value="3-1">3-1</option>
                            <option value="2-3">2-3</option>
                            <option value="3-3">3-3</option>
                            <option value="4-3">4-3</option>
                            <option value="5-3">5-3</option>
                        </select>
                    </div>
                </div>
                
                <div class="form-buttons">
                    <button onclick="addStudent()" style="background: #4CAF50;">➕ إضافة الطالب</button>
                    <button onclick="clearStudentForm()" style="background: #f44336;">🗑️ مسح النموذج</button>
                </div>
            </div>
            
            <div class="management-form">
                <h5>↔️ نقل طالب بين الصفوف</h5>
                
                <div class="admin-row">
                    <div class="admin-label">اختر الطالب:</div>
                    <div class="admin-input">
                        <select id="studentToMove" style="width: 100%;" onchange="updateStudentMoveInfo()">
                            <option value="">-- اختر الطالب --</option>
                        </select>
                    </div>
                </div>
                
                <div class="admin-row">
                    <div class="admin-label">الصف الحالي:</div>
                    <div class="admin-input">
                        <input type="text" id="currentStudentClass" readonly style="width: 100%; background: #f5f5f5;">
                    </div>
                </div>
                
                <div class="admin-row">
                    <div class="admin-label">الصف الهدف:</div>
                    <div class="admin-input">
                        <select id="targetClass" style="width: 100%;">
                            <option value="3-1">3-1</option>
                            <option value="2-3">2-3</option>
                            <option value="3-3">3-3</option>
                            <option value="4-3">4-3</option>
                            <option value="5-3">5-3</option>
                        </select>
                    </div>
                </div>
                
                <div class="form-buttons">
                    <button onclick="moveStudent()" style="background: #2196F3;">↔️ نقل الطالب</button>
                    <button onclick="refreshStudentList()" style="background: #FF9800;">🔄 تحديث القائمة</button>
                </div>
            </div>
            
            <div style="text-align:center; margin-top:15px;">
                <button onclick="randomAttendance()" style="background: #9C27B0;">🎲 تحضير عشوائي للتاريخ الحالي</button>
            </div>
        </div>
        
        <div style="text-align:center; margin-top:20px;">
            <button onclick="checkAdmin()" style="background: #f44336; padding: 10px 30px; font-size: 16px;">
                🔒 إغلاق لوحة الإدارة
            </button>
        </div>
    </div>
</div>

<script>
// بيانات الطلاب لكل صف (محدثة حسب القائمة المقدمة)
const studentsData = {
    "3-1": [
        "إسماعيل محمد هاشم شفيق الرحمن",
        "ابراهيم علي ابو بكر محمد",
        "باسم محمد ابو طالب",
        "حسين بشير أمادو جازير",
        "حسين هارون عثمان عبدالمؤمن ادم",
        "حمد محمد عثمان بخش",
        "رمضان عيسى باكور محمد",
        "ريان عبد الرحمن موسى جيبو",
        "ريحان محمد مقبول حسين عمر حمزه",
        "عامر مولوي حسن شريف",
        "عبدالحليم نور كبير صديق احمد",
        "عمران يعقوب محمد محمد مسلم",
        "عمير محمد محمد شفيع حكيم علي",
        "فارس محمد ابو البشر واعظ علي",
        "محمد احمد فضل الرحمن فايز اللّٰه",
        "حمد انوار رشيد احمد اظهار مياه",
        "حمد عبدالرزاق محمد عبدالقادر",
        "حمد عبدالشكور عبدالحميد عبد الرشيد",
        "مهدي محمد محمد اسلام عبدالسلام",
        "مهدي موسى حميد الحق احمد",
        "ياسين محمد يوسف"
    ],
    "2-3": [
        "إبراهيم إدريس إبراهيم اولوجيوم",
        "إدريس محمد حسن أحمد",
        "امين عبداللّه دايابو عثمان",
        "بسام عبدالسلام هاشم انور علي",
        "حافظ بيلو موسى سليمان",
        "حسين علي حسن مهاوش",
        "خالد طيب اسماعيل محمد",
        "خالد عبد الحميد محمد هاشم",
        "خالد وليد محمد محمد",
        "ريان عبدالرحمن عمر نانتومي",
        "سليمان ابراهيم ديقوقا",
        "صالح عبدالله محمد قاسم يوسف علي",
        "عبدالعزيز اول اودو محمد",
        "عثمان عبد الرحمن باي محمد",
        "عدنان نور امير حسين",
        "عمر سراج محمد زكريا",
        "فهد محمد حسين عبداللّه مياه حسين",
        "محمد ابراهيم سعيد هو ساوي",
        "محمد محمد امين اسلام خليل الرحمن",
        "مشعل ابو طاهر ناظر حسين عبدالمطلب",
        "موسى ابو بكر الصديق عبدالجبار امة علي",
        "يوسف مهدي عابدين محمد"
    ],
    "3-3": [
        "ابراهيم جزولي اسدانور",
        "تركي عبدالصمد عبدالغني محمد حسين",
        "حسام حسن ابو الكلام مقبول احمد",
        "حسن عيسى بكوري محمد",
        "سعد سلام ستار ارشاد اللّٰه",
        "عايض سيف الاسلام نور احمد علي",
        "عبدالكريم عثمان ابكر كوجو",
        "عزام شمس العالم قاسم علي",
        "عماد محمد صديق محمد شفيع سيد",
        "عمر عبد القدوس عبدالسلام عبد السبحان",
        "عمر مورتلا أبو بكر محمد",
        "فيصل احمد ابو بكر محمد",
        "محمد اسحاق محمد اسلام عبدالحكيم",
        "محمد عبدالله ابو سعيد مياه",
        "حمد محمد اسماعيل امير حسين ابو بكر",
        "حمد موسى ساليفو ديقوقا",
        "مشاري شيهو اسماعيل محمد بكر",
        "ياسر عبدالرحيم محمد علي سفر علي",
        "يوسف محمد عبد الرحمن علي"
    ],
    "4-3": [
        "ابراهيم عوض احمد فليس",
        "احمد ابراهيم ابن زكريا الهوسه",
        "احمد عبد القيوم محمد يعقوب",
        "اسماعيل اول اودو محمد",
        "اوسامة سعيدو دو غويد",
        "تامر عبد الصمد عبد الغني",
        "تركي هارون حسن شريف",
        "ريان محمد مقبول حسين حسين",
        "ريان هارون الرشيد طفيل احمد نذير احمد",
        "عبدالحليم محمد عبدالله عبدالحكيم",
        "عبدالله حفيظ اللّٰه سلطان أحمد",
        "عيسى عثمان سعيد عالم حبيب الرحمن",
        "فهد أسار رشيد احمد",
        "فهد محمد نور مقبول اشرف",
        "محمد محمد ادريس نبية حسين يعقوب علي",
        "مصلح محمد ولي احمد",
        "معاذ عثمان صديق كالو",
        "يوسف بدماسي ابراهيم البد ماسي"
    ],
    "5-3": [
        "ابراهيم خالد سليمان ابراهيم",
        "انس عبدالعزيز نور احمد",
        "بدر بكر عمر محمد",
        "حمد محمد حسين مياه شمس العالم اظهر مياه",
        "رضوان رشيد أحمد نور محمد لال مياه",
        "سعيد عبدالله سعيد محمد",
        "عامر رحمة اللّٰه محمد شفيع",
        "عبد اللّٰه حسين علي فليس",
        "عبد العزيز سراج ابكر عثمان",
        "عبدالله عيسى ابراهيم",
        "عمر محمد عمر صالح",
        "غسان عثمان اسماعيل عبدالله عبد اللّٰه",
        "فاضل عادل صالح الرايس",
        "محمد فريد كبير احمد عباد اللّٰه",
        "محمد محمد سلطان احمد محمد",
        "محمد موسى أدامو محمد",
        "محمد نور محمد زكريا آمال حسين",
        "مشاري محمد هارو",
        "مشاري يعقوب أبو بكر ابراهيم",
        "منذر علي عمر قوني",
        "هود حسن عبدالكريم الياس",
        "يعقوب محمد إسحاق يار محمد فضل على"
    ]
};

// بيانات الأسابيع الدراسية للترم الأول (1-19)
const studyWeeks = {
    1: { name: "الأسبوع 1", days: 5, startDate: "2025/08/24", endDate: "2025/08/28" },
    2: { name: "الأسبوع 2", days: 5, startDate: "2025/08/31", endDate: "2025/09/04" },
    3: { name: "الأسبوع 3", days: 5, startDate: "2025/09/07", endDate: "2025/09/11" },
    4: { name: "الأسبوع 4", days: 5, startDate: "2025/09/14", endDate: "2025/09/18" },
    5: { name: "الأسبوع 5", days: 5, startDate: "2025/09/21", endDate: "2025/09/25" },
    6: { name: "الأسبوع 6", days: 5, startDate: "2025/09/28", endDate: "2025/10/02" },
    7: { name: "الأسبوع 7", days: 5, startDate: "2025/10/05", endDate: "2025/10/09" },
    8: { name: "الأسبوع 8", days: 4, startDate: "2025/10/13", endDate: "2025/10/16" },
    9: { name: "الأسبوع 9", days: 5, startDate: "2025/10/19", endDate: "2025/10/23" },
    10: { name: "الأسبوع 10", days: 5, startDate: "2025/10/26", endDate: "2025/10/30" },
    11: { name: "الأسبوع 11", days: 5, startDate: "2025/11/02", endDate: "2025/11/06" },
    12: { name: "الأسبوع 12", days: 5, startDate: "2025/11/09", endDate: "2025/11/13" },
    13: { name: "الأسبوع 13", days: 5, startDate: "2025/11/16", endDate: "2025/11/20" },
    14: { name: "الأسبوع 14", days: 0, startDate: "إجازة", endDate: "إجازة", holiday: true },
    15: { name: "الأسبوع 15", days: 4, startDate: "2025/11/30", endDate: "2025/12/03" },
    16: { name: "الأسبوع 16", days: 4, startDate: "2025/12/08", endDate: "2025/12/11" },
    17: { name: "الأسبوع 17", days: 5, startDate: "2025/12/14", endDate: "2025/12/18" },
    18: { name: "الأسبوع 18", days: 5, startDate: "2025/12/21", endDate: "2025/12/25" },
    19: { name: "الأسبوع 19", days: 5, startDate: "2025/12/28", endDate: "2026/01/01" }
};

// حالة الإدارة
let adminActive = false;
let currentFilter = 'all';
let currentClass = 'all';

// إعدادات الفصل الدراسي
let semesterSettings = {
    semester: "2",
    academicYear: "١٤٤٦-١٤٤٧هـ"
};

// الأسابيع المحددة
let selectedWeeks = [];

// بيانات التحضير المخزنة لكل يوم
let periodAttendanceData = {};

// تحويل الأرقام الإنجليزية إلى عربية
function convertToArabicNumbers(num) {
    const arabicNumbers = ['٠', '١', '٢', '٣', '٤', '٥', '٦', '٧', '٨', '٩'];
    return num.toString().replace(/\d/g, digit => arabicNumbers[digit]);
}

// تهيئة الصفحة
function initPage() {
    // محاولة تحميل إعدادات الفصل الدراسي
    const savedSemester = localStorage.getItem('teacherTracker_semesterSettings');
    if (savedSemester) {
        semesterSettings = JSON.parse(savedSemester);
        document.getElementById('semesterSelect').value = semesterSettings.semester;
        document.getElementById('academicYear').value = semesterSettings.academicYear;
        updateSemesterInfo();
    }
    
    // محاولة تحميل الأسابيع المحددة
    const savedWeeks = localStorage.getItem('teacherTracker_selectedWeeks');
    if (savedWeeks) {
        selectedWeeks = JSON.parse(savedWeeks);
    }
    
    // محاولة تحميل بيانات التحضير المحفوظة
    loadPeriodAttendanceData();
    
    createClassTabs();
    createTables();
    createWeekButtons();
    updateStudentCount();
    updateDateDisplay();
    refreshStudentList();
    updateWeekButtons(); // تأكد من تحديث أزرار الأسابيع عند التحميل
    
    // تحديث التاريخ تلقائياً
    updateCurrentDate();
    setInterval(updateCurrentDate, 60000);
}

// تحديث التاريخ الحالي
function updateCurrentDate() {
    const now = new Date();
    const hijriDate = calculateHijriDate(now);
    
    document.getElementById('gregorianDateText').innerHTML = formatGregorianDate(now);
    document.getElementById('hijriDateText').innerHTML = hijriDate;
}

// تنسيق التاريخ الميلادي
function formatGregorianDate(date) {
    const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
    const dateStr = date.toLocaleDateString('ar-SA', options);
    return dateStr.replace(/\d/g, d => convertToArabicNumbers(d));
}

// حساب التاريخ الهجري
function calculateHijriDate(gregorianDate) {
    try {
        if (typeof HijriDate !== 'undefined') {
            const hijri = new HijriDate(gregorianDate);
            const hijriDay = convertToArabicNumbers(hijri.date);
            const hijriMonth = getHijriMonthName(hijri.month);
            const hijriYear = convertToArabicNumbers(hijri.year);
            return `${hijriDay} ${hijriMonth} ${hijriYear}هـ`;
        }
    } catch (error) {
        console.error("Error calculating Hijri date:", error);
    }
    return "١٤٤٧هـ";
}

// الحصول على اسم الشهر الهجري
function getHijriMonthName(month) {
    const hijriMonths = [
        "محرم", "صفر", "ربيع الأول", "ربيع الثاني", 
        "جمادى الأولى", "جمادى الآخرة", "رجب", "شعبان", 
        "رمضان", "شوال", "ذو القعدة", "ذو الحجة"
    ];
    return hijriMonths[month - 1] || "";
}

// إنشاء أزرار الأسابيع
function createWeekButtons() {
    const firstSemesterContainer = document.getElementById('firstSemesterWeeks');
    firstSemesterContainer.innerHTML = '';
    
    // إنشاء أزرار للأسابيع 1-19
    for (let week = 1; week <= 19; week++) {
        const weekData = studyWeeks[week];
        const button = document.createElement('button');
        button.className = 'week-button';
        button.id = `week-${week}`;
        button.setAttribute('data-week', week);
        
        if (weekData.holiday) {
            button.classList.add('holiday');
            button.innerHTML = `
                <span class="week-number">${week}</span>
                <span class="week-dates">إجازة</span>
            `;
            button.title = `${weekData.name} - إجازة`;
            button.disabled = true;
        } else {
            button.innerHTML = `
                <span class="week-number">${week}</span>
                <span class="week-dates">${formatDateForDisplay(weekData.startDate)} - ${formatDateForDisplay(weekData.endDate)}</span>
                <span style="font-size:10px; color:#666;">(${weekData.days} أيام)</span>
            `;
            button.title = `${weekData.name} - ${weekData.days} أيام دراسية`;
            
            // إضافة حدث النقر بشكل صحيح
            button.addEventListener('click', function() {
                toggleWeekSelection(week);
            });
        }
        
        firstSemesterContainer.appendChild(button);
    }
    
    updateWeekButtons();
    updateSelectedWeeksDisplay(); // تحديث العرض بعد إنشاء الأزرار
}

// تنسيق التاريخ للعرض
function formatDateForDisplay(dateStr) {
    if (dateStr === "إجازة") return dateStr;
    const parts = dateStr.split('/');
    return `${parts[1]}/${parts[2].slice(-2)}`;
}

// تبديل اختيار الأسبوع
function toggleWeekSelection(week) {
    console.log('Toggle week:', week); // للمساعدة في التصحيح
    
    const index = selectedWeeks.indexOf(week);
    if (index === -1) {
        selectedWeeks.push(week);
        console.log('Added week:', week, 'Selected weeks:', selectedWeeks);
    } else {
        selectedWeeks.splice(index, 1);
        console.log('Removed week:', week, 'Selected weeks:', selectedWeeks);
    }
    
    // ترتيب الأسابيع تصاعدياً
    selectedWeeks.sort((a, b) => a - b);
    
    updateWeekButtons();
    updateSelectedWeeksDisplay();
    saveSelectedWeeks();
}

// تحديث مظهر أزرار الأسابيع
function updateWeekButtons() {
    console.log('Updating week buttons, selected weeks:', selectedWeeks);
    
    for (let week = 1; week <= 19; week++) {
        const button = document.getElementById(`week-${week}`);
        if (button && !button.disabled) {
            if (selectedWeeks.includes(week)) {
                button.classList.add('selected');
                console.log('Week', week, 'is selected');
            } else {
                button.classList.remove('selected');
            }
        }
    }
}

// تحديث عرض الأسابيع المحددة
function updateSelectedWeeksDisplay() {
    const displayElement = document.getElementById('selectedWeeksText');
    const countElement = document.getElementById('selectedWeeksCount');
    
    if (selectedWeeks.length === 0) {
        displayElement.textContent = "لا توجد أسابيع محددة";
        countElement.textContent = "0 أسبوع | 0 يوم";
    } else {
        const weekNames = selectedWeeks.map(w => studyWeeks[w].name).join('، ');
        
        // حساب عدد الأيام
        let totalDays = 0;
        selectedWeeks.forEach(weekNum => {
            totalDays += studyWeeks[weekNum].days;
        });
        
        displayElement.textContent = `${weekNames}`;
        countElement.textContent = `${selectedWeeks.length} أسبوع | ${totalDays} يوم`;
    }
}

// حفظ الأسابيع المحددة
function saveSelectedWeeks() {
    localStorage.setItem('teacherTracker_selectedWeeks', JSON.stringify(selectedWeeks));
}

// تحديد جميع الأسابيع (باستثناء الإجازات)
function selectAllWeeks() {
    selectedWeeks = [];
    for (let week = 1; week <= 19; week++) {
        if (!studyWeeks[week].holiday) {
            selectedWeeks.push(week);
        }
    }
    updateWeekButtons();
    updateSelectedWeeksDisplay();
    saveSelectedWeeks();
    alert(`تم تحديد جميع أسابيع الترم الأول (${selectedWeeks.length} أسبوع)`);
}

// مسح جميع الأسابيع
function clearSelectedWeeks() {
    selectedWeeks = [];
    updateWeekButtons();
    updateSelectedWeeksDisplay();
    saveSelectedWeeks();
    alert("تم مسح جميع الأسابيع المحددة");
}

// تحديد أسابيع الترم الأول
function selectFirstSemesterWeeks() {
    selectAllWeeks();
}

// تحديث معلومات الفصل الدراسي المعروضة
function updateSemesterInfo() {
    const semesterNames = {
        "1": "الترم الأول",
        "2": "الترم الثاني"
    };
    
    const semesterName = semesterNames[semesterSettings.semester] || "الترم الدراسي";
    document.getElementById('currentSemesterInfo').textContent = 
        `${semesterName} ${semesterSettings.academicYear}`;
}

// تحديث إعدادات الفصل الدراسي
function updateSemester() {
    semesterSettings.semester = document.getElementById('semesterSelect').value;
    semesterSettings.academicYear = document.getElementById('academicYear').value;
    updateSemesterInfo();
}

// حفظ إعدادات الفصل الدراسي
function saveSemesterSettings() {
    updateSemester();
    localStorage.setItem('teacherTracker_semesterSettings', JSON.stringify(semesterSettings));
    alert(`✅ تم حفظ إعدادات الفصل الدراسي`);
}

// تحميل بيانات التحضير المحفوظة للفترة
function loadPeriodAttendanceData() {
    const savedData = localStorage.getItem('teacherTracker_periodAttendanceData');
    if (savedData) {
        periodAttendanceData = JSON.parse(savedData);
    }
}

// حفظ بيانات التحضير للفترة
function savePeriodAttendanceData() {
    localStorage.setItem('teacherTracker_periodAttendanceData', JSON.stringify(periodAttendanceData));
}

// تحضير عشوائي للأسابيع المحددة
function randomAttendanceForSelectedWeeks() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    if (selectedWeeks.length === 0) {
        alert("⚠️ لم تحدد أي أسابيع!\n\nالرجاء اختيار أسبوع أو أكثر من القائمة");
        return;
    }
    
    // حساب عدد الأيام
    let totalDays = 0;
    selectedWeeks.forEach(weekNum => {
        totalDays += studyWeeks[weekNum].days;
    });
    
    const confirmMessage = `🎲 تحضير عشوائي للأسابيع المحددة\n\n` +
                          `✅ الأسابيع: ${selectedWeeks.map(w => studyWeeks[w].name).join(', ')}\n` +
                          `📅 عدد الأيام: ${totalDays} يوم\n\n` +
                          `⭐ سيتم وضع ✓ لكل الخيارات للطلاب المتميزين (الذين لديهم نجمة ⭐)\n\n` +
                          `هل تريد المتابعة؟`;
    
    const confirmAction = confirm(confirmMessage);
    if (!confirmAction) return;
    
    // عرض مؤشر التحميل
    showLoading(true);
    
    // محاكاة المعالجة
    setTimeout(() => {
        let totalStudentsProcessed = 0;
        let totalStarredStudents = 0;
        let totalDaysProcessed = 0;
        
        // معالجة كل أسبوع
        selectedWeeks.forEach(weekNum => {
            const week = studyWeeks[weekNum];
            
            // معالجة كل يوم في الأسبوع
            for (let day = 1; day <= week.days; day++) {
                // إنشاء تاريخ افتراضي
                const date = new Date();
                date.setDate(date.getDate() + (weekNum - 1) * 7 + day);
                
                // إنشاء تحضير عشوائي لهذا اليوم
                const attendanceData = generateRandomAttendanceForDate(date);
                const dateKey = date.toISOString().split('T')[0];
                
                // حفظ بيانات اليوم
                periodAttendanceData[dateKey] = attendanceData;
                
                // حساب الإحصائيات لهذا اليوم
                let dayStudents = 0;
                let dayStarred = 0;
                
                for (const className in attendanceData.classes) {
                    dayStudents += attendanceData.classes[className].stats.total;
                    dayStarred += attendanceData.classes[className].stats.starred;
                }
                
                // تحديث المجاميع
                totalStudentsProcessed += dayStudents;
                totalStarredStudents += dayStarred;
                totalDaysProcessed++;
            }
        });
        
        // حفظ بيانات الفترة
        savePeriodAttendanceData();
        
        // إخفاء مؤشر التحميل
        showLoading(false);
        
        // حساب الإحصائيات
        const avgStudentsPerDay = totalStudentsProcessed / totalDaysProcessed;
        const avgStarredPerDay = totalStarredStudents / totalDaysProcessed;
        const avgRegularPerDay = (totalStudentsProcessed - totalStarredStudents) / totalDaysProcessed;
        
        // عرض تقرير النتائج
        const resultMessage = `✅ تم إنشاء التحضير العشوائي بنجاح!\n\n` +
                             `📊 الإحصائيات النهائية:\n` +
                             `   - عدد الأسابيع: ${selectedWeeks.length}\n` +
                             `   - عدد الأيام: ${totalDaysProcessed}\n` +
                             `   - إجمالي الطلاب المعالجين: ${totalStudentsProcessed}\n` +
                             `   - متوسط الطلاب في اليوم: ${avgStudentsPerDay.toFixed(1)}\n` +
                             `   - متوسط الطلاب المتميزين في اليوم: ${avgStarredPerDay.toFixed(1)}\n` +
                             `   - متوسط الطلاب العاديين في اليوم: ${avgRegularPerDay.toFixed(1)}\n\n` +
                             `💾 تم حفظ بيانات التحضير في النظام.\n` +
                             `📥 يمكنك الآن تصدير التقرير باستخدام زر "تصدير الأسابيع المحددة"`;
        
        alert(resultMessage);
    }, 1500);
}

// توليد تحضير عشوائي ليوم معين
function generateRandomAttendanceForDate(date) {
    const dateKey = date.toISOString().split('T')[0];
    
    const attendanceData = {
        date: dateKey,
        gregorianDate: formatGregorianDate(date),
        hijriDate: calculateHijriDate(date),
        classes: {}
    };
    
    // توليد بيانات لكل صف
    for (const className in studentsData) {
        attendanceData.classes[className] = {
            students: [],
            stats: {
                total: 0,
                present: 0,
                absent: 0,
                starred: 0
            }
        };
        
        studentsData[className].forEach((studentName, index) => {
            // تحديد عشوائياً إذا كان الطالب متميزاً (30% احتمال)
            const isStarred = Math.random() < 0.3;
            
            // إنشاء بيانات الطالب
            const studentData = {
                id: index + 1,
                name: studentName,
                isStarred: isStarred,
                attendance: [],
                hasStar: isStarred
            };
            
            // توليد بيانات الحضور (5 عناصر)
            for (let i = 0; i < 5; i++) {
                if (isStarred) {
                    // الطلاب المتميزون يحصلون على ✓ في كل الخيارات
                    studentData.attendance.push({
                        type: ['الحضور', 'الواجبات', 'المشروعات', 'تطبيقات وأنشطة', 'مشاركة'][i],
                        value: '✔',
                        isPresent: true
                    });
                    attendanceData.classes[className].stats.present++;
                } else {
                    // الطلاب العاديون يحصلون على تقييم عشوائي
                    const isPresent = Math.random() > 0.25; // 75% حضور
                    studentData.attendance.push({
                        type: ['الحضور', 'الواجبات', 'المشروعات', 'تطبيقات وأنشطة', 'مشاركة'][i],
                        value: isPresent ? '✔' : '✖',
                        isPresent: isPresent
                    });
                    
                    if (isPresent) {
                        attendanceData.classes[className].stats.present++;
                    } else {
                        attendanceData.classes[className].stats.absent++;
                    }
                }
            }
            
            attendanceData.classes[className].students.push(studentData);
            attendanceData.classes[className].stats.total++;
            
            if (isStarred) {
                attendanceData.classes[className].stats.starred++;
            }
        });
    }
    
    return attendanceData;
}

// عرض/إخفاء مؤشر التحميل
function showLoading(show) {
    const spinner = document.getElementById('loadingSpinner');
    if (show) {
        spinner.style.display = 'block';
    } else {
        spinner.style.display = 'none';
    }
}

// تصدير الأسابيع المحددة إلى Excel
function exportSelectedWeeks() {
    if (selectedWeeks.length === 0) {
        alert("⚠️ لم تحدد أي أسابيع!\n\nالرجاء اختيار أسبوع أو أكثر أولاً");
        return;
    }
    
    showLoading(true);
    
    // محاكاة المعالجة
    setTimeout(() => {
        let tablesHTML = `<h2>تقرير التحضير للأسابيع المحددة</h2>`;
        tablesHTML += `<h3>المعلم: فهد الخالدي - المادة: اللغة الإنجليزية</h3>`;
        tablesHTML += `<h3>${document.getElementById('currentSemesterInfo').textContent}</h3>`;
        tablesHTML += `<h3>المدرسة: سعيد بن العاص المتوسطة</h3>`;
        
        const weekNames = selectedWeeks.map(w => studyWeeks[w].name).join('، ');
        tablesHTML += `<h3>الأسابيع: ${weekNames} (${selectedWeeks.length} أسابيع)</h3>`;
        
        let totalDays = 0;
        let totalStudents = 0;
        let totalPresent = 0;
        let totalAbsent = 0;
        let totalStarred = 0;
        
        // إضافة بيانات كل أسبوع
        selectedWeeks.forEach(weekNum => {
            const week = studyWeeks[weekNum];
            
            tablesHTML += `<h3 style="background:#e8f5e9; padding:10px; margin-top:20px;">${week.name}</h3>`;
            tablesHTML += `<p style="text-align:center;">${week.startDate} - ${week.endDate} (${week.days} أيام)</p>`;
            
            // إنشاء جداول وهمية للبيانات
            for (const className in studentsData) {
                const classSize = studentsData[className].length;
                
                tablesHTML += `<h5>الصف ${className} (${classSize} طالب)</h5>`;
                tablesHTML += `<table border="1" cellpadding="5" cellspacing="0" style="width:100%; border-collapse:collapse; margin-bottom:15px;">`;
                tablesHTML += `<thead><tr>
                    <th width="5%">م</th>
                    <th>الاسم</th>
                    <th width="8%">الحضور</th>
                    <th width="8%">الواجبات</th>
                    <th width="8%">المشروعات</th>
                    <th width="8%">تطبيقات وأنشطة</th>
                    <th width="8%">مشاركة</th>
                    <th width="8%">⭐</th>
                </tr></thead><tbody>`;
                
                studentsData[className].forEach((student, index) => {
                    tablesHTML += `<tr>`;
                    tablesHTML += `<td>${index + 1}</td>`;
                    tablesHTML += `<td>${student}</td>`;
                    
                    // بيانات وهمية
                    for (let i = 0; i < 5; i++) {
                        const isPresent = Math.random() > 0.3;
                        tablesHTML += `<td style="${isPresent ? 'background-color:#e8f5e9;' : 'background-color:#ffebee;'}">${isPresent ? '✔' : '✖'}</td>`;
                        
                        if (isPresent) {
                            totalPresent++;
                        } else {
                            totalAbsent++;
                        }
                    }
                    
                    const hasStar = Math.random() < 0.3;
                    tablesHTML += `<td>${hasStar ? '⭐' : ''}</td>`;
                    if (hasStar) totalStarred++;
                    
                    tablesHTML += `</tr>`;
                });
                
                tablesHTML += `</tbody></table>`;
                
                totalDays += week.days;
                totalStudents += classSize * week.days;
            }
        });
        
        // إضافة ملخص شامل
        tablesHTML += `<h3 style="background:#e0f7fa; padding:10px; margin-top:20px;">ملخص شامل للأسابيع المحددة</h3>`;
        tablesHTML += `<div style="padding:15px; background:#fff8e1; border-radius:5px; margin-bottom:20px;">
            <strong>إجمالي الأسابيع المحددة:</strong><br>
            - عدد الأسابيع: ${selectedWeeks.length} أسبوع<br>
            - عدد الأيام: ${totalDays} يوم<br>
            - إجمالي الطلاب: ${totalStudents} طالب<br>
            - إجمالي الحضور: ${totalPresent} حالة حضور<br>
            - إجمالي الغياب: ${totalAbsent} حالة غياب<br>
            - إجمالي المتميزين: ${totalStarred} طالب<br>
            - متوسط الحضور: ${totalDays > 0 ? ((totalPresent / (totalPresent + totalAbsent)) * 100).toFixed(1) : 0}%
        </div>`;
        
        // إنشاء ملف Excel
        let uri = 'data:application/vnd.ms-excel;base64,';
        let template = `<html xmlns:o="urn:schemas-microsoft-com:office:office" 
                       xmlns:x="urn:schemas-microsoft-com:office:excel" 
                       xmlns="http://www.w3.org/TR/REC-html40">
                       <head>
                       <meta charset="UTF-8">
                       <!--[if gte mso 9]>
                       <xml>
                       <x:ExcelWorkbook>
                       <x:ExcelWorksheets>
                       <x:ExcelWorksheet>
                       <x:Name>تقرير الأسابيع</x:Name>
                       <x:WorksheetOptions><x:DisplayGridlines/></x:WorksheetOptions>
                       </x:ExcelWorksheet>
                       </x:ExcelWorksheets>
                       </x:ExcelWorkbook>
                       </xml>
                       <![endif]-->
                       </head>
                       <body dir="rtl">${tablesHTML}</body></html>`;
        
        let link = document.createElement("a");
        link.href = uri + btoa(unescape(encodeURIComponent(template)));
        const weekRange = `الأسابيع_${selectedWeeks[0]}_إلى_${selectedWeeks[selectedWeeks.length - 1]}`;
        link.download = `تقرير_${weekRange}.xls`;
        link.click();
        
        showLoading(false);
        
        alert(`✅ تم تصدير التقرير بنجاح!\n\n📊 يحتوي على:\n- ${selectedWeeks.length} أسبوع\n- ${totalDays} يوم\n- ${totalStudents} حالة حضور`);
    }, 1500);
}

// تصدير جميع أسابيع الترم الأول
function exportAllWeeks() {
    // تحديد جميع أسابيع الترم الأول (باستثناء الإجازات)
    const allWeeks = [];
    for (let week = 1; week <= 19; week++) {
        if (!studyWeeks[week].holiday) {
            allWeeks.push(week);
        }
    }
    
    // حفظ الأسابيع الحالية مؤقتاً
    const tempWeeks = [...selectedWeeks];
    selectedWeeks = allWeeks;
    updateSelectedWeeksDisplay();
    
    exportSelectedWeeks();
    
    // استعادة الأسابيع الأصلية
    selectedWeeks = tempWeeks;
    updateSelectedWeeksDisplay();
}

// ======== إدارة الطلاب ========

// تحديث قائمة الطلاب في القائمة المنسدلة
function refreshStudentList() {
    const studentSelect = document.getElementById('studentToMove');
    studentSelect.innerHTML = '<option value="">-- اختر الطالب --</option>';
    
    // جمع جميع الطلاب من جميع الصفوف
    let allStudents = [];
    
    for (const className in studentsData) {
        studentsData[className].forEach(studentName => {
            allStudents.push({
                name: studentName,
                class: className
            });
        });
    }
    
    // إضافة الطلاب إلى القائمة
    allStudents.forEach((student, index) => {
        const option = document.createElement('option');
        option.value = index;
        option.setAttribute('data-class', student.class);
        option.textContent = `${student.name} (${student.class})`;
        studentSelect.appendChild(option);
    });
}

// تحديث معلومات نقل الطالب
function updateStudentMoveInfo() {
    const studentSelect = document.getElementById('studentToMove');
    const selectedIndex = studentSelect.value;
    const currentClassInput = document.getElementById('currentStudentClass');
    
    if (selectedIndex === "") {
        currentClassInput.value = "";
        return;
    }
    
    const selectedOption = studentSelect.options[studentSelect.selectedIndex];
    const studentClass = selectedOption.getAttribute('data-class');
    
    currentClassInput.value = studentClass;
}

// إضافة طالب جديد
function addStudent() {
    const studentName = document.getElementById('newStudentName').value.trim();
    const studentClass = document.getElementById('newStudentClass').value;
    
    if (!studentName) {
        alert("⚠️ الرجاء إدخال اسم الطالب");
        return;
    }
    
    if (!studentsData[studentClass]) {
        alert("⚠️ الصف المحدد غير صحيح");
        return;
    }
    
    // التحقق من عدم وجود الطالب مسبقاً
    for (const className in studentsData) {
        if (studentsData[className].includes(studentName)) {
            alert(`⚠️ الطالب "${studentName}" موجود بالفعل في الصف ${className}`);
            return;
        }
    }
    
    // إضافة الطالب
    studentsData[studentClass].push(studentName);
    
    // تحديث العرض
    fillClassTable(studentClass);
    updateStudentCount();
    refreshStudentList();
    
    // تحديث عنوان الصف
    document.querySelector(`#class-${studentClass} .class-header`).textContent = 
        `الصف ${studentClass} - ${studentsData[studentClass].length} طالب`;
    
    // مسح النموذج
    document.getElementById('newStudentName').value = "";
    
    alert(`✅ تمت إضافة الطالب "${studentName}" إلى الصف ${studentClass} بنجاح`);
}

// مسح نموذج إضافة الطالب
function clearStudentForm() {
    document.getElementById('newStudentName').value = "";
    document.getElementById('newStudentClass').value = "3-1";
}

// نقل طالب بين الصفوف
function moveStudent() {
    const studentSelect = document.getElementById('studentToMove');
    const selectedIndex = studentSelect.value;
    const targetClass = document.getElementById('targetClass').value;
    
    if (selectedIndex === "") {
        alert("⚠️ الرجاء اختيار الطالب");
        return;
    }
    
    const selectedOption = studentSelect.options[studentSelect.selectedIndex];
    const studentName = selectedOption.textContent.split(' (')[0];
    const currentClass = selectedOption.getAttribute('data-class');
    
    if (currentClass === targetClass) {
        alert("⚠️ الطالب موجود بالفعل في هذا الصف");
        return;
    }
    
    // التحقق من وجود الطالب في الصف الهدف
    if (studentsData[targetClass].includes(studentName)) {
        alert(`⚠️ الطالب "${studentName}" موجود بالفعل في الصف ${targetClass}`);
        return;
    }
    
    // نقل الطالب
    const currentClassIndex = studentsData[currentClass].indexOf(studentName);
    if (currentClassIndex !== -1) {
        // إزالة من الصف الحالي
        studentsData[currentClass].splice(currentClassIndex, 1);
        
        // إضافة إلى الصف الهدف
        studentsData[targetClass].push(studentName);
        
        // تحديث العرض
        fillClassTable(currentClass);
        fillClassTable(targetClass);
        updateStudentCount();
        refreshStudentList();
        
        // تحديث عناوين الصفوف
        document.querySelector(`#class-${currentClass} .class-header`).textContent = 
            `الصف ${currentClass} - ${studentsData[currentClass].length} طالب`;
        document.querySelector(`#class-${targetClass} .class-header`).textContent = 
            `الصف ${targetClass} - ${studentsData[targetClass].length} طالب`;
        
        // مسح النموذج
        studentSelect.value = "";
        document.getElementById('currentStudentClass').value = "";
        
        alert(`✅ تم نقل الطالب "${studentName}" من الصف ${currentClass} إلى الصف ${targetClass} بنجاح`);
    } else {
        alert("⚠️ لم يتم العثور على الطالب في الصف الحالي");
    }
}

// ======== باقي الوظائف الأساسية ========

// إنشاء ألسنة الصفوف
function createClassTabs() {
    const classTabs = document.getElementById('classTabs');
    classTabs.innerHTML = '<div class="class-tab active" onclick="showClass(\'all\')">جميع الصفوف</div>';
    
    for (const className in studentsData) {
        classTabs.innerHTML += `<div class="class-tab" onclick="showClass('${className}')">الصف ${className}</div>`;
    }
}

// إنشاء الجداول للصفوف
function createTables() {
    const container = document.getElementById('tablesContainer');
    container.innerHTML = '';
    
    for (const className in studentsData) {
        const classDiv = document.createElement('div');
        classDiv.className = 'class-section';
        classDiv.id = `class-${className}`;
        
        const classHeader = document.createElement('div');
        classHeader.className = 'class-header';
        classHeader.textContent = `الصف ${className} - ${studentsData[className].length} طالب`;
        
        const table = document.createElement('table');
        table.innerHTML = `
            <thead>
                <tr>
                    <th width="5%">م</th>
                    <th>الاسم</th>
                    <th width="10%">الحضور</th>
                    <th width="10%">الواجبات</th>
                    <th width="10%">المشروعات</th>
                    <th width="10%">تطبيقات وأنشطة</th>
                    <th width="10%">مشاركة</th>
                    <th width="10%">⭐</th>
                </tr>
            </thead>
            <tbody id="tbody-${className}">
            </tbody>
        `;
        
        classDiv.appendChild(classHeader);
        classDiv.appendChild(table);
        container.appendChild(classDiv);
        
        fillClassTable(className);
    }
    
    showClass('all');
}

// ملء جدول الصف بالطلاب
function fillClassTable(className) {
    const tbody = document.getElementById(`tbody-${className}`);
    tbody.innerHTML = '';
    
    studentsData[className].forEach((student, index) => {
        const row = document.createElement('tr');
        row.innerHTML = `
            <td>${index + 1}</td>
            <td>${student}</td>
            <td onclick="toggle(this)" class="present">✔</td>
            <td onclick="toggle(this)" class="present">✔</td>
            <td onclick="toggle(this)" class="present">✔</td>
            <td onclick="toggle(this)" class="present">✔</td>
            <td onclick="toggle(this)" class="present">✔</td>
            <td onclick="toggleStar(this)" class="star-cell">☆</td>
        `;
        tbody.appendChild(row);
    });
}

// عرض صف معين أو جميع الصفوف
function showClass(className) {
    currentClass = className;
    
    document.querySelectorAll('.class-tab').forEach(tab => {
        tab.classList.remove('active');
    });
    
    if (className === 'all') {
        document.querySelectorAll('.class-tab')[0].classList.add('active');
        document.querySelectorAll('.class-section').forEach(section => {
            section.style.display = 'block';
        });
    } else {
        document.querySelector(`.class-tab[onclick="showClass('${className}')"]`).classList.add('active');
        document.querySelectorAll('.class-section').forEach(section => {
            section.style.display = 'none';
        });
        document.getElementById(`class-${className}`).style.display = 'block';
    }
    
    filterByStatus(currentFilter);
    updateStudentCount();
}

// عرض جميع الصفوف
function showAllClasses() {
    showClass('all');
}

// تبديل حالة ✔ و ✖
function toggle(cell) {
    if (cell.innerHTML === "✔") {
        cell.innerHTML = "✖";
        cell.classList.remove('present');
        cell.classList.add('absent');
    } else {
        cell.innerHTML = "✔";
        cell.classList.remove('absent');
        cell.classList.add('present');
    }
}

// تبديل النجمة - تم التعديل لإزالة التلميح بكلمة المرور
function toggleStar(cell) {
    if (adminActive) {
        cell.innerHTML = cell.innerHTML === "☆" ? "⭐" : "☆";
        const row = cell.closest('tr');
        if (cell.innerHTML === "⭐") {
            row.classList.add('starred-student');
        } else {
            row.classList.remove('starred-student');
        }
    } else {
        alert('يجب تفعيل وضع الإدارة أولا');
    }
}

// التحقق من كلمة المرور - تم التعديل لإزالة التلميح بكلمة المرور
function checkAdmin() {
    const pass = document.getElementById("adminPass").value;
    if (pass === "1406") {
        adminActive = !adminActive;
        document.getElementById("adminPanel").style.display = adminActive ? "block" : "none";
        document.getElementById("adminPass").value = "";
        
        if (adminActive) {
            alert("✅ تم تفعيل خصائص الإدارة بنجاح!");
        } else {
            alert("تم إغلاق لوحة الإدارة");
        }
    } else {
        alert("❌ كلمة مرور خاطئة!");
    }
}

// تحضير عشوائي للتاريخ الحالي
function randomAttendance() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const confirmAction = confirm("هل تريد تعيين الحضور عشوائيا لجميع الطلاب للتاريخ الحالي؟");
    if (!confirmAction) return;
    
    document.querySelectorAll('.class-section').forEach(section => {
        const rows = section.querySelectorAll('tbody tr');
        rows.forEach(row => {
            const starCell = row.querySelector('.star-cell');
            const hasStar = starCell && starCell.innerHTML === "⭐";
            const attendanceCells = row.querySelectorAll('td[onclick="toggle(this)"]');
            
            attendanceCells.forEach(cell => {
                if (hasStar) {
                    cell.innerHTML = "✔";
                    cell.classList.remove('absent');
                    cell.classList.add('present');
                } else {
                    cell.innerHTML = Math.random() > 0.3 ? "✔" : "✖";
                    if (cell.innerHTML === "✔") {
                        cell.classList.remove('absent');
                        cell.classList.add('present');
                    } else {
                        cell.classList.remove('present');
                        cell.classList.add('absent');
                    }
                }
            });
        });
    });
    
    alert("تم تعيين الحضور عشوائيا للتاريخ الحالي!");
}

// تصدير إلى Excel للتاريخ الحالي
function exportToExcel() {
    const now = new Date();
    const gregorianDate = formatGregorianDate(now);
    const hijriDate = calculateHijriDate(now);
    
    let tablesHTML = `<h2>سجل متابعة الطلاب - المعلم: فهد الخالدي</h2>`;
    tablesHTML += `<h3>المادة: اللغة الإنجليزية - ${document.getElementById('currentSemesterInfo').textContent}</h3>`;
    tablesHTML += `<h3>المدرسة: سعيد بن العاص المتوسطة</h3>`;
    tablesHTML += `<h3>التاريخ الميلادي: ${gregorianDate}</h3>`;
    tablesHTML += `<h3>التاريخ الهجري: ${hijriDate}</h3>`;
    
    for (const className in studentsData) {
        tablesHTML += `<h3>الصف ${className}</h3>`;
        tablesHTML += document.getElementById(`class-${className}`).querySelector('table').outerHTML;
    }
    
    let uri = 'data:application/vnd.ms-excel;base64,';
    let template = `<html xmlns:o="urn:schemas-microsoft-com:office:office" 
                   xmlns:x="urn:schemas-microsoft-com:office:excel" 
                   xmlns="http://www.w3.org/TR/REC-html40">
                   <head>
                   <meta charset="UTF-8">
                   <!--[if gte mso 9]>
                   <xml>
                   <x:ExcelWorkbook>
                   <x:ExcelWorksheets>
                   <x:ExcelWorksheet>
                   <x:Name>تقرير الطلاب</x:Name>
                   <x:WorksheetOptions><x:DisplayGridlines/></x:WorksheetOptions>
                   </x:ExcelWorksheet>
                   </x:ExcelWorksheets>
                   </x:ExcelWorkbook>
                   </xml>
                   <![endif]-->
                   </head>
                   <body dir="rtl">${tablesHTML}</body></html>`;
    
    let link = document.createElement("a");
    link.href = uri + btoa(unescape(encodeURIComponent(template)));
    const dateStr = now.toISOString().split('T')[0];
    link.download = `تقرير_حضور_${dateStr}.xls`;
    link.click();
}

// طباعة الصفحة
function printPage() {
    window.print();
}

// تصفية حسب الحالة
function filterByStatus(status) {
    currentFilter = status;
    
    document.querySelectorAll('.status-filter button').forEach(btn => {
        btn.classList.remove('active');
    });
    
    // الحصول على الزر الذي تم النقر عليه
    let targetButton = event ? event.target : document.querySelector('.status-filter button.active');
    if (targetButton) {
        targetButton.classList.add('active');
    }
    
    let classSections = document.querySelectorAll('.class-section');
    if (currentClass !== 'all') {
        classSections = [document.getElementById(`class-${currentClass}`)];
    }
    
    classSections.forEach(section => {
        const rows = section.querySelectorAll('tbody tr');
        rows.forEach(row => {
            let showRow = false;
            
            if (status === 'all') {
                showRow = true;
            } else if (status === 'present') {
                const attendanceCells = row.querySelectorAll('td[onclick="toggle(this)"]');
                const allPresent = Array.from(attendanceCells).every(cell => cell.innerHTML === "✔");
                showRow = allPresent;
            } else if (status === 'absent') {
                const attendanceCells = row.querySelectorAll('td[onclick="toggle(this)"]');
                const anyAbsent = Array.from(attendanceCells).some(cell => cell.innerHTML === "✖");
                showRow = anyAbsent;
            } else if (status === 'star') {
                const starCell = row.querySelector('.star-cell');
                showRow = starCell && starCell.innerHTML === "⭐";
            }
            
            row.style.display = showRow ? '' : 'none';
        });
    });
}

// تحديث عدد الطلاب
function updateStudentCount() {
    let totalStudents = 0;
    
    if (currentClass === 'all') {
        for (const className in studentsData) {
            totalStudents += studentsData[className].length;
        }
    } else {
        totalStudents = studentsData[currentClass].length;
    }
    
    document.getElementById('studentCount').textContent = `إجمالي الطلاب: ${totalStudents}`;
}

// تحديث عرض التاريخ
function updateDateDisplay() {
    updateCurrentDate();
}

// عرض تحضير اليوم
function showTodayAttendance() {
    alert("✅ تم العرض بتاريخ اليوم الحقيقي");
}

// تهيئة الصفحة عند التحميل
window.onload = initPage;
</script>
</body>
</html>
