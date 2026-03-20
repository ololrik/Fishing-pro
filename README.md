<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ФишингПро — Помощник Рыболова</title>
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #2980b9;
            --accent: #27ae60;
            --light: #ecf0f1;
            --danger: #e74c3c;
        }

        body { font-family: 'Segoe UI', sans-serif; margin: 0; background: #f4f7f6; color: #333; scroll-behavior: smooth; }
        header { background: var(--primary); color: white; padding: 15px; text-align: center; position: sticky; top: 0; z-index: 100; }
        
        nav { background: #34495e; padding: 10px; display: flex; justify-content: center; flex-wrap: wrap; gap: 10px; }
        nav a { color: white; text-decoration: none; font-size: 0.9rem; padding: 5px 10px; border-radius: 5px; }
        nav a:hover { background: var(--secondary); }

        .container { max-width: 900px; margin: 20px auto; padding: 0 15px; }
        section { margin-bottom: 40px; background: white; padding: 20px; border-radius: 15px; box-shadow: 0 4px 10px rgba(0,0,0,0.05); }
        h2 { color: var(--primary); border-bottom: 2px solid var(--light); padding-bottom: 10px; text-align: center; }

        /* Энциклопедия */
        .fish-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 15px; }
        .fish-card { border: 1px solid #eee; padding: 15px; border-radius: 10px; background: #fafafa; }
        .tag { background: #d1e9ff; color: #0277bd; padding: 2px 8px; border-radius: 4px; font-size: 0.8rem; margin: 2px; display: inline-block; }

        /* Календарь */
        .table-wrapper { overflow-x: auto; }
        table { width: 100%; border-collapse: collapse; min-width: 400px; }
        th, td { padding: 12px; text-align: left; border-bottom: 1px solid #eee; }
        th { background: var(--secondary); color: white; }

        /* Чек-лист */
        .check-group { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
        .check-item { background: #f9f9f9; padding: 10px; border-radius: 8px; cursor: pointer; display: flex; align-items: center; }
        .check-item input { margin-right: 10px; }

        /* Форум */
        .forum-form input, .forum-form textarea { width: 100%; padding: 10px; margin-bottom: 10px; border: 1px solid #ddd; border-radius: 8px; box-sizing: border-box; }
        button { background: var(--accent); color: white; border: none; padding: 10px 20px; border-radius: 8px; cursor: pointer; width: 100%; font-weight: bold; }
        .btn-clear { background: var(--danger); margin-top: 10px; }
        .post-item { background: #fdfdfd; padding: 15px; border-radius: 10px; border-left: 5px solid var(--accent); margin-top: 15px; box-shadow: 0 2px 5px rgba(0,0,0,0.05); }
        .post-item img { max-width: 100%; border-radius: 8px; margin-top: 10px; }

        /* Галерея */
        .gallery { display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr)); gap: 10px; }
        .gallery img { width: 100%; height: 150px; object-fit: cover; border-radius: 10px; }

        @media (max-width: 600px) { .check-group { grid-template-columns: 1fr; } }
    </style>
</head>
<body>

<header>
    <h1>🎣 ФишингПро</h1>
    <p>Все для успешной рыбалки</p>
</header>

<nav>
    <a href="#info">Рыбы</a>
    <a href="#calendar">Календарь</a>
    <a href="#checklist">Сборы</a>
    <a href="#forum">Форум</a>
</nav>

<div class="container">

    <!-- Энциклопедия -->
    <section id="info">
        <h2>Справочник наживок</h2>
        <div class="fish-grid">
            <div class="fish-card">
                <h3>🐟 Щука</h3>
                <p>Ловить на: <span class="tag">Живец</span> <span class="tag">Блесна</span> <span class="tag">Воблер</span></p>
                <small>Ищи в корягах и камышах.</small>
            </div>
            <div class="fish-card">
                <h3>🐟 Карп</h3>
                <p>Ловить на: <span class="tag">Кукуруза</span> <span class="tag">Бойлы</span> <span class="tag">Червь</span></p>
                <small>Любит сладкие прикормки.</small>
            </div>
        </div>
    </section>

    <!-- Календарь -->
    <section id="calendar">
        <h2>Прогноз активности</h2>
        <div class="table-wrapper">
            <table>
                <tr><th>Рыба</th><th>Весна</th><th>Лето</th><th>Осень</th></tr>
                <tr><td>Щука</td><td>🔥 Жор</td><td>✅ Утро</td><td>🔥 Жор</td></tr>
                <tr><td>Карп</td><td>✅ Средне</td><td>🔥 Пик</td><td>✅ Слабо</td></tr>
                <tr><td>Окунь</td><td>🔥 Активен</td><td>✅ Средне</td><td>🔥 Активен</td></tr>
            </table>
        </div>
    </section>

    <!-- Чек-лист -->
    <section id="checklist">
        <h2>Сборы на водоем</h2>
        <div class="check-group">
            <label class="check-item"><input type="checkbox"> Удочки / Катушки</label>
            <label class="check-item"><input type="checkbox"> Наживка / Прикорм</label>
            <label class="check-item"><input type="checkbox"> Садок / Подсак</label>
            <label class="check-item"><input type="checkbox"> Стул / Термос</label>
            <label class="check-item"><input type="checkbox"> Нож / Фонарик</label>
            <label class="check-item"><input type="checkbox"> Средство от комаров</label>
        </div>
        <button onclick="resetCheck()" style="background:#95a5a6; height: 30px; padding:0; margin-top:10px;">Сбросить</button>
    </section>

    <!-- Галерея -->
    <section>
        <h2>Галерея трофеев</h2>
        <div class="gallery">
            <img src="https://images.unsplash.com" alt="fish">
            <img src="https://images.unsplash.com" alt="fish">
            <img src="https://images.unsplash.com" alt="fish">
        </div>
    </section>

    <!-- Форум -->
    <section id="forum">
        <h2>Форум рыбаков</h2>
        <div class="forum-form">
            <input type="text" id="nick" placeholder="Твой ник">
            <textarea id="msg" placeholder="Напиши отчет о рыбалке..."></textarea>
            <input type="text" id="imgUrl" placeholder="Ссылка на фото (если есть)">
            <button onclick="addPost()">Опубликовать</button>
            <button onclick="clearPosts()" class="btn-clear">Удалить все сообщения</button>
        </div>
        <div id="postsBox"></div>
    </section>

</div>

<footer style="text-align: center; padding: 20px; color: #888;">
    <p>&copy; 2024 ФишингПро. Ни хвоста, ни чешуи!</p>
</footer>

<script>
    // Логика форума
    function renderPosts() {
        const posts = JSON.parse(localStorage.getItem('fish_posts')) || [];
        document.getElementById('postsBox').innerHTML = posts.map(p => `
            <div class="post-item">
                <strong>${p.author}</strong> <small style="color:#999">${p.date}</small>
                <p>${p.text}</p>
                ${p.img ? `<img src="${p.img}">` : ''}
            </div>
        `).join('');
    }

    function addPost() {
        const nick = document.getElementById('nick').value || 'Аноним';
        const msg = document.getElementById('msg').value;
        const img = document.getElementById('imgUrl').value;

        if(!msg) return alert("Введите сообщение!");

        const posts = JSON.parse(localStorage.getItem('fish_posts')) || [];
        posts.unshift({ author: nick, text: msg, img: img, date: new Date().toLocaleDateString() });
        localStorage.setItem('fish_posts', JSON.stringify(posts));
        
        document.getElementById('msg').value = '';
        document.getElementById('imgUrl').value = '';
        renderPosts();
    }

    function clearPosts() {
        if(confirm("Удалить всё?")) {
            localStorage.removeItem('fish_posts');
            renderPosts();
        }
    }

    function resetCheck() {
        document.querySelectorAll('#checklist input').forEach(c => c.checked = false);
    }

    // Запуск при загрузке
    renderPosts();
</script>

</body>
</html>
