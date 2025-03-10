
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Сайт Игры</title>
    <style>
        /* Общие стили */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
            transition: background-color 0.3s, color 0.3s;
            background-image: url('images/background.png');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
        }
        body.dark-mode {
            background-color: #333;
            color: #f4f4f4;
        }
        header {
            text-align: center;
            padding: 20px;
            background-color: rgba(0, 0, 0, 0.8);
            color: white;
        }
        #logo {
            width: 200px;
            cursor: pointer;
            transition: transform 0.3s;
        }
        #logo:hover {
            transform: scale(1.05);
        }
        nav {
            margin: 20px 0;
            display: flex;
            justify-content: center;
        }
        nav img {
            width: 50px;
            margin: 0 10px;
            cursor: pointer;
            transition: transform 0.3s;
            opacity: 0.7;
        }
        nav img:hover {
            transform: scale(1.1);
            opacity: 1;
        }
        main {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 20px;
            background-color: rgba(0, 0, 0, 0.7);
            border-radius: 10px;
            color: white;
            margin: 20px auto;
            max-width: 800px;
        }
        h1, h2 {
            margin-bottom: 20px;
        }
        .screenshot {
            width: 100%;
            max-width: 500px;
            margin-bottom: 10px;
            border-radius: 5px;
            display: none;
        }
        .screenshot.show {
            display: block;
        }
        #news {
            margin-top: 30px;
            width: 100%;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 5px;
        }
        .news-item {
            margin-bottom: 20px;
            padding: 15px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 5px;
        }
        .comments-section {
            margin-top: 15px;
        }
        .comment {
            padding: 10px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 5px;
            margin-bottom: 5px;
        }
        footer {
            text-align: center;
            padding: 10px;
            background-color: rgba(0, 0, 0, 0.8);
            color: white;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            z-index: 1;
        }
        .modal-content {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background-color: #008000;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        .close {
            position: absolute;
            top: 0;
            right: 0;
            padding: 10px;
            cursor: pointer;
        }
        #theme-toggle {
            background-color: #4CAF50;
            border: none;
            color: white;
                        padding: 10px 20px;
            text-align: center;
            text-decoration: none;
            display: inline-block;
            font-size: 16px;
            margin: 4px 2px;
            cursor: pointer;
            border-radius: 5px;
            position: absolute;
            top: 15px;
            right: 20px;
        }
        button {
            transition: background 0.3s ease-in-out;
        }
        button:hover {
            background: #ff6600;
            color: white;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        .modal {
            animation: fadeIn 0.5s ease-in-out;
        }
    </style>
</head>
<body>
    <header>
        <img id="logo" src="images/logo.jpg" alt="Логотип игры">
        <nav>
            <img src="images/icon-menu1.jpg" alt="Иконка 1" onclick="showImages('category1')">
            <img src="images/icon-menu2.jpg" alt="Иконка 2" onclick="showImages('category2')">
            <img src="images/icon-menu-all.jpg" alt="Показать все" onclick="showImages('all')">
        </nav>
        <button id="theme-toggle">Сменить тему</button>
    </header>
    <main>
        <h1>Добро пожаловать в игру!</h1>
        <h2>Скриншоты игры</h2>
        <img class="screenshot category1" src="images/screenshot1.jpg" alt="Скриншот 1">
        <img class="screenshot category2" src="images/screenshot2.jpg" alt="Скриншот 2">
        <img class="screenshot category2" src="images/screenshot3.jpg" alt="Скриншот 3">
        <section id="news">
            <h2>Новости</h2>
            <div class="news-item">
                <h3>Обновление системы</h3>
                <p>Выпущено новое обновление с улучшениями и исправлениями.</p>
                <div class="comments-section" id="comment-section">
                    <h4>Комментарии:</h4>
                    <div class="comment">Отличная обнова! Спасибо разработчикам!</div>
                    <div class="comment">Есть небольшие баги, но в целом хорошо.</div>
                </div>
                <div class="new-comment">
                    <textarea id="comment-input" rows="4" cols="20" placeholder="Введите ваш комментарий"></textarea><br />
                    <button id="submit-comment">Отправить</button>
                </div>
            </div>
            <div class="news-item">
                <h3>Турнир по игре</h3>
                <p>Объявляем о начале турнира с ценными призами! Регистрация открыта до 20.12.2023.</p>
                <div class="comments-section">
                    <h4>Комментарии:</h4>
                    <div class="comment">Участвую!</div>
                    <div class="comment-form">
                        <textarea id="commentText2" placeholder="Оставить комментарий"></textarea>
                        <button onclick="addComment(2)">Отправить</button>
                    </div>
                </div>
            </div>
        </section>
        <h6>О нашей игре</h6>
        <p>Это увлекательная компьютерная игра в жанре RPG с открытым миром...</p>
        <img src="images/game_image.jpg" alt="Изображение из игры">
        <!-- Модальное окно -->
        <div id="myModal" class="modal">
            <div class="modal-content">
                <span class="close" onclick="closeModal()">&times;</span>
                <p>Добро пожаловать на сайт нашей игры!</p>
            </div>
        </div>
    </main>
    <footer>
        <p>&copy; 2023 Сайт Игры. Все права защищены.</p>
    </footer>
    <script>
        document.getElementById('submit-comment').addEventListener('click', function() {
            const commentInput = document.getElementById('comment-input');
            const newCommentText = commentInput.value.trim();
            if (newCommentText) {
                const newComment = document.createElement('div');
                newComment.className = 'comment';
                newComment.textContent = newCommentText;
                const commentSection = document.getElementById('comment-section');
                commentSection.appendChild(newComment);
                commentInput.value = ''; // Очищаем поле ввода
            }
        });
        // Функция для переключения тем
        document.getElementById('theme-toggle').addEventListener('click', function() {
            document.body.classList.toggle('dark-mode');
        });
        // Функция для показа изображений по категориям
        function showImages(category) {
            const screenshots = document.querySelectorAll('.screenshot');
            screenshots.forEach(img => {
                img.classList.remove('show');
                if (category === 'all' || img.classList.contains(category)) {
                    img.classList.add('show');
                }
            });
        }
        // Функция для закрытия модального окна
        function closeModal() {
            document.getElementById('myModal').style.display = 'none';
        }
        // Открытие модального окна при загрузке страницы
        window.onload = function() {
            document.getElementById('myModal').style.display = 'block';
        };
    </script>
</body>
</html>

