<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Traditional Sudanese Juices | العصائر السودانية التقليدية</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;600;700&family=Tajawal:wght@400;500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --aradaib-color: #d4a017;
            --karkade-color: #8b0000;
            --hulu-marr-color: #5e2c04;
            --tabaldi-color: #654321;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Montserrat', sans-serif;
            background-color: #f8f8f8;
            color: #333;
            min-height: 100vh;
            overflow-x: hidden;
        }

        .arabic {
            font-family: 'Tajawal', sans-serif;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 2rem;
        }

        /* Modern Header */
        .header {
            text-align: center;
            margin-bottom: 4rem;
            position: relative;
            padding-top: 2rem;
        }

        .header h1 {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
            color: #222;
            letter-spacing: -1px;
            position: relative;
            display: inline-block;
        }

        .header h1::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: #222;
            border-radius: 2px;
        }

        .header h2 {
            font-size: 1.8rem;
            font-weight: 300;
            color: #555;
            margin-top: 1.5rem;
            direction: rtl;
        }

        /* Modern Grid Layout */
        .juice-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2.5rem;
            margin-bottom: 4rem;
        }

        /* Card Design */
        .juice-card {
            background: white;
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0,0,0,0.08);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            cursor: pointer;
            position: relative;
        }

        .juice-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.12);
        }

        .juice-image-container {
            width: 100%;
            height: 220px;
            overflow: hidden;
            position: relative;
        }

        .juice-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }

        .juice-card:hover .juice-image {
            transform: scale(1.1);
        }

        .juice-content {
            padding: 1.8rem;
        }

        .juice-name {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: #222;
        }

        .juice-name-arabic {
            font-size: 1.1rem;
            color: #666;
            direction: rtl;
            margin-bottom: 1rem;
        }

        .view-btn {
            display: inline-block;
            padding: 0.6rem 1.5rem;
            background: #222;
            color: white;
            border-radius: 50px;
            font-size: 0.9rem;
            font-weight: 500;
            text-decoration: none;
            transition: all 0.3s ease;
            border: 2px solid #222;
        }

        .view-btn:hover {
            background: transparent;
            color: #222;
        }

        /* Modal Styles */
        .detail-modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            opacity: 0;
            transition: opacity 0.4s ease;
            backdrop-filter: blur(8px);
        }

        .detail-modal.active {
            display: flex;
            opacity: 1;
        }

        .modal-content {
            background: white;
            max-width: 1100px;
            width: 90%;
            max-height: 90vh;
            overflow-y: auto;
            border-radius: 20px;
            box-shadow: 0 30px 80px rgba(0,0,0,0.4);
            transform: scale(0.8);
            transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .detail-modal.active .modal-content {
            transform: scale(1);
        }

        .modal-header {
            padding: 3rem 3rem 2rem;
            text-align: center;
            color: white;
            position: relative;
        }

        .modal-header h2 {
            font-size: 2.8rem;
            margin-bottom: 0.5rem;
            font-weight: 700;
        }

        .modal-header h3 {
            font-size: 1.8rem;
            opacity: 0.9;
            font-weight: 400;
        }

        .close-btn {
            position: absolute;
            top: 1.5rem;
            right: 1.5rem;
            background: rgba(255, 255, 255, 0.2);
            border: none;
            color: white;
            font-size: 1.8rem;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .close-btn:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: rotate(90deg);
        }

        .modal-body {
            display: flex;
        }

        .modal-image-container {
            flex: 1;
            min-height: 400px;
            overflow: hidden;
        }

        .modal-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .content-section {
            flex: 1;
            padding: 2.5rem;
        }

        .arabic-section {
            direction: rtl;
            text-align: right;
            border-right: 1px solid #eee;
        }

        .english-section {
            direction: ltr;
            text-align: left;
        }

        .section-title {
            font-size: 1.8rem;
            font-weight: 600;
            margin-bottom: 1.5rem;
            color: #222;
            position: relative;
            padding-bottom: 0.5rem;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 60px;
            height: 3px;
            background: currentColor;
        }

        .arabic-section .section-title::after {
            left: auto;
            right: 0;
        }

        .section-content {
            line-height: 1.8;
            color: #555;
        }

        .section-content h4 {
            color: #222;
            margin: 2rem 0 1rem 0;
            font-size: 1.3rem;
            font-weight: 600;
        }

        .section-content p {
            margin-bottom: 1.5rem;
        }

        .section-content ul {
            margin: 1rem 0;
            padding-left: 1.8rem;
        }

        .section-content li {
            margin-bottom: 0.8rem;
            position: relative;
        }

        .arabic-section ul {
            padding-right: 1.8rem;
            padding-left: 0;
        }

        /* Color Themes for Modals */
        .aradaib-theme .modal-header {
            background: var(--aradaib-color);
        }
        .aradaib-theme .section-title::after {
            background: var(--aradaib-color);
        }

        .karkade-theme .modal-header {
            background: var(--karkade-color);
        }
        .karkade-theme .section-title::after {
            background: var(--karkade-color);
        }

        .hulu-marr-theme .modal-header {
            background: var(--hulu-marr-color);
        }
        .hulu-marr-theme .section-title::after {
            background: var(--hulu-marr-color);
        }

        .tabaldi-theme .modal-header {
            background: var(--tabaldi-color);
        }
        .tabaldi-theme .section-title::after {
            background: var(--tabaldi-color);
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .modal-body {
                flex-direction: column;
            }
            .modal-image-container {
                min-height: 300px;
            }
            .arabic-section {
                border-right: none;
                border-bottom: 1px solid #eee;
            }
        }

        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.5rem;
            }
            .header h2 {
                font-size: 1.5rem;
            }
            .juice-grid {
                grid-template-columns: 1fr;
            }
            .modal-header {
                padding: 2rem 2rem 1.5rem;
            }
            .modal-header h2 {
                font-size: 2rem;
            }
            .modal-header h3 {
                font-size: 1.4rem;
            }
            .content-section {
                padding: 1.8rem;
            }
        }

        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Stagger Animation for Cards */
        .juice-card {
            opacity: 0;
            animation: slideUp 0.6s forwards;
        }

        .juice-card:nth-child(1) { animation-delay: 0.1s; }
        .juice-card:nth-child(2) { animation-delay: 0.2s; }
        .juice-card:nth-child(3) { animation-delay: 0.3s; }
        .juice-card:nth-child(4) { animation-delay: 0.4s; }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>Traditional Sudanese Juices</h1>
            <h2 class="arabic">العصائر السودانية التقليدية</h2>
        </div>

        <div class="juice-grid">
            <div class="juice-card" onclick="openModal('aradaib')">
                <div class="juice-image-container">
                    <img src="https://www.sarahanews.net/wp-content/uploads/2024/03/61-103731-benefits-tamarind-drink-health-ramadan_700x400.jpg" alt="Aradaib Juice" class="juice-image">
                </div>
                <div class="juice-content">
                    <h3 class="juice-name">ARADAIB</h3>
                    <p class="juice-name-arabic arabic">عصير العرديب</p>
                    <a href="#" class="view-btn" onclick="event.preventDefault(); openModal('aradaib')">View Details</a>
                </div>
            </div>

            <div class="juice-card" onclick="openModal('karkade')">
                <div class="juice-image-container">
                    <img src="https://www.wellnesswarrior.org/wp-content/uploads/2025/05/KETO-Karkade-Iced-Hibiscus-Tea-Sudan-750x400.jpg" alt="Karkade Juice" class="juice-image">
                </div>
                <div class="juice-content">
                    <h3 class="juice-name">KARKADE</h3>
                    <p class="juice-name-arabic arabic">عصير الكركديه</p>
                    <a href="#" class="view-btn" onclick="event.preventDefault(); openModal('karkade')">View Details</a>
                </div>
            </div>

            <div class="juice-card" onclick="openModal('hulu-marr')">
                <div class="juice-image-container">
                    <img src="https://vid.alarabiya.net/images/2024/03/08/84a97b40-cd62-4bf2-a061-063b64e6058b/84a97b40-cd62-4bf2-a061-063b64e6058b_16x9_1200x676.jpg" alt="Hulu Marr Juice" class="juice-image">
                </div>
                <div class="juice-content">
                    <h3 class="juice-name">HULU MARR</h3>
                    <p class="juice-name-arabic arabic">حلو مر</p>
                    <a href="#" class="view-btn" onclick="event.preventDefault(); openModal('hulu-marr')">View Details</a>
                </div>
            </div>

            <div class="juice-card" onclick="openModal('tabaldi')">
                <div class="juice-image-container">
                    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRxwDPBy3n0Ha4lfM1HVjHe_1hfHeTH3fnQzg&s" alt="Tabaldi Juice" class="juice-image">
                </div>
                <div class="juice-content">
                    <h3 class="juice-name">TABALDI</h3>
                    <p class="juice-name-arabic arabic">التبلدي</p>
                    <a href="#" class="view-btn" onclick="event.preventDefault(); openModal('tabaldi')">View Details</a>
                </div>
            </div>
        </div>
    </div>

    <!-- Modals -->
    <div id="aradaib-modal" class="detail-modal aradaib-theme">
        <div class="modal-content">
            <div class="modal-header">
                <button class="close-btn" onclick="closeModal('aradaib')">&times;</button>
                <h2>ARADAIB</h2>
                <h3 class="arabic">عصير العرديب (تمر هندي)</h3>
            </div>
            <div class="modal-body">
                <div class="modal-image-container">
                    <img src="https://www.sarahanews.net/wp-content/uploads/2024/03/61-103731-benefits-tamarind-drink-health-ramadan_700x400.jpg" alt="Aradaib Juice" class="modal-image">
                </div>
                <div class="content-section arabic-section">
                    <div class="section-title arabic">المعلومات بالعربية</div>
                    <div class="section-content">
                        <h4>الأصل والمكونات</h4>
                        <p>يُستخرج من ثمار شجرة التمر الهندي (Tamarindus indica) المنتشرة في السودان.</p>
                        <p><strong>المكونات:</strong> لب التمر الهندي المجفف، ماء، سكر/عسل، ونكهات مثل الزنجبيل أو ماء الورد (اختياري).</p>
                        
                        <h4>طريقة التحضير</h4>
                        <ul>
                            <li>انقعي التمر الهندي في ماء دافئ لمدة ساعة</li>
                            <li>اعصري اللب باستخدام مصفاة ناعمة</li>
                            <li>أضيفي الماء البارد والسكر، ثم برديه في الثلاجة</li>
                            <li>قدّميه مع ثلج ونعناع طازج</li>
                        </ul>
                        
                        <h4>معلومات إضافية</h4>
                        <p>مشروب تقليدي سوداني منعش في الصيف، يُعتقد أنه يساعد على الهضم ويخفض الحرارة.</p>
                    </div>
                </div>
                <div class="content-section english-section">
                    <div class="section-title">Information in English</div>
                    <div class="section-content">
                        <h4>Origin & Ingredients</h4>
                        <p>Made from the pulp of the tamarind tree (Tamarindus indica), native to Sudan.</p>
                        <p><strong>Ingredients:</strong> Dried tamarind pulp, water, sugar/honey, and optional flavors like ginger or rose water.</p>
                        
                        <h4>Preparation Method</h4>
                        <ul>
                            <li>Soak tamarind in warm water for 1 hour</li>
                            <li>Strain the pulp through a fine sieve</li>
                            <li>Add cold water + sugar, then refrigerate</li>
                            <li>Serve with ice and fresh mint</li>
                        </ul>
                        
                        <h4>Additional Facts</h4>
                        <p>A popular Sudanese summer drink, known for digestive and cooling benefits.</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div id="karkade-modal" class="detail-modal karkade-theme">
        <div class="modal-content">
            <div class="modal-header">
                <button class="close-btn" onclick="closeModal('karkade')">&times;</button>
                <h2>KARKADE</h2>
                <h3 class="arabic">عصير الكركديه</h3>
            </div>
            <div class="modal-body">
                <div class="modal-image-container">
                    <img src="https://www.wellnesswarrior.org/wp-content/uploads/2025/05/KETO-Karkade-Iced-Hibiscus-Tea-Sudan-750x400.jpg" alt="Karkade Juice" class="modal-image">
                </div>
                <div class="content-section arabic-section">
                    <div class="section-title arabic">المعلومات بالعربية</div>
                    <div class="section-content">
                        <h4>الأصل والمكونات</h4>
                        <p>يُصنع من زهور الكركديه المجففة (Hibiscus sabdariffa).</p>
                        <p><strong>المكونات:</strong> كركديه مجفف، ماء، سكر، وعصير ليمون (اختياري).</p>
                        
                        <h4>طريقة التحضير</h4>
                        <ul>
                            <li>انقعي الكركديه في ماء مغلي لمدة 15-20 دقيقة</li>
                            <li>صفّي الزهور، ثم أضيفي السكر وعصير الليمون</li>
                            <li>برديه وقدميه مثلجًا</li>
                        </ul>
                        
                        <h4>معلومات إضافية</h4>
                        <p>مشروب شعبي في رمضان وفي المناسبات، يخفض ضغط الدم وغني بفيتامين C.</p>
                    </div>
                </div>
                <div class="content-section english-section">
                    <div class="section-title">Information in English</div>
                    <div class="section-content">
                        <h4>Origin & Ingredients</h4>
                        <p>Made from dried hibiscus flowers (Hibiscus sabdariffa).</p>
                        <p><strong>Ingredients:</strong> Dried hibiscus, water, sugar, and optional lemon juice.</p>
                        
                        <h4>Preparation Method</h4>
                        <ul>
                            <li>Steep hibiscus in boiling water for 15-20 mins</li>
                            <li>Strain, add sugar + lemon juice</li>
                            <li>Chill and serve over ice</li>
                        </ul>
                        
                        <h4>Additional Facts</h4>
                        <p>A festive drink, especially during Ramadan. Rich in antioxidants and may reduce hypertension.</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div id="hulu-marr-modal" class="detail-modal hulu-marr-theme">
        <div class="modal-content">
            <div class="modal-header">
                <button class="close-btn" onclick="closeModal('hulu-marr')">&times;</button>
                <h2>HULU MARR</h2>
                <h3 class="arabic">حلو مر</h3>
            </div>
            <div class="modal-body">
                <div class="modal-image-container">
                    <img src="https://vid.alarabiya.net/images/2024/03/08/84a97b40-cd62-4bf2-a061-063b64e6058b/84a97b40-cd62-4bf2-a061-063b64e6058b_16x9_1200x676.jpg" alt="Hulu Marr Juice" class="modal-image">
                </div>
                <div class="content-section arabic-section">
                    <div class="section-title arabic">المعلومات بالعربية</div>
                    <div class="section-content">
                        <h4>الأصل والمكونات</h4>
                        <p>حلوى سودانية تقليدية تجمع بين الحلو والحرّيف.</p>
                        <p><strong>المكونات:</strong> سمسم، فول سوداني، سكر، زنجبيل، وفلفل حار.</p>
                        
                        <h4>طريقة التحضير</h4>
                        <ul>
                            <li>حمّصي السمسم والفول السوداني</li>
                            <li>اخلطي المكونات مع السكر والزنجبيل</li>
                            <li>سخني الخليط حتى يتماسك، ثم قطعيه إلى مربعات</li>
                        </ul>
                        
                        <h4>معلومات إضافية</h4>
                        <p>تُقدم في المناسبات والأعراس، وتجمع بين الحلاوة والحرافة (طعم فريد).</p>
                    </div>
                </div>
                <div class="content-section english-section">
                    <div class="section-title">Information in English</div>
                    <div class="section-content">
                        <h4>Origin & Ingredients</h4>
                        <p>A traditional Sudanese sweet with a sweet-spicy taste.</p>
                        <p><strong>Ingredients:</strong> Sesame, peanuts, sugar, ginger, and chili.</p>
                        
                        <h4>Preparation Method</h4>
                        <ul>
                            <li>Roast sesame and peanuts</li>
                            <li>Mix with sugar + ginger</li>
                            <li>Heat until firm, then cut into squares</li>
                        </ul>
                        
                        <h4>Additional Facts</h4>
                        <p>Served at weddings and celebrations. Combines sweet and spicy flavors uniquely.</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div id="tabaldi-modal" class="detail-modal tabaldi-theme">
        <div class="modal-content">
            <div class="modal-header">
                <button class="close-btn" onclick="closeModal('tabaldi')">&times;</button>
                <h2>TABALDI (GONGOLAZE)</h2>
                <h3 class="arabic">التبلدي (قنقليز)</h3>
            </div>
            <div class="modal-body">
                <div class="modal-image-container">
                    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRxwDPBy3n0Ha4lfM1HVjHe_1hfHeTH3fnQzg&s" alt="Tabaldi Juice" class="modal-image">
                </div>
                <div class="content-section arabic-section">
                    <div class="section-title arabic">المعلومات بالعربية</div>
                    <div class="section-content">
                        <h4>الأصل والمكونات</h4>
                        <p>يُصنع من مسحوق ثمار شجرة التبلدي (Adansonia digitata).</p>
                        <p><strong>المكونات:</strong> مسحوق باوباب، ماء، سكر، وفانيليا (اختياري).</p>
                        
                        <h4>طريقة التحضير</h4>
                        <ul>
                            <li>اخلطي مسحوق التبلدي مع الماء البارد</li>
                            <li>أضيفي السكر وحركي جيدًا</li>
                            <li>قدّميه مثلجًا</li>
                        </ul>
                        
                        <h4>معلومات إضافية</h4>
                        <p>شجرة التبلدي مقدسة في بعض الثقافات السودانية، والعصير منعش ويُسمى أحيانًا "عصير القنقليز".</p>
                    </div>
                </div>
                <div class="content-section english-section">
                    <div class="section-title">Information in English</div>
                    <div class="section-content">
                        <h4>Origin & Ingredients</h4>
                        <p>Made from baobab fruit powder (Adansonia digitata).</p>
                        <p><strong>Ingredients:</strong> Baobab powder, water, sugar, and optional vanilla.</p>
                        
                        <h4>Preparation Method</h4>
                        <ul>
                            <li>Mix baobab powder with cold water</li>
                            <li>Add sugar and stir well</li>
                            <li>Serve chilled</li>
                        </ul>
                        
                        <h4>Additional Facts</h4>
                        <p>The baobab tree is culturally significant in Sudan. The drink is also called "Gongolaze".</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        function openModal(juiceId) {
            const modal = document.getElementById(juiceId + '-modal');
            modal.classList.add('active');
            document.body.style.overflow = 'hidden';
        }

        function closeModal(juiceId) {
            const modal = document.getElementById(juiceId + '-modal');
            modal.classList.remove('active');
            document.body.style.overflow = 'auto';
        }

        // Close modal when clicking outside
        document.addEventListener('click', function(e) {
            if (e.target.classList.contains('detail-modal')) {
                e.target.classList.remove('active');
                document.body.style.overflow = 'auto';
            }
        });

        // Close modal with Escape key
        document.addEventListener('keydown', function(e) {
            if (e.key === 'Escape') {
                const activeModal = document.querySelector('.detail-modal.active');
                if (activeModal) {
                    activeModal.classList.remove('active');
                    document.body.style.overflow = 'auto';
                }
            }
        });
    </script>
</body>
</html>
