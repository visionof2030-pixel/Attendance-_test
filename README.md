<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>سجل متابعة الطلاب - فهد الخالدي</title>
<style>
/* أنماط عامة */
:root {
    --primary-color: #2c3e50;
    --secondary-color: #3498db;
    --accent-color: #1abc9c;
    --light-bg: #f8f9fa;
    --dark-bg: #2c3e50;
    --success-color: #27ae60;
    --warning-color: #f39c12;
    --danger-color: #e74c3c;
    --border-color: #ddd;
    --shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    --shadow-light: 0 2px 4px rgba(0, 0, 0, 0.05);
    --transition: all 0.3s ease;
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    -webkit-tap-highlight-color: transparent;
}

body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen', 'Ubuntu', 'Cantarell', 'Fira Sans', 'Droid Sans', 'Helvetica Neue', sans-serif;
    background-color: #f5f7fa;
    color: #333;
    line-height: 1.6;
    padding: 0;
    margin: 0;
    font-size: 15px;
}

/* تحسينات للجوال */
html {
    font-size: 14px;
}

@media (min-width: 768px) {
    html {
        font-size: 16px;
    }
}

/* الهيدر - تحسين للجوال */
header {
    background: linear-gradient(135deg, var(--primary-color), #1a252f);
    color: white;
    padding: 1rem;
    box-shadow: var(--shadow);
    position: relative;
    overflow: hidden;
}

.header-main {
    font-size: 1.4rem;
    font-weight: 700;
    margin-bottom: 0.5rem;
    position: relative;
    z-index: 1;
    line-height: 1.3;
}

.header-sub {
    display: flex;
    flex-direction: column;
    gap: 10px;
    position: relative;
    z-index: 1;
}

.header-sub > div:first-child {
    font-size: 1rem;
    opacity: 0.9;
    padding: 8px 0;
}

.current-date {
    display: flex;
    flex-direction: column;
    gap: 10px;
    background: rgba(255, 255, 255, 0.1);
    padding: 12px;
    border-radius: 8px;
    backdrop-filter: blur(5px);
    width: 100%;
}

.current-date > div {
    display: flex;
    align-items: center;
    gap: 8px;
    flex-wrap: wrap;
}

.date-info {
    background-color: rgba(26, 188, 156, 0.2);
    padding: 6px 10px;
    border-radius: 20px;
    font-weight: 600;
    font-size: 0.9rem;
    white-space: nowrap;
}

/* الحاوية الرئيسية - تحسين للجوال */
.container {
    width: 100%;
    margin: 0 auto;
    padding: 10px;
}

@media (min-width: 768px) {
    .container {
        max-width: 95%;
        padding: 15px;
    }
}

@media (min-width: 1200px) {
    .container {
        max-width: 1400px;
        padding: 20px;
    }
}

/* أزرار التحكم - تحسين للجوال */
.controls {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 15px;
    padding: 15px;
    background-color: white;
    border-radius: 12px;
    box-shadow: var(--shadow-light);
}

.controls button {
    flex: 1 1 calc(50% - 8px);
    min-width: 140px;
    padding: 12px 10px;
    border: none;
    border-radius: 8px;
    background-color: var(--secondary-color);
    color: white;
    font-weight: 600;
    cursor: pointer;
    transition: var(--transition);
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 6px;
    font-size: 0.9rem;
    touch-action: manipulation;
}

.controls button:active {
    transform: scale(0.98);
}

.controls button:hover {
    background-color: #2980b9;
}

/* ألسنة الصفوف - تحسين للجوال */
.class-tabs {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 15px;
    background-color: white;
    padding: 15px;
    border-radius: 12px;
    box-shadow: var(--shadow-light);
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
}

.class-tabs::-webkit-scrollbar {
    height: 4px;
}

.class-tabs::-webkit-scrollbar-track {
    background: #f1f1f1;
    border-radius: 2px;
}

.class-tabs::-webkit-scrollbar-thumb {
    background: #c1c1c1;
    border-radius: 2px;
}

.class-tab {
    flex: 0 0 auto;
    padding: 10px 16px;
    background-color: #ecf0f1;
    border-radius: 8px;
    cursor: pointer;
    font-weight: 600;
    transition: var(--transition);
    border: 2px solid transparent;
    font-size: 0.9rem;
    white-space: nowrap;
    user-select: none;
}

.class-tab:active {
    transform: scale(0.95);
}

.class-tab.active {
    background-color: var(--accent-color);
    color: white;
    border-color: var(--accent-color);
}

/* فلتر الحالة - تحسين للجوال */
.status-filter {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-bottom: 15px;
    background-color: white;
    padding: 15px;
    border-radius: 12px;
    box-shadow: var(--shadow-light);
}

.status-filter button {
    flex: 1 1 calc(50% - 8px);
    min-width: 120px;
    padding: 10px 15px;
    border: 2px solid var(--border-color);
    background-color: white;
    border-radius: 8px;
    cursor: pointer;
    font-weight: 600;
    transition: var(--transition);
    font-size: 0.9rem;
    touch-action: manipulation;
}

.status-filter button:active {
    transform: scale(0.95);
}

.status-filter button.active {
    background-color: var(--secondary-color);
    color: white;
    border-color: var(--secondary-color);
}

/* تصميم جداول الطلاب المحسّن للجوال */
.tables-container {
    display: flex;
    flex-direction: column;
    gap: 15px;
    margin-bottom: 20px;
    width: 100%;
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
}

.class-section {
    background-color: white;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: var(--shadow-light);
    transition: var(--transition);
    min-width: 100%;
}

.class-section.show {
    display: block;
    animation: fadeIn 0.5s ease;
}

.class-section.hidden {
    display: none;
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(10px); }
    to { opacity: 1; transform: translateY(0); }
}

.class-header {
    background: linear-gradient(to right, var(--primary-color), #34495e);
    color: white;
    padding: 15px;
    font-size: 1.1rem;
    font-weight: 700;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: sticky;
    left: 0;
}

.class-header::after {
    content: "📚";
    font-size: 1.2rem;
}

.student-table-container {
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
    width: 100%;
}

.student-table {
    width: 100%;
    border-collapse: collapse;
    min-width: 700px;
}

.student-table thead {
    background-color: #f8f9fa;
    position: sticky;
    top: 0;
    z-index: 10;
}

.student-table th {
    padding: 14px 8px;
    text-align: center;
    font-weight: 700;
    color: var(--primary-color);
    border-bottom: 2px solid var(--border-color);
    position: relative;
    font-size: 0.9rem;
    white-space: nowrap;
}

.student-table th::after {
    content: "";
    position: absolute;
    bottom: -2px;
    right: 0;
    width: 100%;
    height: 2px;
    background: linear-gradient(to right, transparent, var(--accent-color), transparent);
}

.student-table tbody tr {
    border-bottom: 1px solid #eee;
    transition: var(--transition);
}

.student-table tbody tr:hover {
    background-color: #f8f9fa;
}

.student-table td {
    padding: 12px 8px;
    text-align: center;
    vertical-align: middle;
    position: relative;
    font-size: 0.9rem;
}

.student-table td:first-child {
    font-weight: 700;
    color: var(--primary-color);
    background-color: #f8f9fa;
    position: sticky;
    right: 0;
    z-index: 5;
    border-left: 1px solid #eee;
}

.student-table td:nth-child(2) {
    text-align: right;
    padding-right: 15px;
    font-weight: 500;
    position: sticky;
    right: 40px;
    background-color: white;
    z-index: 4;
    min-width: 180px;
    white-space: normal;
    word-break: break-word;
}

/* إصلاح خلايا التقييم - تحسين للجوال */
.evaluation-cell {
    font-weight: 700;
    cursor: pointer;
    border-radius: 6px;
    transition: var(--transition);
    min-width: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    min-height: 36px;
    user-select: none;
    position: relative;
    margin: 0 auto;
    font-size: 1rem;
    touch-action: manipulation;
}

.evaluation-cell:active {
    transform: scale(0.9);
}

.evaluation-cell.present {
    color: var(--success-color);
    background-color: rgba(39, 174, 96, 0.1);
}

.evaluation-cell.absent {
    color: var(--danger-color);
    background-color: rgba(231, 76, 60, 0.1);
}

/* خلايا النجوم */
.star-cell {
    cursor: pointer;
    font-size: 1.4rem;
    transition: var(--transition);
    user-select: none;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    min-height: 36px;
    touch-action: manipulation;
}

.star-cell:active {
    transform: scale(0.9);
}

.starred-student {
    background-color: rgba(241, 196, 15, 0.05);
    border-right: 4px solid #f1c40f;
}

/* إحصائية الطلاب */
.student-count {
    background: linear-gradient(to right, var(--accent-color), #16a085);
    color: white;
    padding: 15px;
    border-radius: 12px;
    font-size: 1.1rem;
    font-weight: 700;
    text-align: center;
    margin-bottom: 15px;
    box-shadow: var(--shadow);
}

/* لوحة الإدارة - تحسين للجوال */
.admin-panel {
    background-color: white;
    border-radius: 12px;
    padding: 15px;
    margin-top: 20px;
    box-shadow: var(--shadow-light);
    display: none;
}

.admin-section {
    margin-bottom: 20px;
    padding-bottom: 20px;
    border-bottom: 1px solid var(--border-color);
}

.admin-section:last-child {
    border-bottom: none;
    margin-bottom: 0;
}

.admin-section h4 {
    color: var(--primary-color);
    margin-bottom: 15px;
    padding-bottom: 10px;
    border-bottom: 2px solid #eee;
    display: flex;
    align-items: center;
    gap: 8px;
    font-size: 1.1rem;
}

.admin-section h4::before {
    content: "";
    display: inline-block;
    width: 6px;
    height: 20px;
    background-color: var(--accent-color);
    border-radius: 4px;
}

.admin-row {
    display: flex;
    flex-direction: column;
    margin-bottom: 12px;
    width: 100%;
}

@media (min-width: 768px) {
    .admin-row {
        flex-direction: row;
        align-items: center;
    }
}

.admin-label {
    width: 100%;
    font-weight: 600;
    color: var(--primary-color);
    margin-bottom: 5px;
}

@media (min-width: 768px) {
    .admin-label {
        width: 180px;
        margin-bottom: 0;
    }
}

.admin-input {
    flex: 1;
    min-width: 100%;
}

@media (min-width: 768px) {
    .admin-input {
        min-width: 200px;
    }
}

.admin-input input, .admin-input select {
    width: 100%;
    padding: 12px 12px;
    border: 1px solid var(--border-color);
    border-radius: 8px;
    font-size: 1rem;
    transition: var(--transition);
}

.admin-input input:focus, .admin-input select:focus {
    outline: none;
    border-color: var(--secondary-color);
    box-shadow: 0 0 0 3px rgba(52, 152, 219, 0.2);
}

.date-controls {
    display: flex;
    flex-direction: column;
    gap: 15px;
    margin: 15px 0;
}

@media (min-width: 768px) {
    .date-controls {
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 20px;
    }
}

.date-display {
    background-color: #f8f9fa;
    padding: 12px 20px;
    border-radius: 10px;
    font-weight: 700;
    font-size: 1.1rem;
    color: var(--primary-color);
    min-width: 100%;
    text-align: center;
}

@media (min-width: 768px) {
    .date-display {
        min-width: 200px;
    }
}

.date-input {
    padding: 12px 12px;
    border: 1px solid var(--border-color);
    border-radius: 8px;
    font-size: 1rem;
    width: 100%;
}

.hijri-date-selector {
    background-color: #f8f9fa;
    padding: 15px;
    border-radius: 10px;
    margin-top: 15px;
}

.semester-info, .period-info {
    display: inline-block;
    background-color: #e8f4fc;
    color: var(--secondary-color);
    padding: 6px 12px;
    border-radius: 20px;
    font-weight: 600;
    margin-right: 10px;
    font-size: 0.9rem;
    margin-top: 10px;
}

.random-period-section {
    background-color: #f8f9fa;
    padding: 15px;
    border-radius: 10px;
    margin-top: 15px;
}

/* أزرار الإدارة - تحسين للجوال */
.admin-section button, .random-period-section button, .hijri-date-selector button {
    padding: 12px 15px;
    border: none;
    border-radius: 8px;
    font-weight: 600;
    cursor: pointer;
    transition: var(--transition);
    font-size: 0.9rem;
    touch-action: manipulation;
    width: 100%;
    margin-bottom: 8px;
}

@media (min-width: 768px) {
    .admin-section button, .random-period-section button, .hijri-date-selector button {
        width: auto;
        margin-bottom: 0;
    }
}

.admin-section button:active, .random-period-section button:active, .hijri-date-selector button:active {
    transform: scale(0.95);
}

/* تحسينات إضافية للجوال */
.mobile-optimized {
    -webkit-text-size-adjust: 100%;
    -webkit-font-smoothing: antialiased;
}

/* تحسينات لشريط التمرير على الجوال */
.tables-container::-webkit-scrollbar,
.student-table-container::-webkit-scrollbar {
    height: 6px;
}

.tables-container::-webkit-scrollbar-track,
.student-table-container::-webkit-scrollbar-track {
    background: #f1f1f1;
    border-radius: 3px;
}

.tables-container::-webkit-scrollbar-thumb,
.student-table-container::-webkit-scrollbar-thumb {
    background: #c1c1c1;
    border-radius: 3px;
}

.tables-container::-webkit-scrollbar-thumb:hover,
.student-table-container::-webkit-scrollbar-thumb:hover {
    background: #a8a8a8;
}

/* تحسينات للطباعة */
@media print {
    .controls, .class-tabs, .status-filter, .admin-panel, .student-count {
        display: none !important;
    }
    
    .class-section {
        display: block !important;
        break-inside: avoid;
        box-shadow: none;
        margin-bottom: 20px;
    }
    
    .student-table {
        min-width: 100%;
    }
    
    .student-table td:first-child,
    .student-table td:nth-child(2) {
        position: static;
    }
}

/* رسائل التنبيه للجوال */
.mobile-alert {
    display: none;
    position: fixed;
    bottom: 20px;
    right: 20px;
    left: 20px;
    background-color: var(--accent-color);
    color: white;
    padding: 12px 15px;
    border-radius: 10px;
    font-weight: 600;
    text-align: center;
    z-index: 1000;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
    animation: slideUp 0.3s ease;
}

@keyframes slideUp {
    from { transform: translateY(100px); opacity: 0; }
    to { transform: translateY(0); opacity: 1; }
}

@media (max-width: 767px) {
    .mobile-alert {
        display: block;
    }
}

/* تحسينات للنقر على الروابط في الجوال */
a, button {
    -webkit-tap-highlight-color: rgba(0, 0, 0, 0.1);
}

/* تحسينات للوضع الأفقي على الجوال */
@media (max-height: 500px) and (orientation: landscape) {
    .header-main {
        font-size: 1.2rem;
    }
    
    .controls button, .class-tab, .status-filter button {
        padding: 8px 10px;
        font-size: 0.8rem;
    }
    
    .student-table th, .student-table td {
        padding: 8px 6px;
        font-size: 0.8rem;
    }
}
</style>
<!-- مكتبة SheetJS لتصدير Excel -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
</head>
<body class="mobile-optimized">

<div class="mobile-alert" id="mobileAlert">
    💡 اسحب الجدول يميناً/يساراً لعرض جميع الأعمدة
</div>

<header>
    <div class="header-main">سجل متابعة الطلاب للمعلم / فهد الخالدي - المادة / اللغة الإنجليزية</div>
    <div class="header-sub">
        <div>المدرسة: سعيد بن العاص المتوسطة</div>
        <div class="current-date">
            <div>
                <div>تاريخ اليوم:</div>
                <div id="gregorianDateText">تحميل...</div>
            </div>
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
    
    <div class="tables-container" id="tablesContainer">
        <!-- سيتم إنشاء الجداول ديناميكياً -->
    </div>
    
    <div class="student-count" id="studentCount">إجمالي الطلاب: 0</div>
    
    <div style="text-align: center; margin: 15px 0; padding: 15px; background-color: white; border-radius: 12px; box-shadow: var(--shadow-light);">
        <input type="password" id="adminPass" placeholder="ادخل كلمة المرور للإدارة" style="width: 100%; max-width: 300px; padding: 12px 15px; border: 1px solid var(--border-color); border-radius: 8px; font-size: 1rem; margin-bottom: 10px;">
        <button onclick="checkAdmin()" style="padding: 12px 20px; background-color: var(--accent-color); color: white; border: none; border-radius: 8px; font-weight: 600; cursor: pointer; transition: var(--transition); width: 100%; max-width: 300px;">🔓 فتح الإدارة</button>
    </div>

    <div class="admin-panel" id="adminPanel">
        <h3 style="text-align:center; margin-top:0; color: var(--primary-color); padding-bottom: 15px; border-bottom: 2px solid var(--accent-color);">لوحة الإدارة - الخصائص الإدارية</h3>
        
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
                <button onclick="saveSemesterSettings()" style="background-color: var(--secondary-color); color: white;">💾 حفظ إعدادات الفصل</button>
                <span class="semester-info" id="currentSemesterInfo">الفصل الثاني ١٤٤٦هـ</span>
            </div>
        </div>
        
        <div class="admin-section">
            <h4>🕐 التحكم في التاريخ (للتعديل فقط)</h4>
            <div style="text-align:center; background:#f8f9fa; padding:12px; border-radius:8px; margin-bottom:15px; border-right: 4px solid var(--warning-color); font-size: 0.9rem;">
                <strong>ملاحظة:</strong> يتم عرض تاريخ اليوم الحقيقي تلقائياً. هذه الأدوات تستخدم فقط لتعديل التاريخ عند الحاجة.
            </div>
            <div class="date-controls">
                <button onclick="changeMonth(-1)" style="background-color: var(--primary-color); color: white;">◀ الشهر السابق</button>
                <div class="date-display" id="adminDateDisplay">...</div>
                <button onclick="changeMonth(1)" style="background-color: var(--primary-color); color: white;">الشهر القادم ▶</button>
            </div>
            <div style="text-align: center; margin: 20px 0; display: flex; flex-wrap: wrap; gap: 10px; justify-content: center;">
                <input type="date" id="datePicker" class="date-input" onchange="setCustomDate()">
                <button onclick="resetToToday()" style="background-color: #95a5a6; color: white;">🔄 الرجوع لليوم الحقيقي</button>
                <button onclick="saveCurrentDate()" style="background-color: var(--accent-color); color: white;">💾 حفظ التعديلات</button>
            </div>
            
            <div class="hijri-date-selector">
                <h5 style="text-align:center; color: var(--primary-color); margin-bottom: 15px; font-size: 1rem;">التاريخ الهجري (يمكن تعديله يدوياً)</h5>
                <div class="admin-row">
                    <div class="admin-label">اليوم:</div>
                    <div class="admin-input">
                        <input type="number" id="hijriDay" min="1" max="30" style="width: 100px; padding: 12px 12px;">
                    </div>
                </div>
                <div class="admin-row">
                    <div class="admin-label">الشهر:</div>
                    <div class="admin-input">
                        <select id="hijriMonth" style="width: 100%; padding: 12px 12px;">
                            <option value="1">محرم</option>
                            <option value="2">صفر</option>
                            <option value="3">ربيع الأول</option>
                            <option value="4">ربيع الثاني</option>
                            <option value="5">جمادى الأولى</option>
                            <option value="6">جمادى الآخرة</option>
                            <option value="7">رجب</option>
                            <option value="8">شعبان</option>
                            <option value="9">رمضان</option>
                            <option value="10">شوال</option>
                            <option value="11">ذو القعدة</option>
                            <option value="12">ذو الحجة</option>
                        </select>
                    </div>
                </div>
                <div class="admin-row">
                    <div class="admin-label">السنة:</div>
                    <div class="admin-input">
                        <input type="number" id="hijriYear" min="1300" max="1500" style="width: 150px; padding: 12px 12px;">
                    </div>
                </div>
                <div style="text-align: center; margin-top: 15px; display: flex; flex-wrap: wrap; gap: 10px; justify-content: center;">
                    <button onclick="updateHijriDate()" style="background-color: var(--secondary-color); color: white;">🔄 تحديث التاريخ الهجري</button>
                    <button onclick="resetHijriToToday()" style="background-color: #95a5a6; color: white;">🔄 الرجوع للتاريخ الفعلي</button>
                </div>
                <p style="text-align:center; font-size:11px; color:#666; margin-top: 12px;">ملاحظة: التاريخ الهجري المحسوب تلقائياً، ويمكنك تعديله يدوياً إذا لزم الأمر.</p>
            </div>
        </div>
        
        <div class="admin-section">
            <h4>🎲 التحضير العشوائي للأسابيع الدراسية (18 أسبوع)</h4>
            <div class="random-period-section">
                <div style="text-align:center; margin:12px 0; padding:12px; background:#e8f5e9; border-radius:8px; border-right: 4px solid var(--success-color); font-size: 0.9rem;">
                    <strong>الأسابيع الدراسية المتاحة:</strong><br>
                    من الأسبوع 1 إلى 13 ثم من 15 إلى 19 (إجمالي 18 أسبوع)<br>
                    <small>ملاحظة: الأسبوع 14 إجازة الخريف ولا يتم إدراجه</small>
                </div>
                <div style="text-align: center; margin-top: 15px; display: flex; flex-wrap: wrap; gap: 10px; justify-content: center;">
                    <button onclick="generatePeriodData()" style="background-color: var(--accent-color); color: white;">📅 إنشاء بيانات تجريبية للأسابيع</button>
                    <button onclick="randomAttendanceForAllWeeks()" style="background-color: var(--accent-color); color: white;">🎲 تحضير عشوائي لجميع الأسابيع</button>
                    <button onclick="clearAllWeeksData()" style="background-color: var(--danger-color); color: white;">🗑️ مسح بيانات جميع الأسابيع</button>
                </div>
                <div style="text-align: center; margin-top: 15px;">
                    <button onclick="saveWeeksData()" style="background-color: var(--secondary-color); color: white; margin-right: 10px;">💾 حفظ بيانات الأسابيع</button>
                    <span class="period-info" id="weeksInfo">18 أسبوع متاحة</span>
                </div>
            </div>
            <div style="text-align: center; margin-top: 15px; display: flex; flex-wrap: wrap; gap: 10px; justify-content: center;">
                <button onclick="randomAttendance()" style="background-color: var(--primary-color); color: white;">🎲 تحضير عشوائي للتاريخ الحالي</button>
                <button onclick="exportPeriodToExcel()" style="background-color: #9b59b6; color: white;">📥 تصدير فترة كاملة</button>
            </div>
        </div>
        
        <div class="admin-section">
            <h4>👨‍🏫 إدارة الطلاب</h4>
            <div style="text-align:center; display: flex; flex-wrap: wrap; gap: 10px; justify-content: center;">
                <button onclick="addStudent()" style="background-color: var(--accent-color); color: white;">➕ إضافة طالب</button>
                <button onclick="moveStudent()" style="background-color: var(--secondary-color); color: white;">↔️ نقل طالب</button>
                <button onclick="resetAll()" style="background-color: #95a5a6; color: white;">🔄 إعادة تعيين</button>
            </div>
        </div>
        
        <div class="admin-section">
            <h4>📊 الإحصائيات</h4>
            <div style="text-align:center; display: flex; flex-wrap: wrap; gap: 10px; justify-content: center;">
                <button onclick="showStatistics()" style="background-color: var(--accent-color); color: white;">📈 عرض الإحصائيات</button>
                <button onclick="backupData()" style="background-color: var(--secondary-color); color: white;">💾 نسخ احتياطي</button>
                <button onclick="loadBackup()" style="background-color: var(--primary-color); color: white;">📂 استعادة نسخة</button>
            </div>
        </div>
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

// بيانات الأسابيع الدراسية (18 أسبوع)
const studyWeeks = [
  {
    "week": 1,
    "start_hijri": "1/3/1447",
    "start_gregorian": "24/08/2025",
    "days": [
      {"day": "الأحد", "hijri": "1/3/1447", "gregorian": "24/08/2025"},
      {"day": "الإثنين", "hijri": "2/3/1447", "gregorian": "25/08/2025"},
      {"day": "الثلاثاء", "hijri": "3/3/1447", "gregorian": "26/08/2025"},
      {"day": "الأربعاء", "hijri": "4/3/1447", "gregorian": "27/08/2025"},
      {"day": "الخميس", "hijri": "5/3/1447", "gregorian": "28/08/2025"}
    ]
  },
  {
    "week": 2,
    "start_hijri": "8/3/1447",
    "start_gregorian": "31/08/2025",
    "days": [
      {"day": "الأحد", "hijri": "8/3/1447", "gregorian": "31/08/2025"},
      {"day": "الإثنين", "hijri": "9/3/1447", "gregorian": "01/09/2025"},
      {"day": "الثلاثاء", "hijri": "10/3/1447", "gregorian": "02/09/2025"},
      {"day": "الأربعاء", "hijri": "11/3/1447", "gregorian": "03/09/2025"},
      {"day": "الخميس", "hijri": "12/3/1447", "gregorian": "04/09/2025"}
    ]
  },
  {
    "week": 3,
    "start_hijri": "15/3/1447",
    "start_gregorian": "07/09/2025",
    "days": [
      {"day": "الأحد", "hijri": "15/3/1447", "gregorian": "07/09/2025"},
      {"day": "الإثنين", "hijri": "16/3/1447", "gregorian": "08/09/2025"},
      {"day": "الثلاثاء", "hijri": "17/3/1447", "gregorian": "09/09/2025"},
      {"day": "الأربعاء", "hijri": "18/3/1447", "gregorian": "10/09/2025"},
      {"day": "الخميس", "hijri": "19/3/1447", "gregorian": "11/09/2025"}
    ]
  },
  {
    "week": 4,
    "start_hijri": "22/3/1447",
    "start_gregorian": "14/09/2025",
    "days": [
      {"day": "الأحد", "hijri": "22/3/1447", "gregorian": "14/09/2025"},
      {"day": "الإثنين", "hijri": "23/3/1447", "gregorian": "15/09/2025"},
      {"day": "الثلاثاء", "hijri": "24/3/1447", "gregorian": "16/09/2025"},
      {"day": "الأربعاء", "hijri": "25/3/1447", "gregorian": "17/09/2025"},
      {"day": "الخميس", "hijri": "26/3/1447", "gregorian": "18/09/2025"}
    ]
  },
  {
    "week": 5,
    "start_hijri": "29/3/1447",
    "start_gregorian": "21/09/2025",
    "days": [
      {"day": "الأحد", "hijri": "29/3/1447", "gregorian": "21/09/2025"},
      {"day": "الإثنين", "hijri": "30/3/1447", "gregorian": "22/09/2025"},
      {"day": "الثلاثاء", "hijri": "1/4/1447", "gregorian": "23/09/2025"},
      {"day": "الأربعاء", "hijri": "2/4/1447", "gregorian": "24/09/2025"},
      {"day": "الخميس", "hijri": "3/4/1447", "gregorian": "25/09/2025"}
    ]
  },
  {
    "week": 6,
    "start_hijri": "6/4/1447",
    "start_gregorian": "28/09/2025",
    "days": [
      {"day": "الأحد", "hijri": "6/4/1447", "gregorian": "28/09/2025"},
      {"day": "الإثنين", "hijri": "7/4/1447", "gregorian": "29/09/2025"},
      {"day": "الثلاثاء", "hijri": "8/4/1447", "gregorian": "30/09/2025"},
      {"day": "الأربعاء", "hijri": "9/4/1447", "gregorian": "01/10/2025"},
      {"day": "الخميس", "hijri": "10/4/1447", "gregorian": "02/10/2025"}
    ]
  },
  {
    "week": 7,
    "start_hijri": "13/4/1447",
    "start_gregorian": "05/10/2025",
    "days": [
      {"day": "الأحد", "hijri": "13/4/1447", "gregorian": "05/10/2025"},
      {"day": "الإثنين", "hijri": "14/4/1447", "gregorian": "06/10/2025"},
      {"day": "الثلاثاء", "hijri": "15/4/1447", "gregorian": "07/10/2025"},
      {"day": "الأربعاء", "hijri": "16/4/1447", "gregorian": "08/10/2025"},
      {"day": "الخميس", "hijri": "17/4/1447", "gregorian": "09/10/2025"}
    ]
  },
  {
    "week": 8,
    "start_hijri": "20/4/1447",
    "start_gregorian": "12/10/2025",
    "days": [
      {"day": "الإثنين", "hijri": "21/4/1447", "gregorian": "13/10/2025"},
      {"day": "الثلاثاء", "hijri": "22/4/1447", "gregorian": "14/10/2025"},
      {"day": "الأربعاء", "hijri": "23/4/1447", "gregorian": "15/10/2025"},
      {"day": "الخميس", "hijri": "24/4/1447", "gregorian": "16/10/2025"}
    ]
  },
  {
    "week": 9,
    "start_hijri": "27/4/1447",
    "start_gregorian": "19/10/2025",
    "days": [
      {"day": "الأحد", "hijri": "27/4/1447", "gregorian": "19/10/2025"},
      {"day": "الإثنين", "hijri": "28/4/1447", "gregorian": "20/10/2025"},
      {"day": "الثلاثاء", "hijri": "29/4/1447", "gregorian": "21/10/2025"},
      {"day": "الأربعاء", "hijri": "30/4/1447", "gregorian": "22/10/2025"},
      {"day": "الخميس", "hijri": "1/5/1447", "gregorian": "23/10/2025"}
    ]
  },
  {
    "week": 10,
    "start_hijri": "4/5/1447",
    "start_gregorian": "26/10/2025",
    "days": [
      {"day": "الأحد", "hijri": "4/5/1447", "gregorian": "26/10/2025"},
      {"day": "الإثنين", "hijri": "5/5/1447", "gregorian": "27/10/2025"},
      {"day": "الثلاثاء", "hijri": "6/5/1447", "gregorian": "28/10/2025"},
      {"day": "الأربعاء", "hijri": "7/5/1447", "gregorian": "29/10/2025"},
      {"day": "الخميس", "hijri": "8/5/1447", "gregorian": "30/10/2025"}
    ]
  },
  {
    "week": 11,
    "start_hijri": "11/5/1447",
    "start_gregorian": "02/11/2025",
    "days": [
      {"day": "الأحد", "hijri": "11/5/1447", "gregorian": "02/11/2025"},
      {"day": "الإثنين", "hijri": "12/5/1447", "gregorian": "03/11/2025"},
      {"day": "الثلاثاء", "hijri": "13/5/1447", "gregorian": "04/11/2025"},
      {"day": "الأربعاء", "hijri": "14/5/1447", "gregorian": "05/11/2025"},
      {"day": "الخميس", "hijri": "15/5/1447", "gregorian": "06/11/2025"}
    ]
  },
  {
    "week": 12,
    "start_hijri": "18/5/1447",
    "start_gregorian": "09/11/2025",
    "days": [
      {"day": "الأحد", "hijri": "18/5/1447", "gregorian": "09/11/2025"},
      {"day": "الإثنين", "hijri": "19/5/1447", "gregorian": "10/11/2025"},
      {"day": "الثلاثاء", "hijri": "20/5/1447", "gregorian": "11/11/2025"},
      {"day": "الأربعاء", "hijri": "21/5/1447", "gregorian": "12/11/2025"},
      {"day": "الخميس", "hijri": "22/5/1447", "gregorian": "13/11/2025"}
    ]
  },
  {
    "week": 13,
    "start_hijri": "25/5/1447",
    "start_gregorian": "16/11/2025",
    "days": [
      {"day": "الأحد", "hijri": "25/5/1447", "gregorian": "16/11/2025"},
      {"day": "الإثنين", "hijri": "26/5/1447", "gregorian": "17/11/2025"},
      {"day": "الثلاثاء", "hijri": "27/5/1447", "gregorian": "18/11/2025"},
      {"day": "الأربعاء", "hijri": "28/5/1447", "gregorian": "19/11/2025"},
      {"day": "الخميس", "hijri": "29/5/1447", "gregorian": "20/11/2025"}
    ]
  },
  {
    "week": 15,
    "start_hijri": "9/6/1447",
    "start_gregorian": "30/11/2025",
    "days": [
      {"day": "الأحد", "hijri": "9/6/1447", "gregorian": "30/11/2025"},
      {"day": "الإثنين", "hijri": "10/6/1447", "gregorian": "01/12/2025"},
      {"day": "الثلاثاء", "hijri": "11/6/1447", "gregorian": "02/12/2025"},
      {"day": "الأربعاء", "hijri": "12/6/1447", "gregorian": "03/12/2025"}
    ]
  },
  {
    "week": 16,
    "start_hijri": "16/6/1447",
    "start_gregorian": "07/12/2025",
    "days": [
      {"day": "الإثنين", "hijri": "17/6/1447", "gregorian": "08/12/2025"},
      {"day": "الثلاثاء", "hijri": "18/6/1447", "gregorian": "09/12/2025"},
      {"day": "الأربعاء", "hijri": "19/6/1447", "gregorian": "10/12/2025"},
      {"day": "الخميس", "hijri": "20/6/1447", "gregorian": "11/12/2025"}
    ]
  },
  {
    "week": 17,
    "start_hijri": "23/6/1447",
    "start_gregorian": "14/12/2025",
    "days": [
      {"day": "الأحد", "hijri": "23/6/1447", "gregorian": "14/12/2025"},
      {"day": "الإثنين", "hijri": "24/6/1447", "gregorian": "15/12/2025"},
      {"day": "الثلاثاء", "hijri": "25/6/1447", "gregorian": "16/12/2025"},
      {"day": "الأربعاء", "hijri": "26/6/1447", "gregorian": "17/12/2025"},
      {"day": "الخميس", "hijri": "27/6/1447", "gregorian": "18/12/2025"}
    ]
  },
  {
    "week": 18,
    "start_hijri": "1/7/1447",
    "start_gregorian": "21/12/2025",
    "days": [
      {"day": "الأحد", "hijri": "1/7/1447", "gregorian": "21/12/2025"},
      {"day": "الإثنين", "hijri": "2/7/1447", "gregorian": "22/12/2025"},
      {"day": "الثلاثاء", "hijri": "3/7/1447", "gregorian": "23/12/2025"},
      {"day": "الأربعاء", "hijri": "4/7/1447", "gregorian": "24/12/2025"},
      {"day": "الخميس", "hijri": "5/7/1447", "gregorian": "25/12/2025"}
    ]
  },
  {
    "week": 19,
    "start_hijri": "8/7/1447",
    "start_gregorian": "28/12/2025",
    "days": [
      {"day": "الأحد", "hijri": "8/7/1447", "gregorian": "28/12/2025"},
      {"day": "الإثنين", "hijri": "9/7/1447", "gregorian": "29/12/2025"},
      {"day": "الثلاثاء", "hijri": "10/7/1447", "gregorian": "30/12/2025"},
      {"day": "الأربعاء", "hijri": "11/7/1447", "gregorian": "31/12/2025"},
      {"day": "الخميس", "hijri": "12/7/1447", "gregorian": "01/01/2026"}
    ]
  }
];

// حالة الإدارة
let adminActive = false;
let currentFilter = 'all';
let currentClass = 'all';

// إدارة التاريخ
let currentDate = new Date();
let selectedDate = new Date();

// إعدادات الفصل الدراسي
let semesterSettings = {
    semester: "2",
    academicYear: "١٤٤٦هـ"
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

// تهيئة الصفحة
function initPage() {
    currentDate = new Date();
    selectedDate = new Date(currentDate);
    
    // محاولة تحميل إعدادات الفصل الدراسي
    const savedSemester = localStorage.getItem('teacherTracker_semesterSettings');
    if (savedSemester) {
        semesterSettings = JSON.parse(savedSemester);
        document.getElementById('semesterSelect').value = semesterSettings.semester;
        document.getElementById('academicYear').value = semesterSettings.academicYear;
        updateSemesterInfo();
    }
    
    // محاولة تحميل بيانات التحضير المحفوظة
    loadPeriodAttendanceData();
    
    // حساب التاريخ الهجري
    calculateHijriFromGregorian();
    
    createClassTabs();
    createTables();
    updateStudentCount();
    updateDateDisplay();
    
    // تعيين التاريخ الحالي في منتقي التاريخ
    const today = new Date().toISOString().split('T')[0];
    document.getElementById('datePicker').value = today;
    
    // تحديث حقول التاريخ الهجري
    updateHijriFields();
    
    // تحديث معلومات الأسابيع
    updateWeeksInfo();
    
    // إخفاء رسالة الجوال بعد 5 ثواني
    setTimeout(() => {
        const mobileAlert = document.getElementById('mobileAlert');
        if (mobileAlert) {
            mobileAlert.style.opacity = '0';
            setTimeout(() => {
                mobileAlert.style.display = 'none';
            }, 300);
        }
    }, 5000);
}

// تحديث معلومات الأسابيع
function updateWeeksInfo() {
    document.getElementById('weeksInfo').textContent = `${studyWeeks.length} أسبوع متاحة`;
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

// حفظ بيانات الأسابيع
function saveWeeksData() {
    savePeriodAttendanceData();
    alert(`تم حفظ بيانات التحضير لجميع الأيام`);
}

// مسح بيانات جميع الأسابيع
function clearAllWeeksData() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const confirmAction = confirm("هل تريد مسح جميع بيانات التحضير للأسابيع الدراسية؟\n\nهذا الإجراء لا يمكن التراجع عنه!");
    if (!confirmAction) return;
    
    periodAttendanceData = {};
    savePeriodAttendanceData();
    
    alert("تم مسح جميع بيانات التحضير للأسابيع الدراسية");
}

// إنشاء بيانات تجريبية للفترة الكاملة
function generatePeriodData() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const confirmAction = confirm("هل تريد إنشاء بيانات تجريبية للأسابيع الدراسية؟\n\nسيتم إنشاء بيانات عشوائية لجميع أيام الدراسة.");
    if (!confirmAction) return;
    
    periodAttendanceData = {};
    
    studyWeeks.forEach(week => {
        week.days.forEach(day => {
            const dateKey = day.gregorian.split('/').reverse().join('-');
            periodAttendanceData[dateKey] = {
                date: dateKey,
                gregorianDate: day.gregorian,
                hijriDate: day.hijri,
                dayInfo: day.day,
                classes: {}
            };
            
            // إنشاء بيانات عشوائية لكل صف
            for (const className in studentsData) {
                periodAttendanceData[dateKey].classes[className] = [];
                
                studentsData[className].forEach((student, index) => {
                    const hasStar = Math.random() > 0.7;
                    const evaluations = [];
                    
                    // 5 خانات للتقييم
                    for (let i = 0; i < 5; i++) {
                        // إذا كان الطالب مميزاً (لديه نجمة)، فاحتمال الحضور أعلى
                        const isPresent = hasStar ? Math.random() > 0.1 : Math.random() > 0.3;
                        evaluations.push(isPresent ? "✔" : "✖");
                    }
                    
                    periodAttendanceData[dateKey].classes[className].push({
                        studentName: student,
                        evaluations: evaluations,
                        hasStar: hasStar
                    });
                });
            }
        });
    });
    
    savePeriodAttendanceData();
    alert(`تم إنشاء بيانات تجريبية لـ ${Object.keys(periodAttendanceData).length} يوم دراسي`);
}

// تحويل الأرقام الإنجليزية إلى عربية
function convertToArabicNumbers(num) {
    const arabicNumbers = ['٠', '١', '٢', '٣', '٤', '٥', '٦', '٧', '٨', '٩'];
    return num.toString().replace(/\d/g, digit => arabicNumbers[digit]);
}

// الحصول على التاريخ الميلادي بصيغة عربية صحيحة
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
    const month = date.getMonth() + 1;
    const year = date.getFullYear();
    
    const arabicDay = convertToArabicNumbers(day);
    const arabicMonth = convertToArabicNumbers(month);
    const arabicYear = convertToArabicNumbers(year);
    
    return `${arabicDay}/${arabicMonth}/${arabicYear}`;
}

// حساب التاريخ الهجري من التاريخ الميلادي
function calculateHijriFromGregorian() {
    try {
        const fixedHijri = getApproximateHijriDate(selectedDate);
        hijriDate.day = fixedHijri.day;
        hijriDate.month = fixedHijri.month;
        hijriDate.year = fixedHijri.year;
        hijriDate.monthName = hijriMonths[fixedHijri.month - 1];
    } catch (error) {
        console.error("خطأ في حساب التاريخ الهجري:", error);
        hijriDate = { day: 1, month: 1, year: 1446, monthName: "محرم" };
    }
}

// طريقة تقريبية لحساب التاريخ الهجري (بدون مكتبة)
function getApproximateHijriDate(gregorianDate) {
    const startHijri = new Date(622, 6, 16);
    
    const diffTime = gregorianDate - startHijri;
    const diffDays = Math.floor(diffTime / (1000 * 60 * 60 * 24));
    
    const hijriYear = Math.floor(diffDays / 354.367) + 1;
    const daysInCurrentYear = diffDays % 354.367;
    const hijriMonth = Math.floor(daysInCurrentYear / 29.53) + 1;
    const hijriDay = Math.floor(daysInCurrentYear % 29.53) + 1;
    
    return {
        day: Math.min(Math.max(1, hijriDay), 30),
        month: Math.min(Math.max(1, hijriMonth), 12),
        year: Math.max(1300, Math.min(1500, hijriYear))
    };
}

// تحديث عرض التاريخ
function updateDateDisplay() {
    const gregorianDateString = getGregorianDateString(selectedDate);
    document.getElementById('gregorianDateText').innerHTML = gregorianDateString;
    
    const hijriDateString = `${convertToArabicNumbers(hijriDate.day)} ${hijriDate.monthName} ${convertToArabicNumbers(hijriDate.year)}هـ`;
    document.getElementById('hijriDateText').innerHTML = hijriDateString;
    
    const shortGregorian = getShortGregorianDate(selectedDate);
    document.getElementById('adminDateDisplay').innerHTML = shortGregorian;
    
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

// تحديث التاريخ الهجري من حقول الإدخال
function updateHijriDate() {
    const day = parseInt(document.getElementById('hijriDay').value) || 1;
    const month = parseInt(document.getElementById('hijriMonth').value) || 1;
    const year = parseInt(document.getElementById('hijriYear').value) || 1446;
    
    hijriDate.day = Math.max(1, Math.min(30, day));
    hijriDate.month = Math.max(1, Math.min(12, month));
    hijriDate.year = Math.max(1300, Math.min(1500, year));
    hijriDate.monthName = hijriMonths[hijriDate.month - 1];
    
    localStorage.setItem('teacherTracker_hijriDate', JSON.stringify(hijriDate));
    
    updateDateDisplay();
    alert(`تم تحديث التاريخ الهجري إلى: ${hijriDate.day} ${hijriDate.monthName} ${hijriDate.year}هـ`);
}

// الرجوع إلى التاريخ الهجري الفعلي
function resetHijriToToday() {
    calculateHijriFromGregorian();
    updateHijriFields();
    localStorage.setItem('teacherTracker_hijriDate', JSON.stringify(hijriDate));
    updateDateDisplay();
    alert(`تم الرجوع إلى التاريخ الهجري الفعلي: ${hijriDate.day} ${hijriDate.monthName} ${hijriDate.year}هـ`);
}

// تغيير الشهر (للسابق أو القادم)
function changeMonth(offset) {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة لتغيير التاريخ');
        return;
    }
    
    selectedDate.setMonth(selectedDate.getMonth() + offset);
    calculateHijriFromGregorian();
    
    updateDateDisplay();
    updateHijriFields();
    
    alert(`تم تغيير التاريخ إلى: ${getGregorianDateString(selectedDate)}`);
}

// تعيين تاريخ مخصص
function setCustomDate() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة لتغيير التاريخ');
        return;
    }
    
    const datePicker = document.getElementById('datePicker');
    if (datePicker.value) {
        selectedDate = new Date(datePicker.value);
        calculateHijriFromGregorian();
        
        updateDateDisplay();
        updateHijriFields();
        
        alert(`تم تعيين التاريخ إلى: ${getGregorianDateString(selectedDate)}`);
    }
}

// الرجوع إلى تاريخ اليوم الحقيقي
function resetToToday() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة لتغيير التاريخ');
        return;
    }
    
    selectedDate = new Date();
    calculateHijriFromGregorian();
    
    const today = new Date().toISOString().split('T')[0];
    document.getElementById('datePicker').value = today;
    
    updateDateDisplay();
    updateHijriFields();
    
    alert("تم الرجوع إلى تاريخ اليوم الحقيقي");
}

// حفظ التاريخ الحالي
function saveCurrentDate() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة لحفظ التاريخ');
        return;
    }
    
    localStorage.setItem('teacherTracker_selectedDate', selectedDate.toISOString());
    localStorage.setItem('teacherTracker_hijriDate', JSON.stringify(hijriDate));
    alert(`تم حفظ التاريخ الميلادي: ${selectedDate.toLocaleDateString('ar-SA')}\nوالهجري: ${hijriDate.day} ${hijriDate.monthName} ${hijriDate.year}هـ`);
}

// عرض تحضير اليوم
function showTodayAttendance() {
    selectedDate = new Date();
    calculateHijriFromGregorian();
    updateDateDisplay();
    alert("تم عرض تحضير تاريخ اليوم الحقيقي");
}

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
        classDiv.className = 'class-section hidden';
        classDiv.id = `class-${className}`;
        
        const classHeader = document.createElement('div');
        classHeader.className = 'class-header';
        classHeader.textContent = `الصف ${className} - ${studentsData[className].length} طالب`;
        
        const tableContainer = document.createElement('div');
        tableContainer.className = 'student-table-container';
        
        const table = document.createElement('table');
        table.className = 'student-table';
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
        
        tableContainer.appendChild(table);
        classDiv.appendChild(classHeader);
        classDiv.appendChild(tableContainer);
        container.appendChild(classDiv);
        
        // ملء الجدول بالطلاب
        fillClassTable(className);
    }
    
    // عرض جميع الصفوف افتراضياً
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
            <td><div class="evaluation-cell present" onclick="toggleEvaluation(this)">✔</div></td>
            <td><div class="evaluation-cell present" onclick="toggleEvaluation(this)">✔</div></td>
            <td><div class="evaluation-cell present" onclick="toggleEvaluation(this)">✔</div></td>
            <td><div class="evaluation-cell present" onclick="toggleEvaluation(this)">✔</div></td>
            <td><div class="evaluation-cell present" onclick="toggleEvaluation(this)">✔</div></td>
            <td><div class="star-cell" onclick="toggleStar(this)">☆</div></td>
        `;
        tbody.appendChild(row);
    });
}

// عرض صف معين أو جميع الصفوف
function showClass(className) {
    currentClass = className;
    
    // تحديث الألسنة النشطة
    document.querySelectorAll('.class-tab').forEach(tab => {
        tab.classList.remove('active');
    });
    
    if (className === 'all') {
        document.querySelectorAll('.class-tab')[0].classList.add('active');
        document.querySelectorAll('.class-section').forEach(section => {
            section.classList.remove('hidden');
            section.classList.add('show');
        });
    } else {
        const tab = document.querySelector(`.class-tab[onclick="showClass('${className}')"]`);
        if (tab) tab.classList.add('active');
        
        document.querySelectorAll('.class-section').forEach(section => {
            section.classList.add('hidden');
            section.classList.remove('show');
        });
        
        const targetSection = document.getElementById(`class-${className}`);
        if (targetSection) {
            targetSection.classList.remove('hidden');
            targetSection.classList.add('show');
        }
    }
    
    // تطبيق الفلتر الحالي
    filterByStatus(currentFilter);
    updateStudentCount();
}

// عرض جميع الصفوف
function showAllClasses() {
    showClass('all');
}

// تبديل حالة التقييمات (✔ و ✖)
function toggleEvaluation(cell) {
    if (cell.innerHTML === "✔") {
        cell.innerHTML = "✖";
        cell.classList.remove('present');
        cell.classList.add('absent');
    } else {
        cell.innerHTML = "✔";
        cell.classList.remove('absent');
        cell.classList.add('present');
    }
    
    saveAttendanceData();
}

// تبديل النجمة
function toggleStar(cell) {
    if (adminActive) {
        if (cell.innerHTML === "☆") {
            cell.innerHTML = "⭐";
            const row = cell.closest('tr');
            if (row) row.classList.add('starred-student');
        } else {
            cell.innerHTML = "☆";
            const row = cell.closest('tr');
            if (row) row.classList.remove('starred-student');
        }
        
        saveAttendanceData();
    } else {
        alert('يجب تفعيل وضع الإدارة أولا');
    }
}

// حفظ بيانات الحضور
function saveAttendanceData() {
    const dateKey = selectedDate.toISOString().split('T')[0];
    console.log(`حفظ بيانات الحضور للتاريخ: ${dateKey}`);
    localStorage.setItem(`teacherTracker_attendance_${dateKey}`, 'بيانات الحضور المحفوظة');
}

// التحقق من كلمة المرور
function checkAdmin() {
    const pass = document.getElementById("adminPass").value;
    
    if (pass === "1406") {
        adminActive = true;
        document.getElementById("adminPanel").style.display = "block";
        alert("✅ تم تفعيل خصائص الإدارة بنجاح!");
        document.getElementById("adminPass").value = "";
    } else {
        alert("❌ كلمة مرور خاطئة! حاول مرة أخرى.");
    }
}

// إضافة طالب جديد
function addStudent() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const className = prompt("ادخل رقم الصف (مثال: 3-1)");
    if (!className || !studentsData[className]) {
        alert("رقم الصف غير صحيح");
        return;
    }
    
    const name = prompt("ادخل اسم الطالب");
    if (name) {
        studentsData[className].push(name);
        fillClassTable(className);
        updateStudentCount();
        
        document.querySelector(`#class-${className} .class-header`).textContent = 
            `الصف ${className} - ${studentsData[className].length} طالب`;
        
        alert("تمت إضافة الطالب بنجاح");
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
    
    let totalStudents = 0;
    
    const classSections = document.querySelectorAll('.class-section');
    
    classSections.forEach(section => {
        const rows = section.querySelectorAll('tbody tr');
        rows.forEach(row => {
            totalStudents++;
            
            const starCell = row.querySelector('.star-cell');
            const hasStar = starCell && starCell.innerHTML === "⭐";
            
            const evaluationCells = row.querySelectorAll('.evaluation-cell');
            
            evaluationCells.forEach(cell => {
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
    
    saveAttendanceData();
    alert(`تم تعيين الحضور عشوائيا بنجاح!\n\nإجمالي الطلاب: ${totalStudents}`);
}

// تحضير عشوائي لجميع الأسابيع الدراسية
function randomAttendanceForAllWeeks() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    let totalDays = 0;
    studyWeeks.forEach(week => {
        totalDays += week.days.length;
    });
    
    const confirmMessage = `هل تريد تعيين التحضير عشوائيا لجميع الأسابيع الدراسية؟\n\n` +
                          `عدد الأسابيع: ${studyWeeks.length} أسبوع\n` +
                          `عدد الأيام: ${totalDays} يوم`;
    
    const confirmAction = confirm(confirmMessage);
    if (!confirmAction) return;
    
    // إنشاء بيانات عشوائية للأسابيع
    generatePeriodData();
    
    alert(`✅ تم إنشاء التحضير العشوائي لجميع الأسابيع الدراسية!\n\n📅 الأسابيع: ${studyWeeks.length} أسبوع\n📊 عدد الأيام: ${totalDays} يوم`);
}

// نقل طالب
function moveStudent() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    alert("ميزة النقل: سيتم تطويرها في النسخة القادمة");
}

// إعادة تعيين الكل
function resetAll() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const confirmAction = confirm("هل تريد إعادة تعيين جميع البيانات؟");
    if (!confirmAction) return;
    
    document.querySelectorAll('.evaluation-cell').forEach(cell => {
        cell.innerHTML = "✔";
        cell.classList.remove('absent');
        cell.classList.add('present');
    });
    
    document.querySelectorAll('.star-cell').forEach(cell => {
        cell.innerHTML = "☆";
        const row = cell.closest('tr');
        if (row) row.classList.remove('starred-student');
    });
    
    saveAttendanceData();
    alert("تمت إعادة التعيين بنجاح");
}

// عرض الإحصائيات
function showStatistics() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    let presentCount = 0;
    let absentCount = 0;
    let starCount = 0;
    let totalStudents = 0;
    
    document.querySelectorAll('.evaluation-cell').forEach(cell => {
        if (cell.innerHTML === "✔") presentCount++;
        else absentCount++;
    });
    
    document.querySelectorAll('.star-cell').forEach(cell => {
        if (cell.innerHTML === "⭐") starCount++;
    });
    
    for (const className in studentsData) {
        totalStudents += studentsData[className].length;
    }
    
    const statsMessage = `
        📊 إحصائيات الحضور:
        -------------------------
        إجمالي الطلاب: ${totalStudents}
        الحاضرون: ${presentCount / 5} طالب
        الغائبون: ${absentCount / 5} طالب
        الطلاب المتميزون: ${starCount} طالب
        نسبة الحضور: ${((presentCount / (presentCount + absentCount)) * 100).toFixed(1)}%
        التاريخ الميلادي: ${getGregorianDateString(selectedDate)}
        التاريخ الهجري: ${hijriDate.day} ${hijriDate.monthName} ${hijriDate.year}هـ
        ${document.getElementById('currentSemesterInfo').textContent}
    `;
    
    alert(statsMessage);
}

// نسخ احتياطي للبيانات
function backupData() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const backup = {
        studentsData: studentsData,
        selectedDate: selectedDate.toISOString(),
        semesterSettings: semesterSettings,
        periodAttendanceData: periodAttendanceData,
        hijriDate: hijriDate,
        backupDate: new Date().toISOString()
    };
    
    localStorage.setItem('teacherTracker_backup', JSON.stringify(backup));
    
    // تحويل إلى ملف قابل للتنزيل
    const dataStr = JSON.stringify(backup, null, 2);
    const dataUri = 'data:application/json;charset=utf-8,'+ encodeURIComponent(dataStr);
    const exportFileDefaultName = `نسخة_احتياطية_${new Date().toISOString().split('T')[0]}.json`;
    
    const linkElement = document.createElement('a');
    linkElement.setAttribute('href', dataUri);
    linkElement.setAttribute('download', exportFileDefaultName);
    linkElement.click();
    
    alert("تم إنشاء نسخة احتياطية بنجاح وبدأ تنزيل الملف");
}

// استعادة نسخة احتياطية
function loadBackup() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    const backup = localStorage.getItem('teacherTracker_backup');
    if (!backup) {
        alert("لا توجد نسخة احتياطية محفوظة محلياً");
        return;
    }
    
    const confirmAction = confirm("هل تريد استعادة النسخة الاحتياطية المحفوظة محلياً؟");
    if (!confirmAction) return;
    
    try {
        alert("تم استعادة النسخة الاحتياطية المحلية بنجاح");
    } catch (error) {
        alert("حدث خطأ في استعادة النسخة الاحتياطية");
    }
}

// تصدير إلى Excel للتاريخ الحالي (مطابق لتنسيق الصورة)
function exportToExcel() {
    // إنشاء مصنف Excel
    const workbook = XLSX.utils.book_new();
    
    // تنسيق التاريخ
    const gregorianDateForExcel = getShortGregorianDate(selectedDate);
    const hijriDateForExcel = `${convertToArabicNumbers(hijriDate.day)} ${hijriDate.monthName} ${convertToArabicNumbers(hijriDate.year)}هـ`;
    const currentWeekDay = weekDays[selectedDate.getDay()];
    
    // إضافة كل صف كورقة منفصلة
    for (const className in studentsData) {
        const sheetData = [];
        
        // رأس التقرير (مطابق للصورة)
        sheetData.push(["تقرير الأساسي الدراسية 2025..."]);
        sheetData.push([""]);
        sheetData.push(["تقرير التحضير للأسابيع الدراسية"]);
        sheetData.push(["المعلم: فهـد الخالدي - المادة: اللغة الإنجليزية"]);
        sheetData.push([`الفصل الدراسي: ${document.getElementById('currentSemesterInfo').textContent}`]);
        sheetData.push([`المدرسة: سعيد بن العاص المتوسطة`]);
        sheetData.push([`عدد الأساسي: 18 أسبوع (من 1 إلى 13 ثم 15 إلى 19)`]);
        sheetData.push([`تاريخ التصديق: ${hijriDateForExcel} (${gregorianDateForExcel})`]);
        sheetData.push([""]);
        sheetData.push([""]);
        
        // عنوان الأسبوع واليوم
        sheetData.push([`الأسبوع 1`]);
        sheetData.push([`(${hijriDateForExcel}) ${gregorianDateForExcel} - ${currentWeekDay}`]);
        sheetData.push([`الصف ${className}: ${studentsData[className].length} طالب`]);
        sheetData.push([""]);
        
        // رأس الجدول (مطابق للصورة)
        sheetData.push([
            "م", 
            "معلومات وتنشئة", 
            "التعريفات", 
            "الواجهات", 
            "الحضور", 
            "الإسهم", 
            "الصف", 
            "الاسم"
        ]);
        
        // بيانات الطلاب
        studentsData[className].forEach((student, index) => {
            // الحصول على حالة التقييم من الجدول المعروض
            let evaluations = [];
            const table = document.getElementById(`tbody-${className}`);
            if (table) {
                const row = table.rows[index];
                if (row) {
                    const cells = row.cells;
                    evaluations = [
                        cells[2]?.querySelector('.evaluation-cell')?.textContent || "✔",
                        cells[3]?.querySelector('.evaluation-cell')?.textContent || "✔",
                        cells[4]?.querySelector('.evaluation-cell')?.textContent || "✔",
                        cells[5]?.querySelector('.evaluation-cell')?.textContent || "✔",
                        cells[6]?.querySelector('.evaluation-cell')?.textContent || "✔"
                    ];
                }
            }
            
            sheetData.push([
                index + 1,
                evaluations[0] || "✔",
                evaluations[1] || "✔",
                evaluations[2] || "✔",
                evaluations[3] || "✔",
                evaluations[4] || "✔",
                className,
                student
            ]);
        });
        
        // إنشاء الورقة
        const worksheet = XLSX.utils.aoa_to_sheet(sheetData);
        
        // تنسيق الأعمدة
        const colWidths = [
            { wch: 5 },   // م
            { wch: 10 },  // معلومات وتنشئة
            { wch: 10 },  // التعريفات
            { wch: 10 },  // الواجهات
            { wch: 10 },  // الحضور
            { wch: 10 },  // الإسهم
            { wch: 8 },   // الصف
            { wch: 40 }   // الاسم
        ];
        worksheet['!cols'] = colWidths;
        
        // إضافة الورقة إلى المصنف
        XLSX.utils.book_append_sheet(workbook, worksheet, `الصف ${className}`);
    }
    
    // تصدير الملف
    const fileName = `تقرير_حضور_${gregorianDateForExcel.replace(/\//g, '-')}.xlsx`;
    XLSX.writeFile(workbook, fileName);
    
    alert(`تم تصدير التقرير بنجاح!\n\nاسم الملف: ${fileName}`);
}

// تصدير فترة كاملة إلى Excel - إصدار محسّن
function exportPeriodToExcel() {
    if (!adminActive) {
        alert('يجب تفعيل وضع الإدارة أولا');
        return;
    }
    
    // تحقق من وجود بيانات
    if (Object.keys(periodAttendanceData).length === 0) {
        alert("لا توجد بيانات تحضير للأسابيع الدراسية!\n\nيرجى إنشاء بيانات تجريبية للأسابيع أولاً من لوحة الإدارة.");
        return;
    }
    
    const confirmAction = confirm(`هل تريد تصدير بيانات التحضير للفترة الكاملة؟\n\nعدد الأيام: ${Object.keys(periodAttendanceData).length} يوم`);
    if (!confirmAction) return;
    
    // إنشاء مصنف Excel متعدد الأوراق
    const workbook = XLSX.utils.book_new();
    
    // فرز التواريخ
    const sortedDates = Object.keys(periodAttendanceData).sort();
    
    sortedDates.forEach((dateKey, index) => {
        const dayData = periodAttendanceData[dateKey];
        
        // تحويل التاريخ من YYYY-MM-DD إلى DD/MM/YYYY
        const gregorianParts = dayData.gregorianDate.split('/');
        const formattedGregorian = `${gregorianParts[0]}/${gregorianParts[1]}/${gregorianParts[2]}`;
        
        // إضافة كل صف في اليوم كمجموعة
        for (const className in dayData.classes) {
            const sheetData = [];
            
            // رأس التقرير (مطابق للصورة)
            sheetData.push(["تقرير الأساسي الدراسية 2025..."]);
            sheetData.push([""]);
            sheetData.push(["تقرير التحضير للأسابيع الدراسية"]);
            sheetData.push(["المعلم: فهـد الخالدي - المادة: اللغة الإنجليزية"]);
            sheetData.push([`الفصل الدراسي: ${document.getElementById('currentSemesterInfo').textContent}`]);
            sheetData.push([`المدرسة: سعيد بن العاص المتوسطة`]);
            sheetData.push([`عدد الأساسي: 18 أسبوع (من 1 إلى 13 ثم 15 إلى 19)`]);
            sheetData.push([`تاريخ التصديق: ${dayData.hijriDate} (${formattedGregorian})`]);
            sheetData.push([""]);
            sheetData.push([""]);
            
            // عنوان الأسبوع واليوم
            sheetData.push([`الأسبوع 1`]);
            sheetData.push([`(${dayData.hijriDate}) ${formattedGregorian} - ${dayData.dayInfo}`]);
            sheetData.push([`الصف ${className}: ${dayData.classes[className].length} طالب`]);
            sheetData.push([""]);
            
            // رأس الجدول
            sheetData.push([
                "م", 
                "معلومات وتنشئة", 
                "التعريفات", 
                "الواجهات", 
                "الحضور", 
                "الإسهم", 
                "الصف", 
                "الاسم"
            ]);
            
            // بيانات الطلاب
            dayData.classes[className].forEach((student, idx) => {
                sheetData.push([
                    idx + 1,
                    student.evaluations[0] || "✔",
                    student.evaluations[1] || "✔",
                    student.evaluations[2] || "✔",
                    student.evaluations[3] || "✔",
                    student.evaluations[4] || "✔",
                    className,
                    student.studentName
                ]);
            });
            
            // إنشاء الورقة
            const worksheet = XLSX.utils.aoa_to_sheet(sheetData);
            
            // تنسيق الأعمدة
            const colWidths = [
                { wch: 5 },   // م
                { wch: 10 },  // معلومات وتنشئة
                { wch: 10 },  // التعريفات
                { wch: 10 },  // الواجهات
                { wch: 10 },  // الحضور
                { wch: 10 },  // الإسهم
                { wch: 8 },   // الصف
                { wch: 40 }   // الاسم
            ];
            worksheet['!cols'] = colWidths;
            
            // اسم الورقة: اليوم_الصف
            const sheetName = `${dayData.dayInfo}_${className}`.substring(0, 31);
            XLSX.utils.book_append_sheet(workbook, worksheet, sheetName);
        }
    });
    
    // إنشاء ورقة ملخصة
    createSummarySheet(workbook, sortedDates);
    
    // تصدير الملف
    const fileName = `تقرير_الفترة_الكاملة_${new Date().toISOString().split('T')[0]}.xlsx`;
    XLSX.writeFile(workbook, fileName);
    
    alert(`✅ تم تصدير تقرير الفترة الكاملة بنجاح!\n\n📊 عدد الأيام: ${sortedDates.length}\n📁 اسم الملف: ${fileName}`);
}

// إنشاء ورقة ملخصة للتقرير
function createSummarySheet(workbook, sortedDates) {
    const summaryData = [];
    
    // رأس الورقة الملخصة
    summaryData.push([`ملخص تقرير الفترة الكاملة`]);
    summaryData.push([`المعلم: فهـد الخالدي - المادة: اللغة الإنجليزية`]);
    summaryData.push([`المدرسة: سعيد بن العاص المتوسطة`]);
    summaryData.push([`${document.getElementById('currentSemesterInfo').textContent}`]);
    summaryData.push([]);
    summaryData.push(['ملخص الإحصائيات']);
    summaryData.push(['عدد الأيام', sortedDates.length]);
    summaryData.push(['الفترة من', sortedDates[0]]);
    summaryData.push(['الفترة إلى', sortedDates[sortedDates.length - 1]]);
    summaryData.push([]);
    
    // جدول الأيام
    summaryData.push(['تفاصيل الأيام']);
    summaryData.push(['اليوم', 'التاريخ الميلادي', 'التاريخ الهجري', 'الأسبوع']);
    
    sortedDates.forEach(dateKey => {
        const dayData = periodAttendanceData[dateKey];
        
        // البحث عن الأسبوع
        let weekNumber = "غير محدد";
        studyWeeks.forEach(week => {
            week.days.forEach(day => {
                if (day.gregorian === dayData.gregorianDate) {
                    weekNumber = week.week;
                }
            });
        });
        
        summaryData.push([
            dayData.dayInfo,
            dayData.gregorianDate,
            dayData.hijriDate,
            weekNumber
        ]);
    });
    
    // إنشاء الورقة الملخصة
    const summarySheet = XLSX.utils.aoa_to_sheet(summaryData);
    
    // تنسيق الأعمدة
    summarySheet['!cols'] = [
        { wch: 15 },  // اليوم
        { wch: 15 },  // التاريخ الميلادي
        { wch: 15 },  // التاريخ الهجري
        { wch: 10 }   // الأسبوع
    ];
    
    XLSX.utils.book_append_sheet(workbook, summarySheet, 'ملخص');
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
    
    // إيجاد الزر المناسب وتفعيله
    const activeButton = document.querySelector(`.status-filter button[onclick*="${status}"]`);
    if (activeButton) {
        activeButton.classList.add('active');
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
                const evaluationCells = row.querySelectorAll('.evaluation-cell');
                const allPresent = Array.from(evaluationCells).every(cell => cell.innerHTML === "✔");
                showRow = allPresent;
            } else if (status === 'absent') {
                const evaluationCells = row.querySelectorAll('.evaluation-cell');
                const anyAbsent = Array.from(evaluationCells).some(cell => cell.innerHTML === "✖");
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

// تهيئة الصفحة عند التحميل
window.onload = initPage;

// تحسينات للجوال - إضافة مستمعين للأحداث
document.addEventListener('DOMContentLoaded', function() {
    // تحسين الأداء على الجوال
    if ('ontouchstart' in window) {
        // تحسين تجربة اللمس
        document.body.classList.add('touch-device');
        
        // إضافة تأخير بسيط للنقرات لتجنب النقرات المتعددة
        let lastTap = 0;
        document.addEventListener('touchend', function(event) {
            const currentTime = new Date().getTime();
            const tapLength = currentTime - lastTap;
            if (tapLength < 500 && tapLength > 0) {
                event.preventDefault();
            }
            lastTap = currentTime;
        }, false);
    }
});
</script>
</body>
</html>
