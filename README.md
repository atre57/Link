<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HAPPY MARKET | Taze, Hesaplı, Kapınızda</title>
    
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons+Sharp" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;800&family=Poppins:wght@300;400;500;600&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --primary: #e63946;    /* Market Kırmızısı */
            --secondary: #2a9d8f;  /* Taze Yeşil */
            --dark: #1d3557;
            --light: #f1faee;
            --white: #ffffff;
            --gray: #8d99ae;
            --shadow: 0 10px 30px rgba(0,0,0,0.1);
            --transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
        }

        * { margin: 0; padding: 0; box-sizing: border-box; outline: none; border: none; text-decoration: none; list-style: none; }
        body { font-family: 'Poppins', sans-serif; background: #f8f9fa; color: var(--dark); overflow-x: hidden; }

        /* --- NAVIGASYON --- */
        nav {
            background: var(--white);
            height: 80px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 7%;
            position: fixed;
            top: 0; width: 100%;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.05);
        }

        .logo { font-family: 'Montserrat', sans-serif; font-weight: 800; font-size: 1.8rem; color: var(--primary); display: flex; align-items: center; gap: 5px; }
        .logo span { color: var(--secondary); }

        .nav-links { display: flex; gap: 2rem; }
        .nav-links a { color: var(--dark); font-weight: 500; font-size: 0.95rem; cursor: pointer; }
        .nav-links a:hover, .nav-links a.active { color: var(--primary); }

        .nav-icons { display: flex; gap: 1.5rem; align-items: center; }
        .cart-icon { position: relative; cursor: pointer; }
        .cart-count { 
            position: absolute; top: -8px; right: -8px; 
            background: var(--primary); color: white; 
            font-size: 0.7rem; padding: 2px 6px; border-radius: 50%; 
            font-weight: bold;
        }

        /* --- SAYFA YAPISI --- */
        .page { display: none; padding-top: 100px; min-height: 100vh; animation: fadeIn 0.5s ease; }
        .page.active { display: block; }

        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

        /* --- ANA SAYFA (HERO) --- */
        .hero {
            height: 500px;
            background: linear-gradient(rgba(0,0,0,0.4), rgba(0,0,0,0.4)), url('https://images.unsplash.com/photo-1542838132-92c53300491e?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover; background-position: center;
            display: flex; flex-direction: column; align-items: center; justify-content: center;
            text-align: center; color: white; border-radius: 0 0 50px 50px; margin: 0 2%;
        }
        .hero h1 { font-size: 3.5rem; font-family: 'Montserrat', sans-serif; margin-bottom: 1rem; }
        .hero p { font-size: 1.2rem; margin-bottom: 2rem; opacity: 0.9; }
        .btn-primary { 
            background: var(--primary); color: white; padding: 15px 40px; 
            border-radius: 30px; font-weight: 600; cursor: pointer; transition: var(--transition);
        }
        .btn-primary:hover { transform: scale(1.05); background: #c32f3a; }

        /* --- KATEGORİLER --- */
        .section-title { text-align: center; margin: 4rem 0 2rem; font-family: 'Montserrat', sans-serif; }
        .categories-grid {
            display: grid; grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1.5rem; padding: 0 7%;
        }
        .cat-card {
            background: white; padding: 20px; border-radius: 20px; text-align: center;
            cursor: pointer; transition: var(--transition); box-shadow: var(--shadow);
        }
        .cat-card:hover { background: var(--secondary); color: white; transform: translateY(-5px); }
        .cat-card span { font-size: 3rem; margin-bottom: 10px; display: block; }

        /* --- ÜRÜNLER SAYFASI --- */
        .filter-bar { display: flex; justify-content: center; gap: 1rem; margin-bottom: 2rem; flex-wrap: wrap; }
        .filter-btn { padding: 8px 20px; border-radius: 20px; background: white; cursor: pointer; border: 1px solid #ddd; }
        .filter-btn.active { background: var(--primary); color: white; border-color: var(--primary); }

        .products-container {
            display: grid; grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 2rem; padding: 0 7% 4rem;
        }
        .product-card {
            background: white; border-radius: 20px; overflow: hidden;
            box-shadow: var(--shadow); transition: var(--transition);
            position: relative;
        }
        .product-card:hover { transform: translateY(-10px); }
        .product-img { width: 100%; height: 200px; object-fit: cover; }
        .product-info { padding: 1.5rem; }
        .product-cat { font-size: 0.75rem; color: var(--gray); text-transform: uppercase; }
        .product-title { font-weight: 600; margin: 5px 0; }
        .product-price { font-size: 1.2rem; font-weight: 800; color: var(--secondary); }
        .add-btn { 
            width: 40px; height: 40px; background: var(--primary); color: white;
            border-radius: 50%; position: absolute; bottom: 1.5rem; right: 1.5rem;
            display: flex; align-items: center; justify-content: center; cursor: pointer;
        }

        /* --- SEPET SAYFASI --- */
        .cart-wrapper { padding: 0 7%; display: grid; grid-template-columns: 2fr 1fr; gap: 2rem; }
        .cart-items { background: white; border-radius: 20px; padding: 2rem; box-shadow: var(--shadow); }
        .cart-item { 
            display: flex; align-items: center; justify-content: space-between; 
            padding: 1rem 0; border-bottom: 1px solid #eee; 
        }
        .summary { background: white; border-radius: 20px; padding: 2rem; box-shadow: var(--shadow); height: fit-content; }
        .summary h3 { margin-bottom: 1.5rem; }
        .summary-row { display: flex; justify-content: space-between; margin-bottom: 10px; }
        .total-row { border-top: 2px solid #eee; padding-top: 10px; font-weight: 800; font-size: 1.2rem; }

        /* --- FOOTER --- */
        footer { background: var(--dark); color: white; padding: 4rem 7% 2rem; margin-top: 4rem; }
        .footer-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 3rem; }
        .footer-col h4 { margin-bottom: 1.5rem; font-family: 'Montserrat', sans-serif; }
        .footer-bottom { text-align: center; margin-top: 3rem; padding-top: 2rem; border-top: 1px solid rgba(255,255,255,0.1); font-size: 0.8rem; color: var(--gray); }

        /* Mobil */
        @media (max-width: 768px) {
            .nav-links { display: none; }
            .hero h1 { font-size: 2.2rem; }
            .cart-wrapper { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>

    <nav>
        <div class="logo">HAPPY<span>CENTER</span></div>
        <div class="nav-links">
            <a onclick="showPage('home')" id="link-home" class="active">Ana Sayfa</a>
            <a onclick="showPage('products')" id="link-products">Ürünler</a>
            <a onclick="showPage('about')" id="link-about">Kurumsal</a>
            <a onclick="showPage('contact')" id="link-contact">İletişim</a>
        </div>
        <div class="nav-icons">
            <span class="material-icons-sharp" style="cursor:pointer">search</span>
            <span class="material-icons-sharp" style="cursor:pointer">person</span>
            <div class="cart-icon" onclick="showPage('cart')">
                <span class="material-icons-sharp">shopping_basket</span>
                <div class="cart-count" id="cart-count">0</div>
            </div>
        </div>
    </nav>

    <div id="home" class="page active">
        <section class="hero">
            <h1>Taptaze Market Kapınızda</h1>
            <p>Seçili ürünlerde %40'a varan indirimleri kaçırmayın.</p>
            <div class="btn-primary" onclick="showPage('products')">Alışverişe Başla</div>
        </section>

        <h2 class="section-title">Popüler Kategoriler</h2>
        <div class="categories-grid">
            <div class="cat-card" onclick="filterProducts('meyve')">
                <span class="material-icons-sharp">apple</span>
                <p>Manav</p>
            </div>
            <div class="cat-card" onclick="filterProducts('et')">
                <span class="material-icons-sharp">set_meal</span>
                <p>Kasap</p>
            </div>
            <div class="cat-card" onclick="filterProducts('sut')">
                <span class="material-icons-sharp">egg</span>
                <p>Süt & Kahvaltı</p>
            </div>
            <div class="cat-card" onclick="filterProducts('icecek')">
                <span class="material-icons-sharp">local_cafe</span>
                <p>İçecek</p>
            </div>
        </div>
    </div>

    <div id="products" class="page">
        <h2 class="section-title">Tüm Ürünler</h2>
        <div class="filter-bar" id="filter-bar">
            <div class="filter-btn active" onclick="filterProducts('all')">Hepsi</div>
            <div class="filter-btn" onclick="filterProducts('meyve')">Manav</div>
            <div class="filter-btn" onclick="filterProducts('et')">Kasap</div>
            <div class="filter-btn" onclick="filterProducts('sut')">Süt & Kahvaltı</div>
            <div class="filter-btn" onclick="filterProducts('icecek')">İçecek</div>
        </div>
        <div class="products-container" id="product-list">
            </div>
    </div>

    <div id="cart" class="page">
        <h2 class="section-title">Alışveriş Sepetim</h2>
        <div class="cart-wrapper">
            <div class="cart-items" id="cart-items-list">
                </div>
            <div class="summary">
                <h3>Sipariş Özeti</h3>
                <div class="summary-row"><span>Ara Toplam</span><span id="subtotal">0.00 TL</span></div>
                <div class="summary-row"><span>KDV (%10)</span><span id="tax">0.00 TL</span></div>
                <div class="summary-row"><span>Teslimat</span><span style="color: var(--secondary);">Ücretsiz</span></div>
                <div class="summary-row total-row"><span>Toplam</span><span id="grand-total">0.00 TL</span></div>
                <button class="btn-primary" style="width:100%; margin-top:20px; border-radius:10px;">Ödemeye Geç</button>
            </div>
        </div>
    </div>

    <div id="about" class="page"><h2 class="section-title">Biz Kimiz?</h2><p style="text-align:center">1996'dan beri en taze ürünleri sunuyoruz...</p></div>
    <div id="contact" class="page"><h2 class="section-title">Bize Ulaşın</h2><p style="text-align:center">Destek Hattı: 444 0 000</p></div>

    <footer>
        <div class="footer-grid">
            <div class="footer-col">
                <div class="logo" style="color:white">HAPPY<span>CENTER</span></div>
                <p style="margin-top:15px; color:var(--gray); font-size:0.8rem">Gıda perakendeciliğinde güvenin adresi.</p>
            </div>
            <div class="footer-col">
                <h4>Hızlı Bağlantılar</h4>
                <p>Kampanyalar</p><p>Mağazalarımız</p><p>Kariyer</p>
            </div>
            <div class="footer-col">
                <h4>Sosyal Medya</h4>
                <div style="display:flex; gap:10px; margin-top:10px">
                    <span class="material-icons-sharp">facebook</span>
                    <span class="material-icons-sharp">camera_alt</span>
                </div>
            </div>
        </div>
        <div class="footer-bottom">
            &copy; 2026 Happy Center Dijital Dönüşüm Grubu. Tüm hakları saklıdır.
        </div>
    </footer>

    <script>
        // ÜRÜN VERİTABANI
        const products = [
            { id: 1, title: "Amasya Elması", price: 34.90, cat: "meyve", img: "https://images.unsplash.com/photo-1560806887-1e4cd0b6bcd6?w=400" },
            { id: 2, title: "Dana Kuşbaşı 500g", price: 285.00, cat: "et", img: "https://images.unsplash.com/photo-1607623814075-e512199b9274?w=400" },
            { id: 3, title: "Tam Yağlı Süt 1L", price: 29.50, cat: "sut", img: "https://images.unsplash.com/photo-1550583724-125581cc2532?w=400" },
            { id: 4, title: "Filtre Kahve 250g", price: 145.00, cat: "icecek", img: "https://images.unsplash.com/photo-1559056199-641a0ac8b55e?w=400" },
            { id: 5, title: "Muz Yerli (Kg)", price: 42.00, cat: "meyve", img: "https://images.unsplash.com/photo-1571771894821-ad9b58a32946?w=400" },
            { id: 6, title: "Tavuk Bağet", price: 95.00, cat: "et", img: "https://images.unsplash.com/photo-1587593810167-a84920ea0781?w=400" },
            { id: 7, title: "Süzme Peynir", price: 88.00, cat: "sut", img: "https://images.unsplash.com/photo-1552767059-ce182ead6c1b?w=400" },
            { id: 8, title: "Soğuk Çay Şeftali", price: 22.00, cat: "icecek", img: "https://images.unsplash.com/photo-1581006852262-e4307cf6283a?w=400" },
        ];

        let cart = [];

        // SAYFA YÖNETİMİ
        function showPage(pageId) {
            document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
            document.getElementById(pageId).classList.add('active');
            
            document.querySelectorAll('.nav-links a').forEach(a => a.classList.remove('active'));
            const link = document.getElementById('link-' + pageId);
            if(link) link.classList.add('active');

            window.scrollTo(0,0);
        }

        // ÜRÜNLERİ LİSTELE
        function displayProducts(filter = 'all') {
            const container = document.getElementById('product-list');
            container.innerHTML = "";
            
            const filtered = filter === 'all' ? products : products.filter(p => p.cat === filter);
            
            filtered.forEach(p => {
                container.innerHTML += `
                    <div class="product-card">
                        <img src="${p.img}" class="product-img">
                        <div class="product-info">
                            <p class="product-cat">${p.cat}</p>
                            <h3 class="product-title">${p.title}</h3>
                            <p class="product-price">${p.price.toFixed(2)} TL</p>
                        </div>
                        <div class="add-btn" onclick="addToCart(${p.id})">
                            <span class="material-icons-sharp">add</span>
                        </div>
                    </div>
                `;
            });
        }

        function filterProducts(cat) {
            displayProducts(cat);
            if(document.getElementById('products').style.display !== 'block') showPage('products');
            
            document.querySelectorAll('.filter-btn').forEach(btn => {
                btn.classList.remove('active');
                if(btn.innerText.toLowerCase().includes(cat) || (cat==='all' && btn.innerText==='Hepsi')) btn.classList.add('active');
            });
        }

        // SEPET SİSTEMİ
        function addToCart(id) {
            const product = products.find(p => p.id === id);
            cart.push(product);
            updateCart();
            
            // Küçük bir görsel geri bildirim
            const btn = event.currentTarget;
            btn.innerHTML = '<span class="material-icons-sharp">done</span>';
            btn.style.background = 'var(--secondary)';
            setTimeout(() => {
                btn.innerHTML = '<span class="material-icons-sharp">add</span>';
                btn.style.background = 'var(--primary)';
            }, 1000);
        }

        function updateCart() {
            document.getElementById('cart-count').innerText = cart.length;
            renderCartItems();
        }

        function renderCartItems() {
            const list = document.getElementById('cart-items-list');
            if(cart.length === 0) {
                list.innerHTML = "<p>Sepetiniz şu an boş.</p>";
            } else {
                list.innerHTML = "";
                cart.forEach((item, index) => {
                    list.innerHTML += `
                        <div class="cart-item">
                            <div style="display:flex; align-items:center; gap:1rem">
                                <img src="${item.img}" style="width:50px; height:50px; border-radius:10px; object-fit:cover">
                                <div>
                                    <h4 style="font-size:0.9rem">${item.title}</h4>
                                    <p style="color:var(--secondary); font-weight:bold">${item.price.toFixed(2)} TL</p>
                                </div>
                            </div>
                            <span class="material-icons-sharp" style="color:var(--gray); cursor:pointer" onclick="removeFromCart(${index})">delete</span>
                        </div>
                    `;
                });
            }
            calculateTotal();
        }

        function removeFromCart(index) {
            cart.splice(index, 1);
            updateCart();
        }

        function calculateTotal() {
            const subtotal = cart.reduce((acc, curr) => acc + curr.price, 0);
            const tax = subtotal * 0.1;
            const total = subtotal + tax;

            document.getElementById('subtotal').innerText = subtotal.toFixed(2) + " TL";
            document.getElementById('tax').innerText = tax.toFixed(2) + " TL";
            document.getElementById('grand-total').innerText = total.toFixed(2) + " TL";
        }

        // Başlangıç
        displayProducts();
    </script>
</body>
</html>
