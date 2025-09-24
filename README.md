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
            --success: #27ae60;
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
            min-height: 100vh;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            background: var(--primary);
            color: white;
            padding: 30px 0;
            border-bottom: 5px solid var(--math-symbol);
            position: relative;
            overflow: hidden;
            text-align: center;
        }
        
        header::before {
            content: "∫ ∑ π ∞ ∇ Δ";
            position: absolute;
            top: 50%;
            right: 0;
            transform: translateY(-50%);
            font-size: 100px;
            opacity: 0.1;
            color: white;
            z-index: 0;
            width: 100%;
            text-align: center;
        }
        
        .header-content {
            position: relative;
            z-index: 1;
        }
        
        h1 {
            font-size: 2.8rem;
            margin-bottom: 15px;
            color: white;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }
        
        .subtitle {
            font-size: 1.3rem;
            opacity: 0.9;
            margin-bottom: 10px;
        }
        
        .supervisor {
            margin-top: 15px;
            font-style: italic;
            font-size: 1.1rem;
            background: rgba(0,0,0,0.2);
            display: inline-block;
            padding: 8px 15px;
            border-radius: 5px;
        }
        
        .main-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 30px;
            margin-top: 40px;
        }
        
        @media (max-width: 968px) {
            .main-content {
                grid-template-columns: 1fr;
            }
            
            h1 {
                font-size: 2.2rem;
            }
        }
        
        .form-section, .data-section {
            background: white;
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            border-top: 5px solid var(--secondary);
            transition: transform 0.3s;
        }
        
        .form-section:hover, .data-section:hover {
            transform: translateY(-5px);
        }
        
        .section-title {
            font-size: 1.6rem;
            margin-bottom: 25px;
            color: var(--primary);
            border-bottom: 2px solid var(--light);
            padding-bottom: 12px;
            position: relative;
            display: flex;
            align-items: center;
        }
        
        .section-title::before {
            content: "∑";
            margin-left: 10px;
            color: var(--math-symbol);
            font-size: 1.8rem;
        }
        
        .section-title::after {
            content: "";
            position: absolute;
            bottom: -2px;
            right: 0;
            width: 60px;
            height: 3px;
            background: var(--math-symbol);
            border-radius: 3px;
        }
        
        .form-group {
            margin-bottom: 25px;
        }
        
        label {
            display: block;
            margin-bottom: 10px;
            font-weight: 600;
            color: var(--dark);
            font-size: 1.05rem;
        }
        
        input, select {
            width: 100%;
            padding: 14px 18px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 1rem;
            transition: all 0.3s;
            background: #fafafa;
        }
        
        input:focus, select:focus {
            border-color: var(--secondary);
            background: white;
            outline: none;
            box-shadow: 0 0 0 3px rgba(52, 152, 219, 0.2);
            transform: scale(1.02);
        }
        
        .btn {
            display: inline-block;
            background: linear-gradient(135deg, var(--secondary), #2980b9);
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1.1rem;
            font-weight: 600;
            transition: all 0.3s;
            text-align: center;
            width: 100%;
            box-shadow: 0 4px 15px rgba(52, 152, 219, 0.3);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 7px 20px rgba(52, 152, 219, 0.4);
        }
        
        .btn-masar {
            background: linear-gradient(135deg, var(--math-symbol), #c0392b);
            display: block;
            width: 100%;
            margin-top: 25px;
            text-decoration: none;
            box-shadow: 0 4px 15px rgba(231, 76, 60, 0.3);
        }
        
        .btn-masar:hover {
            box-shadow: 0 7px 20px rgba(231, 76, 60, 0.4);
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            border-radius: 10px;
            overflow: hidden;
        }
        
        th, td {
            padding: 15px 18px;
            text-align: right;
            border-bottom: 1px solid #e0e0e0;
        }
        
        th {
            background: linear-gradient(135deg, var(--primary), #34495e);
            color: white;
            font-weight: 600;
            font-size: 1.05rem;
        }
        
        tr:nth-child(even) {
            background: #f8f9fa;
        }
        
        tr:hover {
            background: #e3f2fd;
            transform: scale(1.01);
            transition: all 0.2s;
        }
        
        .math-decoration {
            text-align: center;
            margin: 40px 0;
            font-size: 2.5rem;
            color: var(--math-symbol);
            opacity: 0.6;
            letter-spacing: 10px;
        }
        
        footer {
            text-align: center;
            margin-top: 60px;
            padding: 25px;
            color: var(--dark);
            font-size: 1rem;
            border-top: 1px solid #ddd;
            background: rgba(255,255,255,0.7);
            border-radius: 10px;
        }
        
        .notification {
            padding: 18px;
            border-radius: 8px;
            margin-bottom: 25px;
            display: none;
            font-weight: 600;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }
        
        .success {
            background: #d4edda;
            color: #155724;
            border: 2px solid #c3e6cb;
        }
        
        .error {
            background: #f8d7da;
            color: #721c24;
            border: 2px solid #f5c6cb;
        }
        
        .loading {
            text-align: center;
            padding: 30px;
            display: none;
        }
        
        .spinner {
            border: 5px solid #f3f3f3;
            border-top: 5px solid var(--secondary);
            border-radius: 50%;
            width: 60px;
            height: 60px;
            animation: spin 1s linear infinite;
            margin: 0 auto 20px;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        .data-actions {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
        }
        
        .btn-small {
            padding: 10px 15px;
            font-size: 0.9rem;
            width: auto;
        }
        
        .export-btn {
            background: linear-gradient(135deg, var(--success), #219653);
        }
        
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 15px;
            margin-bottom: 25px;
        }
        
        .stat-card {
            background: white;
            padding: 15px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 3px 10px rgba(0,0,0,0.08);
            border-left: 4px solid var(--secondary);
        }
        
        .stat-number {
            font-size: 2rem;
            font-weight: bold;
            color: var(--primary);
        }
        
        .stat-label {
            font-size: 0.9rem;
            color: #666;
        }
        
        .empty-data {
            text-align: center;
            padding: 40px;
            color: #666;
            font-style: italic;
        }
        
        .empty-data::before {
            content: "∅";
            font-size: 3rem;
            display: block;
            margin-bottom: 15px;
            opacity: 0.5;
        }
        
        .api-status {
            padding: 10px;
            border-radius: 5px;
            margin-bottom: 15px;
            text-align: center;
            font-weight: bold;
        }
        
        .api-connected {
            background: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }
        
        .api-disconnected {
            background: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
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
        <div class="math-decoration">∫ ∑ π ∞ Δ ∇ √ ∝ ≤ ≥ ± × ÷</div>
        
        <div class="api-status" id="apiStatus">جاري الاتصال بقاعدة البيانات...</div>
        
        <div class="notification success" id="successMsg">تم حفظ البيانات بنجاح!</div>
        <div class="notification error" id="errorMsg">حدث خطأ أثناء حفظ البيانات. يرجى المحاولة مرة أخرى.</div>
        
        <div class="main-content">
            <div class="form-section">
                <h2 class="section-title">إدخال بيانات المعلم</h2>
                <form id="teacherForm">
                    <div class="form-group">
                        <label for="teacherName">اسم المعلم</label>
                        <input type="text" id="teacherName" required placeholder="أدخل الاسم الكامل">
                    </div>
                    
                    <div class="form-group">
                        <label for="teachingLoad">نصاب الحصص</label>
                        <input type="number" id="teachingLoad" min="1" max="30" required placeholder="عدد الحصص الأسبوعي">
                    </div>
                    
                    <div class="form-group">
                        <label for="teachingStage">المرحلة التي يدرسها</label>
                        <select id="teachingStage" required>
                            <option value="">اختر المرحلة</option>
                            <option value="الابتدائية">الابتدائية</option>
                            <option value="الإعدادية">الإعدادية</option>
                            <option value="الثانوية">الثانوية</option>
                        </select>
                    </div>
                    
                    <div class="form-group">
                        <label for="phoneNumber">رقم الهاتف</label>
                        <input type="tel" id="phoneNumber" required placeholder="05XXXXXXXX">
                    </div>
                    
                    <div class="form-group">
                        <label for="email">الإيميل</label>
                        <input type="email" id="email" required placeholder="example@school.edu">
                    </div>
                    
                    <div class="form-group">
                        <label for="appointmentYear">سنة التعيين</label>
                        <input type="number" id="appointmentYear" min="1950" max="2030" required placeholder="سنة التعيين">
                    </div>
                    
                    <button type="submit" class="btn" id="submitBtn">حفظ البيانات</button>
                </form>
                
                <a href="https://m-teacher8.github.io/masar/" class="btn btn-masar" target="_blank">الانتقال إلى منصة مسار</a>
            </div>
            
            <div class="data-section">
                <h2 class="section-title">بيانات المعلمين</h2>
                
                <div class="stats" id="statsContainer">
                    <div class="stat-card">
                        <div class="stat-number" id="totalTeachers">0</div>
                        <div class="stat-label">إجمالي المعلمين</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number" id="primaryTeachers">0</div>
                        <div class="stat-label">المرحلة الابتدائية</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number" id="intermediateTeachers">0</div>
                        <div class="stat-label">المرحلة الإعدادية</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-number" id="secondaryTeachers">0</div>
                        <div class="stat-label">المرحلة الثانوية</div>
                    </div>
                </div>
                
                <div class="data-actions">
                    <button class="btn btn-small" onclick="refreshData()">تحديث البيانات</button>
                    <button class="btn btn-small export-btn" onclick="exportData()">تصدير البيانات</button>
                </div>
                
                <div class="loading" id="loadingData">
                    <div class="spinner"></div>
                    <p>جاري تحميل البيانات...</p>
                </div>
                
                <div id="tableContainer">
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
        </div>
        
        <div class="math-decoration">α β γ δ ε ζ η θ ι κ λ μ ν ξ ο π ρ σ τ υ φ χ ψ ω</div>
    </div>
    
    <footer>
        <div class="container">
            <p>جميع الحقوق محفوظة © قاعدة بيانات الرياضيات - مدرسة محمد بن سليمان الغافري</p>
            <p>تم التطوير بتصميم يعكس روح مادة الرياضيات</p>
        </div>
    </footer>

    <script>
        // استبدل هذا الرابط برابط التطبيق النصي الذي نشرته
        const API_URL = 'https:/[/script.google.com/macros/s/YOUR_SCRIPT_ID/exec](https://docs.google.com/spreadsheets/d/1kTIrXx9-d2rxjDaM66--h2DTNgBKDAPgJMwDjz5mkDI/edit?usp=sharing)';
        
        // عناصر DOM
        const teacherForm = document.getElementById('teacherForm');
        const teachersTableBody = document.getElementById('teachersTableBody');
        const successMsg = document.getElementById('successMsg');
        const errorMsg = document.getElementById('errorMsg');
        const loadingData = document.getElementById('loadingData');
        const tableContainer = document.getElementById('tableContainer');
        const apiStatus = document.getElementById('apiStatus');
        const submitBtn = document.getElementById('submitBtn');
        
        // عناصر الإحصائيات
        const totalTeachersEl = document.getElementById('totalTeachers');
        const primaryTeachersEl = document.getElementById('primaryTeachers');
        const intermediateTeachersEl = document.getElementById('intermediateTeachers');
        const secondaryTeachersEl = document.getElementById('secondaryTeachers');
        
        // حالة التطبيق
        let isOnline = false;
        
        // تحميل البيانات عند فتح الصفحة
        document.addEventListener('DOMContentLoaded', function() {
            checkAPIStatus();
            loadTeachersData();
        });
        
        // التحقق من حالة API
        async function checkAPIStatus() {
            try {
                const response = await fetch(`${API_URL}?action=getTeachers`);
                if (response.ok) {
                    apiStatus.textContent = '✓ متصل بقاعدة البيانات بنجاح';
                    apiStatus.className = 'api-status api-connected';
                    isOnline = true;
                } else {
                    throw new Error('API not responding');
                }
            } catch (error) {
                apiStatus.textContent = '✗ غير متصل بقاعدة البيانات - يتم استخدام التخزين المحلي';
                apiStatus.className = 'api-status api-disconnected';
                isOnline = false;
            }
        }
        
        // معالجة إرسال النموذج
        teacherForm.addEventListener('submit', async function(e) {
            e.preventDefault();
            
            // جمع بيانات النموذج
            const formData = {
                name: document.getElementById('teacherName').value.trim(),
                load: parseInt(document.getElementById('teachingLoad').value),
                stage: document.getElementById('teachingStage').value,
                phone: document.getElementById('phoneNumber').value.trim(),
                email: document.getElementById('email').value.trim(),
                year: parseInt(document.getElementById('appointmentYear').value)
            };
            
            // التحقق من صحة البيانات
            if (!validateFormData(formData)) {
                showNotification(errorMsg, "يرجى ملء جميع الحقول بشكل صحيح");
                return;
            }
            
            // تعطيل الزر أثناء المعالجة
            submitBtn.disabled = true;
            submitBtn.textContent = 'جاري الحفظ...';
            
            try {
                if (isOnline) {
                    // محاولة الحفظ عبر API
                    await saveTeacherToAPI(formData);
                } else {
                    // الحفظ محلياً
                    saveTeacherToLocal(formData);
                }
                
                showNotification(successMsg, "تم حفظ بيانات المعلم بنجاح!");
                teacherForm.reset();
                loadTeachersData();
            } catch (error) {
                showNotification(errorMsg, "حدث خطأ أثناء حفظ البيانات: " + error.message);
            } finally {
                // إعادة تمكين الزر
                submitBtn.disabled = false;
                submitBtn.textContent = 'حفظ البيانات';
            }
        });
        
        // دالة للتحقق من صحة البيانات
        function validateFormData(data) {
            if (!data.name || data.name.length < 2) return false;
            if (!data.load || data.load < 1 || data.load > 30) return false;
            if (!data.stage) return false;
            if (!data.phone || data.phone.length < 10) return false;
            if (!data.email || !isValidEmail(data.email)) return false;
            if (!data.year || data.year < 1950 || data.year > new Date().getFullYear()) return false;
            
            return true;
        }
        
        // دالة للتحقق من صحة البريد الإلكتروني
        function isValidEmail(email) {
            const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            return emailRegex.test(email);
        }
        
        // دالة للحفظ عبر API
        async function saveTeacherToAPI(teacherData) {
            const params = new URLSearchParams();
            params.append('action', 'addTeacher');
            Object.keys(teacherData).forEach(key => {
                params.append(key, teacherData[key]);
            });
            
            const response = await fetch(API_URL, {
                method: 'POST',
                body: params
            });
            
            if (!response.ok) {
                throw new Error('Failed to save data');
            }
            
            const result = await response.json();
            if (result.error) {
                throw new Error(result.error);
            }
        }
        
        // دالة للحفظ محلياً
        function saveTeacherToLocal(teacherData) {
            const teachers = getTeachersFromLocalStorage();
            teacherData.id = Date.now();
            teacherData.timestamp = new Date().toLocaleString('ar-EG');
            teachers.push(teacherData);
            localStorage.setItem('math_teachers_backup', JSON.stringify(teachers));
        }
        
        // دالة لتحميل بيانات المعلمين
        async function loadTeachersData() {
            loadingData.style.display = 'block';
            tableContainer.style.display = 'none';
            
            try {
                let teachers = [];
                
                if (isOnline) {
                    // جلب البيانات من API
                    const response = await fetch(`${API_URL}?action=getTeachers`);
                    if (response.ok) {
                        teachers = await response.json();
                    } else {
                        throw new Error('Failed to fetch data');
                    }
                } else {
                    // جلب البيانات من التخزين المحلي
                    teachers = getTeachersFromLocalStorage();
                }
                
                displayTeachers(teachers);
                updateStatistics(teachers);
                
            } catch (error) {
                console.error('Error loading data:', error);
                // استخدام البيانات المحلية كنسخة احتياطية
                const localTeachers = getTeachersFromLocalStorage();
                displayTeachers(localTeachers);
                updateStatistics(localTeachers);
            } finally {
                loadingData.style.display = 'none';
                tableContainer.style.display = 'block';
            }
        }
        
        // دالة لجلب البيانات من التخزين المحلي
        function getTeachersFromLocalStorage() {
            const teachersJSON = localStorage.getItem('math_teachers_backup');
            return teachersJSON ? JSON.parse(teachersJSON) : [];
        }
        
        // دالة لعرض بيانات المعلمين في الجدول
        function displayTeachers(teachers) {
            if (teachers.length === 0) {
                teachersTableBody.innerHTML = `
                    <tr>
                        <td colspan="6">
                            <div class="empty-data">لا توجد بيانات متاحة حالياً</div>
                        </td>
                    </tr>
                `;
                return;
            }
            
            let tableHTML = '';
            teachers.forEach(teacher => {
                tableHTML += `
                    <tr>
                        <td>${teacher.name || teacher['اسم المعلم'] || 'غير محدد'}</td>
                        <td>${teacher.load || teacher['نصاب الحصص'] || 'غير محدد'}</td>
                        <td>${teacher.stage || teacher['المرحلة'] || 'غير محدد'}</td>
                        <td>${teacher.phone || teacher['رقم الهاتف'] || 'غير محدد'}</td>
                        <td>${teacher.email || teacher['الإيميل'] || 'غير محدد'}</td>
                        <td>${teacher.year || teacher['سنة التعيين'] || 'غير محدد'}</td>
                    </tr>
                `;
            });
            
            teachersTableBody.innerHTML = tableHTML;
        }
        
        // دالة لتحديث الإحصائيات
        function updateStatistics(teachers) {
            const total = teachers.length;
            const primary = teachers.filter(t => 
                (t.stage === 'الابتدائية' || t['المرحلة'] === 'الابتدائية')).length;
            const intermediate = teachers.filter(t => 
                (t.stage === 'الإعدادية' || t['المرحلة'] === 'الإعدادية')).length;
            const secondary = teachers.filter(t => 
                (t.stage === 'الثانوية' || t['المرحلة'] === 'الثانوية')).length;
            
            totalTeachersEl.textContent = total;
            primaryTeachersEl.textContent = primary;
            intermediateTeachersEl.textContent = intermediate;
            secondaryTeachersEl.textContent = secondary;
        }
        
        // دالة لتحديث البيانات
        function refreshData() {
            loadTeachersData();
            checkAPIStatus();
            showNotification(successMsg, "تم تحديث البيانات بنجاح!");
        }
        
        // دالة لتصدير البيانات
        function exportData() {
            const teachers = getTeachersFromLocalStorage();
            if (teachers.length === 0) {
                showNotification(errorMsg, "لا توجد بيانات للتصدير");
                return;
            }
            
            let csvContent = "data:text/csv;charset=utf-8,\ufeff";
            csvContent += "اسم المعلم,نصاب الحصص,المرحلة,رقم الهاتف,الإيميل,سنة التعيين\n";
            
            teachers.forEach(teacher => {
                const name = teacher.name || teacher['اسم المعلم'] || '';
                const load = teacher.load || teacher['نصاب الحصص'] || '';
                const stage = teacher.stage || teacher['المرحلة'] || '';
                const phone = teacher.phone || teacher['رقم الهاتف'] || '';
                const email = teacher.email || teacher['الإيميل'] || '';
                const year = teacher.year || teacher['سنة التعيين'] || '';
                
                csvContent += `"${name}",${load},"${stage}","${phone}","${email}",${year}\n`;
            });
            
            const encodedUri = encodeURI(csvContent);
            const link = document.createElement("a");
            link.setAttribute("href", encodedUri);
            link.setAttribute("download", "بيانات_معلمي_الرياضيات.csv");
            document.body.appendChild(link);
            link.click();
            document.body.removeChild(link);
        }
        
        // دالة لعرض الإشعارات
        function showNotification(notification, message = '') {
            if (message) {
                notification.textContent = message;
            }
            notification.style.display = 'block';
            setTimeout(() => {
                notification.style.display = 'none';
            }, 5000);
        }
    </script>
</body>
</html>
