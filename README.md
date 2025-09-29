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
        <div class="hidden md:block absolute top-2 left-4 bg-white/20 backdrop-blur-sm rounded-2xl p-4 border border-white/30 w-80 h-24">
            <div class="flex items-center justify-between h-full">
                <div class="flex items-center space-x-2">
                    <svg class="w-8 h-8 text-yellow-300" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M12 2L13.09 8.26L20 9L13.09 9.74L12 16L10.91 9.74L4 9L10.91 8.26L12 2Z"/>
                    </svg>
                    <div class="text-2xl font-bold text-white tracking-wider" style="text-shadow: 2px 2px 4px rgba(0,0,0,0.3);">
                        <span class="text-yellow-300">2</span><span class="text-blue-200">0</span><span class="text-green-300">2</span><span class="text-pink-300">5</span>
                    </div>
                </div>
                <div class="text-center">
                    <p class="text-white text-sm font-semibold">إعداد أستاذ محمد المزروعي</p>
                    <p class="text-blue-100 text-xs">معلم أول مادة رياضيات</p>
                </div>
            </div>
        </div>
        
        <!-- رموز الرياضيات في الجانب الأيمن العلوي -->
        <div class="hidden md:block absolute top-2 right-4 bg-white/20 backdrop-blur-sm rounded-2xl p-4 border border-white/30 w-80 h-24">
            <div class="flex items-center justify-center h-full">
                <div class="flex gap-3 text-center">
                    <div class="text-2xl text-yellow-300">∫</div>
                    <div class="text-2xl text-blue-200">∑</div>
                    <div class="text-2xl text-green-300">π</div>
                    <div class="text-2xl text-pink-300">√</div>
                    <div class="text-2xl text-purple-300">∞</div>
                    <div class="text-2xl text-orange-300">∆</div>
                    <div class="text-2xl text-red-300">α</div>
                    <div class="text-2xl text-cyan-300">β</div>
                    <div class="text-2xl text-lime-300">θ</div>
                </div>
            </div>
        </div>

        <!-- Header -->
        <div class="text-center mb-8 mt-8 md:mt-20">
            <!-- إطار العنوان الجميل -->
            <div class="bg-white/10 backdrop-blur-sm rounded-2xl p-4 border border-white/30 shadow-lg mx-auto max-w-lg">
                <div class="flex items-center justify-center mb-2">
                    <svg class="w-6 h-6 md:w-8 md:h-8 text-yellow-300 mx-1 md:mx-2" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-8 12H9.5v-2H11c.8 0 1.5-.7 1.5-1.5S11.8 10 11 10H9.5V8H11c1.3 0 2.5 1.1 2.5 2.5 0 .7-.3 1.4-.8 1.9.5.4.8 1.1.8 1.9 0 1.4-1.2 2.7-2.5 2.7zm3.5 0h-1v-2h1c.6 0 1-.4 1-1s-.4-1-1-1h-1v-2h1c.6 0 1-.4 1-1s-.4-1-1-1h-1V8h1c1.1 0 2 .9 2 2 0 .5-.2 1-.5 1.4.3.4.5.9.5 1.4 0 1.1-.9 2.2-2 2.2z"/>
                    </svg>
                    <h1 class="text-lg md:text-2xl font-bold text-white text-center">متابعة سير المنهج وأدوات التقويم</h1>
                    <svg class="w-6 h-6 md:w-8 md:h-8 text-blue-300 mx-1 md:mx-2" fill="currentColor" viewBox="0 0 24 24">
                        <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
                    </svg>
                </div>
                <div class="border-t border-white/30 pt-2">
                    <h2 class="text-base md:text-lg text-blue-100 mb-1 font-semibold">مدرسة محمد بن سليمان الغافري</h2>
                    <div class="flex items-center justify-center">
                        <span class="text-sm md:text-base text-blue-200">مادة الرياضيات</span>
                        <span class="text-lg md:text-xl text-yellow-300 mx-1 md:mx-2">📐</span>
                        <span class="text-lg md:text-xl text-blue-300">📊</span>
                        <span class="text-lg md:text-xl text-green-300 mx-1 md:mx-2">🔢</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- Main Form -->
        <div class="bg-white rounded-2xl p-4 md:p-8 card-shadow">
            <form id="curriculumForm" class="space-y-6">
                <!-- اسم المعلم -->
                <div>
                    <label class="block text-gray-700 text-base md:text-lg font-semibold mb-3">اسم المعلم</label>
                    <select id="studentName" class="form-input w-full p-3 md:p-4 border-2 border-gray-300 rounded-xl focus:border-blue-500 focus:outline-none text-base md:text-lg" required>
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
                    <label class="block text-gray-700 text-base md:text-lg font-semibold mb-3">الصف (يمكن اختيار أكثر من صف)</label>
                    <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-2 md:gap-3 max-h-60 overflow-y-auto border-2 border-gray-300 rounded-xl p-3 md:p-4">
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="خامس 1" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">خامس 1</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="خامس 2" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">خامس 2</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="خامس 3" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">خامس 3</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="خامس 4" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">خامس 4</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="خامس 5" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">خامس 5</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="خامس 6" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">خامس 6</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="سادس 1" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">سادس 1</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="سادس 2" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">سادس 2</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="سادس 3" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">سادس 3</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="سادس 4" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">سادس 4</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="سادس 5" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">سادس 5</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="سابع 1" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">سابع 1</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="سابع 2" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">سابع 2</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="سابع 3" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">سابع 3</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="سابع 4" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">سابع 4</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="سابع 5" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">سابع 5</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="ثامن 1" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">ثامن 1</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="ثامن 2" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">ثامن 2</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="ثامن 3" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">ثامن 3</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="ثامن 4" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">ثامن 4</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="تاسع 1" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">تاسع 1</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="تاسع 2" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">تاسع 2</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="تاسع 3" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">تاسع 3</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="تاسع 4" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">تاسع 4</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="عاشر 1" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">عاشر 1</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="عاشر 2" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">عاشر 2</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="عاشر 3" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">عاشر 3</span>
                        </label>
                        <label class="flex items-center p-2 border border-gray-200 rounded-lg hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="grade" value="عاشر 4" class="ml-2 w-4 h-4 text-blue-600">
                            <span class="text-gray-700 text-xs md:text-sm">عاشر 4</span>
                        </label>
                    </div>
                </div>

                <!-- الدرس -->
                <div>
                    <label class="block text-gray-700 text-base md:text-lg font-semibold mb-3">الدرس</label>
                    <textarea id="lesson" class="form-input w-full p-3 md:p-4 border-2 border-gray-300 rounded-xl focus:border-blue-500 focus:outline-none text-base md:text-lg resize-none" rows="3" placeholder="اكتب عنوان الدرس هنا..." required></textarea>
                </div>

                <!-- أدوات التقويم -->
                <div>
                    <label class="block text-gray-700 text-base md:text-lg font-semibold mb-3">ما تم إنجازه من أدوات التقويم</label>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-3 md:gap-4">
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="assessment" value="الحوار الشفوي 1" class="ml-3 w-4 h-4 md:w-5 md:h-5 text-blue-600">
                            <span class="text-gray-700 text-sm md:text-base">الحوار الشفوي 1</span>
                        </label>
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="assessment" value="الحوار الشفوي 2" class="ml-3 w-4 h-4 md:w-5 md:h-5 text-blue-600">
                            <span class="text-gray-700 text-sm md:text-base">الحوار الشفوي 2</span>
                        </label>
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="assessment" value="سؤال قصير 1" class="ml-3 w-4 h-4 md:w-5 md:h-5 text-blue-600">
                            <span class="text-gray-700 text-sm md:text-base">سؤال قصير 1</span>
                        </label>
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="assessment" value="سؤال قصير 2" class="ml-3 w-4 h-4 md:w-5 md:h-5 text-blue-600">
                            <span class="text-gray-700 text-sm md:text-base">سؤال قصير 2</span>
                        </label>
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="assessment" value="اختبار قصير 1" class="ml-3 w-4 h-4 md:w-5 md:h-5 text-blue-600">
                            <span class="text-gray-700 text-sm md:text-base">اختبار قصير 1</span>
                        </label>
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="assessment" value="اختبار قصير 2" class="ml-3 w-4 h-4 md:w-5 md:h-5 text-blue-600">
                            <span class="text-gray-700 text-sm md:text-base">اختبار قصير 2</span>
                        </label>
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="assessment" value="واجب منزلي 1" class="ml-3 w-4 h-4 md:w-5 md:h-5 text-blue-600">
                            <span class="text-gray-700 text-sm md:text-base">واجب منزلي 1</span>
                        </label>
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors">
                            <input type="checkbox" name="assessment" value="واجب منزلي 2" class="ml-3 w-4 h-4 md:w-5 md:h-5 text-blue-600">
                            <span class="text-gray-700 text-sm md:text-base">واجب منزلي 2</span>
                        </label>
                        <label class="flex items-center p-3 border-2 border-gray-200 rounded-xl hover:border-blue-300 cursor-pointer transition-colors md:col-span-2">
                            <input type="checkbox" name="assessment" value="المشروع" class="ml-3 w-4 h-4 md:w-5 md:h-5 text-blue-600">
                            <span class="text-gray-700 text-sm md:text-base">المشروع</span>
                        </label>
                    </div>
                </div>

                <!-- التاريخ -->
                <div>
                    <label class="block text-gray-700 text-base md:text-lg font-semibold mb-3">التاريخ</label>
                    <input type="date" id="date" class="form-input w-full p-3 md:p-4 border-2 border-gray-300 rounded-xl focus:border-blue-500 focus:outline-none text-base md:text-lg" required>
                </div>

                <!-- زر الإرسال -->
                <div class="text-center pt-4">
                    <button type="submit" class="submit-btn text-white px-8 md:px-12 py-3 md:py-4 rounded-xl text-lg md:text-xl font-bold">
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
                grade: Array.from(document.querySelectorAll('input[name="grade"]:checked')).map(cb => cb.value),
                lesson: document.getElementById('lesson').value,
                assessments: Array.from(document.querySelectorAll('input[name="assessment"]:checked')).map(cb => cb.value),
                date: document.getElementById('date').value
            };

            // إرسال البيانات باستخدام GET مع المعاملات
            const params = new URLSearchParams();
            params.append('teacherName', formData.teacherName);
            params.append('grade', formData.grade.join(', '));
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
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'986d128cf0b9f9f0',t:'MTc1OTE2NTYwMS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
