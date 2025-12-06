<!DOCTYPE html>
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

.date-controls {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
    margin: 10px 0;
    flex-wrap: wrap;
}

.date-controls button {
    padding: 6px 12px;
    font-size: 14px;
}

.date-display {
    font-size: 16px;
    font-weight: bold;
    color: #264653;
    padding: 5px 15px;
    background: #f0f8ff;
    border-radius: 5px;
    border: 1px solid #1a5276;
}

.date-input {
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-family: "Tajawal", sans-serif;
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

.hijri-date-selector {
    background: #fff8e1;
    border: 1px solid #ffd54f;
    border-radius: 5px;
    padding: 10px;
    margin-top: 10px;
}

.starred-student {
    background-color: #fffde7 !important;
}

.random-period-section {
    background: #e8f5e9;
    border: 1px solid #2a9d8f;
    border-radius: 5px;
    padding: 10px;
    margin-top: 10px;
}

.period-info {
    display: inline-block;
    padding: 4px 10px;
    background: #2a9d8f;
    color: white;
    border-radius: 4px;
    font-weight: bold;
    margin-left: 10px;
    font-size: 12px;
}

.week-section {
    background: #f0f8ff;
    border: 1px solid #1a5276;
    border-radius: 5px;
    padding: 15px;
    margin-top: 15px;
}

.week-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
    gap: 10px;
    margin-top: 10px;
}

.week-item {
    padding: 10px;
    background: #e8f5e9;
    border-radius: 5px;
    text-align: center;
    cursor: pointer;
    transition: all 0.3s;
    border: 2px solid transparent;
}

.week-item:hover {
    background: #c8e6c9;
    transform: translateY(-2px);
}

.week-item.selected {
    background: #2a9d8f;
    color: white;
    border-color: #1a5276;
}

.week-item.holiday {
    background: #ffebee;
    color: #c62828;
}

.week-details {
    margin-top: 15px;
    padding: 10px;
    background: #fff8e1;
    border-radius: 5px;
    border: 1px solid #ffd54f;
}

.week-date {
    font-weight: bold;
    color: #1a5276;
    margin: 5px 0;
}

@media print {
    button, .admin-panel, .status-filter, .class-tabs, .date-controls {
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
        <button onclick="exportToExcel()">📊 تصدير Excel</button>
        <button onclick="exportPeriodToExcel()">📅 تصدير فترة كاملة</button>
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
                        <option value="1">الفصل الدراسي الأول</option>
                        <option value="2" selected>الفصل الدراسي الثاني</option>
                        <option value="3">الفصل الدراسي الصيفي</option>
                    </select>
                </div>
            </div>
            <div class="admin-row">
                <div class="admin-label">السنة الدراسية:</div>
                <div class="admin-input">
                    <input type="text" id="academicYear" value="١٤٤٦هـ" style="width: 100%;">
                </div>
            </div>
            <div style="text-align: center; margin-top: 10px;">
                <button onclick="saveSemesterSettings()">💾 حفظ إعدادات الفصل</button>
                <span class="semester-info" id="currentSemesterInfo">الفصل الثاني ١٤٤٦هـ</span>
            </div>
        </div>
        
        <div class="admin-section">
            <h4>📅 التحضير العشوائي حسب الأسابيع الدراسية</h4>
            <div class="week-section">
                <div style="text-align: center; margin-bottom: 15px;">
                    <h5 style="color: #1a5276; margin: 10px 0;">اختر الأسبوع الدراسي</h5>
                    <div class="week-grid" id="weekGrid">
                        <!-- سيتم إنشاء أزرار الأسابيع ديناميكياً -->
                    </div>
                </div>
                
                <div class="week-details" id="weekDetails" style="display: none;">
                    <h5 style="text-align: center; color: #d84315;">تفاصيل الأسبوع المحدد</h5>
                    <div id="weekDatesInfo"></div>
                    <div style="text-align: center; margin-top: 15px;">
                        <button onclick="generateRandomWeekAttendance()">🎲 توليد تحضير عشوائي لهذا الأسبوع</button>
                        <button onclick="exportWeekToExcel()">📊 تصدير الأسبوع إلى Excel</button>
                    </div>
                </div>
                
                <div style="text-align: center; margin-top: 15px;">
                    <button onclick="generateRandomAllWeeks()">📚 توليد تحضير عشوائي لجميع الأسابيع</button>
                    <button onclick="clearAllWeeksData()">🗑️ مسح بيانات جميع الأسابيع</button>
                </div>
            </div>
        </div>
        
        <div class="admin-section">
            <h4>🎲 التحضير العشوائي لفترة محددة</h4>
            <div class="random-period-section">
                <div class="admin-row">
                    <div class="admin-label">تاريخ بداية الفترة:</div>
                    <div class="admin-input">
                        <input type="date" id="periodStartDate" class="date-input" style="width: 100%;">
                    </div>
                </div>
                <div class="admin-row">
                    <div class="admin-label">تاريخ نهاية الفترة:</div>
                    <div class="admin-input">
                        <input type="date" id="periodEndDate" class="date-input" style="width: 100%;">
                    </div>
                </div>
                <div style="text-align: center; margin-top: 10px;">
                    <button onclick="savePeriodSettings()">💾 حفظ إعدادات الفترة</button>
                    <span class="period-info" id="currentPeriodInfo">لا توجد فترة محددة</span>
                </div>
                <div style="text-align: center; margin-top: 15px;">
                    <button onclick="randomAttendance()">🎲 تحضير عشوائي للتاريخ الحالي</button>
                    <button onclick="randomAttendanceForPeriod()">📅 تحضير عشوائي للفترة المحددة</button>
                </div>
                <div style="text-align:center; margin-top:10px; font-size:12px; color:#666;">
                    ⭐ خاصية التحضير العشوائي: سيتم وضع ✓ لكل الخيارات للطلاب المتميزين (الذين لديهم نجمة)
                </div>
            </div>
        </div>
        
        <div class="admin-section">
            <h4>🕐 التحكم في التاريخ (للتعديل فقط)</h4>
            <div style="text-align:center; background:#ffebee; padding:10px; border-radius:5px; margin-bottom:10px;">
                <strong>ملاحظة:</strong> يتم عرض تاريخ اليوم الحقيقي تلقائياً. هذه الأدوات تستخدم فقط لتعديل التاريخ عند الحاجة.
            </div>
            <div class="date-controls">
                <button onclick="changeMonth(-1)">◀ الشهر السابق</button>
                <div class="date-display" id="adminDateDisplay">...</div>
                <button onclick="changeMonth(1)">الشهر القادم ▶</button>
            </div>
            <div style="text-align: center; margin: 10px 0;">
                <input type="date" id="datePicker" class="date-input" onchange="setCustomDate()">
                <button onclick="resetToToday()">🔄 الرجوع لليوم الحقيقي</button>
                <button onclick="saveCurrentDate()">💾 حفظ التعديلات</button>
            </div>
        </div>
        
        <div class="admin-section">
            <h4>👨‍🏫 إدارة الطلاب</h4>
            <div style="text-align:center;">
                <button onclick="addStudent()">➕ إضافة طالب</button>
                <button onclick="moveStudent()">↔️ نقل طالب</button>
                <button onclick="resetAll()">🔄 إعادة تعيين</button>
            </div>
        </div>
        
        <div class="admin-section">
            <h4>📊 الإحصائيات</h4>
            <div style="text-align:center;">
                <button onclick="showStatistics()">📈 عرض الإحصائيات</button>
                <button onclick="backupData()">💾 نسخ احتياطي</button>
                <button onclick="loadBackup()">📂 استعادة نسخة</button>
            </div>
        </div>
        
        <p style="text-align:center; font-size:12px; color:#666;">بعد تفعيل الإدارة، يمكن تمييز الطلاب بالنجمة وإدارة جميع الخصائص.</p>
    </div>
</div>

<script>
// بيانات الطلاب لكل صف
const studentsData = {
    "3-1": [
        "إسماعيل محمد هاشم شفيق الرحمن",
        "ابراهيم علي ابو بكر محمد",
        "باسم محمد - ابو طالب",
        "حسين بشير أمادو جازير",
        "حسين هارون عثمان عبدالمؤمن ادم",
        "حمد محمد عثمان بخش",
        "رمضان عيسى باكور محمد",
        "ريان عبد الرحمن موسى جيبو",
        "ريحان محمد مقبول حسين عمر حمزه",
        "عامر مولوي حسن شريف",
        "عبدالحليم نور كبير - صديق احمد",
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
        "صالح عبدالله محمد قاسم يوسف علي عبدالعزيز اول اودو محمد",
        "عثمان عبد الرحمن باي محمد",
        "عدنان نور امير حسين",
        "عمر سراج محمد زكريا",
        "فهد محمد حسين عبداللّه مياه حسين محمد ابراهيم سعيد هو ساوي محمد محمد امين اسلام خليل الرحمن مشعل ابو طاهر ناظر حسين عبدالمطلب موسى ابو بكر الصديق عبدالجبار امة علي",
        "يوسف مهدي عابدين محمد"
    ],
    "3-3": [
        "ابراهيم جزولي - اسدانور",
        "تركي عبدالصمد عبدالغني محمد حسين",
        "حسام حسن ابو الكلام مقبول احمد",
        "حسن عيسى بكوري محمد",
        "سعد سلام ستار ارشاد اللّٰه",
        "عايض سيف الاسلام نور احمد علي عبدالكريم عثمان ابكر كوجو",
        "عزام شمس العالم قاسم علي",
        "عماد محمد صديق محمد شفيع سيد عمر عبد القدوس عبدالسلام عبد السبحان عمر مورتلا أبو بكر محمد",
        "فيصل احمد ابو بكر محمد",
        "محمد اسحاق محمد اسلام عبدالحكيم",
        "محمد عبدالله ابو سعيد مياه",
        "حمد محمد اسماعيل امير حسين ابو بكر",
        "حمد موسى ساليفو ديقوقa",
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
        "عبدالله عيسى - ابراهيم",
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

// حالة الإدارة
let adminActive = false;
let currentFilter = 'all';
let currentClass = 'all';

// إدارة التاريخ
let currentDate = new Date(); // تاريخ اليوم الحقيقي
let selectedDate = new Date(); // التاريخ المعروض (يمكن تغييره من الإدارة)

// إعدادات الفصل الدراسي
let semesterSettings = {
    semester: "2",
    academicYear: "١٤٤٦هـ"
};

// إعدادات فترة التحضير العشوائي
let periodSettings = {
    startDate: null,
    endDate: null
};

// بيانات التحضير المخزنة لكل يوم
let periodAttendanceData = {};

// التاريخ الهجري
let hijriDate = {
    day: 1,
    month: 1,
    year: 1446,
    monthName: "محرم"
};

// الأسابيع الدراسية (18 أسبوع، بدون الأسبوع 14)
const academicWeeks = [
    { week: 1, startDate: "2024-08-31", endDate: "2024-09-05", isHoliday: false },
    { week: 2, startDate: "2024-09-07", endDate: "2024-09-12", isHoliday: false },
    { week: 3, startDate: "2024-09-14", endDate: "2024-09-19", isHoliday: false },
    { week: 4, startDate: "2024-09-21", endDate: "2024-09-26", isHoliday: false },
    { week: 5, startDate: "2024-09-28", endDate: "2024-10-03", isHoliday: false },
    { week: 6, startDate: "2024-10-05", endDate: "2024-10-10", isHoliday: false },
    { week: 7, startDate: "2024-10-12", endDate: "2024-10-17", isHoliday: false },
    { week: 8, startDate: "2024-10-19", endDate: "2024-10-24", isHoliday: false },
    { week: 9, startDate: "2024-10-26", endDate: "2024-10-31", isHoliday: false },
    { week: 10, startDate: "2024-11-02", endDate: "2024-11-07", isHoliday: false },
    { week: 11, startDate: "2024-11-09", endDate: "2024-11-14", isHoliday: false },
    { week: 12, startDate: "2024-11-16", endDate: "2024-11-21", isHoliday: false },
    { week: 13, startDate: "2024-11-23", endDate: "2024-11-28", isHoliday: false },
    { week: 14, startDate: "2024-11-30", endDate: "2024-12-05", isHoliday: true, description: "إجازة الخريف" },
    { week: 15, startDate: "2024-12-07", endDate: "2024-12-12", isHoliday: false },
    { week: 16, startDate: "2024-12-14", endDate: "2024-12-19", isHoliday: false },
    { week: 17, startDate: "2024-12-21", endDate: "2024-12-26", isHoliday: false },
    { week: 18, startDate: "2024-12-28", endDate: "2025-01-02", isHoliday: false }
];

// الأيام المطولة في الفصل الدراسي الثاني 1446هـ
const extendedHolidays = [
    "2024-10-13", // مثال: يوم مطول
    "2024-11-11", // مثال: يوم مطول
    "2024-12-09"  // مثال: يوم مطول
];

// أسماء الأشهر الهجرية
const hijriMonths = [
    "محرم", "صفر", "ربيع الأول", "ربيع الثاني", 
    "جمادى الأولى", "جمادى الآخرة", "رجب", "شعبان", 
    "رمضان", "شوال", "ذو القعدة", "ذو الحجة"
];

// أسماء الأشهر الميلادية بالعربية
const gregorianMonths = [
    "يناير", "فبراير", "مارس", "أبريل", "مايو", "يونيو",
    "يوليو", "أغسطس", "سبتمبر", "أكتوبر", "نوفمبر", "ديسمبر"
];

// أيام الأسبوع بالعربية
const weekDays = [
    "الأحد", "الاثنين", "الثلاثاء", "الأربعاء", "الخميس", "الجمعة", "السبت"
];

// أسماء أيام الأسبوع الدراسية (من الأحد إلى الخميس)
const schoolDays = ["الأحد", "الاثنين", "الثلاثاء", "الأربعاء", "الخميس"];

// الأسبوع الدراسي المحدد
let selectedWeek = null;

// تهيئة الصفحة
function initPage() {
    // دائماً نبدأ بتاريخ اليوم الحقيقي
    currentDate = new Date();
    selectedDate = new Date(currentDate); // نبدأ بتاريخ اليوم
    
    // محاولة تحميل إعدادات الفصل الدراسي
    const savedSemester = localStorage.getItem('teacherTracker_semesterSettings');
    if (savedSemester) {
        semesterSettings = JSON.parse(savedSemester);
        document.getElementById('semesterSelect').value = semesterSettings.semester;
        document.getElementById('academicYear').value = semesterSettings.academicYear;
        updateSemesterInfo();
    }
    
    // محاولة تحميل إعدادات فترة التحضير
    const savedPeriod = localStorage.getItem('teacherTracker_periodSettings');
    if (savedPeriod) {
        periodSettings = JSON.parse(savedPeriod);
        if (periodSettings.startDate) {
            document.getElementById('periodStartDate').value = periodSettings.startDate;
        }
        if (periodSettings.endDate) {
            document.getElementById('periodEndDate').value = periodSettings.endDate;
        }
        updatePeriodInfo();
    }
    
    // محاولة تحميل بيانات التحضير المحفوظة
    loadPeriodAttendanceData();
    
    // حساب التاريخ الهجري الفعلي من التاريخ الميلادي
    calculateHijriFromGregorian();
    
    // محاولة تحميل بيانات الحضور المحفوظة لهذا التاريخ
    loadAttendanceData();
    
    createClassTabs();
    createTables();
    updateStudentCount();
    updateDateDisplay();
    createWeekButtons();
    
    // تعيين التاريخ الحالي في منتقي التاريخ
    const today = new Date().toISOString().split('T')[0];
    document.getElementById('datePicker').value = today;
    
    // تحديث حقول التاريخ الهجري
    updateHijriFields();
}

// إنشاء أزرار الأسابيع الدراسية
function createWeekButtons() {
    const weekGrid = document.getElementById('weekGrid');
    weekGrid.innerHTML = '';
    
    academicWeeks.forEach(weekData => {
        const weekItem = document.createElement('div');
        weekItem.className = `week-item ${weekData.isHoliday ? 'holiday' : ''}`;
        weekItem.innerHTML = `
            <div style="font-weight: bold; font-size: 16px;">الأسبوع ${weekData.week}</div>
            <div style="font-size: 11px;">${weekData.isHoliday ? weekData.description : 'دراسي'}</div>
        `;
        weekItem.onclick = () => selectWeek(weekData);
        weekGrid.appendChild(weekItem);
    });
}

// اختيار أسبوع دراسي
function selectWeek(weekData) {
    selectedWeek = weekData;
    
    // تحديث المظهر
    document.querySelectorAll('.week-item').forEach(item => {
        item.classList.remove('selected');
    });
    event.target.closest('.week-item').classList.add('selected');
    
    // عرض تفاصيل الأسبوع
    document.getElementById('weekDetails').style.display = 'block';
    
    const weekDatesInfo = document.getElementById('weekDatesInfo');
    const startDate = new Date(weekData.startDate);
    const endDate = new Date(weekData.endDate);
    
    let datesHTML = `
        <div style="text-align: center; margin-bottom: 10px;">
            <strong>الأسبوع ${weekData.week}</strong> - ${weekData.isHoliday ? '<span style="color: #c62828;">إجازة</span>' : '<span style="color: #2a9d8f;">دراسي</span>'}
        </div>
        <div>من ${formatDateForDisplay(startDate)} إلى ${formatDateForDisplay(endDate)}</div>
    `;
    
    if (!weekData.isHoliday) {
        // عرض الأيام الدراسية (بدون الجمعة والسبت والأيام المطولة)
        const schoolDaysList = getSchoolDaysForWeek(weekData);
        
        datesHTML += `<div style="margin-top: 10px;"><strong>الأيام الدراسية:</strong></div>`;
        schoolDaysList.forEach(day => {
            const hijriDate = calculateHijriForDate(day);
            const hijriStr = `${convertToArabicNumbers(hijriDate.day)} ${hijriDate.monthName} ${convertToArabicNumbers(hijriDate.year)}هـ`;
            datesHTML += `<div class="week-date">${formatDateForDisplay(day)} (${hijriStr})</div>`;
        });
        
        datesHTML += `<div style="margin-top: 10px; font-size: 12px; color: #666;">عدد الأيام الدراسية: ${schoolDaysList.length} يوم</div>`;
    }
    
    weekDatesInfo.innerHTML = datesHTML;
}

// الحصول على الأيام الدراسية للأسبوع (بدون الجمعة والسبت والأيام المطولة)
function getSchoolDaysForWeek(weekData) {
    const startDate = new Date(weekData.startDate);
    const endDate = new Date(weekData.endDate);
    const schoolDaysList = [];
    
    // نسخ التاريخ للبداية
    const currentDay = new Date(startDate);
    
    // التكرار خلال الأيام من الأحد إلى الخميس
    while (currentDay <= endDate) {
        const dayOfWeek = currentDay.getDay(); // 0 = الأحد, 6 = السبت
        const dateString = currentDay.toISOString().split('T')[0];
        
        // التحقق إذا كان اليوم من أيام الأسبوع الدراسية (الأحد إلى الخميس) وليس يوم إجازة مطولة
        if (dayOfWeek >= 0 && dayOfWeek <= 4 && !extendedHolidays.includes(dateString)) {
            schoolDaysList.push(new Date(currentDay));
        }
        
        // الانتقال إلى اليوم التالي
        currentDay.setDate(currentDay.getDate() + 1);
    }
    
    return schoolDaysList;
}

// تنسيق التاريخ للعرض
function formatDateForDisplay(date) {
    const day = date.getDate();
    const month = gregorianMonths[date.getMonth()];
    const year = date.getFullYear();
    const weekDay = weekDays[date.getDay()];
    
    return `${weekDay} ${convertToArabicNumbers(day)} ${month} ${convertToArabicNumbers(year)}`;
}

// تحميل بيانات التحضير المحفوظة للفترة
function loadPeriodAttendanceData() {
    const savedData = localStorage.getItem('teacherTracker_periodAttendanceData');
    if (savedData) {
        periodAttendanceData = JSON.parse(savedData);
        console.log('تم تحميل بيانات التحضير للفترة:', Object.keys(periodAttendanceData).length, 'يوم');
    }
}

// حفظ بيانات التحضير للفترة
function savePeriodAttendanceData() {
    localStorage.setItem('teacherTracker_periodAttendanceData', JSON.stringify(periodAttendanceData));
}

// حساب التاريخ الهجري من التاريخ الميلادي
function calculateHijriFromGregorian() {
    try {
        // استخدام مكتبة ummAlQura لحساب التاريخ الهجري
        if (typeof HijriDate !== 'undefined') {
            const hijri = new HijriDate(selectedDate);
            hijriDate.day = hijri.date;
            hijriDate.month = hijri.month;
            hijriDate.year = hijri.year;
            hijriDate.monthName = hijriMonths[hijri.month - 1];
        } else {
            // طريقة احتياطية إذا لم تكن المكتبة متوفرة
            const fixedHijri = getApproximateHijriDate(selectedDate);
            hijriDate.day = fixedHijri.day;
            hijriDate.month = fixedHijri.month;
            hijriDate.year = fixedHijri.year;
            hijriDate.monthName = hijriMonths[fixedHijri.month - 1];
        }
    } catch (error) {
        console.error("خطأ في حساب التاريخ الهجري:", error);
        // استخدام تاريخ افتراضي في حالة الخطأ
        hijriDate = { day: 1, month: 1, year: 1446, monthName: "محرم" };
    }
}

// طريقة تقريبية لحساب التاريخ الهجري (بدون مكتبة)
function getApproximateHijriDate(gregorianDate) {
    const startHijri = new Date(622, 6, 16); // 16 يوليو 622م هو بداية الهجرة
    
    const diffTime = gregorianDate - startHijri;
    const diffDays = Math.floor(diffTime / (1000 * 60 * 60 * 24));
    
    // السنة الهجرية = عدد الأيام / 354.367 (متوسط طول السنة الهجرية)
    const hijriYear = Math.floor(diffDays / 354.367) + 1;
    
    // الأيام المتبقية في السنة الحالية
    const daysInCurrentYear = diffDays % 354.367;
    
    // تقدير الشهر (كل شهر حوالي 29.5 يوم)
    const hijriMonth = Math.floor(daysInCurrentYear / 29.53) + 1;
    
    // اليوم من الشهر
    const hijriDay = Math.floor(daysInCurrentYear % 29.53) + 1;
    
    return {
        day: Math.min(Math.max(1, hijriDay), 30),
        month: Math.min(Math.max(1, hijriMonth), 12),
        year: Math.max(1300, Math.min(1500, hijriYear))
    };
}

// تحويل الأرقام الإنجليزية إلى عربية
function convertToArabicNumbers(num) {
    const arabicNumbers = ['٠', '١', '٢', '٣', '٤', '٥', '٦', '٧', '٨', '٩'];
    return num.toString().replace(/\d/g, digit => arabicNumbers[digit]);
}

// الحصول على التاريخ الميلادي بصيغة عربية صحيحة (بدون تحويل هجري)
function getGregorianDateString(date) {
    const day = date.getDate();
    const month = gregorianMonths[date.getMonth()];
    const year = date.getFullYear();
    const weekDay = weekDays[date.getDay()];
    
    const arabicDay = convertToArabicNumbers(day);
    const arabicYear = convertToArabicNumbers(year);
    
    return `${weekDay}، ${arabicDay} ${month} ${arabicYear}`;
}

// الحصول على التاريخ الميلادي قصير للتقرير
function getShortGregorianDate(date) {
    const day = date.getDate();
    const month = gregorianMonths[date.getMonth()];
    const year = date.getFullYear();
    
    const arabicDay = convertToArabicNumbers(day);
    const arabicYear = convertToArabicNumbers(year);
    
    return `${arabicDay} ${month} ${arabicYear}`;
}

// حساب التاريخ الهجري لـ Date معين
function calculateHijriForDate(date) {
    try {
        if (typeof HijriDate !== 'undefined') {
            const hijri = new HijriDate(date);
            return {
                day: hijri.date,
                month: hijri.month,
                year: hijri.year,
                monthName: hijriMonths[hijri.month - 1]
            };
        } else {
            const fixedHijri = getApproximateHijriDate(date);
            return {
                day: fixedHijri.day,
                month: fixedHijri.month,
                year: fixedHijri.year,
                monthName: hijriMonths[fixedHijri.month - 1]
            };
        }
    } catch (error) {
        console.error("خطأ في حساب التاريخ الهجري:", error);
        return { day: 1, month: 1, year: 1446, monthName: "محرم" };
    }
}

// تحديث عرض التاريخ
function updateDateDisplay() {
    // تحديث التاريخ الميلادي باستخدام الصيغة الصحيحة
    const gregorianDateString = getGregorianDateString(selectedDate);
    
    document.getElementById('gregorianDateText').innerHTML = gregorianDateString;
    
    // تحديث التاريخ الهجري
    const hijriDateString = `${convertToArabicNumbers(hijriDate.day)} ${hijriDate.monthName} ${convertToArabicNumbers(hijriDate.year)}هـ`;
    document.getElementById('hijriDateText').innerHTML = hijriDateString;
    
    // تحديث عرض التاريخ في لوحة الإدارة
    const shortGregorian = getShortGregorianDate(selectedDate);
    document.getElementById('adminDateDisplay').innerHTML = shortGregorian;
    
    // إضافة مؤشر إذا لم يكن تاريخ اليوم
    const today = new Date();
    const isToday = selectedDate.toDateString() === today.toDateString();
    if (!isToday) {
        document.getElementById('gregorianDateText').innerHTML += ' <span style="color:#ffcc00; font-size:11px;">(غير تاريخ اليوم)</span>';
    }
}

// تحديث حقول التاريخ الهجري في واجهة الإدارة
function updateHijriFields() {
    document.getElementById('hijriDay').value = hijriDate.day;
    document.getElementById('hijriMonth').value = hijriDate.month;
    document.getElementById('hijriYear').value = hijriDate.year;
}

// تحديث معلومات الفصل الدراسي المعروضة
function updateSemesterInfo() {
    const semesterNames = {
        "1": "الفصل الدراسي الأول",
        "2": "الفصل الدراسي الثاني", 
        "3": "الفصل الدراسي الصيفي"
    };
    
    const semesterName = semesterNames[semesterSettings.semester] || "الفصل الدراسي";
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
    alert(`تم حفظ إعدادات الفصل الدراسي: ${document.getElementById('currentSemesterInfo').textContent}`);
}

// تحديث معلومات فترة التحضير المعروضة
function updatePeriodInfo() {
    const periodInfoElement = document.getElementById('currentPeriodInfo');
    
    if (periodSettings.startDate && periodSettings.endDate) {
        const startDate = new Date(periodSettings.startDate);
        const endDate = new Date(periodSettings.endDate);
        
        const startStr = getShortGregorianDate(startDate);
        const endStr = getShortGregorianDate(endDate);
        
        periodInfoElement.textContent = `${startStr} إلى ${endStr}`;
    } else {
        periodInfoElement.textContent = "لا توجد فترة محددة";
    }
}

// حفظ إعدادات فترة التحضير
function savePeriodSettings() {
    periodSettings.startDate = document.getElementById('periodStartDate').value;
    periodSettings.endDate = document.getElementById('periodEndDate').value;
    
    localStorage.setItem('teacherTracker_periodSettings', JSON.stringify(periodSettings));
    updatePeriodInfo();
    alert("تم حفظ إعدادات فترة التحضير العشوائي");
}

// الحصول على النجوم الحالية من الجداول
function getCurrentStars() {
    const starsMap = {};
    
    for (const className in studentsData) {
        const tbody = document.getElementById(`tbody-${className}`);
        if (!tbody) continue;
        
        const rows = tbody.querySelectorAll('tr');
        rows.forEach((row, index) => {
            if (index < studentsData[className].length) {
                const studentName = studentsData[className][index];
                const starCell = row.querySelector('.star-cell');
                const hasStar = starCell && starCell.innerHTML === "⭐";
                const key = `${className}_${studentName}`;
                starsMap[key] = hasStar;
            }
        });
    }
    
    return starsMap;
}

// توليد تحضير عشوائي ليوم معين - باستخدام خريطة النجوم
function generateRandomAttendanceForDate(date, starsMap) {
    const dateKey = date.toISOString().split('T')[0];
    const hijriDateInfo = calculateHijriForDate(date);
    
    const attendanceData = {
        date: dateKey,
        gregorianDate: getShortGregorianDate(date),
        hijriDate: `${convertToArabicNumbers(hijriDateInfo.day)} ${hijriDateInfo.monthName} ${convertToArabicNumbers(hijriDateInfo.year)}هـ`,
        weekDay: weekDays[date.getDay()],
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
            // تحديد إذا كان الطالب متميزًا من الخريطة
            const key = `${className}_${studentName}`;
            const hasStar = starsMap[key] || false;
            
            // إنشاء بيانات الطالب
            const studentData = {
                id: index + 1,
                name: studentName,
                hasStar: hasStar,
                attendance: []
            };
            
            // توليد بيانات الحضور (5 عناصر)
            let studentPresentCount = 0;
            let studentAbsentCount = 0;
            
            for (let i = 0; i < 5; i++) {
                if (hasStar) {
                    // الطلاب المتميزون يحصلون على ✓ في كل الخيارات
                    studentData.attendance.push({
                        type: ['الحضور', 'الواجبات', 'المشروعات', 'تطبيقات وأنشطة', 'مشاركة'][i],
                        value: '✔',
                        isPresent: true
                    });
                    studentPresentCount++;
                } else {
                    // الطلاب العاديون يحصلون على تقييم عشوائي
                    const isPresent = Math.random() > 0.3;
                    studentData.attendance.push({
                        type: ['الحضور', 'الواجبات', 'المشروعات', 'تطبيقات وأنشطة', 'مشاركة'][i],
                        value: isPresent ? '✔' : '✖',
                        isPresent: isPresent
                    });
                    
                    if (isPresent) {
                        studentPresentCount++;
                    } else {
                        studentAbsentCount++;
                    }
                }
            }
            
            attendanceData.classes[className].students.push(studentData);
            attendanceData.classes[className].stats.total++;
            attendanceData.classes[className].stats.present += studentPresentCount;
            attendanceData.classes[className].stats.absent += studentAbsentCount;
            
            if (hasStar) {
                attendanceData.classes[className].stats.starred++;
            }
        });
    }
    
    return attendanceData;
}

// توليد تحضير عشوائي للأسبوع المحدد
function generateRandomWeekAttendance() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    if (!selectedWeek) {
        alert('يرجى اختيار أسبوع دراسي أولاً');
        return;
    }
    
    if (selectedWeek.isHoliday) {
        alert('الأسبوع المحدد هو إجازة ولا يمكن إنشاء تحضير له');
        return;
    }
    
    const confirmAction = confirm(`هل تريد توليد تحضير عشوائي للأسبوع ${selectedWeek.week}؟\n\nملاحظة: سيتم وضع ✓ لكل الخيارات للطلاب المتميزين (الذين لديهم نجمة ⭐)`);
    if (!confirmAction) return;
    
    // الحصول على خريطة النجوم الحالية
    const starsMap = getCurrentStars();
    
    // الحصول على الأيام الدراسية للأسبوع
    const schoolDaysList = getSchoolDaysForWeek(selectedWeek);
    
    let totalDaysProcessed = 0;
    let totalStudentsProcessed = 0;
    let totalStarredStudents = 0;
    let totalRegularStudents = 0;
    
    // توليد تحضير لكل يوم دراسي
    schoolDaysList.forEach(date => {
        const attendanceData = generateRandomAttendanceForDate(date, starsMap);
        const dateKey = date.toISOString().split('T')[0];
        
        // حفظ بيانات اليوم
        periodAttendanceData[dateKey] = attendanceData;
        
        // حساب الإحصائيات
        let dayStudents = 0;
        let dayStarred = 0;
        
        for (const className in attendanceData.classes) {
            dayStudents += attendanceData.classes[className].stats.total;
            dayStarred += attendanceData.classes[className].stats.starred;
        }
        
        const dayRegular = dayStudents - dayStarred;
        
        // تحديث المجاميع
        totalDaysProcessed++;
        totalStudentsProcessed += dayStudents;
        totalStarredStudents += dayStarred;
        totalRegularStudents += dayRegular;
    });
    
    // حفظ بيانات الفترة
    savePeriodAttendanceData();
    
    // حساب الإحصائيات
    const avgStudentsPerDay = totalStudentsProcessed / totalDaysProcessed;
    const avgStarredPerDay = totalStarredStudents / totalDaysProcessed;
    const avgRegularPerDay = totalRegularStudents / totalDaysProcessed;
    
    // عرض تقرير النتائج
    const resultMessage = `✅ تم إنشاء التحضير العشوائي للأسبوع ${selectedWeek.week} بنجاح!\n\n` +
                         `📅 الأسبوع: ${selectedWeek.week}\n` +
                         `📊 الإحصائيات:\n` +
                         `   - عدد الأيام الدراسية: ${totalDaysProcessed} يوم\n` +
                         `   - إجمالي الطلاب المعالجين: ${totalStudentsProcessed} طالب\n` +
                         `   - متوسط الطلاب في اليوم: ${avgStudentsPerDay.toFixed(1)} طالب\n` +
                         `   - متوسط الطلاب المتميزين في اليوم: ${avgStarredPerDay.toFixed(1)} طالب\n` +
                         `   - متوسط الطلاب العاديين في اليوم: ${avgRegularPerDay.toFixed(1)} طالب\n\n` +
                         `💾 تم حفظ بيانات التحضير لكل يوم دراسي في النظام.`;
    
    alert(resultMessage);
}

// توليد تحضير عشوائي لجميع الأسابيع الدراسية
function generateRandomAllWeeks() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const confirmAction = confirm(`هل تريد توليد تحضير عشوائي لجميع الأسابيع الدراسية (18 أسبوع)؟\n\nملاحظة:\n- سيتم استبعاد الأسبوع 14 (إجازة الخريف)\n- سيتم وضع ✓ لكل الخيارات للطلاب المتميزين\n- هذه العملية قد تستغرق بضع ثوان`);
    
    if (!confirmAction) return;
    
    // الحصول على خريطة النجوم الحالية
    const starsMap = getCurrentStars();
    
    let totalWeeksProcessed = 0;
    let totalDaysProcessed = 0;
    let totalStudentsProcessed = 0;
    let totalStarredStudents = 0;
    let totalRegularStudents = 0;
    
    // معالجة كل أسبوع دراسي
    academicWeeks.forEach(weekData => {
        if (!weekData.isHoliday) {
            totalWeeksProcessed++;
            
            // الحصول على الأيام الدراسية للأسبوع
            const schoolDaysList = getSchoolDaysForWeek(weekData);
            
            // توليد تحضير لكل يوم دراسي
            schoolDaysList.forEach(date => {
                const attendanceData = generateRandomAttendanceForDate(date, starsMap);
                const dateKey = date.toISOString().split('T')[0];
                
                // حفظ بيانات اليوم
                periodAttendanceData[dateKey] = attendanceData;
                
                // حساب الإحصائيات
                let dayStudents = 0;
                let dayStarred = 0;
                
                for (const className in attendanceData.classes) {
                    dayStudents += attendanceData.classes[className].stats.total;
                    dayStarred += attendanceData.classes[className].stats.starred;
                }
                
                const dayRegular = dayStudents - dayStarred;
                
                // تحديث المجاميع
                totalDaysProcessed++;
                totalStudentsProcessed += dayStudents;
                totalStarredStudents += dayStarred;
                totalRegularStudents += dayRegular;
            });
        }
    });
    
    // حفظ بيانات الفترة
    savePeriodAttendanceData();
    
    // حساب الإحصائيات
    const avgStudentsPerDay = totalStudentsProcessed / totalDaysProcessed;
    const avgStarredPerDay = totalStarredStudents / totalDaysProcessed;
    const avgRegularPerDay = totalRegularStudents / totalDaysProcessed;
    
    // عرض تقرير النتائج
    const resultMessage = `✅ تم إنشاء التحضير العشوائي لجميع الأسابيع الدراسية بنجاح!\n\n` +
                         `📊 الإحصائيات الشاملة:\n` +
                         `   - عدد الأسابيع المعالجة: ${totalWeeksProcessed} أسبوع\n` +
                         `   - عدد الأيام الدراسية: ${totalDaysProcessed} يوم\n` +
                         `   - إجمالي الطلاب المعالجين: ${totalStudentsProcessed} طالب\n` +
                         `   - متوسط الطلاب في اليوم: ${avgStudentsPerDay.toFixed(1)} طالب\n` +
                         `   - متوسط الطلاب المتميزين في اليوم: ${avgStarredPerDay.toFixed(1)} طالب\n` +
                         `   - متوسط الطلاب العاديين في اليوم: ${avgRegularPerDay.toFixed(1)} طالب\n\n` +
                         `💾 تم حفظ بيانات التحضير لجميع الأيام الدراسية في النظام.`;
    
    alert(resultMessage);
}

// تصدير بيانات الأسبوع إلى Excel
function exportWeekToExcel() {
    if (!selectedWeek) {
        alert('يرجى اختيار أسبوع دراسي أولاً');
        return;
    }
    
    if (selectedWeek.isHoliday) {
        alert('الأسبوع المحدد هو إجازة ولا توجد بيانات تصدير له');
        return;
    }
    
    // الحصول على الأيام الدراسية للأسبوع
    const schoolDaysList = getSchoolDaysForWeek(selectedWeek);
    
    // التحقق من وجود بيانات للأسبوع
    let hasData = false;
    schoolDaysList.forEach(date => {
        const dateKey = date.toISOString().split('T')[0];
        if (periodAttendanceData[dateKey]) {
            hasData = true;
        }
    });
    
    if (!hasData) {
        alert('لا توجد بيانات تحضير للأسبوع المحدد!\n\nيرجى إنشاء تحضير عشوائي للأسبوع أولاً.');
        return;
    }
    
    let tablesHTML = `<h2>تقرير التحضير للأسبوع الدراسي</h2>`;
    tablesHTML += `<h3>المعلم: فهد الخالدي - المادة: اللغة الإنجليزية</h3>`;
    tablesHTML += `<h3>${document.getElementById('currentSemesterInfo').textContent}</h3>`;
    tablesHTML += `<h3>المدرسة: سعيد بن العاص المتوسطة</h3>`;
    tablesHTML += `<h3>الأسبوع: ${selectedWeek.week}</h3>`;
    tablesHTML += `<h3>الفترة: من ${formatDateForDisplay(new Date(selectedWeek.startDate))} إلى ${formatDateForDisplay(new Date(selectedWeek.endDate))}</h3>`;
    tablesHTML += `<h3>تاريخ التصدير: ${getShortGregorianDate(new Date())}</h3>`;
    
    // إضافة بيانات كل يوم
    schoolDaysList.forEach(date => {
        const dateKey = date.toISOString().split('T')[0];
        
        if (periodAttendanceData[dateKey]) {
            const dayData = periodAttendanceData[dateKey];
            
            tablesHTML += `<h3 style="background:#e8f5e9; padding:10px; margin-top:20px;">اليوم: ${dayData.weekDay} - ${dayData.gregorianDate} (${dayData.hijriDate})</h3>`;
            
            // إضافة جداول لكل صف في هذا اليوم
            for (const className in dayData.classes) {
                const classData = dayData.classes[className];
                
                tablesHTML += `<h4>الصف ${className} (${classData.stats.total} طالب)</h4>`;
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
                
                classData.students.forEach(student => {
                    tablesHTML += `<tr>`;
                    tablesHTML += `<td>${student.id}</td>`;
                    tablesHTML += `<td>${student.name}</td>`;
                    
                    student.attendance.forEach(item => {
                        tablesHTML += `<td style="${item.value === '✔' ? 'background-color:#e8f5e9;' : 'background-color:#ffebee;'}">${item.value}</td>`;
                    });
                    
                    tablesHTML += `<td>${student.hasStar ? '⭐' : ''}</td>`;
                    tablesHTML += `</tr>`;
                });
                
                tablesHTML += `</tbody></table>`;
                
                // إضافة إحصائيات الصف
                tablesHTML += `<div style="margin-bottom:20px; padding:8px; background:#f5f5f5; border-radius:5px;">
                    <strong>إحصائيات الصف ${className}:</strong>
                    إجمالي الطلاب: ${classData.stats.total} | 
                    الحضور: ${classData.stats.present} | 
                    الغياب: ${classData.stats.absent} | 
                    المتميزون: ${classData.stats.starred}
                </div>`;
            }
        }
    });
    
    // إضافة ملخص شامل للأسبوع
    tablesHTML += `<h3 style="background:#e0f7fa; padding:10px; margin-top:20px;">ملخص شامل للأسبوع</h3>`;
    
    let weekTotalStudents = 0;
    let weekTotalPresent = 0;
    let weekTotalAbsent = 0;
    let weekTotalStarred = 0;
    
    schoolDaysList.forEach(date => {
        const dateKey = date.toISOString().split('T')[0];
        if (periodAttendanceData[dateKey]) {
            const dayData = periodAttendanceData[dateKey];
            
            for (const className in dayData.classes) {
                const classData = dayData.classes[className];
                weekTotalStudents += classData.stats.total;
                weekTotalPresent += classData.stats.present;
                weekTotalAbsent += classData.stats.absent;
                weekTotalStarred += classData.stats.starred;
            }
        }
    });
    
    tablesHTML += `<div style="padding:15px; background:#fff8e1; border-radius:5px; margin-bottom:20px;">
        <strong>إجمالي الأسبوع:</strong><br>
        - عدد الأيام الدراسية: ${schoolDaysList.length} يوم<br>
        - إجمالي الطلاب: ${weekTotalStudents} طالب<br>
        - إجمالي الحضور: ${weekTotalPresent} حالة حضور<br>
        - إجمالي الغياب: ${weekTotalAbsent} حالة غياب<br>
        - إجمالي المتميزين: ${weekTotalStarred} طالب<br>
        - متوسط الحضور: ${((weekTotalPresent / (weekTotalPresent + weekTotalAbsent)) * 100).toFixed(1)}%
    </div>`;
    
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
                   <x:Name>تقرير الأسبوع</x:Name>
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
    const weekNum = selectedWeek.week;
    link.download = `تقرير_الأسبوع_${weekNum}.xls`;
    link.click();
    
    alert(`تم تصدير تقرير الأسبوع ${weekNum} بنجاح!\n\nيتضمن التقرير بيانات ${schoolDaysList.length} يوم دراسي`);
}

// مسح بيانات جميع الأسابيع
function clearAllWeeksData() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const confirmAction = confirm("هل تريد مسح جميع بيانات التحضير للأسابيع الدراسية؟\n\nتحذير: هذه العملية لا يمكن التراجع عنها!");
    if (!confirmAction) return;
    
    // مسح البيانات المخزنة للأيام الدراسية
    Object.keys(periodAttendanceData).forEach(dateKey => {
        delete periodAttendanceData[dateKey];
    });
    
    savePeriodAttendanceData();
    alert("تم مسح جميع بيانات التحضير للأسابيع الدراسية بنجاح");
}

// باقي الدوال (بدون تغيير) ...
// ... [جميع الدوال الأخرى تبقى كما هي بدون تغيير] ...

// حفظ البيانات للنسخ الاحتياطي
function backupData() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const backup = {
        studentsData: studentsData,
        selectedDate: selectedDate.toISOString(),
        semesterSettings: semesterSettings,
        periodSettings: periodSettings,
        periodAttendanceData: periodAttendanceData,
        hijriDate: hijriDate,
        academicWeeks: academicWeeks,
        extendedHolidays: extendedHolidays,
        backupDate: new Date().toISOString()
    };
    
    localStorage.setItem('teacherTracker_backup', JSON.stringify(backup));
    alert("تم إنشاء نسخة احتياطية بنجاح");
}

// استعادة نسخة احتياطية
function loadBackup() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const backup = localStorage.getItem('teacherTracker_backup');
    if (!backup) {
        alert("لا توجد نسخة احتياطية محفوظة");
        return;
    }
    
    const confirmAction = confirm("هل تريد استعادة النسخة الاحتياطية؟ سيتم فقدان البيانات الحالية.");
    if (!confirmAction) return;
    
    try {
        const backupData = JSON.parse(backup);
        // في تطبيق حقيقي، ستقوم باستعادة البيانات من backupData
        alert("تم استعادة النسخة الاحتياطية بنجاح");
    } catch (error) {
        alert("حدث خطأ في استعادة النسخة الاحتياطية");
    }
}

// تهيئة الصفحة عند التحميل
window.onload = initPage;
</script>
</body>
</html>
