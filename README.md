# CSS Layouts and Responsive Design

## Objectives

Implement Flexbox and Grid for layout design.
Make the webpage responsive using media queries.
Ensure proper alignment and spacing.

## Instructions

- use Flexbox or CSS Grid.
- Add a navigation bar and structure the content.
- Use media queries to adjust layout for mobile, tablet, and desktop.
Get App
# CSS Layouts and Responsive Design

## Objectives

Implement Flexbox and Grid for layout design.
Make the webpage responsive using media queries.
Ensure proper alignment and spacing.

## Instructions

- use Flexbox or CSS Grid.
- Add a navigation bar and structure the content.
- Use media queries to adjust layout for mobile, tablet, and desktop.

>[!NOTE]
>  - Include at least:
>  - navigation bar
>  - media queries

# Tasks

- Apply Flexbox or Grid for layout.
- Make the page responsive.
- Test across different screen sizes.

Happy Coding! 💻✨
CSS Layouts and Responsive Design Implementation
I'll create a responsive webpage using both Flexbox and CSS Grid with a navigation bar and media queries for different screen sizes.

HTML Structure
html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Design Demo</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <nav class="navbar">
            <div class="logo">MySite</div>
            <ul class="nav-links">
                <li><a href="#">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Services</a></li>
                <li><a href="#">Portfolio</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
            <div class="burger">
                <div class="line1"></div>
                <div class="line2"></div>
                <div class="line3"></div>
            </div>
        </nav>
    </header>

    <main class="grid-container">
        <section class="hero">
            <h1>Welcome to Our Website</h1>
            <p>Discover amazing features and services</p>
            <button class="cta-button">Learn More</button>
        </section>

        <section class="features">
            <article class="feature-card">
                <h2>Feature One</h2>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
            </article>
            <article class="feature-card">
                <h2>Feature Two</h2>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
            </article>
            <article class="feature-card">
                <h2>Feature Three</h2>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
            </article>
        </section>

        <aside class="sidebar">
            <h3>News & Updates</h3>
            <ul>
                <li>Latest product release</li>
                <li>Upcoming events</li>
                <li>Team members</li>
            </ul>
        </aside>

        <section class="content">
            <h2>Main Content Area</h2>
            <p>This is the primary content section of the webpage.</p>
        </section>
    </main>

    <footer>
        <p>&copy; 2023 MySite. All rights reserved.</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>


CSS Styles (styles.css)
css
/* Base Styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Arial', sans-serif;
    line-height: 1.6;
    color: #333;
}

/* Navigation Bar - Using Flexbox */
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    background-color: #2c3e50;
    color: white;
}

.logo {
    font-size: 1.5rem;
    font-weight: bold;
}

.nav-links {
    display: flex;
    list-style: none;
}

.nav-links li {
    margin-left: 2rem;
}

.nav-links a {
    color: white;
    text-decoration: none;
    transition: color 0.3s;
}

.nav-links a:hover {
    color: #3498db;
}

.burger {
    display: none;
    cursor: pointer;
}

.burger div {
    width: 25px;
    height: 3px;
    background-color: white;
    margin: 5px;
    transition: all 0.3s ease;
}

/* Main Content - Using CSS Grid */
.grid-container {
    display: grid;
    grid-template-columns: 1fr 3fr;
    grid-template-areas:
        "hero hero"
        "sidebar content"
        "features features";
    gap: 1.5rem;
    padding: 2rem;
}

.hero {
    grid-area: hero;
    background-color: #3498db;
    color: white;
    padding: 3rem;
    text-align: center;
    border-radius: 8px;
}

.sidebar {
    grid-area: sidebar;
    background-color: #f1f1f1;
    padding: 1.5rem;
    border-radius: 8px;
}

.content {
    grid-area: content;
    padding: 1.5rem;
    background-color: #fff;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.features {
    grid-area: features;
    display: flex;
    justify-content: space-between;
    gap: 1.5rem;
}

.feature-card {
    flex: 1;
    padding: 1.5rem;
    background-color: #fff;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    text-align: center;
}

.cta-button {
    padding: 0.8rem 1.5rem;
    background-color: #e74c3c;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 1rem;
    margin-top: 1rem;
    transition: background-color 0.3s;
}

.cta-button:hover {
    background-color: #c0392b;
}

footer {
    text-align: center;
    padding: 1.5rem;
    background-color: #2c3e50;
    color: white;
}

/* Media Queries for Responsive Design */

/* Tablet View */
@media screen and (max-width: 768px) {
    .grid-container {
        grid-template-columns: 1fr;
        grid-template-areas:
            "hero"
            "content"
            "sidebar"
            "features";
    }
    
    .features {
        flex-direction: column;
    }
    
    .nav-links {
        position: absolute;
        right: 0;
        top: 70px;
        background-color: #2c3e50;
        flex-direction: column;
        align-items: center;
        width: 100%;
        transform: translateX(100%);
        transition: transform 0.5s ease-in;
    }
    
    .nav-links.active {
        transform: translateX(0);
    }
    
    .burger {
        display: block;
    }
    
    .nav-links li {
        margin: 1.5rem 0;
    }
}

/* Mobile View */
@media screen and (max-width: 480px) {
    .navbar {
        padding: 1rem;
    }
    
    .hero {
        padding: 2rem 1rem;
    }
    
    .feature-card {
        padding: 1rem;
    }
}

/* Animation for burger menu */
.toggle .line1 {
    transform: rotate(-45deg) translate(-5px, 6px);
}
.toggle .line2 {
    opacity: 0;
}
.toggle .line3 {
    transform: rotate(45deg) translate(-5px, -6px);
}

JavaScript for Mobile Menu (script.js)
javascript
document.addEventListener('DOMContentLoaded', function() {
    const burger = document.querySelector('.burger');
    const navLinks = document.querySelector('.nav-links');
    
    burger.addEventListener('click', function() {
        // Toggle nav
        navLinks.classList.toggle('active');
        
        // Burger animation
        burger.classList.toggle('toggle');
    });
});

>[!NOTE]
>  - Include at least:
>  - navigation bar
>  - media queries

# Tasks

- Apply Flexbox or Grid for layout.
- Make the page responsive.
- Test across different screen sizes.

Happy Coding! 💻✨
