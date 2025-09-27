<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>نموذج بيانات المعلمين</title>
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f5f5;
            color: #333;
            line-height: 1.6;
            padding: 20px;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
        }
        
        h1 {
            text-align: center;
            color: #2c3e50;
            margin-bottom: 30px;
            border-bottom: 2px solid #3498db;
            padding-bottom: 10px;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #2c3e50;
        }
        
        input, select {
            width: 100%;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
            transition: border 0.3s;
        }
        
        input:focus, select:focus {
            border-color: #3498db;
            outline: none;
            box-shadow: 0 0 5px rgba(52, 152, 219, 0.5);
        }
        
        button {
            background-color: #3498db;
            color: white;
            border: none;
            padding: 12px 25px;
            font-size: 16px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
            width: 100%;
            margin-top: 10px;
        }
        
        button:hover {
            background-color: #2980b9;
        }
        
        button:disabled {
            background-color: #95a5a6;
            cursor: not-allowed;
        }
        
        .success-message {
            background-color: #d4edda;
            color: #155724;
            padding: 15px;
            border-radius: 5px;
            margin-top: 20px;
            display: none;
        }
        
        .error-message {
            background-color: #f8d7da;
            color: #721c24;
            padding: 15px;
            border-radius: 5px;
            margin-top: 20px;
            display: none;
        }
        
        .instructions {
            background-color: #e8f4f8;
            border-right: 4px solid #3498db;
            padding: 15px;
            margin-bottom: 25px;
            border-radius: 5px;
        }
        
        .instructions h3 {
            margin-bottom: 10px;
            color: #2c3e50;
        }
        
        .instructions ol {
            padding-right: 20px;
        }
        
        .instructions li {
            margin-bottom: 8px;
        }
        
        @media (max-width: 600px) {
            .container {
                padding: 15px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>نموذج تسجيل بيانات المعلمين</h1>
        
        <div class="instructions">
            <h3>تعليمات الاستخدام:</h3>
            <ol>
                <li>أنشئ جدول بيانات جديد في Google Sheets</li>
                <li>أضف العناوين في الصف الأول: الاسم، الصف، العمر، التاريخ</li>
                <li>انشر الجدول كتطبيق ويب (من قائمة النشر)</li>
                <li>انسخ رابط النشر وأدخله في الحقل أدناه</li>
                <li>شارك رابط هذه الصفحة مع المعلمين</li>
            </ol>
        </div>
        
        <div class="form-group">
            <label for="sheetUrl">https://docs.google.com/spreadsheets/d/1NWeBeNDDlZn3g8tojXMnGYVSKIiFtQLGAdrn8ePMPPk/edit?usp=sharing (Google Sheets):</label>
            <input type="text" id="sheetUrl" placeholder="https://script.google.com/macros/s/.../exec">
            <button id="saveUrlBtn">حفظ الرابط</button>
        </div>
        
        <form id="teacherForm">
            <div class="form-group">
                <label for="name">الاسم الكامل:</label>
                <input type="text" id="name" name="name" required>
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
                    <option value="إدارة">إدارة</option>
                    <option value="أخرى">أخرى</option>
                </select>
            </div>
            
            <div class="form-group">
                <label for="age">العمر:</label>
                <input type="number" id="age" name="age" min="20" max="70" required>
            </div>
            
            <button type="submit" id="submitBtn">تسجيل البيانات</button>
        </form>
        
        <div id="successMessage" class="success-message">
            تم تسجيل بياناتك بنجاح! شكراً لك.
        </div>
        
        <div id="errorMessage" class="error-message">
            حدث خطأ أثناء تسجيل البيانات. يرجى المحاولة مرة أخرى.
        </div>
    </div>

    <script>
        // حفظ رابط الجدول في localStorage
        document.getElementById('saveUrlBtn').addEventListener('click', function() {
            const sheetUrl = document.getElementById('sheetUrl').value;
            if (sheetUrl) {
                localStorage.setItem('teacherSheetUrl', sheetUrl);
                alert('تم حفظ رابط الجدول بنجاح!');
            } else {
                alert('يرجى إدخال رابط صحيح');
            }
        });
        
        // تحميل الرابط المحفوظ عند فتح الصفحة
        document.addEventListener('DOMContentLoaded', function() {
            const savedUrl = localStorage.getItem('teacherSheetUrl');
            if (savedUrl) {
                document.getElementById('sheetUrl').value = savedUrl;
            }
        });
        
        // معالجة إرسال النموذج
        document.getElementById('teacherForm').addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const submitBtn = document.getElementById('submitBtn');
            const successMessage = document.getElementById('successMessage');
            const errorMessage = document.getElementById('errorMessage');
            
            // إخفاء الرسائل السابقة
            successMessage.style.display = 'none';
            errorMessage.style.display = 'none';
            
            // تعطيل الزر أثناء الإرسال
            submitBtn.disabled = true;
            submitBtn.textContent = 'جاري التسجيل...';
            
            const name = document.getElementById('name').value;
            const classValue = document.getElementById('class').value;
            const age = document.getElementById('age').value;
            const sheetUrl = localStorage.getItem('teacherSheetUrl');
            
            if (!sheetUrl) {
                errorMessage.textContent = 'يرجى إدخال وحفظ رابط جدول البيانات أولاً';
                errorMessage.style.display = 'block';
                submitBtn.disabled = false;
                submitBtn.textContent = 'تسجيل البيانات';
                return;
            }
            
            try {
                // إرسال البيانات إلى Google Sheets
                const response = await fetch(sheetUrl, {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/x-www-form-urlencoded',
                    },
                    body: `name=${encodeURIComponent(name)}&class=${encodeURIComponent(classValue)}&age=${encodeURIComponent(age)}&timestamp=${encodeURIComponent(new Date().toLocaleString('ar-SA'))}`
                });
                
                if (response.ok) {
                    // إظهار رسالة النجاح
                    successMessage.style.display = 'block';
                    
                    // إعادة تعيين النموذج
                    document.getElementById('teacherForm').reset();
                    
                    // إخفاء رسالة النجاح بعد 3 ثوان
                    setTimeout(function() {
                        successMessage.style.display = 'none';
                    }, 3000);
                } else {
                    throw new Error('فشل في إرسال البيانات');
                }
            } catch (error) {
                console.error('Error:', error);
                errorMessage.style.display = 'block';
            } finally {
                // إعادة تمكين الزر
                submitBtn.disabled = false;
                submitBtn.textContent = 'تسجيل البيانات';
            }
        });
    </script>
</body>
</html>
