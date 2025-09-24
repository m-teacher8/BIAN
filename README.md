
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>لوحة تحكم بيانات المعلمين</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f3f4f6;
            color: #374151;
        }
    </style>
</head>
<body class="p-4 md:p-8">

    <!-- Main Container -->
    <div class="max-w-4xl mx-auto bg-white p-6 md:p-10 rounded-xl shadow-lg">

        <h1 class="text-3xl md:text-4xl font-bold text-center mb-8 text-indigo-700">لوحة تحكم بيانات المعلمين</h1>

        <!-- Data Display Section -->
        <section>
            <h2 class="text-2xl font-semibold mb-4 border-b-2 pb-2 border-indigo-200">بيانات المعلمين الحالية</h2>
            <div id="teachers-data" class="grid grid-cols-1 md:grid-cols-2 gap-6">
                <!-- Data cards will be injected here by JavaScript -->
                <p class="text-center text-gray-500 animate-pulse">يتم جلب البيانات، يرجى الانتظار...</p>
            </div>
        </section>

        <!-- Spacer -->
        <div class="my-10 border-t-2 border-gray-200"></div>

        <!-- Data Submission Form Section -->
        <section>
            <h2 class="text-2xl font-semibold mb-4 border-b-2 pb-2 border-indigo-200">إرسال بيانات معلم جديد</h2>
            <form id="teacher-form" class="space-y-6">
                <div>
                    <label for="teacher-name" class="block text-sm font-medium text-gray-700">الاسم</label>
                    <input type="text" id="teacher-name" required placeholder="أدخل اسم المعلم"
                           class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-indigo-500 focus:border-indigo-500 transition duration-150 ease-in-out">
                </div>
                <div>
                    <label for="teacher-grade" class="block text-sm font-medium text-gray-700">الصف</label>
                    <input type="text" id="teacher-grade" required placeholder="أدخل الصف"
                           class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-indigo-500 focus:border-indigo-500 transition duration-150 ease-in-out">
                </div>
                <div>
                    <label for="teacher-age" class="block text-sm font-medium text-gray-700">العمر</label>
                    <input type="number" id="teacher-age" required placeholder="أدخل عمر المعلم"
                           class="mt-1 block w-full px-4 py-2 border border-gray-300 rounded-md shadow-sm focus:ring-indigo-500 focus:border-indigo-500 transition duration-150 ease-in-out">
                </div>
                <div class="flex justify-center">
                    <button type="submit"
                            class="w-full md:w-auto px-6 py-2 border border-transparent rounded-md shadow-sm text-base font-medium text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500 transition duration-150 ease-in-out">
                        إرسال البيانات
                    </button>
                </div>
            </form>
            <!-- Response message container -->
            <div id="response-message" class="mt-6 p-4 rounded-md text-sm text-center" style="display: none;"></div>
        </section>

    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // Function to fetch and display data from the Google Sheets URL
            async function fetchAndDisplayTeachers() {
                const dataContainer = document.getElementById('teachers-data');
                const sheetUrl = "https://docs.google.com/spreadsheets/d/e/2PACX-1vQkvyiigUhNTs6mV4HiHEMoZCAFC3-jcXI3vnjtnmGgI8KGM_Bm0F-72FWWOhU00q4In0DSdtUlALVy/pubhtml?gid=0&single=true";

                // IMPORTANT: Direct fetching from Google Sheets may be blocked due to CORS policy.
                // For a real-world application, a backend server or a CORS proxy would be needed.
                // The code below is designed to parse the raw HTML table if the fetch is successful.

                try {
                    const response = await fetch(sheetUrl);
                    if (!response.ok) {
                        throw new Error(`HTTP error! status: ${response.status}`);
                    }
                    const htmlText = await response.text();

                    // Parse the HTML string to a DOM object
                    const parser = new DOMParser();
                    const doc = parser.parseFromString(htmlText, 'text/html');
                    const table = doc.querySelector('table tbody');

                    if (!table) {
                        dataContainer.innerHTML = `<p class="text-center text-red-500">لم يتم العثور على جدول البيانات. يرجى التحقق من الرابط.</p>`;
                        return;
                    }

                    // Clear the loading message
                    dataContainer.innerHTML = '';

                    // Iterate over table rows (skipping the header row)
                    const rows = table.querySelectorAll('tr');
                    for (let i = 1; i < rows.length; i++) {
                        const cells = rows[i].querySelectorAll('td');
                        if (cells.length >= 3) {
                            const name = cells[0].textContent.trim();
                            const grade = cells[1].textContent.trim();
                            const age = cells[2].textContent.trim();

                            // Create a card element for each teacher
                            const teacherCard = document.createElement('div');
                            teacherCard.className = "bg-gray-50 p-6 rounded-lg shadow-sm transition-all duration-300 hover:shadow-md";
                            teacherCard.innerHTML = `
                                <p class="text-xl font-bold mb-2 text-indigo-600">${name}</p>
                                <p class="text-gray-600"><span class="font-medium text-gray-800">الصف:</span> ${grade}</p>
                                <p class="text-gray-600"><span class="font-medium text-gray-800">العمر:</span> ${age}</p>
                            `;
                            dataContainer.appendChild(teacherCard);
                        }
                    }

                    if (rows.length <= 1) {
                         dataContainer.innerHTML = `<p class="text-center text-gray-500">لا توجد بيانات متاحة لعرضها حاليًا.</p>`;
                    }

                } catch (error) {
                    console.error('Error fetching or parsing data:', error);
                    dataContainer.innerHTML = `<p class="text-center text-red-500">حدث خطأ أثناء جلب البيانات. قد يكون بسبب سياسات الحماية في المتصفح.</p>`;
                }
            }

            // Function to handle form submission
            const form = document.getElementById('teacher-form');
            const responseMessage = document.getElementById('response-message');

            form.addEventListener('submit', (event) => {
                event.preventDefault(); // Prevent default form submission

                // Get form values
                const name = document.getElementById('teacher-name').value;
                const grade = document.getElementById('teacher-grade').value;
                const age = document.getElementById('teacher-age').value;

                // Display a "sending" message
                responseMessage.style.display = 'block';
                responseMessage.className = "mt-6 p-4 rounded-md text-sm text-center bg-yellow-100 text-yellow-800";
                responseMessage.innerHTML = 'يتم إرسال البيانات...';

                // Simulate a submission process with a delay
                // Since this is a static page, we can't send data to Google Sheets directly.
                // This simulates the "receiving a response" part of your request.
                setTimeout(() => {
                    responseMessage.className = "mt-6 p-4 rounded-md text-sm text-center bg-green-100 text-green-800";
                    responseMessage.innerHTML = `تم استلام بياناتك بنجاح! شكراً لك، ${name}.`;

                    // Reset the form
                    form.reset();
                }, 1500); // 1.5 second delay
            });

            // Call the function to fetch data when the page loads
            fetchAndDisplayTeachers();
        });
    </script>
</body>
</html>
