<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>موقع الزواج والتعارف</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            text-align: center;
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h1 {
            color: #333;
        }
        input[type="text"], input[type="date"] {
            width: calc(100% - 20px);
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        select {
            width: calc(100% - 20px);
            padding: 10px;
            margin: 10px 0;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .gender {
            display: flex;
            justify-content: center;
        }
        .gender label {
            margin-right: 10px;
        }
        .submit-btn {
            background-color: #4CAF50;
            color: white;
            padding: 15px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-size: 16px;
        }
        .submit-btn:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>موقع الزواج والتعارف</h1>
        <form>
            <input type="text" id="fullname" placeholder="الاسم الكامل">
            <input type="text" id="login" placeholder="تسجيل الدخول: فيسبوك، جوجل، رقم الهاتف">
            <select id="search-for">
                <option value="marriage">الزواج</option>
                <option value="acquaintance">التعارف</option>
                <option value="friendship">الصداقة</option>
            </select>
            <select id="country">
                <option value="Algeria">الجزائر</option>
                <option value="Palestine">فلسطين</option>
                <option value="Tunisia">تونس</option>
                <option value="Libya">ليبيا</option>
                <option value="Egypt">مصر</option>
                <option value="Iraq">العراق</option>
                <option value="Lebanon">لبنان</option>
                <option value="Syria">سوريا</option>
            </select>
            <input type="file" id="image" accept="image/*" onchange="previewImage()">
            <img id="image-preview" src="#" alt="صورتك">
            <div class="gender">
                <input type="radio" id="male" name="gender" value="male">
                <label for="male">رجل</label>
                <input type="radio" id="female" name="gender" value="female">
                <label for="female">امرأة</label>
            </div>
            <input type="date" id="birthdate" placeholder="تاريخ الميلاد">
            <textarea id="message" rows="4" placeholder="نص جيد ومميز عن الزواج والتعارف"></textarea>
            <button type="button" class="submit-btn">إنشاء الحساب</button>
        </form>
    </div>

    <script>
        function previewImage() {
            var preview = document.getElementById('image-preview');
            var file = document.getElementById('image').files[0];
            var reader = new FileReader();

            reader.onloadend = function () {
                preview.src = reader.result;
            }

            if (file) {
                reader.readAsDataURL(file);
            } else {
                preview.src = "#";
            }
        }
    </script>
</body>
</html>
