/* Reset & Base */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

:root {
    --primary: #ff3c00;
    --primary-dark: #cc3000;
    --secondary: #00d4ff;
    --dark: #0a0a0a;
    --dark-2: #141414;
    --dark-3: #1f1f1f;
    --light: #ffffff;
    --gray: #888888;
    --gray-light: #cccccc;
    --gradient: linear-gradient(135deg, #ff3c00 0%, #ff8c00 100%);
    --shadow: 0 10px 40px rgba(0, 0, 0, 0.5);
    --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

html {
    scroll-behavior: smooth;
}

body {
    font-family: 'Rajdhani', sans-serif;
    background: var(--dark);
    color: var(--light);
    line-height: 1.6;
    overflow-x: hidden;
}

.container {
    max-width: 1400px;
    margin: 0 auto;
    padding: 0 20px;
}

/* Header */
.header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background: rgba(10, 10, 10, 0.95);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid rgba(255, 60, 0, 0.2);
    z-index: 1000;
    padding: 15px 0;
    transition: var(--transition);
}

.header-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo {
    display: flex;
    align-items: center;
    gap: 10px;
    font-family: 'Orbitron', sans-serif;
    font-weight: 900;
    font-size: 1.5rem;
    letter-spacing: 2px;
}

.logo-icon {
    font-size: 1.8rem;
    filter: drop-shadow(0 0 10px var(--primary));
}

.logo-text {
    background: var(--gradient);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
}

.nav {
    display: flex;
    gap: 40px;
}

.nav-link {
    color: var(--light);
    text-decoration: none;
    font-weight: 600;
    font-size: 1.1rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    position: relative;
    transition: var(--transition);
}

.nav-link::after {
    content: '';
    position: absolute;
    bottom: -5px;
    left: 0;
    width: 0;
    height: 2px;
    background: var(--gradient);
    transition: var(--transition);
}

.nav-link:hover {
    color: var(--primary);
}

.nav-link:hover::after {
    width: 100%;
}

.cart-btn {
    position: relative;
    background: transparent;
    border: 2px solid var(--primary);
    color: var(--light);
    padding: 10px 15px;
    border-radius: 50px;
    cursor: pointer;
    font-size: 1.2rem;
    transition: var(--transition);
}

.cart-btn:hover {
    background: var(--primary);
    box-shadow: 0 0 20px rgba(255, 60, 0, 0.5);
}

.cart-count {
    position: absolute;
    top: -8px;
    right: -8px;
    background: var(--primary);
    color: white;
    font-size: 0.75rem;
    font-weight: 700;
    padding: 2px 8px;
    border-radius: 50px;
    min-width: 22px;
    text-align: center;
}

/* Hero */
.hero {
    position: relative;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    background: url('https://images.unsplash.com/photo-1544636331-e26879cd4d9b?w=1920') center/cover no-repeat;
    overflow: hidden;
}

.hero-overlay {
    position: absolute;
    inset: 0;
    background: linear-gradient(180deg, rgba(10,10,10,0.7) 0%, rgba(10,10,10,0.9) 100%);
}

.hero-content {
    position: relative;
    z-index: 2;
    animation: fadeInUp 1s ease-out;
}

.hero-title {
    font-family: 'Orbitron', sans-serif;
    font-size: clamp(2rem, 6vw, 5rem);
    font-weight: 900;
    letter-spacing: 4px;
    background: var(--gradient);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 20px;
    text-shadow: 0 0 60px rgba(255, 60, 0, 0.3);
    animation: glow 2s ease-in-out infinite alternate;
}

@keyframes glow {
    from { filter: drop-shadow(0 0 20px rgba(255, 60, 0, 0.5)); }
    to { filter: drop-shadow(0 0 40px rgba(255, 60, 0, 0.8)); }
}

.hero-subtitle {
    font-size: clamp(1rem, 2vw, 1.5rem);
    color: var(--gray-light);
    margin-bottom: 40px;
    max-width: 700px;
    margin-left: auto;
    margin-right: auto;
}

.hero-btn {
    display: inline-block;
    padding: 18px 50px;
    background: var(--gradient);
    color: white;
    text-decoration: none;
    font-weight: 700;
    font-size: 1.1rem;
    text-transform: uppercase;
    letter-spacing: 2px;
    border-radius: 50px;
    transition: var(--transition);
    box-shadow: 0 10px 30px rgba(255, 60, 0, 0.4);
}

.hero-btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 15px 40px rgba(255, 60, 0, 0.6);
}

/* Stats */
.stats {
    background: var(--dark-2);
    padding: 60px 0;
    border-top: 1px solid rgba(255, 60, 0, 0.1);
    border-bottom: 1px solid rgba(255, 60, 0, 0.1);
}

.stats-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 30px;
    text-align: center;
}

.stat-item {
    padding: 20px;
    opacity: 0;
    transform: translateY(30px);
    transition: var(--transition);
}

.stat-item.visible {
    opacity: 1;
    transform: translateY(0);
}

.stat-value {
    font-family: 'Orbitron', sans-serif;
    font-size: clamp(2rem, 4vw, 3.5rem);
    font-weight: 900;
    background: var(--gradient);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    margin-bottom: 10px;
}

.stat-label {
    color: var(--gray);
    font-size: 1rem;
    text-transform: uppercase;
    letter-spacing: 1px;
}

/* Catalog */
.catalog {
    padding: 100px 0;
}

.section-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 20px;
    margin-bottom: 60px;
}

.section-title {
    font-family: 'Orbitron', sans-serif;
    font-size: clamp(1.5rem, 4vw, 2.5rem);
    font-weight: 900;
    letter-spacing: 3px;
    position: relative;
    display: inline-block;
}

.section-title::after {
    content: '';
    position: absolute;
    bottom: -15px;
    left: 0;
    width: 80px;
    height: 4px;
    background: var(--gradient);
    border-radius: 2px;
}

.filter-controls {
    display: flex;
    align-items: center;
    gap: 15px;
}

.filter-controls label {
    color: var(--gray);
    font-weight: 600;
}

.sort-select {
    background: var(--dark-3);
    color: var(--light);
    border: 2px solid rgba(255, 60, 0, 0.3);
    padding: 10px 20px;
    border-radius: 10px;
    font-family: 'Rajdhani', sans-serif;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: var(--transition);
}

.sort-select:hover,
.sort-select:focus {
    border-color: var(--primary);
    outline: none;
    box-shadow: 0 0 20px rgba(255, 60, 0, 0.3);
}

.cars-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
    gap: 30px;
}

.car-card {
    background: var(--dark-2);
    border-radius: 20px;
    overflow: hidden;
    border: 1px solid rgba(255, 255, 255, 0.05);
    transition: var(--transition);
    opacity: 0;
    transform: translateY(30px);
}

.car-card.visible {
    opacity: 1;
    transform: translateY(0);
}

.car-card:hover {
    transform: translateY(-10px);
    border-color: rgba(255, 60, 0, 0.5);
    box-shadow: 0 20px 60px rgba(255, 60, 0, 0.2);
}

.car-image {
    position: relative;
    height: 220px;
    overflow: hidden;
}

.car-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: var(--transition);
}

.car-card:hover .car-image img {
    transform: scale(1.1);
}

.car-year,
.car-country {
    position: absolute;
    padding: 6px 14px;
    background: rgba(10, 10, 10, 0.85);
    backdrop-filter: blur(10px);
    border-radius: 50px;
    font-weight: 700;
    font-size: 0.85rem;
}

.car-year {
    top: 15px;
    left: 15px;
    color: var(--secondary);
    border: 1px solid rgba(0, 212, 255, 0.5);
}

.car-country {
    top: 15px;
    right: 15px;
    color: var(--primary);
    border: 1px solid rgba(255, 60, 0, 0.5);
    text-transform: uppercase;
}

.car-info {
    padding: 25px;
}

.car-name {
    font-family: 'Orbitron', sans-serif;
    font-size: 1.15rem;
    font-weight: 700;
    margin-bottom: 10px;
    color: var(--light);
    line-height: 1.3;
}

.car-description {
    color: var(--gray);
    font-size: 0.9rem;
    margin-bottom: 20px;
    line-height: 1.5;
}

.car-specs {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 10px;
    margin-bottom: 20px;
    padding: 15px;
    background: var(--dark-3);
    border-radius: 12px;
}

.spec {
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 3px;
}

.spec-icon {
    font-size: 1.2rem;
}

.spec-value {
    font-family: 'Orbitron', sans-serif;
    font-weight: 700;
    font-size: 1rem;
    color: var(--primary);
}

.spec-label {
    font-size: 0.7rem;
    color: var(--gray);
    text-transform: uppercase;
    letter-spacing: 0.5px;
}

.car-engine {
    font-size: 0.85rem;
    color: var(--secondary);
    text-align: center;
    padding: 8px;
    background: rgba(0, 212, 255, 0.08);
    border-radius: 8px;
    margin-bottom: 20px;
    font-weight: 600;
    letter-spacing: 0.5px;
}

.car-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 15px;
}

.car-price {
    display: flex;
    flex-direction: column;
}

.price-label {
    font-size: 0.75rem;
    color: var(--gray);
    text-transform: uppercase;
    letter-spacing: 1px;
}

.price-value {
    font-family: 'Orbitron', sans-serif;
    font-size: 1.2rem;
    font-weight: 700;
    color: var(--primary);
}

.buy-btn {
    padding: 12px 24px;
    background: var(--gradient);
    color: white;
    border: none;
    border-radius: 50px;
    font-family: 'Rajdhani', sans-serif;
    font-weight: 700;
    font-size: 1rem;
    text-transform: uppercase;
    letter-spacing: 1px;
    cursor: pointer;
    transition: var(--transition);
    white-space: nowrap;
}

.buy-btn:hover {
    transform: scale(1.05);
    box-shadow: 0 10px 30px rgba(255, 60, 0, 0.5);
}

.buy-btn:active {
    transform: scale(0.95);
}

/* About */
.about {
    padding: 100px 0;
    background: var(--dark-2);
}

.about-content {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 60px;
    align-items: center;
    margin-top: 60px;
}

.about-text p {
    color: var(--gray-light);
    margin-bottom: 20px;
    font-size: 1.05rem;
}

.about-list {
    list-style: none;
    margin-top: 30px;
}

.about-list li {
    padding: 12px 0;
    color: var(--light);
    font-weight: 600;
    font-size: 1.05rem;
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
}

.about-image img {
    width: 100%;
    border-radius: 20px;
    box-shadow: var(--shadow);
}

/* Contact */
.contact {
    padding: 100px 0;
}

.contact-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 30px;
    margin-top: 60px;
}

.contact-item {
    background: var(--dark-2);
    padding: 40px 30px;
    border-radius: 20px;
    text-align: center;
    border: 1px solid rgba(255, 255, 255, 0.05);
    transition: var(--transition);
}

.contact-item:hover {
    border-color: rgba(255, 60, 0, 0.5);
    transform: translateY(-5px);
    box-shadow: 0 20px 40px rgba(255, 60, 0, 0.15);
}

.contact-icon {
    font-size: 2.5rem;
    margin-bottom: 20px;
}

.contact-item h3 {
    font-family: 'Orbitron', sans-serif;
    font-size: 1.1rem;
    margin-bottom: 10px;
    color: var(--primary);
    letter-spacing: 2px;
}

.contact-item p {
    color: var(--gray-light);
    font-size: 1.05rem;
}

/* Footer */
.footer {
    background: var(--dark-2);
    padding: 40px 0;
    text-align: center;
    border-top: 1px solid rgba(255, 60, 0, 0.2);
}

.footer p {
    color: var(--gray);
}

/* Cart Modal */
.cart-modal {
    position: fixed;
    inset: 0;
    background: rgba(0, 0, 0, 0.8);
    backdrop-filter: blur(10px);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 2000;
    opacity: 0;
    visibility: hidden;
    transition: var(--transition);
}

.cart-modal.show {
    opacity: 1;
    visibility: visible;
}

.cart-modal-content {
    background: var(--dark-2);
    border: 1px solid rgba(255, 60, 0, 0.3);
    border-radius: 20px;
    width: 90%;
    max-width: 550px;
    max-height: 80vh;
    display: flex;
    flex-direction: column;
    transform: scale(0.9);
    transition: var(--transition);
}

.cart-modal.show .cart-modal-content {
    transform: scale(1);
}

.cart-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 25px 30px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.cart-header h2 {
    font-family: 'Orbitron', sans-serif;
    font-size: 1.5rem;
    letter-spacing: 2px;
}

.close-btn {
    background: transparent;
    border: none;
    color: var(--gray);
    font-size: 2rem;
    cursor: pointer;
    transition: var(--transition);
    line-height: 1;
}

.close-btn:hover {
    color: var(--primary);
    transform: rotate(90deg);
}

.cart-items {
    flex: 1;
    overflow-y: auto;
    padding: 20px 30px;
}

.empty-cart {
    text-align: center;
    color: var(--gray);
    padding: 40px 0;
    font-size: 1.1rem;
}

.cart-item {
    display: flex;
    align-items: center;
    gap: 15px;
    padding: 15px 0;
    border-bottom: 1px solid rgba(255, 255, 255, 0.05);
}

.cart-item img {
    width: 80px;
    height: 60px;
    object-fit: cover;
    border-radius: 10px;
}

.cart-item-info {
    flex: 1;
}

.cart-item-info h4 {
    font-family: 'Orbitron', sans-serif;
    font-size: 0.9rem;
    margin-bottom: 5px;
    color: var(--light);
}

.cart-item-info p {
    color: var(--primary);
    font-weight: 700;
    font-size: 1rem;
}

.remove-btn {
    background: transparent;
    border: 2px solid rgba(255, 60, 0, 0.3);
    color: var(--primary);
    width: 32px;
    height: 32px;
    border-radius: 50%;
    cursor: pointer;
    font-size: 1.2rem;
    line-height: 1;
    transition: var(--transition);
    display: flex;
    align-items: center;
    justify-content: center;
}

.remove-btn:hover {
    background: var(--primary);
    color: white;
    border-color: var(--primary);
}

.cart-footer {
    padding: 25px 30px;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    display: none;
}

.cart-total {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
    font-size: 1.2rem;
    font-weight: 700;
}

.cart-total span:last-child {
    font-family: 'Orbitron', sans-serif;
    color: var(--primary);
    font-size: 1.5rem;
}

.checkout-btn {
    width: 100%;
    padding: 16px;
    background: var(--gradient);
    color: white;
    border: none;
    border-radius: 50px;
    font-family: 'Rajdhani', sans-serif;
    font-weight: 700;
    font-size: 1.1rem;
    text-transform: uppercase;
    letter-spacing: 2px;
    cursor: pointer;
    transition: var(--transition);
}

.checkout-btn:hover {
    transform: translateY(-3px);
    box-shadow: 0 15px 40px rgba(255, 60, 0, 0.5);
}

/* Notification */
.notification {
    position: fixed;
    bottom: 30px;
    right: 30px;
    padding: 18px 30px;
    background: var(--dark-2);
    border-radius: 12px;
    color: var(--light);
    font-weight: 600;
    font-size: 1rem;
    box-shadow: var(--shadow);
    transform: translateX(150%);
    transition: var(--transition);
    z-index: 3000;
    border-left: 4px solid var(--primary);
    max-width: 400px;
}

.notification.show {
    transform: translateX(0);
}

.notification.success {
    border-left-color: #00c853;
}

.notification.error {
    border-left-color: #ff1744;
}

.notification.info {
    border-left-color: var(--secondary);
}

/* Animations */
@keyframes fadeInUp {
    from {
        opacity: 0;
        transform: translateY(40px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

/* Responsive */
@media (max-width: 968px) {
    .about-content {
        grid-template-columns: 1fr;
    }
    
    .about-image {
        order: -1;
    }
}

@media (max-width: 768px) {
    .nav {
        display: none;
    }
    
    .header-content {
        padding: 0;
    }
    
    .section-header {
        flex-direction: column;
        align-items: flex-start;
    }
    
    .cars-grid {
        grid-template-columns: 1fr;
    }
    
    .hero-title {
        letter-spacing: 2px;
    }
    
    .notification {
        right: 15px;
        left: 15px;
        max-width: none;
    }
}

/* Scrollbar */
::-webkit-scrollbar {
    width: 10px;
}

::-webkit-scrollbar-track {
    background: var(--dark);
}

::-webkit-scrollbar-thumb {
    background: var(--primary);
    border-radius: 10px;
}

::-webkit-scrollbar-thumb:hover {
    background: var(--primary-dark);
}
