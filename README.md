<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منصة بيانات معلمي الرياضيات</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        .gradient-bg {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }
        .form-container {
            backdrop-filter: blur(10px);
            background: rgba(255, 255, 255, 0.95);
        }
        .input-focus:focus {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }
        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(102, 126, 234, 0.4);
        }
        .success-animation {
            animation: successPulse 0.6s ease-in-out;
        }
        @keyframes successPulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }
    </style>
</head>
<body class="gradient-bg min-h-screen">
    <div class="container mx-auto px-4 py-8">
        <!-- Header -->
        <div class="text-center mb-8">
            <div class="inline-flex items-center justify-center w-20 h-20 bg-white rounded-full shadow-lg mb-4">
                <span class="text-4xl">📊</span>
            </div>
            <h1 class="text-4xl font-bold text-white mb-2">منصة بيانات معلمي الرياضيات</h1>
            <p class="text-white/80 text-lg">نظام تسجيل وإدارة بيانات المعلمين</p>
        </div>

        <div class="max-w-4xl mx-auto">
            <!-- Form Section -->
            <div class="form-container rounded-2xl shadow-2xl p-8 mb-8">
                <div class="flex items-center mb-6">
                    <span class="text-3xl ml-3">👨‍🏫</span>
                    <h2 class="text-2xl font-bold text-gray-800">إضافة معلم جديد</h2>
                </div>

                <form id="teacherForm" class="space-y-6">
                    <div class="grid md:grid-cols-2 gap-6">
                        <!-- Name Field -->
                        <div>
                            <label for="teacherName" class="block text-sm font-semibold text-gray-700 mb-2">
                                الاسم الكامل *
                            </label>
                            <input 
                                type="text" 
                                id="teacherName" 
                                name="teacherName"
                                required
                                class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:border-blue-500 focus:outline-none transition-all duration-300 input-focus"
                                placeholder="أدخل الاسم الكامل للمعلم"
                            >
                        </div>

                        <!-- Grade Field -->
                        <div>
                            <label for="grade" class="block text-sm font-semibold text-gray-700 mb-2">
                                الصف المدرس *
                            </label>
                            <select 
                                id="grade" 
                                name="grade"
                                required
                                class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:border-blue-500 focus:outline-none transition-all duration-300 input-focus"
                            >
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

                        <!-- Age Field -->
                        <div>
                            <label for="age" class="block text-sm font-semibold text-gray-700 mb-2">
                                العمر *
                            </label>
                            <input 
                                type="number" 
                                id="age" 
                                name="age"
                                min="22" 
                                max="65"
                                required
                                class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:border-blue-500 focus:outline-none transition-all duration-300 input-focus"
                                placeholder="أدخل العمر"
                            >
                        </div>

                        <!-- Experience Field -->
                        <div>
                            <label for="experience" class="block text-sm font-semibold text-gray-700 mb-2">
                                سنوات الخبرة
                            </label>
                            <input 
                                type="number" 
                                id="experience" 
                                name="experience"
                                min="0" 
                                max="40"
                                class="w-full px-4 py-3 border-2 border-gray-200 rounded-xl focus:border-blue-500 focus:outline-none transition-all duration-300 input-focus"
                                placeholder="أدخل سنوات الخبرة"
                            >
                        </div>
                    </div>

                    <!-- Submit Button -->
                    <div class="text-center pt-4">
                        <button 
                            type="submit" 
                            class="submit-btn bg-gradient-to-r from-blue-600 to-purple-600 text-white px-8 py-4 rounded-xl font-semibold text-lg transition-all duration-300 hover:from-blue-700 hover:to-purple-700 shadow-lg"
                        >
                            <span class="flex items-center justify-center">
                                <span class="ml-2">📤</span>
                                إرسال البيانات
                            </span>
                        </button>
                    </div>
                </form>

                <!-- Success Message -->
                <div id="successMessage" class="hidden mt-6 p-4 bg-green-100 border border-green-400 text-green-700 rounded-xl text-center">
                    <span class="text-2xl">✅</span>
                    <p class="font-semibold mt-2">تم إرسال البيانات بنجاح!</p>
                </div>
            </div>

            <!-- Teachers List -->
            <div class="form-container rounded-2xl shadow-2xl p-8">
                <div class="flex items-center justify-between mb-6">
                    <div class="flex items-center">
                        <span class="text-3xl ml-3">📋</span>
                        <h2 class="text-2xl font-bold text-gray-800">قائمة المعلمين المسجلين</h2>
                    </div>
                    <div class="bg-blue-100 text-blue-800 px-4 py-2 rounded-lg font-semibold">
                        العدد: <span id="teacherCount">0</span>
                    </div>
                </div>

                <div id="teachersList" class="space-y-4">
                    <div class="text-center text-gray-500 py-8">
                        <span class="text-6xl">👥</span>
                        <p class="mt-4 text-lg">لا توجد بيانات معلمين مسجلة بعد</p>
                        <p class="text-sm text-gray-400">قم بإضافة معلم جديد باستخدام النموذج أعلاه</p>
                    </div>
                </div>
            </div>

            <!-- Google Apps Script Integration Guide -->
            <div class="form-container rounded-2xl shadow-2xl p-8 mt-8">
                <div class="flex items-center mb-6">
                    <span class="text-3xl ml-3">⚙️</span>
                    <h2 class="text-2xl font-bold text-gray-800">دليل إعداد Google Apps Script</h2>
                </div>
                
                <!-- Step 1: Create Google Sheet -->
                <div class="mb-8">
                    <div class="bg-green-50 border border-green-200 rounded-xl p-6">
                        <h3 class="font-bold text-green-800 mb-4 flex items-center">
                            <span class="ml-2">📊</span>
                            الخطوة 1: إنشاء Google Sheets
                        </h3>
                        <ol class="list-decimal list-inside space-y-2 text-green-700">
                            <li>اذهب إلى <a href="https://sheets.google.com" target="_blank" rel="noopener noreferrer" class="underline font-semibold">Google Sheets</a></li>
                            <li>أنشئ جدول بيانات جديد</li>
                            <li>أضف العناوين في الصف الأول: الاسم | الصف | العمر | سنوات الخبرة | التاريخ</li>
                            <li>احفظ الجدول باسم "بيانات معلمي الرياضيات"</li>
                        </ol>
                    </div>
                </div>

                <!-- Step 2: Create Apps Script -->
                <div class="mb-8">
                    <div class="bg-blue-50 border border-blue-200 rounded-xl p-6">
                        <h3 class="font-bold text-blue-800 mb-4 flex items-center">
                            <span class="ml-2">🔧</span>
                            الخطوة 2: إنشاء Google Apps Script
                        </h3>
                        <ol class="list-decimal list-inside space-y-2 text-blue-700 mb-4">
                            <li>من جدول البيانات، اذهب إلى Extensions > Apps Script</li>
                            <li>احذف الكود الموجود والصق الكود التالي:</li>
                        </ol>
                        
                        <div class="bg-gray-900 text-green-400 p-4 rounded-lg text-sm font-mono overflow-x-auto">
                            <pre>function doPost(e) {
  try {
    // الحصول على البيانات المرسلة
    const data = JSON.parse(e.postData.contents);
    
    // فتح جدول البيانات (ضع ID الجدول هنا)
    const sheet = SpreadsheetApp.openById('ضع_ID_الجدول_هنا').getActiveSheet();
    
    // إضافة البيانات إلى صف جديد
    sheet.appendRow([
      data.name,
      data.grade, 
      data.age,
      data.experience,
      new Date()
    ]);
    
    return ContentService
      .createTextOutput(JSON.stringify({success: true}))
      .setMimeType(ContentService.MimeType.JSON);
      
  } catch (error) {
    return ContentService
      .createTextOutput(JSON.stringify({
        success: false, 
        message: error.toString()
      }))
      .setMimeType(ContentService.MimeType.JSON);
  }
}</pre>
                        </div>
                    </div>
                </div>

                <!-- Step 3: Deploy Script -->
                <div class="mb-8">
                    <div class="bg-purple-50 border border-purple-200 rounded-xl p-6">
                        <h3 class="font-bold text-purple-800 mb-4 flex items-center">
                            <span class="ml-2">🚀</span>
                            الخطوة 3: نشر السكريبت
                        </h3>
                        <ol class="list-decimal list-inside space-y-2 text-purple-700">
                            <li>اضغط على "Deploy" > "New deployment"</li>
                            <li>اختر Type: "Web app"</li>
                            <li>Execute as: "Me"</li>
                            <li>Who has access: "Anyone"</li>
                            <li>اضغط "Deploy" وانسخ الرابط</li>
                            <li>ضع الرابط في المتغير GOOGLE_SCRIPT_URL في الكود أعلاه</li>
                        </ol>
                    </div>
                </div>

                <!-- Step 4: Get Sheet ID -->
                <div class="mb-6">
                    <div class="bg-orange-50 border border-orange-200 rounded-xl p-6">
                        <h3 class="font-bold text-orange-800 mb-4 flex items-center">
                            <span class="ml-2">🆔</span>
                            الخطوة 4: الحصول على ID الجدول
                        </h3>
                        <p class="text-orange-700 mb-2">من رابط جدول البيانات، انسخ الجزء بين /d/ و /edit:</p>
                        <div class="bg-gray-100 p-3 rounded font-mono text-sm">
                            https://docs.google.com/spreadsheets/d/<span class="bg-yellow-200 px-1">هذا_هو_الـID</span>/edit
                        </div>
                        <p class="text-orange-700 mt-2 text-sm">ضع هذا الـ ID في مكان "ضع_ID_الجدول_هنا" في الكود</p>
                    </div>
                </div>

                <!-- Current Status -->
                <div class="bg-gray-50 border border-gray-200 rounded-xl p-6">
                    <h3 class="font-bold text-gray-800 mb-3 flex items-center">
                        <span class="ml-2">📊</span>
                        الحالة الحالية
                    </h3>
                    <div id="connectionStatus" class="flex items-center">
                        <span class="w-3 h-3 bg-yellow-500 rounded-full ml-2"></span>
                        <span class="text-gray-700">غير متصل بـ Google Sheets (يعمل محلياً فقط)</span>
                    </div>
                    <p class="text-gray-600 text-sm mt-2">
                        بعد إعداد Google Apps Script، ستتمكن من إرسال البيانات مباشرة إلى Google Sheets
                    </p>
                </div>
            </div>
        </div>
    </div>

    <script>
        let teachers = [];
        let teacherIdCounter = 1;

        const form = document.getElementById('teacherForm');
        const successMessage = document.getElementById('successMessage');
        const teachersList = document.getElementById('teachersList');
        const teacherCount = document.getElementById('teacherCount');

        // رابط Google Apps Script (ضع الرابط الخاص بك هنا)
        const GOOGLE_SCRIPT_URL = 'ضع_رابط_Google_Apps_Script_هنا';

        form.addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const submitButton = form.querySelector('button[type="submit"]');
            const originalText = submitButton.innerHTML;
            
            // تغيير حالة الزر أثناء الإرسال
            submitButton.disabled = true;
            submitButton.innerHTML = '<span class="flex items-center justify-center"><span class="ml-2">⏳</span>جاري الإرسال...</span>';
            
            const formData = new FormData(form);
            const teacher = {
                id: teacherIdCounter++,
                name: formData.get('teacherName'),
                grade: formData.get('grade'),
                age: formData.get('age'),
                experience: formData.get('experience') || 'غير محدد',
                timestamp: new Date().toLocaleString('ar-SA')
            };

            try {
                // إرسال البيانات إلى Google Apps Script
                if (GOOGLE_SCRIPT_URL && GOOGLE_SCRIPT_URL !== 'https://script.google.com/macros/s/AKfycbz9G-G-gYOaZoY5sE1acjAh9MvlS_WUU7dM_Uh9tnSKjRIR6VuitF4Uc4s3JyyzSejwrQ/exec') {
                    const response = await fetch(GOOGLE_SCRIPT_URL, {
                        method: 'POST',
                        headers: {
                            'Content-Type': 'application/json',
                        },
                        body: JSON.stringify({
                            name: teacher.name,
                            grade: teacher.grade,
                            age: teacher.age,
                            experience: teacher.experience
                        })
                    });
                    
                    const result = await response.json();
                    
                    if (!result.success) {
                        throw new Error(result.message || 'فشل في إرسال البيانات');
                    }
                    
                    showSuccessMessage('تم إرسال البيانات إلى Google Sheets بنجاح! ✅');
                } else {
                    showSuccessMessage('تم حفظ البيانات محلياً (قم بإعداد رابط Google Apps Script)');
                }
                
                // إضافة البيانات محلياً أيضاً
                teachers.push(teacher);
                updateTeachersList();
                form.reset();
                
            } catch (error) {
                console.error('خطأ في إرسال البيانات:', error);
                showErrorMessage('حدث خطأ في إرسال البيانات: ' + error.message);
                
                // حفظ البيانات محلياً في حالة الخطأ
                teachers.push(teacher);
                updateTeachersList();
                form.reset();
            } finally {
                // إعادة تعيين حالة الزر
                submitButton.disabled = false;
                submitButton.innerHTML = originalText;
            }
        });

        function updateTeachersList() {
            teacherCount.textContent = teachers.length;
            
            if (teachers.length === 0) {
                teachersList.innerHTML = `
                    <div class="text-center text-gray-500 py-8">
                        <span class="text-6xl">👥</span>
                        <p class="mt-4 text-lg">لا توجد بيانات معلمين مسجلة بعد</p>
                        <p class="text-sm text-gray-400">قم بإضافة معلم جديد باستخدام النموذج أعلاه</p>
                    </div>
                `;
                return;
            }

            teachersList.innerHTML = teachers.map(teacher => `
                <div class="bg-white border border-gray-200 rounded-xl p-6 shadow-sm hover:shadow-md transition-shadow duration-300">
                    <div class="flex items-start justify-between">
                        <div class="flex-1">
                            <div class="flex items-center mb-3">
                                <span class="text-2xl ml-3">👨‍🏫</span>
                                <h3 class="text-xl font-bold text-gray-800">${teacher.name}</h3>
                            </div>
                            
                            <div class="grid md:grid-cols-3 gap-4 text-sm">
                                <div class="flex items-center">
                                    <span class="text-blue-600 ml-2">📚</span>
                                    <span class="text-gray-600">الصف:</span>
                                    <span class="font-semibold mr-2">${teacher.grade}</span>
                                </div>
                                
                                <div class="flex items-center">
                                    <span class="text-green-600 ml-2">🎂</span>
                                    <span class="text-gray-600">العمر:</span>
                                    <span class="font-semibold mr-2">${teacher.age} سنة</span>
                                </div>
                                
                                <div class="flex items-center">
                                    <span class="text-purple-600 ml-2">⭐</span>
                                    <span class="text-gray-600">الخبرة:</span>
                                    <span class="font-semibold mr-2">${teacher.experience}</span>
                                </div>
                            </div>
                            
                            <div class="mt-3 text-xs text-gray-500">
                                تاريخ التسجيل: ${teacher.timestamp}
                            </div>
                        </div>
                        
                        <button onclick="removeTeacher(${teacher.id})" class="text-red-500 hover:text-red-700 transition-colors duration-200 p-2">
                            <span class="text-xl">🗑️</span>
                        </button>
                    </div>
                </div>
            `).join('');
        }

        function removeTeacher(id) {
            teachers = teachers.filter(teacher => teacher.id !== id);
            updateTeachersList();
        }

        function showSuccessMessage(message = 'تم إرسال البيانات بنجاح!') {
            successMessage.innerHTML = `
                <span class="text-2xl">✅</span>
                <p class="font-semibold mt-2">${message}</p>
            `;
            successMessage.classList.remove('hidden');
            successMessage.classList.add('success-animation');
            
            setTimeout(() => {
                successMessage.classList.add('hidden');
                successMessage.classList.remove('success-animation');
            }, 4000);
        }

        function showErrorMessage(message) {
            const errorDiv = document.createElement('div');
            errorDiv.className = 'mt-6 p-4 bg-red-100 border border-red-400 text-red-700 rounded-xl text-center';
            errorDiv.innerHTML = `
                <span class="text-2xl">❌</span>
                <p class="font-semibold mt-2">${message}</p>
            `;
            
            form.parentNode.insertBefore(errorDiv, successMessage);
            
            setTimeout(() => {
                errorDiv.remove();
            }, 5000);
        }

        // Initialize
        updateTeachersList();
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9869d12c64fbf9fa',t:'MTc1OTEzMTQ2Ni4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
