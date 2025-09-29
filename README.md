<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>متابعة سير المنهج وأدوات التقويم</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        .gradient-bg {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }
        .card-shadow {
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }
        .form-input {
            transition: all 0.3s ease;
        }
        .form-input:focus {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.3);
        }
        .submit-btn {
            background: linear-gradient(45deg, #4CAF50, #45a049);
            transition: all 0.3s ease;
        }
        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(76, 175, 80, 0.4);
        }
    </style>
</head>
<body class="gradient-bg min-h-screen py-8">
    <div class="container mx-auto px-4 max-w-4xl">
        <!-- رقم 2025 المزخرف -->
        <div class="absolute top-4 left-4 bg-white/20 backdrop-blur-sm rounded-2xl p-4 border border-white/30">
            <div class="flex items-center space-x-2">
                <svg class="w-8 h-8 text-yellow-300" fill="currentColor" viewBox="0 0 24 24">
                    <path d="M12 2L13.09 8.26L20 9L13.09 9.74L12 16L10.91 9.74L4 9L10.91 8.26L12 2Z"/>
                </svg>
                <div class="text-3xl font-bold text-white tracking-wider" style="text-shadow: 2px 2px 4px rgba(0,0,0,0.3);">
                    <span class="text-yellow-300">2</span><span class="text-blue-200">0</span><span class="text-green-300">2</span><span class="text-pink-300">5</span>
                </div>
                <div class="flex flex-col space-y-1">
                    <span class="text-white text-xs">π</span>
                    <span class="text-white text-xs">∑</span>
                    <span class="text-white text-xs">∞</span>
                </div>
            </div>
            <div class="mt-3 text-center">
                <p class="text-white text-sm font-semibold">إعداد أستاذ محمد المزروعي</p>
                <p class="text-blue-100 text-xs">معلم أول مادة رياضيات</p>
            </div>
        </div>
        
        <!-- Header -->
        <div class="text-center mb-8">
            <h1 class="text-4xl font-bold text-white mb-2">متابعة سير المنهج وأدوات التقويم</h1>
            <h2 class="text-2xl text-blue-100 mb-2">مدرسة محمد بن سليمان الغافري</h2>
            <h3 class="text-xl text-blue-200">مادة الرياضيات</h3>
        </div>

        <!-- Main Form -->
        <div class="bg-white rounded-2xl p-8 card-shadow">
            <form id="curriculumForm" class="space-y-6">
                <!-- اسم المعلم -->
                <div>
                    <label class="block text-gray-700 text-lg font-semibold mb-3">اسم المعلم</label>
                    <select id="studentName" class="form-input w-full p-4 border-2 border-gray-300 rounded-xl focus:border-blue-500 focus:outline-none text-lg" required>
                        <option value="">اختر اسم المعلم</option>
                        <option value="عمر بطيء">عمر بطيء</option>
                        <option value="حمد الجابري">حمد الجابري</option>
                        <option value="حمد السكيتي">حمد السكيتي</option>
                        <option value="محمد المزروعي">محمد المزروعي</option>
                        <option value="مجدي مبارك">مجدي مبارك</option>
                        <option value="بشير المعمري">بشير المعمري</option>
                        <option value="سفيان الأزهر">سفيان الأزهر</option>
                        <option value="درويش الغافري">درويش الغافري</option>
                        <option value="عبدالله الغافري">عبدالله الغافري</option>
                        <option value="وليد الشلع">وليد الشلع</option>
                    </select>
                </div>

                <!-- الصف -->
                <div>
                    <label class="block text-gray-700 text-lg font-semibold mb-3">الصف</label>
                    <select id="grade" class="form-input w-full p-4 border-2 border-gray-300 rounded-xl focus:border-blue-500 focus:outline-none text-lg" required>
                        <option value="">اختر الصف</option>
                        <option value="خامس واحد">خامس واحد</option>
                        <option value="خامس اثنين">خامس اثنين</option>
                        <option value="خامس ثلاثة">خامس ثلاثة</option>
                        <option value="خامس أربعة">خامس أربعة</option>
                        <option value="خامس خمسة">خامس خمسة</option>
                        <option value="خامس ستة">خامس ستة</option>
                        <option value="سادس واحد">سادس واحد</option>
                        <option value="سادس اثنين">سادس اثنين</option>
                        <option value="سادس ثلاثة">سادس ثلاثة</option>
                        <option value="سادس أربعة">سادس أربعة</option>
                        <option value="سادس خمسة">سادس خمسة</option>
                        <option value="سابع واحد">سابع واحد</option>
                        <option value="سابع اثنين">سابع اثنين</option>
                        <option value="سابع ثلاثة">سابع ثلاثة</option>
                        <option value="سابع أربعة">سابع أربعة</option>
                        <option value="سابع خمسة">سابع خمسة</option>
                        <option value="ثامن واحد">ثامن واحد</option>
                        <option value="ثامن اثنين">ثامن اثنين</option>
                        <option value="ثامن ثلاثة">ثامن ثلاثة</option>
                        <option value="ثامن أربعة">ثامن أربعة</option>
                        <option value="تاسع واحد">تاسع واحد</option>
                        <option value="تاسع اثنين">تاسع اثنين</option>
                        <option value="تاسع ثلاثة">تاسع ثلاثة</option>
                        <option value="عاشر واحد">عاشر واحد</option>
                        <option value="عاشر اثنين">عاشر اثنين</option>
                        <option value="عاشر ثلاثة">عاشر ثلاثة</option>
                        <option value="عاشر أربعة">عاشر أربعة</option>
                    </select>
                </div>

                <!-- الدرس -->
                <div>
                    <label class="block text-gray-700 text-lg font-semibold mb-3">الدرس</label>
                    <textarea id="lesson" class="form-input w-full p-4 border-2 border-gray-300 rounded-xl focus:border-blue-500 focus:outline-none text-lg resize-none" rows="3" placeholder="اكتب عنوان الدرس هنا..." required></textarea>
                </div>

                <!-- أدوات التقويم -->
                <div>
                    <label class="block text-gray-700 text-lg font-semibold mb-3">ما تم إنجازه من أدوات التقويم</label>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="assessment" value="سؤال قصير واحد" class="ml-3 w-5 h-5 text-blue-600">
                            <span class="text-gray-700">سؤال قصير واحد</span>
                        </label>
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="assessment" value="سؤال قصير اثنين" class="ml-3 w-5 h-5 text-blue-600">
                            <span class="text-gray-700">سؤال قصير اثنين</span>
                        </label>
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="assessment" value="اختبار قصير واحد" class="ml-3 w-5 h-5 text-blue-600">
                            <span class="text-gray-700">اختبار قصير واحد</span>
                        </label>
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="assessment" value="اختبار قصير اثنين" class="ml-3 w-5 h-5 text-blue-600">
                            <span class="text-gray-700">اختبار قصير اثنين</span>
                        </label>
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="assessment" value="واجب منزلي واحد" class="ml-3 w-5 h-5 text-blue-600">
                            <span class="text-gray-700">واجب منزلي واحد</span>
                        </label>
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="assessment" value="واجب منزلي اثنين" class="ml-3 w-5 h-5 text-blue-600">
                            <span class="text-gray-700">واجب منزلي اثنين</span>
                        </label>
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors md:col-span-2">
                            <input type="checkbox" name="assessment" value="المشروع" class="ml-3 w-5 h-5 text-blue-600">
                            <span class="text-gray-700">المشروع</span>
                        </label>
                    </div>
                </div>

                <!-- التاريخ -->
                <div>
                    <label class="block text-gray-700 text-lg font-semibold mb-3">التاريخ</label>
                    <input type="date" id="date" class="form-input w-full p-4 border-2 border-gray-300 rounded-xl focus:border-blue-500 focus:outline-none text-lg" required>
                </div>

                <!-- زر الإرسال -->
                <div class="text-center pt-4">
                    <button type="submit" class="submit-btn text-white px-12 py-4 rounded-xl text-xl font-bold">
                        إرسال البيانات
                    </button>
                </div>
            </form>

            <!-- رسالة النجاح -->
            <div id="successMessage" class="hidden mt-6 p-4 bg-green-100 border border-green-400 text-green-700 rounded-xl text-center">
                <div class="flex items-center justify-center">
                    <svg class="w-6 h-6 ml-2" fill="currentColor" viewBox="0 0 20 20">
                        <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z" clip-rule="evenodd"></path>
                    </svg>
                    <span class="font-semibold">تم إرسال البيانات بنجاح!</span>
                </div>
            </div>
        </div>


    </div>

    <script>
        // تعيين التاريخ الحالي
        document.getElementById('date').valueAsDate = new Date();

        // معالجة إرسال النموذج
        document.getElementById('curriculumForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // جمع البيانات
            const formData = {
                teacherName: document.getElementById('studentName').value,
                grade: document.getElementById('grade').value,
                lesson: document.getElementById('lesson').value,
                assessments: Array.from(document.querySelectorAll('input[name="assessment"]:checked')).map(cb => cb.value),
                date: document.getElementById('date').value
            };

            // إرسال البيانات باستخدام GET مع المعاملات
            const params = new URLSearchParams();
            params.append('teacherName', formData.teacherName);
            params.append('grade', formData.grade);
            params.append('lesson', formData.lesson);
            params.append('assessments', formData.assessments.join(', '));
            params.append('date', formData.date);

            const url = 'https://script.google.com/macros/s/AKfycbwJdIE9Lkc_hsTqrIoN-t9y7-jH0nhWJcSqI_ljJX9U1XlIzw3FNctd402X-STfhsvJQw/exec?' + params.toString();

            // استخدام iframe مخفي للإرسال
            const iframe = document.createElement('iframe');
            iframe.style.display = 'none';
            iframe.src = url;
            document.body.appendChild(iframe);

            console.log('البيانات المرسلة:', formData);
            console.log('الرابط:', url);
            
            // إظهار رسالة النجاح
            document.getElementById('successMessage').classList.remove('hidden');
            
            // إزالة الـ iframe بعد ثانيتين
            setTimeout(() => {
                document.body.removeChild(iframe);
            }, 2000);
            
            // إخفاء الرسالة بعد 3 ثوان
            setTimeout(() => {
                document.getElementById('successMessage').classList.add('hidden');
            }, 3000);

            // إعادة تعيين النموذج
            setTimeout(() => {
                this.reset();
                document.getElementById('date').valueAsDate = new Date();
            }, 1000);
        });

        // تأثيرات تفاعلية للنموذج
        const inputs = document.querySelectorAll('.form-input');
        inputs.forEach(input => {
            input.addEventListener('focus', function() {
                this.parentElement.classList.add('transform', 'scale-105');
            });
            
            input.addEventListener('blur', function() {
                this.parentElement.classList.remove('transform', 'scale-105');
            });
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'986cbe05e701f9fb',t:'MTc1OTE2MjEzOC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
