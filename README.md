# Ghaith
<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>عطر شخصيتك</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <div class="logo">
            <h1>عطر شخصيتك</h1>
            <p>اكتشف العطر الذي يتناغم مع شخصيتك</p>
        </div>
    </header>

    <section class="quiz">
        <h2>اختبار الشخصية</h2>
        <form id="personality-quiz">
            <label for="mood">كيف تصف مزاجك؟</label>
            <select id="mood" name="mood">
                <option value="مغامر">مغامر</option>
                <option value="هادئ">هادئ</option>
                <option value="عصري">عصري</option>
                <option value="كلاسيكي">كلاسيكي</option>
            </select>

            <label for="fragrance">ما هي الروائح التي تفضلها؟</label>
            <select id="fragrance" name="fragrance">
                <option value="زهور">زهور</option>
                <option value="فاكهة">فاكهة</option>
                <option value="خشب">خشب</option>
                <option value="توابل">توابل</option>
            </select>

            <button type="submit">احصل على توصية</button>
        </form>
    </section>

    <section id="recommendation">
        <h2>توصيات العطور</h2>
        <div id="recommended-fragrance">
            <!-- ستظهر التوصية هنا بعد اختبار الشخصية -->
        </div>
    </section>

    <footer>
        <p>&copy; 2025 عطر شخصيتك. جميع الحقوق محفوظة.</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>
{

    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f1f1f1;
    color: #333;
}

header {
    background-color: #2c3e50;
    color: white;
    padding: 20px;
    text-align: center;
}

header h1 {
    margin-bottom: 10px;
}

.quiz {
    margin: 30px auto;
    width: 80%;
    max-width: 500px;
    background-color: #fff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

label {
    display: block;
    margin-bottom: 10px;
    font-size: 16px;
}

select {
    width: 100%;
    padding: 10px;
    margin-bottom: 20px;
    font-size: 16px;
    border-radius: 4px;
    border: 1px solid #ccc;
}

button {
    background-color: #2c3e50;
    color: white;
    padding: 12px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #34495e;
}

#recommendation {
    display: none;
    text-align: center;
    margin-top: 30px;
}

footer {
    text-align: center;
    padding: 20px;
    background-color: #2c3e50;
    color: white;
    margin-top: 50px;
}
document.getElementById('personality-quiz').addEventListener('submit', function (e) {
    e.preventDefault();

    // الحصول على الاختيارات
    const mood = document.getElementById('mood').value;
    const fragrance = document.getElementById('fragrance').value;

    // توصية العطر بناءً على الاختيارات
    let recommendation = '';

    if (mood === 'مغامر' && fragrance === 'توابل') {
        recommendation = 'عطر التوابل الغني سيمنحك تجربة مغامرة مثيرة!';
    } else if (mood === 'هادئ' && fragrance === 'زهور') {
        recommendation = 'عطر زهري هادئ سيعكس شخصيتك الرقيقة.';
    } else if (mood === 'عصري' && fragrance === 'فاكهة') {
        recommendation = 'عطر فاكهي عصري يناسب ذوقك المتجدد.';
    } else {
        recommendation = 'عطر خشبي كلاسيكي يناسب أسلوبك الراقي.';
    }

    // عرض التوصية
    const recommendationDiv = document.getElementById('recommended-fragrance');
    recommendationDiv.textContent = recommendation;

    document.getElementById('recommendation').style.display = 'block';
}); 
