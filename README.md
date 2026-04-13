<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RODS Construction Corporation | Building Excellence</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', 'Roboto', sans-serif;
            background: #f0f2f5;
            color: #2d3436;
            min-height: 100vh;
            padding: 2rem;
            position: relative;
        }

        /* Modern industrial background */
        body::before {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-image: 
                linear-gradient(135deg, rgba(45, 52, 54, 0.03) 25%, transparent 25%),
                linear-gradient(225deg, rgba(45, 52, 54, 0.03) 25%, transparent 25%);
            background-size: 60px 60px;
            z-index: -1;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 2.5rem;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.1);
            border: 1px solid rgba(255, 255, 255, 0.3);
        }

        .header {
            text-align: center;
            margin-bottom: 2.5rem;
            padding-bottom: 1.5rem;
            border-bottom: 3px solid #d63031; /* Construction Red Accent */
        }

        .header h1 {
            font-size: 2.8rem;
            font-weight: 800;
            letter-spacing: -1px;
            color: #2d3436;
            margin-bottom: 0.5rem;
            text-transform: uppercase;
        }

        .header h1 span {
            font-weight: 300;
            font-size: 1.5rem;
            display: block;
            color: #636e72;
            letter-spacing: 4px;
            margin-top: 0.25rem;
        }

        .header p {
            font-size: 1.1rem;
            color: #636e72;
            max-width: 700px;
            margin: 1rem auto 0;
            line-height: 1.6;
        }

        .menu {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-bottom: 2.5rem;
            flex-wrap: wrap;
        }

        .menu a {
            color: #2d3436;
            text-decoration: none;
            font-size: 0.85rem;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1.5px;
            padding: 0.8rem 1.5rem;
            background: #dfe6e9;
            border-radius: 8px;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .menu a:hover {
            background: #d63031;
            color: white;
            transform: translateY(-2px);
        }

        .menu a.active {
            background: #2d3436;
            color: white;
        }

        .section-title {
            font-size: 1.8rem;
            font-weight: 700;
            color: #2d3436;
            margin: 1.5rem 0 1rem;
            text-transform: uppercase;
            border-left: 5px solid #d63031;
            padding-left: 1rem;
        }

        .section-subtitle {
            color: #636e72;
            margin-bottom: 1.5rem;
            font-size: 1rem;
        }

        .collapsible-container {
            margin: 2rem 0;
        }

        .collapsible-box {
            background: white;
            border: 1px solid #dfe6e9;
            border-radius: 12px;
            margin-bottom: 1rem;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .collapsible-box:hover {
            border-color: #d63031;
            box-shadow: 0 10px 20px rgba(0,0,0,0.05);
        }

        .box-header {
            padding: 1.2rem 1.8rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: space-between;
        }

        .box-header h3 {
            font-size: 1.1rem;
            font-weight: 700;
            color: #2d3436;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .icon-circle {
            width: 35px;
            height: 35px;
            background: #f1f2f6;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.1rem;
        }

        .box-icon {
            font-size: 1.2rem;
            color: #b2bec3;
            transition: transform 0.3s ease;
        }

        .box-icon.expanded {
            transform: rotate(90deg);
            color: #d63031;
        }

        .box-content {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.5s ease-out;
        }

        .box-content.expanded {
            max-height: 1000px;
        }

        .inner-content {
            padding: 0 1.8rem 1.5rem 1.8rem;
            border-top: 1px solid #f1f2f6;
        }

        .inner-content p {
            font-size: 0.95rem;
            line-height: 1.6;
            color: #636e72;
            margin: 1rem 0;
        }

        .inner-content ul {
            list-style: none;
        }

        .inner-content li {
            padding: 0.4rem 0 0.4rem 1.5rem;
            position: relative;
            color: #2d3436;
            font-size: 0.9rem;
        }

        .inner-content li:before {
            content: "→";
            position: absolute;
            left: 0;
            color: #d63031;
            font-weight: bold;
        }

        .info-card {
            background: #2d3436;
            color: white;
            border-radius: 15px;
            padding: 2rem;
            margin: 2rem 0;
            display: flex;
            justify-content: space-around;
            text-align: center;
            flex-wrap: wrap;
            gap: 2rem;
        }

        .stat-number {
            font-size: 2.2rem;
            font-weight: 800;
            color: #d63031;
        }

        .stat-label {
            font-size: 0.7rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            color: #b2bec3;
        }

        .badge-container {
            display: flex;
            justify-content: center;
            gap: 0.8rem;
            flex-wrap: wrap;
            margin-top: 2rem;
        }

        .badge {
            background: #2d3436;
            color: white;
            padding: 0.4rem 1rem;
            border-radius: 4px;
            font-size: 0.7rem;
            font-weight: 600;
            text-transform: uppercase;
        }

        .footer {
            margin-top: 3rem;
            padding-top: 1.5rem;
            text-align: center;
            border-top: 1px solid #dfe6e9;
            font-size: 0.9rem;
            color: #636e72;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .content-wrapper {
            animation: fadeIn 0.4s ease-out;
        }

        @media (max-width: 650px) {
            .header h1 { font-size: 1.8rem; }
            .container { padding: 1.2rem; }
            .menu { gap: 0.5rem; }
            .menu a { padding: 0.6rem 1rem; width: 100%; text-align: center; }
        }
    </style>
</head>
<body>
    <div class="container" id="app">
        <div class="header">
            <h1>RODS Construction<span>CORPORATION</span></h1>
            <p>Constructing the foundations of tomorrow with integrity, precision, and world-class engineering standards.</p>
        </div>

        <div class="menu" id="navMenu">
            <a class="nav-link active" data-page="about">🏗️ About Us</a>
            <a class="nav-link" data-page="services">🛠️ Services</a>
            <a class="nav-link" data-page="projects">🏢 Projects</a>
            <a class="nav-link" data-page="contact">📞 Contact</a>
        </div>

        <div id="dynamicContent">
            </div>

        <div class="badge-container">
            <span class="badge">ISO Certified</span>
            <span class="badge">Safety First</span>
            <span class="badge">Quality Guaranteed</span>
            <span class="badge">On-Time Delivery</span>
        </div>

        <div class="footer">
            <p>&copy; 2026 RODS Construction Corporation. All Rights Reserved.</p>
            <p style="margin-top: 5px; font-size: 0.7rem;">BUILDING BEYOND BOUNDARIES</p>
        </div>
    </div>

    <script>
        const contentMap = {
            about: `
                <div class="content-wrapper">
                    <div class="section-title">Who We Are</div>
                    <div class="section-subtitle">A legacy of strength and reliability in the construction industry.</div>
                    <div class="collapsible-container">
                        <div class="collapsible-box">
                            <div class="box-header">
                                <h3><div class="icon-circle">📜</div> Our Mission</h3>
                                <span class="box-icon">→</span>
                            </div>
                            <div class="box-content">
                                <div class="inner-content">
                                    <p>To provide high-quality construction services that exceed client expectations while maintaining the highest levels of professionalism and safety.</p>
                                </div>
                            </div>
                        </div>
                        <div class="collapsible-box">
                            <div class="box-header">
                                <h3><div class="icon-circle">💎</div> Core Values</h3>
                                <span class="box-icon">→</span>
                            </div>
                            <div class="box-content">
                                <div class="inner-content">
                                    <ul>
                                        <li><b>Integrity:</b> Honest and transparent business practices.</li>
                                        <li><b>Excellence:</b> Uncompromising quality in every square meter.</li>
                                        <li><b>Safety:</b> Ensuring a zero-accident environment for our workforce.</li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="info-card">
                        <div><div class="stat-number">15+</div><div class="stat-label">Years Experience</div></div>
                        <div><div class="stat-number">200+</div><div class="stat-label">Projects Completed</div></div>
                    </div>
                </div>`,
            
            services: `
                <div class="content-wrapper">
                    <div class="section-title">Our Expertise</div>
                    <div class="section-subtitle">Comprehensive construction solutions tailored to your needs.</div>
                    <div class="collapsible-container">
                        <div class="collapsible-box">
                            <div class="box-header">
                                <h3><div class="icon-circle">🏠</div> Residential Construction</h3>
                                <span class="box-icon">→</span>
                            </div>
                            <div class="box-content">
                                <div class="inner-content">
                                    <p>Building dream homes with modern designs and sustainable materials. From luxury villas to high-rise condominiums.</p>
                                </div>
                            </div>
                        </div>
                        <div class="collapsible-box">
                            <div class="box-header">
                                <h3><div class="icon-circle">🏢</div> Commercial & Industrial</h3>
                                <span class="box-icon">→</span>
                            </div>
                            <div class="box-content">
                                <div class="inner-content">
                                    <p>Specializing in office buildings, warehouses, and manufacturing plants designed for maximum efficiency.</p>
                                </div>
                            </div>
                        </div>
                        <div class="collapsible-box">
                            <div class="box-header">
                                <h3><div class="icon-circle">🛣️</div> Infrastructure</h3>
                                <span class="box-icon">→</span>
                            </div>
                            <div class="box-content">
                                <div class="inner-content">
                                    <p>Roadworks, bridges, and drainage systems that connect communities and stand the test of time.</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>`,

            projects: `
                <div class="content-wrapper">
                    <div class="section-title">Recent Portfolio</div>
                    <div class="section-subtitle">Showcasing our commitment to structural excellence.</div>
                    <div class="collapsible-container">
                        <div class="collapsible-box">
                            <div class="box-header">
                                <h3><div class="icon-circle">📍</div> Metro Business Center</h3>
                                <span class="box-icon">→</span>
                            </div>
                            <div class="box-content">
                                <div class="inner-content">
                                    <p>A 25-story green-certified office tower completed ahead of schedule in the heart of the business district.</p>
                                </div>
                            </div>
                        </div>
                        <div class="collapsible-box">
                            <div class="box-header">
                                <h3><div class="icon-circle">📍</div> Northside Bridge Expansion</h3>
                                <span class="box-icon">→</span>
                            </div>
                            <div class="box-content">
                                <div class="inner-content">
                                    <p>Major infrastructure upgrade involving complex structural retrofitting and advanced load testing.</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>`,

            contact: `
                <div class="content-wrapper">
                    <div class="section-title">Get In Touch</div>
                    <div class="section-subtitle">Let's start building your vision today.</div>
                    <div class="info-card" style="background: #f1f2f6; color: #2d3436;">
                        <div style="text-align: left; width: 100%;">
                            <p><b>📍 Head Office:</b> 123 Construction Way, Engineering Plaza</p>
                            <p style="margin-top: 10px;"><b>📧 Email:</b> contact@rodsconstruction.com</p>
                            <p style="margin-top: 10px;"><b>📞 Phone:</b> +63 (02) 888-RODS</p>
                        </div>
                    </div>
                </div>`
        };

        function toggleBox(header) {
            const content = header.nextElementSibling;
            const icon = header.querySelector('.box-icon');
            content.classList.toggle('expanded');
            icon.classList.toggle('expanded');
        }

        function navigateTo(pageId) {
            const container = document.getElementById('dynamicContent');
            container.innerHTML = contentMap[pageId];
            
            document.querySelectorAll('.nav-link').forEach(link => {
                link.classList.toggle('active', link.dataset.page === pageId);
            });

            // Attach event listeners to new elements
            document.querySelectorAll('.box-header').forEach(header => {
                header.addEventListener('click', () => toggleBox(header));
            });
        }

        // Initialize
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', () => navigateTo(link.dataset.page));
        });

        window.onload = () => navigateTo('about');
    </script>
</body>
</html>
