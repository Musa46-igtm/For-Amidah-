<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For Amidah</title>
    <style>
        /* General Reset */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(to top, #001f3f, #00111a); /* Gradient background */
            color: #f3f3f3;
            overflow-x: hidden;
        }

        /* Navbar */
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            background-color: rgba(0, 0, 0, 0.8);
            position: sticky;
            top: 0;
            z-index: 1000;
            transition: all 0.3s ease;
        }

        .navbar.shrink {
            padding: 10px;
            background-color: rgba(0, 0, 0, 0.9);
        }

        .navbar .logo {
            font-size: 2em;
            color: #00c7a0;
            font-weight: bold;
            text-align: center;  
            text-transform: uppercase;
            letter-spacing: 1.5px;
        }

        /* Hamburger Menu */
        .hamburger {
            display: none;
            flex-direction: column;
            cursor: pointer;
        }

        .hamburger span {
            background-color: #f3f3f3;
            width: 25px;
            height: 3px;
            margin: 4px 0;
            transition: 0.3s;
        }

        .nav-links {
            list-style: none;
            display: flex;
            gap: 20px;
        }

        .nav-links li a {
            text-decoration: none;
            color: #f3f3f3;
            font-size: 1.2em;
            transition: color 0.3s ease;
        }

        .nav-links li a:hover {
            color: #00c7a0;
        }

        /* Hero Section */
        .hero {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background: linear-gradient(to bottom, #001f3f, #00111a);
            text-align: center;
            color: #f3f3f3;
            padding: 20px;
        }

        .hero h1 {
            font-size: 4em;
            font-weight: 700;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.7);
            margin-bottom: 20px;
        }

        .hero p {
            font-size: 1.8em;
        }

        /* Why You're Amazing Section */
        .why-amazing {
            text-align: center;
            padding: 50px 20px;
            background: #00c7a0;
            color: #fff;
        }

        .why-amazing button {
            padding: 12px 30px;
            margin-top: 20px;
            font-size: 1.1em;
            border: none;
            background: #005f46;
            color: white;
            border-radius: 5px;
            cursor: pointer;
            transition: transform 0.2s;
        }

        .why-amazing button:hover {
            transform: scale(1.1);
        }

        /* Compliment Animation */
        .compliment-animation {
            margin-top: 20px;
            font-size: 1.2em;
            opacity: 0;
            transition: opacity 0.5s ease;
        }

        /* Gallery Section */
        .gallery {
            padding: 50px 20px;
            background: #002e3f;
            color: #f3f3f3;
            text-align: center;
        }

        .gallery-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            margin-top: 20px;
        }

        .gallery-grid img {
            width: 100%;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.5);
            transition: transform 0.3s;
        }

        .gallery-grid img:hover {
            transform: scale(1.05);
        }

        /* Personal Note Section */
        .personal-note {
            text-align: center;
            padding: 50px 20px;
            background: #00111a;
            color: #f3f3f3;
        }

        .personal-note h2 {
            font-size: 2.5em;
            margin-bottom: 20px;
        }

        .personal-note p {
            font-size: 1.5em;
            line-height: 1.6;
        }

        /* Footer */
        footer {
            padding: 20px;
            text-align: center;
            background: #00111a;
            color: #999;
        }

        footer .social-links a {
            color: #00c7a0;
            margin: 0 10px;
            text-decoration: none;
            transition: color 0.3s;
        }

        footer .social-links a:hover {
            color: #f3f3f3;
        }

        /* Mobile Styles */
        @media (max-width: 768px) {
            .navbar .nav-links {
                display: none;
                width: 100%;
                text-align: center;
                background-color: rgba(0, 0, 0, 0.8);
                position: absolute;
                top: 60px;
                left: 0;
                padding: 20px 0;
            }

            .navbar .nav-links.active {
                display: block;
            }

            .hamburger {
                display: flex;
            }
        }
    </style>
    <script>
        // Compliment List
        const compliments = [
            "You fight a lot sometimes, i am sorry if that hurts.",
            "You do not usually say sorry.",
            "You have an incredible sense of humor.",
            "You are kind usually.",
            "You're truly one of a Friend, Amidah."
        ];

        // Show Random Compliment
        function showCompliment() {
            const randomIndex = Math.floor(Math.random() * compliments.length);
            const complimentElement = document.getElementById("compliment");
            complimentElement.textContent = compliments[randomIndex];
            complimentElement.style.opacity = 1; // Fade-in effect
        }

        // Typewriter Effect
        const typewriterText = "Welcome, Amidah!";
        let charIndex = 0;

        function typeWriterEffect() {
            const typewriterElement = document.getElementById("typewriter");
            if (charIndex < typewriterText.length) {
                typewriterElement.innerHTML += typewriterText.charAt(charIndex);
                charIndex++;
                setTimeout(typeWriterEffect, 100);
            }
        }

        // Navbar Toggle for Mobile View
        function toggleMenu() {
            const navLinks = document.querySelector('.nav-links');
            navLinks.classList.toggle('active');
        }

        // Shrinking Navbar on Scroll
        window.addEventListener("scroll", () => {
            const navbar = document.getElementById("navbar");
            if (window.scrollY > 50) {
                navbar.classList.add("shrink");
            } else {
                navbar.classList.remove("shrink");
            }
        });

        // Initialize Typewriter
        window.onload = typeWriterEffect;
    </script>
</head>
<body>
    <!-- Navigation Bar -->
    <nav class="navbar" id="navbar">
        <div class="logo">Special for Amidah</div>
        <div class="hamburger" onclick="toggleMenu()">
            <span></span>
            <span></span>
            <span></span>
        </div>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#why-amazing">Why You're Amazing</a></li>
            <li><a href="#gallery">Gallery</a></li>
            <li><a href="#note">Personal Note</a></li>
        </ul>
    </nav>

    <!-- Home Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1 id="typewriter"></h1>
            <p>This is a world made just for you—where you shine the brightest!</p>
        </div>
    </section>

    <!-- Why You're Amazing Section -->
    <section id="why-amazing" class="why-amazing">
        <h2>Why You're Amazing</h2>
        <p>Click the button below to find out all the reasons you're truly special:</p>
        <button onclick="showCompliment()">Discover More</button>
        <p id="compliment" class="compliment-animation"></p>
    </section>

    <!-- Gallery Section -->
    <section id="gallery" class="gallery">
        <h2>Gallery of Joy</h2>
        <p>Here are some beautiful visuals inspired by you:</p>
        <div class="gallery-grid">
            <img src="file-A7ifnZHxrBFbHF3Le9XMbP.webp" alt="Pixel Sunset">
            <img src="IMG-20250124-WA0002.jpg" alt="Pixel Forest">
            <img src="IMG-20250124-WA0003.jpg" alt="Pixel Waterfall">
            <img src="IMG-20250124-WA0005.jpg" alt="Pixel Mountains">
        </div>
    </section>

    <!-- Personal Note Section -->
    <section id="note" class="personal-note">
        <h2>A Personal Note</h2>
        <p>
            Dear Amidah,<br>
            This website is a small piece of what I admire about you. From your beautiful voice to your incredible personality, 
            you bring so much light into the world. I hope this makes you smile as much as you make me happy.
        </p>
    </section>

    <!-- Footer -->
    <footer>
        <p>Created with ❤️ by Musa</p>
        <div class="social-links">
            <a href="https://facebook.com/Young Xboy">Facebook</a>
            <a href="#">LinkedIn</a>
            <a href="#">Twitter</a>
        </div>
    </footer>
</body>
</html>
