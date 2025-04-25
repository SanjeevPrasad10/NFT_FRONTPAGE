# NFT_FRONTPAGE
This repository is for my first homepage of the NFT marketplace
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Icon NFT Marketplace</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    :root {
      --primary: #6e45e2;
      --secondary: #88d3ce;
      --dark: #1a1a2e;
      --light: #f5f5f5;
      --accent: #ff6b6b;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      background-color: var(--light);
      color: var(--dark);
      overflow-x: hidden;
    }

    /* Navbar */
    .navbar {
      background: linear-gradient(135deg, var(--primary), var(--secondary));
      color: white;
      height: 80px;
      display: flex;
      align-items: center;
      padding: 0 5%;
      box-shadow: 0 2px 15px rgba(0, 0, 0, 0.1);
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .navbar-brand {
      display: flex;
      align-items: center;
      margin-right: auto;
      font-size: 1.8rem;
    }

    .navbar-brand i {
      margin-right: 10px;
    }

    .nav-links {
      display: flex;
      gap: 30px;
    }

    .nav-links a {
      color: white;
      text-decoration: none;
      font-weight: 500;
      transition: all 0.3s;
      padding: 8px 15px;
      border-radius: 30px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .nav-links a:hover {
      background: rgba(255, 255, 255, 0.2);
      transform: translateY(-3px);
    }

    .wallet-btn {
      background: white;
      color: var(--primary);
      border: none;
      padding: 10px 20px;
      border-radius: 30px;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .wallet-btn:hover {
      transform: translateY(-3px);
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    }

    /* Sidebar */
    .sidebar {
      width: 280px;
      height: calc(100vh - 80px);
      background: white;
      box-shadow: 2px 0 15px rgba(0, 0, 0, 0.05);
      position: fixed;
      top: 80px;
      left: 0;
      padding: 30px 0;
      overflow-y: auto;
    }

    .sidebar-menu {
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .sidebar-menu h3 {
      padding: 10px 25px;
      color: var(--primary);
      font-size: 0.9rem;
      text-transform: uppercase;
      letter-spacing: 1px;
    }

    .sidebar-menu a {
      display: flex;
      align-items: center;
      padding: 12px 25px;
      color: #555;
      text-decoration: none;
      transition: all 0.2s;
      font-size: 0.95rem;
    }

    .sidebar-menu a i {
      margin-right: 12px;
      color: var(--primary);
      width: 20px;
      text-align: center;
    }

    .sidebar-menu a:hover {
      background: rgba(110, 69, 226, 0.05);
      color: var(--primary);
      border-left: 3px solid var(--primary);
    }

    /* Main Content */
    .main-content {
      margin-left: 280px;
      padding: 40px 5%;
    }

    .hero {
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      padding: 60px 0;
    }

    .hero h1 {
      font-size: 3rem;
      margin-bottom: 20px;
      background: linear-gradient(to right, var(--primary), var(--secondary));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .hero p {
      font-size: 1.1rem;
      color: #666;
      max-width: 700px;
      margin-bottom: 30px;
    }

    .search-bar {
      display: flex;
      width: 100%;
      max-width: 600px;
      margin-bottom: 40px;
    }

    .search-bar input {
      flex: 1;
      padding: 15px 20px;
      border: 1px solid #ddd;
      border-radius: 30px 0 0 30px;
      font-size: 1rem;
      outline: none;
    }

    .search-bar button {
      background: var(--primary);
      color: white;
      border: none;
      padding: 0 25px;
      border-radius: 0 30px 30px 0;
      cursor: pointer;
      transition: all 0.3s;
    }

    .search-bar button:hover {
      background: var(--secondary);
    }

    /* NFT Grid */
    .section-title {
      font-size: 1.8rem;
      margin-bottom: 30px;
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .section-title a {
      font-size: 1rem;
      color: var(--primary);
      text-decoration: none;
      display: flex;
      align-items: center;
      gap: 5px;
    }

    .nft-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 30px;
      margin-bottom: 60px;
    }

    .nft-card {
      background: white;
      border-radius: 15px;
      overflow: hidden;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
      transition: all 0.3s;
      text-align: center;
      padding: 30px 20px;
    }

    .nft-card:hover {
      transform: translateY(-10px);
      box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
    }

    .nft-icon {
      font-size: 4rem;
      color: var(--primary);
      margin-bottom: 20px;
      background: rgba(110, 69, 226, 0.1);
      width: 120px;
      height: 120px;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 50%;
      margin: 0 auto 20px;
    }

    .nft-info {
      padding: 0 10px;
    }

    .nft-title {
      font-size: 1.2rem;
      margin-bottom: 10px;
      display: flex;
      justify-content: center;
      gap: 10px;
    }

    .nft-creator {
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 15px;
      font-size: 0.9rem;
      color: #666;
      gap: 8px;
    }

    .creator-icon {
      color: var(--primary);
      font-size: 1rem;
    }

    .nft-price {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding-top: 15px;
      border-top: 1px solid #eee;
    }

    .price-eth {
      font-weight: 600;
      color: var(--primary);
      display: flex;
      align-items: center;
      gap: 5px;
    }

    .buy-btn {
      background: var(--primary);
      color: white;
      border: none;
      padding: 8px 15px;
      border-radius: 20px;
      cursor: pointer;
      transition: all 0.3s;
      font-weight: 500;
    }

    .buy-btn:hover {
      background: var(--secondary);
    }

    /* Categories */
    .categories {
      display: flex;
      gap: 15px;
      margin-bottom: 40px;
      flex-wrap: wrap;
      justify-content: center;
    }

    .category {
      background: white;
      padding: 10px 20px;
      border-radius: 30px;
      cursor: pointer;
      transition: all 0.3s;
      font-size: 0.9rem;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .category:hover, .category.active {
      background: var(--primary);
      color: white;
    }

    /* Footer */
    footer {
      background: var(--dark);
      color: white;
      padding: 60px 5%;
      margin-left: 280px;
    }

    .footer-content {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 40px;
    }

    .footer-column h3 {
      font-size: 1.2rem;
      margin-bottom: 20px;
      position: relative;
      padding-bottom: 10px;
    }

    .footer-column h3::after {
      content: '';
      position: absolute;
      left: 0;
      bottom: 0;
      width: 40px;
      height: 2px;
      background: var(--primary);
    }

    .footer-column ul {
      list-style: none;
    }

    .footer-column ul li {
      margin-bottom: 10px;
    }

    .footer-column ul li a {
      color: #bbb;
      text-decoration: none;
      transition: all 0.3s;
    }

    .footer-column ul li a:hover {
      color: white;
      padding-left: 5px;
    }

    .social-links {
      display: flex;
      gap: 15px;
      margin-top: 20px;
    }

    .social-links a {
      color: white;
      background: rgba(255, 255, 255, 0.1);
      width: 40px;
      height: 40px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: all 0.3s;
    }

    .social-links a:hover {
      background: var(--primary);
      transform: translateY(-3px);
    }

    .copyright {
      text-align: center;
      margin-top: 60px;
      padding-top: 30px;
      border-top: 1px solid rgba(255, 255, 255, 0.1);
      color: #bbb;
      font-size: 0.9rem;
    }

    /* Responsive */
    @media (max-width: 1200px) {
      .sidebar {
        transform: translateX(-100%);
        z-index: 90;
        transition: transform 0.3s;
      }
      .sidebar.active {
        transform: translateX(0);
      }
      .main-content, footer {
        margin-left: 0;
      }
      .toggle-btn {
        display: block;
      }
    }

    @media (max-width: 768px) {
      .navbar {
        padding: 0 20px;
      }
      .nav-links {
        display: none;
      }
      .hero h1 {
        font-size: 2rem;
      }
      .nft-grid {
        grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
      }
    }

    /* Toggle button */
    .toggle-btn {
      background: none;
      border: none;
      color: white;
      font-size: 1.5rem;
      cursor: pointer;
      display: none;
      margin-left: 20px;
    }

    /* Overlay for sidebar */
    .overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.5);
      z-index: 80;
      opacity: 0;
      visibility: hidden;
      transition: all 0.3s;
    }

    .overlay.active {
      opacity: 1;
      visibility: visible;
    }
  </style>
</head>
<body>
  <!-- Navbar -->
  <nav class="navbar">
    <div class="navbar-brand">
      <i class="fas fa-cubes"></i> NFT Market
    </div>
    <div class="nav-links">
      <a href="#"><i class="fas fa-home"></i> Home</a>
      <a href="#"><i class="fas fa-fire"></i> Trending</a>
      <a href="#"><i class="fas fa-search"></i> Discover</a>
      <a href="#"><i class="fas fa-user"></i> Artists</a>
      <button class="wallet-btn"><i class="fas fa-wallet"></i> Connect Wallet</button>
    </div>
    <button class="toggle-btn">
      <i class="fas fa-bars"></i>
    </button>
  </nav>

  <!-- Sidebar -->
  <div class="sidebar">
    <div class="sidebar-menu">
      <h3>Marketplace</h3>
      <a href="#"><i class="fas fa-compass"></i> Discover</a>
      <a href="#"><i class="fas fa-chart-line"></i> Rankings</a>
      <a href="#"><i class="fas fa-calendar"></i> Drops</a>
      
      <h3>Categories</h3>
      <a href="#"><i class="fas fa-paint-brush"></i> Art</a>
      <a href="#"><i class="fas fa-music"></i> Music</a>
      <a href="#"><i class="fas fa-camera"></i> Photography</a>
      <a href="#"><i class="fas fa-gamepad"></i> Games</a>
      <a href="#"><i class="fas fa-basketball-ball"></i> Sports</a>
      
      <h3>Account</h3>
      <a href="#"><i class="fas fa-user"></i> Profile</a>
      <a href="#"><i class="fas fa-heart"></i> Favorites</a>
      <a href="#"><i class="fas fa-cog"></i> Settings</a>
    </div>
  </div>

  <!-- Overlay -->
  <div class="overlay"></div>

  <!-- Main Content -->
  <div class="main-content">
    <section class="hero">
      <h1>Discover, Collect & Sell Extraordinary NFTs</h1>
      <p>Explore the best digital art and collectibles on the largest NFT marketplace</p>
      <div class="search-bar">
        <input type="text" placeholder="Search items, collections, and creators...">
        <button><i class="fas fa-search"></i></button>
      </div>
    </section>

    <section>
        <h2 class="section-title">
            Trending Collections 
            <a href="#">View all <i class="fas fa-arrow-right"></i></a>
          </h2>
          
          <div class="categories">
            <div class="category active">
              <button onclick="window.location.href='second_file.html'" style="all: unset; cursor: pointer;">
                <i class="fas fa-layer-group"></i> All
              </button>
            </div>
          
            <div class="category">
              <button onclick="window.location.href='second_file.html'" style="all: unset; cursor: pointer;">
                <i class="fas fa-paint-brush"></i> Art
              </button>
            </div>
          
            <div class="category">
              <button onclick="window.location.href='second_file.html'" style="all: unset; cursor: pointer;">
                <i class="fas fa-music"></i> Music
              </button>
            </div>
          
            <div class="category">
              <button onclick="window.location.href='second_file.html'" style="all: unset; cursor: pointer;">
                <i class="fas fa-camera"></i> Photography
              </button>
            </div>
          
            <div class="category">
              <button onclick="window.location.href='second_file.html'" style="all: unset; cursor: pointer;">
                <i class="fas fa-vr-cardboard"></i> Virtual Worlds
              </button>
            </div>
          
            <div class="category">
              <button onclick="window.location.href='second_file.html'" style="all: unset; cursor: pointer;">
                <i class="fas fa-chess"></i> Trading Cards
              </button>
            </div>
          </div>
      <div class="nft-grid">
        <!-- NFT Card 1 -->
        <div class="nft-card">
          <div class="nft-icon">
            <i class="fas fa-meteor"></i>
          </div>
          <div class="nft-info">
            <h3 class="nft-title">Cosmic Dreams <i class="fas fa-heart" style="color: #ff6b6b;"></i></h3>
            <div class="nft-creator">
              <i class="fas fa-user-circle creator-icon"></i>
              <span>@sanjeev_artist</span>
            </div>
            <div class="nft-price">
              <div class="price-eth">
                <i class="fab fa-ethereum"></i> 0.25 ETH
              </div>
              <button class="buy-btn">Buy Now</button>
            </div>
          </div>
        </div>

        <!-- NFT Card 2 -->
        <div class="nft-card">
          <div class="nft-icon">
            <i class="fas fa-atom"></i>
          </div>
          <div class="nft-info">
            <h3 class="nft-title">Neon Future <i class="far fa-heart"></i></h3>
            <div class="nft-creator">
              <i class="fas fa-user-astronaut creator-icon"></i>
              <span>@kapilNFTseller</span>
            </div>
            <div class="nft-price">
              <div class="price-eth">
                <i class="fab fa-ethereum"></i> 0.42 ETH
              </div>
              <button class="buy-btn">Buy Now</button>
            </div>
          </div>
        </div>

        <!-- NFT Card 3 -->
        <div class="nft-card">
          <div class="nft-icon">
            <i class="fas fa-tree"></i>
          </div>
          <div class="nft-info">
            <h3 class="nft-title">Forest<i class="far fa-heart"></i></h3>
            <div class="nft-creator">
              <i class="fas fa-user-ninja creator-icon"></i>
              <span>@shivamcreator</span>
            </div>
            <div class="nft-price">
              <div class="price-eth">
                <i class="fab fa-ethereum"></i> 0.18 ETH
              </div>
              <button class="buy-btn">Buy Now</button>
            </div>
          </div>
        </div>

        <!-- NFT Card 4 -->
        <div class="nft-card">
          <div class="nft-icon">
            <i class="fas fa-cloud-moon"></i>
          </div>
          <div class="nft-info">
            <h3 class="nft-title">Surreal Visions <i class="fas fa-heart" style="color: #ff6b6b;"></i></h3>
            <div class="nft-creator">
              <i class="fas fa-user-secret creator-icon"></i>
              <span>@Rajdeployer</span>
            </div>
            <div class="nft-price">
              <div class="price-eth">
                <i class="fab fa-ethereum"></i> 0.35 ETH
              </div>
              <button class="buy-btn">Buy Now</button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section>
      <h2 class="section-title">Top Artists <a href="#">View all <i class="fas fa-arrow-right"></i></a></h2>
      <div class="nft-grid">
        <!-- Artist Card 1 -->
        <div class="nft-card">
          <div class="nft-icon">
            <i class="fas fa-user-astronaut"></i>
          </div>
          <div class="nft-info">
            <h3 class="nft-title">DigitalDev</h3>
            <div class="nft-creator">
              <span>Total Sales: 420 ETH</span>
            </div>
            <div class="nft-price">
              <div class="price-eth">
                <i class="fas fa-star" style="color: gold;"></i> 4.9
              </div>
              <button class="buy-btn">Follow</button>
            </div>
          </div>
        </div>

        <!-- Artist Card 2 -->
        <div class="nft-card">
          <div class="nft-icon">
            <i class="fas fa-user-tie"></i>
          </div>
          <div class="nft-info">
            <h3 class="nft-title">Cyber Mona</h3>
            <div class="nft-creator">
              <span>Total Sales: 380 ETH</span>
            </div>
            <div class="nft-price">
              <div class="price-eth">
                <i class="fas fa-star" style="color: gold;"></i> 4.8
              </div>
              <button class="buy-btn">Follow</button>
            </div>
          </div>
        </div>

        <!-- Artist Card 3 -->
        <div class="nft-card">
          <div class="nft-icon">
            <i class="fas fa-user-graduate"></i>
          </div>
          <div class="nft-info">
            <h3 class="nft-title">Neon Da Vinci</h3>
            <div class="nft-creator">
              <span>Total Sales: 310 ETH</span>
            </div>
            <div class="nft-price">
              <div class="price-eth">
                <i class="fas fa-star" style="color: gold;"></i> 4.7
              </div>
              <button class="buy-btn">Follow</button>
            </div>
          </div>
        </div>

        <!-- Artist Card 4 -->
        <div class="nft-card">
          <div class="nft-icon">
            <i class="fas fa-user-ninja"></i>
          </div>
          <div class="nft-info">
            <h3 class="nft-title">Pixel Hokusai</h3>
            <div class="nft-creator">
              <span>Total Sales: 290 ETH</span>
            </div>
            <div class="nft-price">
              <div class="price-eth">
                <i class="fas fa-star" style="color: gold;"></i> 4.6
              </div>
              <button class="buy-btn">Follow</button>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>

  <!-- Footer -->
  <footer>
    <div class="footer-content">
      <div class="footer-column">
        <h3>Marketplace</h3>
        <ul>
          <li><a href="#"><i class="fas fa-cube"></i> All NFTs</a></li>
          <li><a href="#"><i class="fas fa-paint-brush"></i> Art</a></li>
          <li><a href="#"><i class="fas fa-music"></i> Music</a></li>
          <li><a href="#"><i class="fas fa-camera"></i> Photography</a></li>
          <li><a href="#"><i class="fas fa-vr-cardboard"></i> Virtual Worlds</a></li>
        </ul>
      </div>
      <div class="footer-column">
        <h3>My Account</h3>
        <ul>
          <li><a href="#"><i class="fas fa-user"></i> Profile</a></li>
          <li><a href="#"><i class="fas fa-heart"></i> Favorites</a></li>
          <li><a href="#"><i class="fas fa-eye"></i> Watchlist</a></li>
          <li><a href="#"><i class="fas fa-layer-group"></i> My Collections</a></li>
          <li><a href="#"><i class="fas fa-cog"></i> Settings</a></li>
        </ul>
      </div>
      <div class="footer-column">
        <h3>Resources</h3>
        <ul>
          <li><a href="#"><i class="fas fa-question-circle"></i> Help Center</a></li>
          <li><a href="#"><i class="fas fa-chart-bar"></i> Platform Status</a></li>
          <li><a href="#"><i class="fas fa-handshake"></i> Partners</a></li>
          <li><a href="#"><i class="fas fa-blog"></i> Blog</a></li>
          <li><a href="#"><i class="fas fa-envelope"></i> Newsletter</a></li>
        </ul>
      </div>
      <div class="footer-column">
        <h3>Company</h3>
        <ul>
          <li><a href="#"><i class="fas fa-info-circle"></i> About</a></li>
          <li><a href="#"><i class="fas fa-briefcase"></i> Careers</a></li>
          <li><a href="#"><i class="fas fa-file-alt"></i> Terms of Service</a></li>
          <li><a href="#"><i class="fas fa-lock"></i> Privacy Policy</a></li>
        </ul>
        <div class="social-links">
          <a href="#"><i class="fab fa-twitter"></i></a>
          <a href="#"><i class="fab fa-discord"></i></a>
          <a href="#"><i class="fab fa-instagram"></i></a>
          <a href="#"><i class="fab fa-telegram"></i></a>
        </div>
      </div>
    </div>
    <div class="copyright">
      &copy; 2023 Icon NFT Marketplace. All rights reserved.
    </div>
  </footer>

  <script>
    // Toggle sidebar on mobile
    document.querySelector('.toggle-btn').addEventListener('click', () => {
      document.querySelector('.sidebar').classList.toggle('active');
      document.querySelector('.overlay').classList.toggle('active');
    });

    // Close sidebar when clicking overlay
    document.querySelector('.overlay').addEventListener('click', () => {
      document.querySelector('.sidebar').classList.remove('active');
      document.querySelector('.overlay').classList.remove('active');
    });

    // Toggle favorite heart
    document.querySelectorAll('.fa-heart').forEach(heart => {
      heart.addEventListener('click', (e) => {
        e.stopPropagation();
        heart.classList.toggle('fas');
        heart.classList.toggle('far');
        if (heart.classList.contains('fas')) {
          heart.style.color = '#ff6b6b';
        } else {
          heart.style.color = '';
        }
      });
    });

    // Toggle category selection
    document.querySelectorAll('.category').forEach(category => {
      category.addEventListener('click', () => {
        document.querySelector('.category.active').classList.remove('active');
        category.classList.add('active');
      });
    });
  </script>
</body>
</html>
