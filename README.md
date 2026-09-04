<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BBQ Grill Nights | Authentic Smoked Flavors</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Oswald:wght@500;700&family=Open+Sans:wght@400;600&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* CSS Variables */
        :root {
            --primary-color: #ff4500; /* Flame Orange */
            --secondary-color: #d82c00;
            --dark-bg: #121212;
            --card-bg: #1e1e1e;
            --text-light: #f5f5f5;
            --text-muted: #aaa;
            --font-heading: 'Oswald', sans-serif;
            --font-body: 'Open Sans', sans-serif;
        }

        /* Reset & Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            scroll-behavior: smooth;
        }

        body {
            font-family: var(--font-body);
            background-color: var(--dark-bg);
            color: var(--text-light);
            line-height: 1.6;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        /* Navigation Bar */
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1.2rem 8%;
            background-color: rgba(18, 18, 18, 0.95);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            border-bottom: 2px solid var(--primary-color);
        }

        .logo {
            font-family: var(--font-heading);
            font-size: 1.8rem;
            color: var(--primary-color);
            text-transform: uppercase;
            letter-spacing: 1px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            font-weight: 600;
            text-transform: uppercase;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: var(--primary-color);
        }

        .cta-btn {
            background-color: var(--primary-color);
            color: #fff;
            padding: 0.6rem 1.4rem;
            border: none;
            border-radius: 4px;
            font-weight: bold;
            text-transform: uppercase;
            cursor: pointer;
            transition: background 0.3s, transform 0.2s;
        }

        .cta-btn:hover {
            background-color: var(--secondary-color);
            transform: translateY(-2px);
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), 
                        url('https://images.unsplash.com/photo-1555939594-58d7cb561ad1?auto=format&fit=crop&w=1600&q=80') center/cover no-repeat;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 1rem;
        }

        .hero h1 {
            font-family: var(--font-heading);
            font-size: 4rem;
            text-transform: uppercase;
            margin-bottom: 1rem;
            color: var(--text-light);
            text-shadow: 2px 2px 8px rgba(0,0,0,0.8);
        }

        .hero h1 span {
            color: var(--primary-color);
        }

        .hero p {
            font-size: 1.3rem;
            max-width: 600px;
            margin-bottom: 2rem;
            color: var(--text-muted);
        }

        /* Section Global Styling */
        section {
            padding: 5rem 8%;
        }

        .section-title {
            text-align: center;
            font-family: var(--font-heading);
            font-size: 2.5rem;
            text-transform: uppercase;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            width: 80px;
            height: 4px;
            background-color: var(--primary-color);
            display: block;
            margin: 10px auto 0;
            border-radius: 2px;
        }

        /* Menu Section */
        .menu-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .menu-card {
            background-color: var(--card-bg);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
            transition: transform 0.3s;
        }

        .menu-card:hover {
            transform: translateY(-5px);
        }

        .menu-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .menu-card-content {
            padding: 1.5rem;
        }

        .menu-card-title {
            display: flex;
            justify-content: space-between;
            font-family: var(--font-heading);
            font-size: 1.4rem;
            margin-bottom: 0.5rem;
        }

        .price {
            color: var(--primary-color);
        }

        .menu-card-desc {
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        /* About Section */
        .about-container {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 3rem;
        }

        .about-img {
            flex: 1 1 400px;
            border-radius: 8px;
            overflow: hidden;
            border: 3px solid var(--primary-color);
        }

        .about-img img {
            width: 100%;
            height: auto;
            display: block;
        }

        .about-text {
            flex: 1 1 400px;
        }

        .about-text h3 {
            font-family: var(--font-heading);
            font-size: 2rem;
            margin-bottom: 1rem;
            color: var(--primary-color);
        }

        .about-text p {
            margin-bottom: 1rem;
            color: var(--text-muted);
        }

        /* Reservation / Contact Section */
        .reservation-form {
            max-width: 600px;
            margin: 0 auto;
            background-color: var(--card-bg);
            padding: 2.5rem;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.5);
        }

        .form-group {
            margin-bottom: 1.2rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .form-group input, 
        .form-group select, 
        .form-group textarea {
            width: 100%;
            padding: 0.8rem;
            border-radius: 4px;
            border: 1px solid #333;
            background-color: #2a2a2a;
            color: #fff;
            font-family: inherit;
        }

        .form-group input:focus, 
        .form-group select:focus, 
        .form-group textarea:focus {
            outline: none;
            border-color: var(--primary-color);
        }

        .submit-btn {
            width: 100%;
            padding: 1rem;
            background-color: var(--primary-color);
            color: #fff;
            border: none;
            border-radius: 4px;
            font-family: var(--font-heading);
            font-size: 1.2rem;
            text-transform: uppercase;
            cursor: pointer;
            transition: background 0.3s;
        }

        .submit-btn:hover {
            background-color: var(--secondary-color);
        }

        /* Success Message */
        #form-message {
            display: none;
            margin-top: 1rem;
            padding: 1rem;
            background-color: #2e7d32;
            color: #fff;
            text-align: center;
            border-radius: 4px;
        }

        /* Footer */
        footer {
            background-color: #0a0a0a;
            text-align: center;
            padding: 2rem 1rem;
            border-top: 1px solid #222;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 1rem;
        }

        .social-links a {
            font-size: 1.5rem;
            color: var(--text-muted);
            transition: color 0.3s;
        }

        .social-links a:hover {
            color: var(--primary-color);
        }

        footer p {
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        /* Mobile Menu Toggle */
        .menu-toggle {
            display: none;
            font-size: 1.8rem;
            cursor: pointer;
        }

        /* Responsive Media Queries */
        @media (max-width: 768px) {
            .menu-toggle {
                display: block;
            }

            .nav-links {
                display: none;
                flex-direction: column;
                position: absolute;
                top: 100%;
                left: 0;
                width: 100%;
                background-color: var(--dark-bg);
                padding: 1rem 0;
                text-align: center;
                border-bottom: 2px solid var(--primary-color);
            }

            .nav-links.active {
                display: flex;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero p {
                font-size: 1rem;
            }
        }
    </style>
</head>
<body>

    <!-- Header / Navbar -->
    <nav class="navbar">
        <div class="logo">
            <i class="fa-solid fa-fire-flame-curved"></i> BBQ Grill Nights
        </div>
        <div class="menu-toggle" id="mobile-menu">
            <i class="fa-solid fa-bars"></i>
        </div>
        <ul class="nav-links" id="nav-list">
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About Us</a></li>
            <li><a href="#menu">Menu</a></li>
            <li><a href="#reservations">Reservations</a></li>
        </ul>
        <a href="#reservations"><button class="cta-btn">Book Table</button></a>
    </nav>

    <!-- Hero Section -->
    <header class="hero" id="home">
        <h1>Welcome to <span>BBQ Grill Nights</span></h1>
        <p>Savor the authentic taste of slow-smoked meats, flame-grilled specialties, and unforgettable evening vibes.</p>
        <a href="#menu"><button class="cta-btn" style="font-size: 1.1rem; padding: 0.8rem 2rem;">Explore Menu</button></a>
    </header>

    <!-- About Section -->
    <section id="about">
        <h2 class="section-title">Our Story</h2>
        <div class="about-container">
            <div class="about-img">
                <img src="https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=800&q=80" alt="BBQ Chef Grilling">
            </div>
            <div class="about-text">
                <h3>Smoked Low & Slow, Served Fresh Daily</h3>
                <p>At BBQ Grill Nights, we believe that true barbecue takes time, patience, and passion. Our pitmasters work around the clock using premium hardwood charcoal to deliver deep, smoky flavors to every plate.</p>
                <p>Whether you are here for our signature tender ribs, juicy flame-grilled burgers, or fresh grilled sides, we guarantee an unmatchable dining atmosphere under the stars.</p>
            </div>
        </div>
    </section>

    <!-- Menu Section -->
    <section id="menu">
        <h2 class="section-title">Featured Menu</h2>
        <div class="menu-grid">
            <!-- Item 1 -->
            <div class="menu-card">
                <img src="https://images.unsplash.com/photo-1529193591184-b1d58069ecdd?auto=format&fit=crop&w=600&q=80" alt="Smoked Ribs">
                <div class="menu-card-content">
                    <div class="menu-card-title">
                        <span>Smoked Baby Back Ribs</span>
                        <span class="price">$24.99</span>
                    </div>
                    <p class="menu-card-desc">Slow-smoked pork ribs glazed with our house signature sweet and spicy BBQ sauce.</p>
                </div>
            </div>
            <!-- Item 2 -->
            <div class="menu-card">
                <img src="https://images.unsplash.com/photo-1568901346375-23c9450c58cd?auto=format&fit=crop&w=600&q=80" alt="BBQ Burger">
                <div class="menu-card-content">
                    <div class="menu-card-title">
                        <span>The Ultimate BBQ Burger</span>
                        <span class="price">$16.50</span>
                    </div>
                    <p class="menu-card-desc">Flame-grilled beef patty topped with smoked bacon, cheddar cheese, and crispy onion rings.</p>
                </div>
            </div>
            <!-- Item 3 -->
            <div class="menu-card">
                <img src="https://images.unsplash.com/photo-1532550907401-a500c9a57435?auto=format&fit=crop&w=600&q=80" alt="Grilled Steak">
                <div class="menu-card-content">
                    <div class="menu-card-title">
                        <span>Flame-Grilled Ribeye</span>
                        <span class="price">$29.99</span>
                    </div>
                    <p class="menu-card-desc">Prime cut ribeye steak grilled over open hardwood flames, served with garlic herb butter.</p>
                </div>
            </div>
            <!-- Item 4 -->
            <div class="menu-card">
                <img src="https://images.unsplash.com/photo-1598515214211-89d3c73ae83b?auto=format&fit=crop&w=600&q=80" alt="Grilled Chicken Skewers">
                <div class="menu-card-content">
                    <div class="menu-card-title">
                        <span>Smoked Chicken Skewers</span>
                        <span class="price">$14.99</span>
                    </div>
                    <p class="menu-card-desc">Marinated chicken breast skewers grilled with bell peppers, onions, and smoky seasoning.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Reservations Section -->
    <section id="reservations">
        <h2 class="section-title">Reserve a Table</h2>
        <div class="reservation-form">
            <form id="booking-form">
                <div class="form-group">
                    <label for="name">Full Name</label>
                    <input type="text" id="name" required placeholder="John Doe">
                </div>
                <div class="form-group">
                    <label for="email">Email Address</label>
                    <input type="email" id="email" required placeholder="john@example.com">
                </div>
                <div class="form-group">
                    <label for="guests">Number of Guests</label>
                    <select id="guests" required>
                        <option value="2">2 People</option>
                        <option value="4">4 People</option>
                        <option value="6">6 People</option>
                        <option value="8+">8+ People (Party)</option>
                    </select>
                </div>
                <div class="form-group">
                    <label for="date">Date & Time</label>
                    <input type="datetime-local" id="date" required>
                </div>
                <button type="submit" class="submit-btn">Confirm Reservation</button>
            </form>
            <div id="form-message">Thank you! Your table reservation at BBQ Grill Nights is confirmed.</div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="social-links">
            <a href="#"><i class="fa-brands fa-facebook"></i></a>
            <a href="#"><i class="fa-brands fa-instagram"></i></a>
            <a href="#"><i class="fa-brands fa-twitter"></i></a>
        </div>
        <p>&copy; 2026 BBQ Grill Nights. All Rights Reserved.</p>
    </footer>

    <!-- JavaScript Logic -->
    <script>
        // Toggle Mobile Navigation Menu
        const mobileMenu = document.getElementById('mobile-menu');
        const navList = document.getElementById('nav-list');

        mobileMenu.addEventListener('click', () => {
            navList.classList.toggle('active');
        });

        // Close mobile nav when clicking a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navList.classList.remove('active');
            });
        });

        // Handle Reservation Form Submission
        const bookingForm = document.getElementById('booking-form');
        const formMessage = document.getElementById('form-message');

        bookingForm.addEventListener('submit', function(e) {
            e.preventDefault(); // Prevent standard page refresh
            
            // Show confirmation message
            formMessage.style.display = 'block';
            
            // Reset form fields
            bookingForm.reset();

            // Hide confirmation message after 5 seconds
            setTimeout(() => {
                formMessage.style.display = 'none';
            }, 5000);
        });
    </script>
</body>
</html>
