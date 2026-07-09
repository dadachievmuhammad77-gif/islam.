<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>СтройДом - Строительство под ключ</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Arial', sans-serif;
            background: #0a0a0a;
            color: #fff;
            line-height: 1.6;
        }
        
        /* Фиксированная рекламная панель слева */
        .ad-sidebar-fixed {
            position: fixed;
            left: 0;
            top: 0;
            width: 80px;
            height: 100vh;
            background: linear-gradient(180deg, #cc5500 0%, #ff6600 100%);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            padding: 20px 0;
        }
        
        .ad-sidebar-fixed .ad-item {
            writing-mode: vertical-rl;
            text-orientation: mixed;
            margin: 20px 0;
            font-weight: bold;
            font-size: 0.9em;
            cursor: pointer;
            transition: all 0.3s;
            padding: 10px;
            border-radius: 5px;
        }
        
        .ad-sidebar-fixed .ad-item:hover {
            background: rgba(255,255,255,0.2);
            transform: scale(1.1);
        }
        
        .main-wrapper {
            margin-left: 80px;
        }
        
        header {
            background: #1a1a1a;
            padding: 30px 0;
            border-bottom: 3px solid #ff6600;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 40px;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo h1 {
            font-size: 3em;
            color: #ff6600;
        }
        
        .header-phone {
            font-size: 1.8em;
            font-weight: bold;
        }
        
        /* Главный баннер */
        .hero-banner {
            background: linear-gradient(135deg, #cc5500 0%, #ff6600 100%);
            padding: 60px 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .hero-banner::before {
            content: '🏗️';
            position: absolute;
            font-size: 200px;
            opacity: 0.1;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        
        .hero-banner h2 {
            font-size: 3em;
            margin-bottom: 20px;
            position: relative;
            z-index: 1;
        }
        
        .hero-banner p {
            font-size: 1.5em;
            margin-bottom: 30px;
            position: relative;
            z-index: 1;
        }
        
        /* Рекламные блоки */
        .ad-section {
            padding: 60px 0;
            background: #111;
        }
        
        .ad-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }
        
        .ad-card {
            background: linear-gradient(135deg, #1a1a1a 0%, #2a2a2a 100%);
            border: 3px solid #ff6600;
            border-radius: 20px;
            padding: 40px 30px;
            text-align: center;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }
        
        .ad-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,102,0,0.1), transparent);
            transform: rotate(45deg);
            transition: all 0.5s;
        }
        
        .ad-card:hover::before {
            left: 100%;
        }
        
        .ad-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 20px 50px rgba(255, 102, 0, 0.4);
        }
        
        .ad-card .badge {
            background: #ff0000;
            color: white;
            padding: 5px 15px;
            border-radius: 20px;
            display: inline-block;
            font-weight: bold;
            margin-bottom: 15px;
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.1); }
        }
        
        .ad-card .icon {
            font-size: 4em;
            margin-bottom: 20px;
        }
        
        .ad-card h3 {
            font-size: 1.8em;
            margin-bottom: 15px;
            color: #ff6600;
        }
        
        .ad-card .price {
            font-size: 2.5em;
            font-weight: bold;
            color: #ff6600;
            margin: 15px 0;
        }
        
        .ad-card p {
            color: #aaa;
            margin-bottom: 20px;
        }
        
        .btn-whatsapp {
            display: inline-block;
            background: #25D366;
            color: white;
            padding: 15px 30px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s;
        }
        
        .btn-whatsapp:hover {
            transform: scale(1.1);
            box-shadow: 0 10px 30px rgba(37, 211, 102, 0.5);
        }
        
        /* Услуги */
        .services {
            padding: 80px 0;
            background: #0a0a0a;
        }
        
        .section-title {
            text-align: center;
            font-size: 3em;
            margin-bottom: 50px;
            color: #ff6600;
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 40px;
        }
        
        .service-item {
            background: #1a1a1a;
            border-radius: 15px;
            overflow: hidden;
            transition: all 0.3s;
        }
        
        .service-item:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(255, 102, 0, 0.3);
        }
        
        .service-item img {
            width: 100%;
            height: 250px;
            object-fit: cover;
        }
        
        .service-item-content {
            padding: 30px;
        }
        
        .service-item-content h3 {
            color: #ff6600;
            font-size: 2em;
            margin-bottom: 15px;
        }
        
        .service-item-content p {
            color: #999;
            margin-bottom: 20px;
            line-height: 1.8;
        }
        
        .service-price {
            font-size: 1.5em;
            color: #ff6600;
            font-weight: bold;
            margin-bottom: 15px;
        }
        
        /* WhatsApp кнопка */
        .whatsapp-float {
            position: fixed;
            bottom: 40px;
            right: 40px;
            background: #25D366;
            color: white;
            width: 70px;
            height: 70px;
            border-radius: 50%;
            text-align: center;
            font-size: 35px;
            line-height: 70px;
            box-shadow: 0 5px 20px rgba(0,0,0,0.4);
            z-index: 999;
            transition: all 0.3s;
            text-decoration: none;
        }
        
        .whatsapp-float:hover {
            transform: scale(1.15) rotate(10deg);
            box-shadow: 0 8px 30px rgba(37, 211, 102, 0.6);
        }
        
        footer {
            background: #1a1a1a;
            padding: 40px 0;
            text-align: center;
            border-top: 3px solid #ff6600;
        }
        
        @media (max-width: 768px) {
            .ad-sidebar-fixed {
                display: none;
            }
            
            .main-wrapper {
                margin-left: 0;
            }
            
            .container {
                padding: 0 20px;
            }
        }
    </style>
</head>
<body>
    <!-- Фиксированная боковая реклама -->
    <div class="ad-sidebar-fixed">
        <div class="ad-item" onclick="window.location.href='https://wa.me/79674474787'">🏠 КРЫША</div>
        <div class="ad-item" onclick="window.location.href='https://wa.me/79674474787'">️ ФУНДАМЕНТ</div>
        <div class="ad-item" onclick="window.location.href='https://wa.me/79674474787'">🎨 ФАСАД</div>
        <div class="ad-item" onclick="window.location.href='https://wa.me/79674474787'">🔨 РЕМОНТ</div>
    </div>
    
    <div class="main-wrapper">
        <header>
            <div class="container">
                <div class="header-content">
                    <div class="logo">
                        <h1>🏗️ СтройДом</h1>
                    </div>
                    <div class="header-phone">
                        📞 8 (967) 447-47-87
                    </div>
                </div>
            </div>
        </header>
        
        <section class="hero-banner">
            <div class="container">
                <h2>Строительство вашей мечты</h2>
                <p>От фундамента до крыши - всё под ключ с гарантией качества</p>
                <a href="https://wa.me/79674474787" class="btn-whatsapp" target="_blank" style="font-size: 1.3em; padding: 20px 50px;">
                    💬 Получить консультацию
                </a>
            </div>
        </section>
        
        <section class="ad-section">
            <div class="container">
                <div class="ad-grid">
                    <div class="ad-card">
                        <div class="badge">HOT 🔥</div>
                        <div class="icon"></div>
                        <h3>Крыша под ключ</h3>
                        <div class="price">1500₽/м²</div>
                        <p>Монтаж кровли любой сложности. Водосток в подарок!</p>
                        <a href="https://wa.me/79674474787?text=Заказать крышу" class="btn-whatsapp" target="_blank">Заказать</a>
                    </div>
                    
                    <div class="ad-card">
                        <div class="badge">-20%</div>
                        <div class="icon">🏗️</div>
                        <h3>Фундамент</h3>
                        <div class="price">5000₽/м³</div>
                        <p>Все виды фундамента. Армирование и бетонирование.</p>
                        <a href="https://wa.me/79674474787?text=Заказать фундамент" class="btn-whatsapp" target="_blank">Заказать</a>
                    </div>
                    
                    <div class="ad-card">
                        <div class="badge">NEW ✨</div>
                        <div class="icon">🎨</div>
                        <h3>Фасадные работы</h3>
                        <div class="price">800₽/м²</div>
                        <p>Штукатурка, покраска, утепление. Преобразим ваш дом!</p>
                        <a href="https://wa.me/79674474787?text=Заказать фасад" class="btn-whatsapp" target="_blank">Заказать</a>
                    </div>
                    
                    <div class="ad-card">
                        <div class="badge">0% 📅</div>
                        <div class="icon">🔨</div>
                        <h3>Внутренняя отделка</h3>
                        <div class="price">3000₽/м²</div>
                        <p>Ремонт под ключ. Рассрочка без процентов на 6 месяцев.</p>
                        <a href="https://wa.me/79674474787?text=Заказать отделку" class="btn-whatsapp" target="_blank">Заказать</a>
                    </div>
                </div>
            </div>
        </section>
        
        <section class="services">
            <div class="container">
                <h2 class="section-title">Наши услуги</h2>
                
                <div class="services-grid">
                    <div class="service-item">
                        <img src="roof-construction.jpg" alt="Кровля">
                        <div class="service-item-content">
                            <h3>Кровельные работы</h3>
                            <p>Профессиональный монтаж и ремонт кровли. Металлочерепица, профнастил, мягкая кровля, ондулин. Установка водосточных систем.</p>
                            <div class="service-price">от 1500₽/м²</div>
                            <a href="https://wa.me/79674474787?text=Интересуют кровельные работы" class="btn-whatsapp" target="_blank">Заказать</a>
                        </div>
                    </div>
                    
                    <div class="service-item">
                        <img src="foundation-work.jpg" alt="Фундамент">
                        <div class="service-item-content">
                            <h3>Фундамент</h3>
                            <p>Ленточный, плитный, свайный фундамент. Армирование, бетонирование, гидроизоляция. Работаем по СНиП.</p>
                            <div class="service-price">от 5000₽/м³</div>
                            <a href="https://wa.me/79674474787?text=Интересует фундамент" class="btn-whatsapp" target="_blank">Заказать</a>
                        </div>
                    </div>
                    
                    <div class="service-item">
                        <img src="facade-work.jpg" alt="Фасад">
                        <div class="service-item-content">
                            <h3>Фасад</h3>
                            <p>Штукатурка и покраска фасада. Утепление пенопластом и минватой. Монтаж сайдинга и фасадных панелей.</p>
                            <div class="service-price">от 800₽/м²</div>
                            <a href="https://wa.me/79674474787?text=Интересуют фасадные работы" class="btn-whatsapp" target="_blank">Заказать</a>
                        </div>
                    </div>
                    
                    <div class="service-item">
                        <img src="interior-renovation.jpg" alt="Отделка">
                        <div class="service-item-content">
                            <h3>Отделка помещений</h3>
                            <p>Штукатурка, шпаклевка, гипсокартон. Укладка плитки, ламината, линолеума. Покраска, поклейка обоев.</p>
                            <div class="service-price">от 3000₽/м²</div>
                            <a href="https://wa.me/79674474787?text=Интересует отделка" class="btn-whatsapp" target="_blank">Заказать</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <footer>
            <div class="container">
                <h2 style="color: #ff6600; margin-bottom: 20px;">🏗️ СтройДом</h2>
                <p style="font-size: 1.3em; margin-bottom: 10px;">📞 8 (967) 447-47-87</p>
                <p style="color: #666;">&copy; 2026 Все права защищены</p>
                <p style="color: #ff6600; margin-top: 10px;">Работаем ежедневно с 8:00 до 20:00</p>
            </div>
        </footer>
    </div>
    
    <a href="https://wa.me/79674474787" class="whatsapp-float" target="_blank" title="Написать в WhatsApp">
        💬
    </a>
</body>
</html>
