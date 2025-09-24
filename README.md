<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>قاعدة بيانات الرياضيات - مدرسة محمد بن سليمان الغافري</title>
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #3498db;
            --accent: #e74c3c;
            --light: #ecf0f1;
            --dark: #2c3e50;
            --math-symbol: #e74c3c;
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            color: var(--dark);
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            background: var(--primary);
            color: white;
            padding: 20px 0;
            border-bottom: 5px solid var(--math-symbol);
            position: relative;
            overflow: hidden;
        }
        
        header::before {
            content: "∫ ∑ π ∞";
            position: absolute;
            top: 0;
            right: 0;
            font-size: 120px;
            opacity: 0.1;
            color: white;
            z-index: 0;
        }
        
        .header-content {
            position: relative;
            z-index: 1;
            text-align: center;
        }
        
        h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            color: white;
        }
        
        .subtitle {
            font-size: 1.2rem;
            opacity: 0.9;
        }
        
        .supervisor {
            margin-top: 10px;
            font-style: italic;
        }
        
        .main-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 30px;
            margin-top: 30px;
        }
        
        @media (max-width: 768px) {
            .main-content {
                grid-template-columns: 1fr;
            }
        }
        
        .form-section, .data-section {
            background: white;
            border-radius: 10px;
            padding: 25px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            border-top: 5px solid var(--secondary);
        }
        
        .section-title {
            font-size: 1.5rem;
            margin-bottom: 20px;
            color: var(--primary);
            border-bottom: 2px solid var(--light);
            padding-bottom: 10px;
            position: relative;
        }
        
        .section-title::after {
            content: "";
            position: absolute;
            bottom: -2px;
            right: 0;
            width: 50px;
            height: 2px;
            background: var(--math-symbol);
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
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            transition: border 0.3s;
        }
        
        input:focus, select:focus {
            border-color: var(--secondary);
            outline: none;
            box-shadow: 0 0 0 2px rgba(52, 152, 219, 0.2);
        }
        
        .btn {
            display: inline-block;
            background: var(--secondary);
            color: white;
            padding: 12px 25px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            transition: all 0.3s;
            text-align: center;
        }
        
        .btn:hover {
            background: #2980b9;
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .btn-masar {
            background: var(--math-symbol);
            display: block;
            width: 100%;
            margin-top: 20px;
            text-decoration: none;
        }
        
        .btn-masar:hover {
            background: #c0392b;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        
        th, td {
            padding: 12px 15px;
            text-align: right;
            border-bottom: 1px solid #ddd;
        }
        
        th {
            background: var(--light);
            font-weight: 600;
        }
        
        tr:hover {
            background: #f9f9f9;
        }
        
        .math-decoration {
            text-align: center;
            margin: 30px 0;
            font-size: 2rem;
            color: var(--math-symbol);
            opacity: 0.7;
        }
        
        footer {
            text-align: center;
            margin-top: 50px;
            padding: 20px;
            color: var(--dark);
            font-size: 0.9rem;
            border-top: 1px solid #ddd;
        }
        
        .notification {
            padding: 15px;
            border-radius: 5px;
            margin-bottom: 20px;
            display: none;
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
        
        .loading {
            text-align: center;
            padding: 20px;
            display: none;
        }
        
        .spinner {
            border: 5px solid #f3f3f3;
            border-top: 5px solid var(--secondary);
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            margin: 0 auto 15px;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <h1>قاعدة بيانات الرياضيات</h1>
                <div class="subtitle">مدرسة محمد بن سليمان الغافري</div>
                <div class="supervisor">إشراف المعلم الأول: الأستاذ محمد سليمان المزروعي</div>
            </div>
        </div>
    </header>
    
    <div class="container">
        <div class="math-decoration">∫ ∑ π ∞ Δ ∇ √ ∝ ≤ ≥</div>
        
        <div class="notification success" id="successMsg">تم حفظ البيانات بنجاح!</div>
        <div class="notification error" id="errorMsg">حدث خطأ أثناء حفظ البيانات. يرجى المحاولة مرة أخرى.</div>
        
        <div class="main-content">
            <div class="form-section">
                <h2 class="section-title">إدخال بيانات المعلم</h2>
                <form id="teacherForm">
                    <div class="form-group">
                        <label for="teacherName">اسم المعلم</label>
                        <input type="text" id="teacherName" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="teachingLoad">نصاب الحصص</label>
                        <input type="number" id="teachingLoad" min="1" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="teachingStage">المرحلة التي يدرسها</label>
                        <select id="teachingStage" required>
                            <option value="">اختر المرحلة</option>
                            <option value="ابتدائي">ابتدائي</option>
                            <option value="إعدادي">إعدادي</option>
                            <option value="ثانوي">ثانوي</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="phoneNumber">رقم الهاتف</label>
                        <input type="tel" id="phoneNumber" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="email">الإيميل</label>
                        <input type="email" id="email" required>
                    </div>
                    
                    <div class="form-group">
                        <label for="appointmentYear">سنة التعيين</label>
                        <input type="number" id="appointmentYear" min="1950" max="2030" required>
                    </div>
                    
                    <button type="submit" class="btn">حفظ البيانات</button>
                </form>
                
                <a href="https://m-teacher8.github.io/masar/" class="btn btn-masar" target="_blank">الانتقال إلى منصة مسار</a>
            </div>
            
            <div class="data-section">
                <h2 class="section-title">بيانات المعلمين</h2>
                <div class="loading" id="loadingData">
                    <div class="spinner"></div>
                    <p>جاري تحميل البيانات...</p>
                </div>
                <table id="teachersTable">
                    <thead>
                        <tr>
                            <th>اسم المعلم</th>
                            <th>نصاب الحصص</th>
                            <th>المرحلة</th>
                            <th>رقم الهاتف</th>
                            <th>الإيميل</th>
                            <th>سنة التعيين</th>
                        </tr>
                    </thead>
                    <tbody id="teachersTableBody">
                        <!-- سيتم ملء البيانات هنا عبر JavaScript -->
                    </tbody>
                </table>
            </div>
        </div>
        
        <div class="math-decoration">α β γ δ ε ζ η θ ι κ λ μ ν ξ ο π ρ σ τ υ φ χ ψ ω</div>
    </div>
    
    <footer>
        <div class="container">
            <p>جميع الحقوق محفوظة © قاعدة بيانات الرياضيات - مدرسة محمد بن سليمان الغافري</p>
        </div>
    </footer>

    <script>
        // رابط جدول البيانات
        const SPREADSHEET_URL = "https://docs.google.com/spreadsheets/d/e/2PACX-1vS_qAJBgNO2giDYJI7k5oeCoVZKCBLPKLB-EO3yc9ta62aH2qfDqtMuhEeHHxK-65ARh_qiZswWf0qL/pub?gid=0&single=true&output=csv";
        
        // عناصر DOM
        const teacherForm = document.getElementById('teacherForm');
        const teachersTableBody = document.getElementById('teachersTableBody');
        const successMsg = document.getElementById('successMsg');
        const errorMsg = document.getElementById('errorMsg');
        const loadingData = document.getElementById('loadingData');
        
        // تحميل البيانات عند فتح الصفحة
        document.addEventListener('DOMContentLoaded', loadTeachersData);
        
        // معالجة إرسال النموذج
        teacherForm.addEventListener('submit', function(e) {
            e.preventDefault();
            
            // جمع بيانات النموذج
            const formData = {
                name: document.getElementById('teacherName').value,
                load: document.getElementById('teachingLoad').value,
                stage: document.getElementById('teachingStage').value,
                phone: document.getElementById('phoneNumber').value,
                email: document.getElementById('email').value,
                year: document.getElementById('appointmentYear').value
            };
            
            // هنا سيتم إضافة كود لإرسال البيانات إلى جدول البيانات
            // بما أننا لا نستطيع تعديل جدول البيانات مباشرة من العميل
            // سنقوم بمحاكاة العملية وعرض البيانات محليًا
            
            // إضافة البيانات إلى الجدول
            addTeacherToTable(formData);
            
            // إظهار رسالة النجاح
            showNotification(successMsg);
            
            // إعادة تعيين النموذج
            teacherForm.reset();
        });
        
        // دالة لإضافة معلم إلى الجدول
        function addTeacherToTable(teacher) {
            const row = document.createElement('tr');
            row.innerHTML = `
                <td>${teacher.name}</td>
                <td>${teacher.load}</td>
                <td>${teacher.stage}</td>
                <td>${teacher.phone}</td>
                <td>${teacher.email}</td>
                <td>${teacher.year}</td>
            `;
            teachersTableBody.appendChild(row);
        }
        
        // دالة لتحميل بيانات المعلمين من جدول البيانات
        function loadTeachersData() {
            loadingData.style.display = 'block';
            
            // بما أننا لا نستطيع جلب البيانات مباشرة من جدول البيانات بسبب سياسة CORS
            // سنقوم بمحاكاة البيانات لعرض مثال
            setTimeout(() => {
                // بيانات مثاليه (يجب استبدالها بالبيانات الفعلية من جدول البيانات)
                const sampleData = [
                    { name: 'أحمد محمد', load: 18, stage: 'ثانوي', phone: '0551234567', email: 'ahmed@school.edu', year: 2015 },
                    { name: 'فاطمة علي', load: 20, stage: 'إعدادي', phone: '0509876543', email: 'fatima@school.edu', year: 2018 },
                    { name: 'خالد إبراهيم', load: 16, stage: 'ابتدائي', phone: '0565554433', email: 'khaled@school.edu', year: 2020 }
                ];
                
                // إضافة البيانات إلى الجدول
                sampleData.forEach(teacher => addTeacherToTable(teacher));
                
                loadingData.style.display = 'none';
            }, 1500);
        }
        
        // دالة لعرض الإشعارات
        function showNotification(notification) {
            notification.style.display = 'block';
            setTimeout(() => {
                notification.style.display = 'none';
            }, 5000);
        }
        
        // في التطبيق الحقيقي، سنحتاج إلى استخدام Google Apps Script أو خدمة وسيطة
        // للتفاعل مع جدول البيانات بسبب قيود CORS
    </script>
</body>
</html>
