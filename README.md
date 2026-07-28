<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bhavan's B.P. Vidya Mandir, Koradi, Nagpur</title>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;700;800;900&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Montserrat', sans-serif;
    scroll-behavior: smooth;
}

body {
    background: #0b111e;
    color: #ffffff;
    overflow-x: hidden;
}

/* Custom Scrollbar */
::-webkit-scrollbar {
    width: 8px;
}
::-webkit-scrollbar-track {
    background: #0b111e;
}
::-webkit-scrollbar-thumb {
    background: #334155;
    border-radius: 4px;
}
::-webkit-scrollbar-thumb:hover {
    background: #475569;
}

/* Header & Nav */
header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    padding: 22px 8%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 1000;
    background: linear-gradient(180deg, rgba(0,0,0,0.85) 0%, rgba(0,0,0,0) 100%);
    transition: all 0.4s ease;
}

header.scrolled {
    background: rgba(11, 17, 30, 0.95);
    backdrop-filter: blur(12px);
    padding: 15px 8%;
    border-bottom: 1px solid rgba(255, 255, 255, 0.08);
    box-shadow: 0 10px 30px rgba(0,0,0,0.6);
}

.logo-container {
    display: flex;
    align-items: center;
    gap: 12px;
    cursor: pointer;
}

.logo-icon {
    width: 36px;
    height: 36px;
    border: 2px solid #38bdf8;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: #38bdf8;
    transition: transform 0.5s ease;
}

.logo-container:hover .logo-icon {
    transform: rotate(180deg);
}

.logo-text {
    font-size: 18px;
    font-weight: 800;
    letter-spacing: -0.5px;
    color: #ffffff;
    text-transform: uppercase;
}

.logo-sub {
    font-size: 11px;
    color: #38bdf8;
    letter-spacing: 1.5px;
    font-weight: 600;
}

nav {
    display: flex;
    align-items: center;
    gap: 28px;
}

nav a {
    color: #cbd5e1;
    text-decoration: none;
    font-size: 13px;
    font-weight: 600;
    letter-spacing: 0.5px;
    transition: all 0.3s ease;
    position: relative;
    text-transform: uppercase;
}

nav a::after {
    content: '';
    position: absolute;
    bottom: -6px;
    left: 0;
    width: 0;
    height: 2px;
    background: #38bdf8;
    transition: width 0.3s ease;
}

nav a:hover {
    color: #ffffff;
}

nav a:hover::after {
    width: 100%;
}

.social-icons {
    display: flex;
    gap: 16px;
    margin-left: 15px;
}

.social-icons a {
    color: #ffffff;
    font-size: 15px;
    opacity: 0.85;
    transition: all 0.3s ease;
}

.social-icons a:hover {
    opacity: 1;
    color: #38bdf8;
    transform: translateY(-2px);
}

/* Hero Section */
.hero {
    position: relative;
    height: 100vh;
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 0 8%;
    background: linear-gradient(to right, rgba(11, 17, 30, 0.88) 0%, rgba(11, 17, 30, 0.4) 100%),
                url('https://images.unsplash.com/photo-1541829070764-84a7d30dd3f3?auto=format&fit=crop&w=2000&q=80') center/cover no-repeat;
    overflow: hidden;
}

.hero-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: radial-gradient(circle at 20% 50%, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0) 70%);
    pointer-events: none;
}

.hero-content {
    max-width: 900px;
    z-index: 2;
    animation: fadeInUp 1.2s cubic-bezier(0.16, 1, 0.3, 1);
}

.hero-badge {
    display: inline-block;
    padding: 6px 16px;
    background: rgba(56, 189, 248, 0.15);
    border: 1px solid rgba(56, 189, 248, 0.4);
    border-radius: 20px;
    color: #38bdf8;
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 20px;
}

.hero h1 {
    font-size: clamp(42px, 7vw, 90px);
    font-weight: 900;
    line-height: 0.95;
    text-transform: uppercase;
    letter-spacing: -2px;
    margin-bottom: 25px;
    color: #ffffff;
    text-shadow: 0 10px 30px rgba(0,0,0,0.6);
}

.hero p {
    font-size: clamp(16px, 1.8vw, 20px);
    line-height: 1.6;
    color: #cbd5e1;
    max-width: 650px;
    font-weight: 400;
    margin-bottom: 35px;
    text-shadow: 0 4px 12px rgba(0,0,0,0.6);
}

/* Scroll Indicator */
.scroll-indicator {
    position: absolute;
    bottom: 40px;
    left: 8%;
    display: flex;
    align-items: center;
    gap: 10px;
    color: #ffffff;
    text-decoration: none;
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 3px;
    text-transform: uppercase;
    z-index: 2;
    transition: opacity 0.3s ease;
}

.scroll-indicator i {
    animation: bounce 2s infinite;
    color: #38bdf8;
}

@keyframes bounce {
    0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
    40% { transform: translateY(6px); }
    60% { transform: translateY(3px); }
}

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

/* Sections Styling */
section {
    padding: 110px 8%;
    position: relative;
}

.section-title {
    font-size: 36px;
    font-weight: 800;
    text-transform: uppercase;
    letter-spacing: -1px;
    margin-bottom: 15px;
    color: #ffffff;
}

.section-subtitle {
    font-size: 15px;
    color: #94a3b8;
    max-width: 580px;
    margin-bottom: 50px;
    line-height: 1.6;
}

/* About Section */
.about-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 60px;
    align-items: center;
}

.about-text p {
    color: #cbd5e1;
    font-size: 16px;
    line-height: 1.8;
    margin-bottom: 22px;
}

.stats-container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
    margin-top: 35px;
}

.stat-box {
    background: rgba(255, 255, 255, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.08);
    padding: 22px;
    border-radius: 12px;
    transition: all 0.3s ease;
}

.stat-box:hover {
    background: rgba(255, 255, 255, 0.06);
    border-color: rgba(56, 189, 248, 0.3);
    transform: translateY(-5px);
}

.stat-number {
    font-size: 32px;
    font-weight: 800;
    color: #38bdf8;
    margin-bottom: 4px;
}

.stat-label {
    font-size: 13px;
    color: #94a3b8;
    font-weight: 500;
}

.about-img {
    width: 100%;
    height: 480px;
    border-radius: 16px;
    object-fit: cover;
    box-shadow: 0 20px 40px rgba(0,0,0,0.5);
    filter: brightness(0.92);
    transition: filter 0.3s ease;
}

.about-img:hover {
    filter: brightness(1);
}

/* Cards & Facilities */
.cards-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(270px, 1fr));
    gap: 28px;
}

.card {
    position: relative;
    height: 380px;
    border-radius: 16px;
    overflow: hidden;
    background-size: cover;
    background-position: center;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    padding: 30px;
    transition: all 0.4s cubic-bezier(0.16, 1, 0.3, 1);
    cursor: pointer;
}

.card::before {
    content: '';
    position: absolute;
    inset: 0;
    background: linear-gradient(180deg, rgba(0,0,0,0) 30%, rgba(11,17,30,0.95) 100%);
    transition: opacity 0.3s ease;
}

.card:hover {
    transform: translateY(-8px);
    box-shadow: 0 20px 40px rgba(0,0,0,0.6);
}

.card-content {
    position: relative;
    z-index: 2;
}

.card-tag {
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: #38bdf8;
    margin-bottom: 8px;
}

.card-title {
    font-size: 22px;
    font-weight: 700;
    color: #ffffff;
    margin-bottom: 10px;
}

.card-desc {
    font-size: 13px;
    color: #cbd5e1;
    line-height: 1.5;
    opacity: 0.88;
}

/* Principal Section */
.principal-box {
    background: rgba(30, 41, 59, 0.4);
    border: 1px solid rgba(255, 255, 255, 0.08);
    border-radius: 20px;
    padding: 50px;
    display: grid;
    grid-template-columns: 240px 1fr;
    gap: 40px;
    align-items: center;
}

.principal-badge {
    text-align: center;
}

.principal-badge img {
    width: 160px;
    height: 160px;
    border-radius: 50%;
    object-fit: cover;
    border: 3px solid #38bdf8;
    box-shadow: 0 10px 25px rgba(0,0,0,0.5);
    margin-bottom: 15px;
}

.principal-name {
    font-size: 18px;
    font-weight: 700;
    color: #ffffff;
}

.principal-title {
    font-size: 12px;
    color: #38bdf8;
    text-transform: uppercase;
    letter-spacing: 1px;
}

.principal-quote {
    color: #cbd5e1;
    font-size: 16px;
    line-height: 1.8;
    font-style: italic;
    border-left: 3px solid #38bdf8;
    padding-left: 20px;
}

/* Contact Section */
.contact-container {
    background: linear-gradient(135deg, rgba(30, 41, 59, 0.6) 0%, rgba(15, 23, 42, 0.8) 100%);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 20px;
    padding: 50px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 50px;
    backdrop-filter: blur(10px);
}

.contact-info h3 {
    font-size: 26px;
    font-weight: 700;
    margin-bottom: 20px;
}

.contact-info p {
    color: #94a3b8;
    line-height: 1.7;
    margin-bottom: 30px;
}

.contact-details {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.contact-item {
    display: flex;
    align-items: center;
    gap: 15px;
    color: #e2e8f0;
    font-size: 14px;
}

.contact-item i {
    color: #38bdf8;
    font-size: 18px;
    width: 24px;
}

.contact-form {
    display: flex;
    flex-direction: column;
    gap: 18px;
}

.form-group input,
.form-group textarea {
    width: 100%;
    padding: 14px;
    background: rgba(255, 255, 255, 0.04);
    border: 1px solid rgba(255, 255, 255, 0.1);
    border-radius: 8px;
    color: #ffffff;
    font-size: 14px;
    outline: none;
    transition: border-color 0.3s ease;
}

.form-group input:focus,
.form-group textarea:focus {
    border-color: #38bdf8;
}

.submit-btn {
    padding: 14px 28px;
    background: #38bdf8;
    color: #0b111e;
    font-weight: 700;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: all 0.3s ease;
    text-transform: uppercase;
    letter-spacing: 1px;
}

.submit-btn:hover {
    background: #7dd3fc;
    box-shadow: 0 0 20px rgba(56, 189, 248, 0.4);
}

/* Footer */
footer {
    padding: 35px 8%;
    border-top: 1px solid rgba(255, 255, 255, 0.08);
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: #64748b;
    font-size: 13px;
}

/* Responsive */
@media (max-width: 900px) {
    header {
        padding: 20px 5%;
    }
    nav {
        display: none;
    }
    .hero h1 {
        font-size: 48px;
    }
    .about-grid,
    .principal-box,
    .contact-container {
        grid-template-columns: 1fr;
    }
}
</style>
</head>

<body>

<header id="navbar">
    <div class="logo-container">
        <div class="logo-icon"><i class="fa-solid fa-graduation-cap"></i></div>
        <div>
            <div class="logo-text">Bhavan's B.P. Vidya Mandir</div>
            <div class="logo-sub">Koradi, Nagpur</div>
        </div>
    </div>
    <nav>
        <a href="#home">Home</a>
        <a href="#about">About Us</a>
        <a href="#facilities">Campus & Facilities</a>
        <a href="#principal">Leadership</a>
        <a href="#contact">Contact</a>
    </nav>
    <div class="social-icons">
        <a href="#" aria-label="Facebook"><i class="fa-brands fa-facebook-f"></i></a>
        <a href="#" aria-label="Instagram"><i class="fa-brands fa-instagram"></i></a>
    </div>
</header>

<section id="home" class="hero">
    <div class="hero-overlay"></div>
    <div class="hero-content">
        <div class="hero-badge">CBSE Affiliated • Est. 2016</div>
        <h1>Roots &<br>Wings</h1>
        <p>Empowering students with excellence in academics, leadership, innovation, and character building for a brighter tomorrow at our 10-acre green campus in Koradi, Nagpur.</p>
    </div>
    <a href="#about" class="scroll-indicator">
        Scroll <i class="fa-solid fa-arrow-down"></i>
    </a>
</section>

<section id="about">
    <div class="about-grid">
        <div class="about-text">
            <h2 class="section-title">About Our School</h2>
            <p>Bhavan's Bhagwandas Purohit Vidya Mandir, Koradi was established in July 2016 under Bharatiya Vidya Bhavan, Nagpur Kendra. We provide holistic education from Nursery to Class XII.</p>
            <p>Our curriculum balances academic rigor with co-curricular growth including Robotics, Drama, Sports Training, and Creative Arts to nurture well-rounded global citizens.</p>
            <div class="stats-container">
                <div class="stat-box">
                    <div class="stat-number">2500+</div>
                    <div class="stat-label">Students Enrolled</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">10 Acres</div>
                    <div class="stat-label">Sprawling Campus</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">85+</div>
                    <div class="stat-label">Classrooms & Labs</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">100%</div>
                    <div class="stat-label">Academic Excellence</div>
                </div>
            </div>
        </div>
        <img class="about-img" src="https://images.unsplash.com/photo-1523050854058-8df90110c9f1?auto=format&fit=crop&w=1000&q=80" alt="Bhavans School Campus">
    </div>
</section>

<section id="facilities">
    <h2 class="section-title">Campus Facilities</h2>
    <p class="section-subtitle">State-of-the-art infrastructure designed to foster intellectual curiosity and physical development.</p>

    <div class="cards-grid">
        <div class="card" style="background-image: url('https://images.unsplash.com/photo-1580582932707-520aed937b7b?auto=format&fit=crop&w=800&q=80');">
            <div class="card-content">
                <div class="card-tag">Technology</div>
                <div class="card-title">Smart Classrooms</div>
                <div class="card-desc">Interactive smart boards and modern visual teaching aids in every section.</div>
            </div>
        </div>
        <div class="card" style="background-image: url('https://images.unsplash.com/photo-1532094349884-543bc11b234d?auto=format&fit=crop&w=800&q=80');">
            <div class="card-content">
                <div class="card-tag">Research</div>
                <div class="card-title">Science & Computer Labs</div>
                <div class="card-desc">Advanced Physics, Chemistry, Biology, and ICT labs fostering practical innovation.</div>
            </div>
        </div>
        <div class="card" style="background-image: url('https://images.unsplash.com/photo-1521587760476-6c12a4b040da?auto=format&fit=crop&w=800&q=80');">
            <div class="card-content">
                <div class="card-tag">Knowledge Hub</div>
                <div class="card-title">Digital Library</div>
                <div class="card-desc">Extensive repository with over 8,000+ books, periodicals, and online learning portals.</div>
            </div>
        </div>
        <div class="card" style="background-image: url('https://images.unsplash.com/photo-1461896836934-ffe607ba8211?auto=format&fit=crop&w=800&q=80');">
            <div class="card-content">
                <div class="card-tag">Athletics</div>
                <div class="card-title">Sports Complex</div>
                <div class="card-desc">Expansive sports ground with dedicated cricket, football, and athletics practice fields.</div>
            </div>
        </div>
    </div>
</section>

<section id="principal">
    <h2 class="section-title">Message from the Principal</h2>
    <p class="section-subtitle">Guiding young minds toward academic mastery and ethical excellence.</p>
    
    <div class="principal-box">
        <div class="principal-badge">
            <img src="https://randomuser.me/api/portraits/women/68.jpg" alt="Ms. Sarbani Bose">
            <div class="principal-name">Ms. Sarbani Bose</div>
            <div class="principal-title">Principal, BVM Koradi</div>
        </div>
        <div class="principal-quote">
            "Our motto of 'Roots & Wings' aims for wholesome all-round personality development. We support each child in creating a healthy learning environment that fosters academic rigor, sportsmanship, and moral integrity."
        </div>
    </div>
</section>

<section id="contact">
    <div class="contact-container">
        <div class="contact-info">
            <h3>Contact School Office</h3>
            <p>Reach out to us for admission inquiries, campus visits, or general administrative queries.</p>
            <div class="contact-details">
                <div class="contact-item"><i class="fa-solid fa-location-dot"></i> Nanda, Khaparkheda Road, Koradi, Nagpur - 441111</div>
                <div class="contact-item"><i class="fa-solid fa-phone"></i> +91 9272225522 / +91 8793225522</div>
                <div class="contact-item"><i class="fa-solid fa-envelope"></i> bvmkoradi@gmail.com</div>
            </div>
        </div>
        <form class="contact-form" onsubmit="event.preventDefault(); alert('Thank you! Your message has been sent to Bhavan's Koradi school office.');">
            <div class="form-group">
                <input type="text" placeholder="Parent / Student Name" required>
            </div>
            <div class="form-group">
                <input type="email" placeholder="Email Address" required>
            </div>
            <div class="form-group">
                <textarea rows="4" placeholder="Your Message / Admission Inquiry" required></textarea>
            </div>
            <button type="submit" class="submit-btn">Submit Inquiry</button>
        </form>
    </div>
</section>

<footer>
    <div>© 2026 Bhavan's Bhagwandas Purohit Vidya Mandir, Koradi, Nagpur.</div>
    <div>CBSE Affiliation No. 1130802</div>
</footer>

<script>
window.addEventListener('scroll', function() {
    const navbar = document.getElementById('navbar');
    if (window.scrollY > 50) {
        navbar.classList.add('scrolled');
    } else {
        navbar.classList.remove('scrolled');
    }
});
</script>

</body>
</html>
bhavans_koradi.html
Displaying bhavans_koradi.html.
