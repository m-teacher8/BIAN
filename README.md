<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منصة بيانات معلمي الرياضيات</title>
    <style>
        :root {
            --primary: #3498db;
            --primary-dark: #2980b9;
            --secondary: #2ecc71;
            --dark: #2c3e50;
            --light: #ecf0f1;
            --gray: #bdc3c7;
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            color: #333;
            line-height: 1.6;
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1000px;
            margin: 0 auto;
        }
        
        header {
            text-align: center;
            margin-bottom: 30px;
            padding: 20px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        
        h1 {
            color: var(--dark);
            margin-bottom: 10px;
            font-size: 2.2rem;
        }
        
        .subtitle {
            color: #7f8c8d;
            font-size: 1.1rem;
        }
        
        .content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }
        
        @media (max-width: 768px) {
            .content {
                grid-template-columns: 1fr;
            }
        }
        
        .form-section, .data-section {
            background: white;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        
        .section-title {
            color: var(--dark);
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--primary);
            font-size: 1.5rem;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: var(--dark);
        }
        
        input, select {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid var(--gray);
            border-radius: 5px;
            font-size: 16px;
            transition: border 0.3s;
        }
        
        input:focus, select:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 2px rgba(52, 152, 219, 0.2);
        }
        
        button {
            background: var(--primary);
            color: white;
            border: none;
            padding: 14px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 600;
            width: 100%;
            transition: background 0.3s;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }
        
        button:hover {
            background: var(--primary-dark);
        }
        
        button:disabled {
            background: var(--gray);
            cursor: not-allowed;
        }
        
        .message {
            padding: 12px;
            border-radius: 5px;
            margin-top: 20px;
            display: none;
            text-align: center;
        }
        
        .success {
            background: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }
        
        .error {
            background: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 15px;
        }
        
        th, td {
            border: 1px solid #ddd;
            padding: 12px;
            text-align: center;
        }
        
        th {
            background-color: #f2f2f2;
            font-weight: 600;
        }
        
        tr:nth-child(even) {
            background-color: #f9f9f9;
        }
        
        .empty-data {
            text-align: center;
            padding: 20px;
            color: #7f8c8d;
        }
        
        .stats {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin-top: 20px;
        }
        
        .stat-card {
            background: var(--light);
            padding: 15px;
            border-radius: 8px;
            text-align: center;
        }
        
        .stat-value {
            font-size: 1.8rem;
            font-weight: bold;
            color: var(--primary);
        }
        
        .stat-label {
            font-size: 0.9rem;
            color: #7f8c8d;
        }
        
        .actions {
            display: flex;
            gap: 10px;
            margin-top: 20px;
        }
        
        .actions button {
            flex: 1;
        }
        
        .btn-secondary {
            background: #95a5a6;
        }
        
        .btn-secondary:hover {
            background: #7f8c8d;
        }
        
        footer {
            text-align: center;
            margin-top: 30px;
            color: #7f8c8d;
            font-size: 0.9rem;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>منصة بيانات معلمي مادة الرياضيات</h1>
            <p class="subtitle">أدخل بيانات المعلمين واحصل على تقارير فورية</p>
        </header>
        
        <div class="content">
            <section class="form-section">
                <h2 class="section-title">إدخال بيانات المعلم</h2>
                <form id="teacherForm">
                    <div class="form-group">
                        <label for="name">الاسم الكامل:</label>
                        <input type="text" id="name" name="name" required placeholder="أدخل الاسم الكامل">
                    </div>
                    
                    <div class="form-group">
                        <label for="class">الصف الذي تدرسه:</label>
                        <select id="class" name="class" required>
                            <option value="">اختر الصف</option>
                            <option value="الصف الأول">الصف الأول</option>
                            <option value="الصف الثاني">الصف الثاني</option>
                            <option value="الصف الثالث">الصف الثالث</option>
                            <option value="الصف الرابع">الصف الرابع</option>
                            <option value="الصف الخامس">الصف الخامس</option>
                            <option value="الصف السادس">الصف السادس</option>
                            <option value="الصف السابع">الصف السابع</option>
                            <option value="الصف الثامن">الصف الثامن</option>
                            <option value="الصف التاسع">الصف التاسع</option>
                            <option value="الصف العاشر">الصف العاشر</option>
                            <option value="الصف الحادي عشر">الصف الحادي عشر</option>
                            <option value="الصف الثاني عشر">الصف الثاني عشر</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="specialization">التخصص:</label>
                        <input type="text" id="specialization" name="specialization" required placeholder="أدخل التخصص">
                    </div>
                    
                    <button type="submit" id="submitBtn">
                        <span>إرسال البيانات</span>
                    </button>
                </form>
                
                <div id="message" class="message"></div>
            </section>
            
            <section class="data-section">
                <h2 class="section-title">بيانات المعلمين المسجلين</h2>
                
                <div class="stats">
                    <div class="stat-card">
                        <div class="stat-value" id="totalTeachers">0</div>
                        <div class="stat-label">إجمالي المعلمين</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value" id="uniqueClasses">0</div>
                        <div class="stat-label">صفوف مختلفة</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-value" id="uniqueSpecializations">0</div>
                        <div class="stat-label">تخصصات مختلفة</div>
                    </div>
                </div>
                
                <div class="table-container">
                    <table id="teachersTable">
                        <thead>
                            <tr>
                                <th>الاسم</th>
                                <th>الصف</th>
                                <th>التخصص</th>
                                <th>تاريخ الإرسال</th>
                            </tr>
                        </thead>
                        <tbody id="teachersTableBody">
                            <tr>
                                <td colspan="4" class="empty-data">لا توجد بيانات متاحة</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                
                <div class="actions">
                    <button id="refreshBtn" class="btn-secondary">تحديث البيانات</button>
                    <button id="exportBtn">تصدير إلى Excel</button>
                </div>
            </section>
        </div>
        
        <footer>
            <p>© 2023 منصة بيانات معلمي الرياضيات. جميع الحقوق محفوظة.</p>
        </footer>
    </div>

    <script>
        // بيانات تجريبية (سيتم استبدالها بالاتصال مع Google Sheets)
        let teachersData = [
            { name: "أحمد محمد", class: "الصف العاشر", specialization: "رياضيات", timestamp: "2023-10-15" },
            { name: "فاطمة عبدالله", class: "الصف السادس", specialization: "رياضيات تطبيقية", timestamp: "2023-10-14" },
            { name: "خالد سعيد", class: "الصف الثاني عشر", specialization: "إحصاء", timestamp: "2023-10-13" }
        ];
        
        // عناصر DOM
        const teacherForm = document.getElementById('teacherForm');
        const submitBtn = document.getElementById('submitBtn');
        const messageDiv = document.getElementById('message');
        const teachersTableBody = document.getElementById('teachersTableBody');
        const refreshBtn = document.getElementById('refreshBtn');
        const exportBtn = document.getElementById('exportBtn');
        const totalTeachersEl = document.getElementById('totalTeachers');
        const uniqueClassesEl = document.getElementById('uniqueClasses');
        const uniqueSpecializationsEl = document.getElementById('uniqueSpecializations');
        
        // استبدل هذا الرابط برابط النموذج الخاص بك في Google Apps Script
        const SCRIPT_URL = "https://script.google.com/macros/s/AKfycbztp7yPZrbbfPjHm5JWhLC8T5uwGiXDLG0N4SRhVU23vEeYYuU6C94JN-e6NnQPwSYL/exec";
        
        // إرسال النموذج
        teacherForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            const formData = new FormData(teacherForm);
            const data = {
                name: formData.get('name'),
                class: formData.get('class'),
                specialization: formData.get('specialization')
            };
            
            // عرض حالة التحميل
            submitBtn.disabled = true;
            submitBtn.innerHTML = '<span>جاري الإرسال...</span>';
            
            // في بيئة حقيقية، سنستخدم fetch لإرسال البيانات إلى Google Sheets
            // fetch(SCRIPT_URL, {
            //     method: 'POST',
            //     headers: {
            //         'Content-Type': 'application/json',
            //     },
            //     body: JSON.stringify(data)
            // })
            
            // لمثالنا، سنستخدم محاكاة
            setTimeout(() => {
                // إضافة البيانات الجديدة
                const timestamp = new Date().toLocaleDateString('ar-SA');
                teachersData.unshift({
                    name: data.name,
                    class: data.class,
                    specialization: data.specialization,
                    timestamp: timestamp
                });
                
                // إعادة تعيين النموذج
                teacherForm.reset();
                
                // عرض رسالة النجاح
                showMessage('تم إرسال البيانات بنجاح!', 'success');
                
                // تحديث واجهة المستخدم
                updateTeachersTable();
                updateStats();
                
                // إعادة تعيين الزر
                submitBtn.disabled = false;
                submitBtn.innerHTML = '<span>إرسال البيانات</span>';
            }, 1000);
        });
        
        // تحديث البيانات
        refreshBtn.addEventListener('click', function() {
            // في بيئة حقيقية، سنجلب البيانات من Google Sheets
            // fetch(SCRIPT_URL + '?action=getTeachers')
            //     .then(response => response.json())
            //     .then(data => {
            //         teachersData = data;
            //         updateTeachersTable();
            //         updateStats();
            //         showMessage('تم تحديث البيانات بنجاح!', 'success');
            //     });
            
            // لمثالنا، سنستخدم محاكاة
            showMessage('تم تحديث البيانات بنجاح!', 'success');
            updateTeachersTable();
            updateStats();
        });
        
        // تصدير البيانات
        exportBtn.addEventListener('click', function() {
            // في بيئة حقيقية، سنصدر البيانات إلى Excel
            // هذا مثال مبسط للمحاكاة
            showMessage('جاري تحضير البيانات للتصدير...', 'success');
            
            setTimeout(() => {
                // محاكاة تصدير البيانات
                const csvContent = "data:text/csv;charset=utf-8," 
                    + "الاسم,الصف,التخصص,تاريخ الإرسال\n"
                    + teachersData.map(teacher => 
                        `"${teacher.name}","${teacher.class}","${teacher.specialization}","${teacher.timestamp}"`
                    ).join("\n");
                
                const encodedUri = encodeURI(csvContent);
                const link = document.createElement("a");
                link.setAttribute("href", encodedUri);
                link.setAttribute("download", "معلمي_الرياضيات.csv");
                document.body.appendChild(link);
                link.click();
                document.body.removeChild(link);
                
                showMessage('تم تصدير البيانات بنجاح!', 'success');
            }, 1500);
        });
        
        // عرض الرسائل
        function showMessage(text, type) {
            messageDiv.textContent = text;
            messageDiv.className = 'message ' + type;
            messageDiv.style.display = 'block';
            
            setTimeout(() => {
                messageDiv.style.display = 'none';
            }, 5000);
        }
        
        // تحديث جدول المعلمين
        function updateTeachersTable() {
            if (teachersData.length === 0) {
                teachersTableBody.innerHTML = '<tr><td colspan="4" class="empty-data">لا توجد بيانات متاحة</td></tr>';
                return;
            }
            
            teachersTableBody.innerHTML = teachersData.map(teacher => `
                <tr>
                    <td>${teacher.name}</td>
                    <td>${teacher.class}</td>
                    <td>${teacher.specialization}</td>
                    <td>${teacher.timestamp}</td>
                </tr>
            `).join('');
        }
        
        // تحديث الإحصائيات
        function updateStats() {
            totalTeachersEl.textContent = teachersData.length;
            
            const uniqueClasses = new Set(teachersData.map(teacher => teacher.class));
            uniqueClassesEl.textContent = uniqueClasses.size;
            
            const uniqueSpecializations = new Set(teachersData.map(teacher => teacher.specialization));
            uniqueSpecializationsEl.textContent = uniqueSpecializations.size;
        }
        
        // تهيئة الصفحة
        document.addEventListener('DOMContentLoaded', function() {
            updateTeachersTable();
            updateStats();
        });
    </script>
</body>
</html>
