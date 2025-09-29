إزالة قسم إعدادات الربط

سأقوم بإزالة قسم "دليل إعداد Google Apps Script" من الصفحة مع الحفاظ على بقية الوظائف والمظهر. إليك الكود المحدث:

```html
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
        </div>
    </div>

    <script>
        let teachers = [];
        let teacherIdCounter = 1;

        const form = document.getElementById('teacherForm');
        const successMessage = document.getElementById('successMessage');
        const teachersList = document.getElementById('teachersList');
        const teacherCount = document.getElementById('teacherCount');

        form.addEventListener('submit', async function(e) {
            e.preventDefault();
            
            const submitButton = form.querySelector('button[type="submit"]');
            const originalText = submitButton.innerHTML;
            
            // التحقق من صحة البيانات
            const formData = new FormData(form);
            const name = formData.get('teacherName')?.trim();
            const grade = formData.get('grade');
            const age = formData.get('age');
            
            if (!name || !grade || !age) {
                showErrorMessage('يرجى ملء جميع الحقول المطلوبة');
                return;
            }
            
            // تغيير حالة الزر أثناء الإرسال
            submitButton.disabled = true;
            submitButton.innerHTML = '<span class="flex items-center justify-center"><span class="ml-2 animate-spin">⏳</span>جاري الإرسال...</span>';
            
            const teacher = {
                id: teacherIdCounter++,
                name: name,
                grade: grade,
                age: age,
                experience: formData.get('experience') || 'غير محدد',
                timestamp: new Date().toLocaleString('ar-SA')
            };

            try {
                // حفظ البيانات محلياً
                teachers.push(teacher);
                updateTeachersList();
                form.reset();
                showSuccessMessage('تم حفظ البيانات بنجاح!');
                
            } catch (error) {
                console.error('خطأ في حفظ البيانات:', error);
                showErrorMessage('حدث خطأ أثناء حفظ البيانات');
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
</body>
</html>
```

التغييرات التي تمت:

1. إزالة قسم Google Apps Script بالكامل - تم حذف القسم الذي كان يحتوي على دليل الإعداد والربط مع Google Sheets.
2. تبسيط وظيفة الإرسال - تم إزالة الكود المتعلق بإرسال البيانات إلى Google Apps Script، والآن يتم حفظ البيانات محلياً فقط.
3. إزالة المتغيرات المتعلقة بالربط - تم حذف المتغير GOOGLE_SCRIPT_URL وجميع الإشارات إليه.
4. تبسيط رسائل النجاح - تم تعديل رسائل النجاح لتتناسب مع الحفظ المحلي فقط.

الآن التطبيق يعمل بشكل مستقل تماماً دون الحاجة إلى أي تكوينات خارجية أو ربط مع Google Sheets، ويحفظ البيانات محلياً في المتصفح فقط.
