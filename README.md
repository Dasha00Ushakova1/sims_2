<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Сайт Игры</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <img id="logo" src="images/logo.jpg" alt="Логотип игры">
        <nav>
            <img src="images/icon1.png" alt="Иконка 1" onclick="showImages('category1')">
            <img src="images/icon2.png" alt="Иконка 2" onclick="showImages('category2')">
            <img src="images/icon-all.png" alt="Показать все" onclick="showImages('all')">
        </nav>
        <button id="theme-toggle">Сменить тему</button>
    </header>
    <main>
        <h1>Добро пожаловать в игру!</h1>
        <h2>Скриншоты игры</h2>
        <div class="gallery">
            <img class="screenshot category1" src="images/screenshot1.jpg" alt="Скриншот 1">
            <img class="screenshot category2" src="images/screenshot2.jpg" alt="Скриншот 2">
            <img class="screenshot category2" src="images/screenshot3.jpg" alt="Скриншот 3">
            <img class="screenshot category1" src="images/screenshot4.jpg" alt="Скриншот 4">
        </div>
        <section id="news">
            <h2>Новости</h2>
            <div class="news-item">
                <h3>Обновление 1.0</h3>
                <p>Вышло новое обновление с улучшениями графики и новыми уровнями!</p>
                <div class="comments-section" id="comments-section">
                    <h4>Комментарии:</h4>
                    <!-- Комментарии будут добавляться сюда -->
                </div>
                <form class="comment-form" onsubmit="addComment(event)">
                    <input type="text" id="comment-name" placeholder="Ваше имя" required>
                    <textarea id="comment-text" placeholder="Ваш комментарий" required></textarea>
                    <button type="submit">Отправить</button>
                </form>
            </div>
        </section>
    </main>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
    color: #333;
    transition: background-color 0.3s, color 0.3s;
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

nav {
    margin: 20px 0;
    display: flex;
    justify-content: center;
}

nav img {
    width: 50px;
    margin: 0 10px;
    cursor: pointer;
    opacity: 0.7;
}

nav img:hover {
    opacity: 1;
}

main {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px;
}

.gallery {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
}

.screenshot {
    width: 100%;
    cursor: pointer;
    border-radius: 5px;
}

.comment-form {
    margin-top: 10px;
}

.comment-form input,
.comment-form textarea {
    width: 95%;
    padding: 5px;
    margin-bottom: 5px;
    border-radius: 3px;
    border: 1px solid #ccc;
}

.comment-form button {
    background-color: #5cb85c;
    color: white;
    padding: 8px 12px;
    border: none;
    border-radius: 3px;
    cursor: pointer;
}

.comments-section {
