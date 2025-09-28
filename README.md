<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منصة بيانات معلمي الرياضيات</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #6a11cb 0%, #2575fc 100%);
            color: #333;
            line-height: 1.6;
            padding: 20px;
            min-height: 100vh;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            background-color: rgba(255, 255, 255, 0.95);
            border-radius: 15px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            padding: 30px;
            margin-top: 30px;
            margin-bottom: 30px;
        }
        
        header {
            text-align: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 2px solid #f0f0f0;
        }
        
        h1 {
            color: #2575fc;
            margin-bottom: 10px;
            font-size: 2.2rem;
        }
        
        .description {
            color: #666;
            font-size: 1.1rem;
        }
        
        .form-group {
            margin-bottom: 25px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #444;
        }
        
        input, select {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e1e1e1;
            border-radius: 8px;
            font-size: 16px;
            transition: all 0.3s;
        }
        
        input:focus, select:focus {
            border-color: #2575fc;
            outline: none;
            box-shadow: 0 0 0 3px rgba(37, 117, 252, 0.2);
        }
        
        .btn {
            display: block;
            width: 100%;
            padding: 15px;
            background: linear-gradient(to right, #2575fc, #6a11cb);
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            margin-top: 20px;
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 7px 15px rgba(0, 0, 0, 0.2);
        }
        
        .btn:active {
            transform: translateY(-1px);
        }
        
        .message {
            padding: 15px;
            border-radius: 8px;
            margin-top: 20px;
            text-align: center;
            display: none;
        }
        
        .success {
            background-color: #d4edda;
            color: #155724;
            border: 1px solid #c3e6cb;
        }
        
        .error {
            background-color: #f8d7da;
            color: #721c24;
            border: 1px solid #f5c6cb;
        }
        
        .instructions {
            background-color: #e7f3ff;
            border-radius: 8px;
            padding: 20px;
            margin-top: 30px;
            border-right: 5px solid #2575fc;
        }
        
        .instructions h3 {
            color: #2575fc;
            margin-bottom: 10px;
        }
        
        .instructions ol {
            padding-right: 20px;
        }
        
        .instructions li {
            margin-bottom: 10px;
        }
        
        footer {
            text-align: center;
            margin-top: 30px;
            color: #666;
            font-size: 0.9rem;
        }
        
        @media (max-width: 768px) {
            .container {
                padding: 20px;
            }
            
            h1 {
                font-size: 1.8rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>منصة بيانات معلمي الرياضيات</h1>
            <p class="description">أدخل بيانات معلمي الرياضيات لإرسالها إلى سجل البيانات</p>
        </header>
        
        <form id="teacherForm">
            <div class="form-group">
                <label for="name">اسم المعلم:</label>
                <input type="text" id="name" name="name" required placeholder="أدخل الاسم الكامل للمعلم">
            </div>
            
            <div class="form-group">
                <label for="class">الصف الدراسي:</label>
                <select id="class" name="class" required>
                    <option value="">اختر الصف الدراسي</option>
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
                <label for="age">العمر:</label>
                <input type="number" id="age" name="age" required min="22" max="65" placeholder="أدخل عمر المعلم">
            </div>
            
            <button type="submit" class="btn">إرسال البيانات</button>
        </form>
        
        <div id="message" class="message"></div>
        
        <div class="instructions">
            <h3>كيفية ربط النموذج مع Google Sheets:</h3>
            <ol>
                <li>أنشئ جدول بيانات جديد في Google Sheets</li>
                <li>أضف العناوين: الاسم، الصف، العمر في الصف الأول</li>
                <li>من القائمة: إضافات → الحصول على إضافات → ابحث عن "Google Apps Script"</li>
                <li>أنشئ برنامج نصي جديد وانسخ الكود الموجود في ملف JavaScript</li>
                <li>انشر البرنامج النصي كتطبيق ويب واحصل على رابط الويب</li>
                <li>استبدل رابط الويب في دالة sendDataToSheet في الكود</li>
            </ol>
        </div>
        
        <footer>
            <p>© 2023 منصة بيانات معلمي الرياضيات. جميع الحقوق محفوظة.</p>
        </footer>
    </div>

    <script>
        document.getElementById('teacherForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // جمع البيانات من النموذج
            const formData = {
                name: document.getElementById('name').value,
                class: document.getElementById('class').value,
                age: document.getElementById('age').value
            };
            
            // إرسال البيانات (هنا يجب استبدال الرابط برابط Google Apps Script الخاص بك)
            sendDataToSheet(formData);
        });
        
        function sendDataToSheet(data) {
            const messageDiv = document.getElementById('message');
            
            // هذا الرابط يجب استبداله برابط Google Apps Script الخاص بك
            const scriptURL = 'https://script.google.com/macros/s/AKfycbxvc5RToLyMFmYSwzQLlNmH6VwuyjAvZMN_26tSVgiZFs6UFcAvu4OdnSxwm6a5hyId9A/exec';
            
            // محاكاة إرسال البيانات (في التطبيق الفعلي، استخدم fetch أو XMLHttpRequest)
            setTimeout(() => {
                // في التطبيق الحقيقي، استخدم:
                // fetch(scriptURL, { method: 'POST', body: JSON.stringify(data) })
                // .then(response => response.json())
                // .then(data => { ... })
                
                // عرض رسالة نجاح (محاكاة)
                messageDiv.textContent = 'تم إرسال البيانات بنجاح!';
                messageDiv.className = 'message success';
                messageDiv.style.display = 'block';
                
                // إعادة تعيين النموذج
                document.getElementById('teacherForm').reset();
                
                // إخفاء الرسالة بعد 5 ثوانٍ
                setTimeout(() => {
                    messageDiv.style.display = 'none';
                }, 5000);
            }, 1000);
        }
    </script>
</body>
</html>
