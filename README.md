<html lang="en"><head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Astro Barbie Tarot | Celestial Guidance &amp; Mystical Readings</title>
    <link href="https://fonts.googleapis.com/css2?family=Pacifico&amp;family=Fredoka+One&amp;family=Righteous&amp;family=Poppins:wght@300;400;500;600&amp;display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --hot-pink: #E0218A;
            --barbie-pink: #FF1493;
            --light-pink: #FF69B4;
            --soft-pink: #FFB6D9;
            --pink-glow: #FFB6C1;
            --gold: #FFD700;
            --purple: #DA70D6;
            --white: #FFFFFF;
            --cream: #FFF8F0;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #FF1493 0%, #FF69B4 25%, #FFB6D9 50%, #FF69B4 75%, #FF1493 100%);
            color: var(--white);
            overflow-x: hidden;
            position: relative;
        }

        /* Animated starry background */
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }

        .star {
            position: absolute;
            background: white;
            border-radius: 50%;
            animation: twinkle 3s infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.2); }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: linear-gradient(135deg, #E0218A 0%, #FF1493 100%);
            backdrop-filter: blur(10px);
            padding: 1rem 2rem;
            z-index: 1000;
            box-shadow: 0 6px 30px rgba(224, 33, 138, 0.6), 0 0 40px rgba(255, 105, 180, 0.4);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: 'Fredoka One', cursive;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--white);
            text-shadow: 3px 3px 6px rgba(224, 33, 138, 0.6), 0 0 20px rgba(255, 182, 217, 0.8);
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: var(--white);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: var(--gold);
            text-shadow: 0 0 10px rgba(255, 215, 0, 0.5);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gold);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 6rem 2rem 4rem;
            position: relative;
            background: radial-gradient(circle at 50% 50%, rgba(255, 20, 147, 0.4) 0%, rgba(255, 105, 180, 0.3) 50%, transparent 70%);
        }

        .hero-content {
            position: relative;
            z-index: 10;
            max-width: 900px;
        }

        .hero h1 {
            font-family: 'Pacifico', cursive;
            font-size: 5rem;
            font-weight: 700;
            color: var(--white);
            margin-bottom: 1rem;
            text-shadow: 4px 4px 8px rgba(224, 33, 138, 0.8), 0 0 60px rgba(255, 182, 217, 0.9), 0 0 80px rgba(255, 20, 147, 0.6);
            animation: float 4s ease-in-out infinite;
        }

        .hero .tagline {
            font-family: 'Righteous', cursive;
            font-size: 1.5rem;
            color: var(--white);
            margin-bottom: 1.5rem;
            font-weight: 400;
            letter-spacing: 2px;
            text-shadow: 2px 2px 4px rgba(224, 33, 138, 0.6);
        }

        .hero .welcome {
            font-size: 1.1rem;
            line-height: 1.8;
            margin-bottom: 2.5rem;
            color: var(--cream);
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }

        .cta-buttons {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 1rem 2.5rem;
            font-size: 1.1rem;
            font-weight: 600;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            position: relative;
            overflow: hidden;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--barbie-pink), var(--purple));
            color: var(--white);
            box-shadow: 0 4px 20px rgba(255, 105, 180, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 30px rgba(255, 105, 180, 0.6);
        }

        .btn-secondary {
            background: transparent;
            color: var(--gold);
            border: 2px solid var(--gold);
            box-shadow: 0 4px 20px rgba(255, 215, 0, 0.2);
        }

        .btn-secondary:hover {
            background: var(--gold);
            color: var(--deep-blue);
            transform: translateY(-3px);
            box-shadow: 0 6px 30px rgba(255, 215, 0, 0.4);
        }

        /* Moon decoration */
        .moon {
            position: absolute;
            top: 15%;
            right: 10%;
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--soft-pink) 0%, var(--light-pink) 100%);
            box-shadow: 0 0 60px rgba(255, 182, 193, 0.6), inset -10px -10px 30px rgba(0, 0, 0, 0.2);
            animation: float 6s ease-in-out infinite;
        }

        /* Section Styling */
        section {
            padding: 5rem 2rem;
            position: relative;
            z-index: 10;
        }

        .section-header {
            text-align: center;
            margin-bottom: 3rem;
        }

        .section-header h2 {
            font-family: 'Fredoka One', cursive;
            font-size: 3.5rem;
            color: var(--white);
            margin-bottom: 1rem;
            text-shadow: 3px 3px 6px rgba(224, 33, 138, 0.7), 0 0 30px rgba(255, 182, 217, 0.8);
        }

        .section-header p {
            font-size: 1.1rem;
            color: var(--light-pink);
            max-width: 700px;
            margin: 0 auto;
        }

        .divider {
            width: 100px;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--gold), transparent);
            margin: 2rem auto;
        }

        /* Services Section */
        .services {
            background: radial-gradient(circle at 30% 50%, rgba(255, 20, 147, 0.25) 0%, rgba(255, 105, 180, 0.15) 50%, transparent 70%);
        }

        .services-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .service-category {
            margin-bottom: 4rem;
        }

        .category-title {
            font-family: 'Righteous', cursive;
            font-size: 2.3rem;
            color: var(--white);
            margin-bottom: 2rem;
            text-align: center;
            position: relative;
            text-shadow: 2px 2px 4px rgba(224, 33, 138, 0.7), 0 0 20px rgba(255, 105, 180, 0.6);
        }

        .category-title::before {
            content: '✨';
            margin-right: 0.5rem;
        }

        .category-title::after {
            content: '✨';
            margin-left: 0.5rem;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .service-card {
            background: linear-gradient(135deg, rgba(255, 20, 147, 0.3) 0%, rgba(255, 105, 180, 0.25) 100%);
            border: 3px solid rgba(224, 33, 138, 0.6);
            border-radius: 25px;
            padding: 2rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            box-shadow: 0 8px 25px rgba(224, 33, 138, 0.4), inset 0 0 30px rgba(255, 182, 217, 0.2);
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 215, 0, 0.1) 0%, transparent 70%);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .service-card:hover::before {
            opacity: 1;
        }

        .service-card:hover {
            transform: translateY(-10px) scale(1.02);
            border-color: var(--hot-pink);
            box-shadow: 0 15px 50px rgba(224, 33, 138, 0.6), 0 0 60px rgba(255, 105, 180, 0.4), inset 0 0 40px rgba(255, 182, 217, 0.3);
        }

        .service-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .service-card h3 {
            font-family: 'Righteous', cursive;
            font-size: 1.6rem;
            color: var(--white);
            margin-bottom: 0.5rem;
            text-shadow: 2px 2px 4px rgba(224, 33, 138, 0.5);
        }

        .service-card p {
            color: var(--white);
            line-height: 1.6;
            margin-bottom: 1rem;
        }

        .service-price {
            font-family: 'Fredoka One', cursive;
            font-size: 1.8rem;
            color: var(--gold);
            text-align: center;
            margin: 1rem 0;
            text-shadow: 2px 2px 4px rgba(224, 33, 138, 0.6), 0 0 15px rgba(255, 215, 0, 0.4);
        }

        .book-btn {
            padding: 0.9rem 1.8rem;
            background: linear-gradient(135deg, #E0218A 0%, #FF1493 100%);
            color: var(--white);
            border: none;
            border-radius: 30px;
            cursor: pointer;
            font-family: 'Fredoka One', cursive;
            font-size: 1rem;
            font-weight: 600;
            transition: all 0.3s ease;
            width: 100%;
            box-shadow: 0 6px 20px rgba(224, 33, 138, 0.5), inset 0 -2px 8px rgba(0, 0, 0, 0.2);
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.3);
        }

        .book-btn:hover {
            transform: scale(1.08);
            box-shadow: 0 10px 35px rgba(224, 33, 138, 0.7), 0 0 40px rgba(255, 105, 180, 0.6);
            background: linear-gradient(135deg, #FF1493 0%, #FF69B4 100%);
        }

        /* About Section */
        .about {
            background: radial-gradient(circle at 70% 50%, rgba(255, 20, 147, 0.3) 0%, rgba(255, 105, 180, 0.2) 50%, transparent 70%);
        }

        .about-container {
            max-width: 900px;
            margin: 0 auto;
            background: linear-gradient(135deg, rgba(255, 20, 147, 0.3) 0%, rgba(255, 105, 180, 0.25) 100%);
            border: 3px solid var(--gold);
            border-radius: 30px;
            padding: 3rem;
            position: relative;
            box-shadow: 0 15px 40px rgba(224, 33, 138, 0.4), inset 0 0 30px rgba(255, 182, 217, 0.3);
        }

        .about-container::before {
            content: '🌙';
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 3rem;
        }

        .about-content {
            font-size: 1.15rem;
            line-height: 1.9;
            color: var(--cream);
            text-align: center;
        }

        .about-content p {
            margin-bottom: 1.5rem;
        }

        .mission {
            margin-top: 2rem;
            padding: 2rem;
            background: rgba(255, 20, 147, 0.25);
            border: 3px solid var(--gold);
            border-radius: 20px;
            box-shadow: 0 8px 20px rgba(224, 33, 138, 0.3);
        }

        .mission h3 {
            font-family: 'Righteous', cursive;
            color: var(--white);
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(224, 33, 138, 0.6);
        }

        /* Contact Section */
        .contact {
            background: radial-gradient(circle at 50% 50%, rgba(255, 20, 147, 0.3) 0%, rgba(255, 105, 180, 0.2) 50%, transparent 70%);
        }

        .contact-container {
            max-width: 700px;
            margin: 0 auto;
        }

        .contact-form {
            background: linear-gradient(135deg, rgba(255, 20, 147, 0.3) 0%, rgba(255, 105, 180, 0.25) 100%);
            border: 3px solid var(--hot-pink);
            border-radius: 25px;
            padding: 2.5rem;
            box-shadow: 0 12px 35px rgba(224, 33, 138, 0.4), inset 0 0 30px rgba(255, 182, 217, 0.2);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--white);
            font-weight: 600;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
        }

        .form-group input,
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 0.9rem;
            background: rgba(255, 255, 255, 0.9);
            border: 3px solid rgba(224, 33, 138, 0.5);
            border-radius: 15px;
            color: #333;
            font-family: 'Poppins', sans-serif;
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        .form-group input:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--gold);
            box-shadow: 0 0 20px rgba(255, 215, 0, 0.6);
            background: rgba(255, 255, 255, 1);
        }

        .form-group textarea {
            min-height: 150px;
            resize: vertical;
        }

        .form-group select option {
            background: var(--deep-blue);
            color: var(--cream);
        }

        .submit-btn {
            width: 100%;
            padding: 1.2rem;
            background: linear-gradient(135deg, #E0218A 0%, #FF1493 100%);
            color: var(--white);
            border: none;
            border-radius: 30px;
            font-family: 'Fredoka One', cursive;
            font-size: 1.2rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 8px 25px rgba(224, 33, 138, 0.6), inset 0 -2px 8px rgba(0, 0, 0, 0.2);
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.3);
        }

        .submit-btn:hover {
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 12px 40px rgba(224, 33, 138, 0.8), 0 0 50px rgba(255, 105, 180, 0.6);
            background: linear-gradient(135deg, #FF1493 0%, #FF69B4 100%);
        }

        .contact-info {
            margin-top: 3rem;
            text-align: center;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
        }

        .social-links a {
            color: var(--light-pink);
            font-size: 2rem;
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            color: var(--gold);
            transform: scale(1.2);
            filter: drop-shadow(0 0 10px rgba(255, 215, 0, 0.5));
        }

        /* Footer */
        footer {
            background: rgba(255, 105, 180, 0.2);
            padding: 2rem;
            text-align: center;
            position: relative;
            z-index: 10;
            border-top: 2px solid rgba(255, 215, 0, 0.3);
        }

        footer p {
            color: var(--light-pink);
            font-size: 0.9rem;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                position: fixed;
                top: 70px;
                right: -100%;
                flex-direction: column;
                background: rgba(255, 105, 180, 0.98);
                width: 200px;
                padding: 2rem;
                border-radius: 10px 0 0 10px;
                transition: right 0.3s ease;
                box-shadow: -5px 5px 20px rgba(0, 0, 0, 0.3);
            }

            .nav-links.active {
                right: 0;
            }

            .mobile-menu-btn {
                display: block;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero .tagline {
                font-size: 1rem;
            }

            .hero .welcome {
                font-size: 1rem;
            }

            .moon {
                width: 80px;
                height: 80px;
                top: 10%;
                right: 5%;
            }

            .section-header h2 {
                font-size: 2rem;
            }

            .services-grid {
                grid-template-columns: 1fr;
            }

            .cta-buttons {
                flex-direction: column;
            }

            .btn {
                width: 100%;
                max-width: 300px;
            }
        }

        /* Success message */
        .success-message {
            display: none;
            padding: 1rem;
            background: rgba(147, 112, 219, 0.3);
            border: 2px solid var(--gold);
            border-radius: 10px;
            color: var(--gold);
            text-align: center;
            margin-top: 1rem;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Modal Styles */
        .modal-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(224, 33, 138, 0.7);
            backdrop-filter: blur(8px);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            padding: 1rem;
            overflow-y: auto;
        }

        .modal-overlay.active {
            display: flex;
        }

        .modal-content {
            background: linear-gradient(135deg, #FF1493 0%, #FF69B4 100%);
            border: 4px solid var(--gold);
            border-radius: 30px;
            padding: 2.5rem;
            max-width: 600px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5), 0 0 80px rgba(255, 182, 217, 0.6), inset 0 0 40px rgba(255, 255, 255, 0.2);
            animation: modalSlideIn 0.4s ease;
        }

        @keyframes modalSlideIn {
            from {
                opacity: 0;
                transform: scale(0.8) translateY(-50px);
            }
            to {
                opacity: 1;
                transform: scale(1) translateY(0);
            }
        }

        .modal-header {
            text-align: center;
            margin-bottom: 2rem;
            border-bottom: 3px solid rgba(255, 215, 0, 0.5);
            padding-bottom: 1rem;
        }

        .modal-header h3 {
            font-family: 'Fredoka One', cursive;
            font-size: 2rem;
            color: var(--white);
            margin-bottom: 0.5rem;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.4);
        }

        .modal-price {
            font-family: 'Pacifico', cursive;
            font-size: 2.5rem;
            color: var(--gold);
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5), 0 0 20px rgba(255, 215, 0, 0.5);
        }

        .modal-section {
            margin-bottom: 2rem;
        }

        .modal-section h4 {
            font-family: 'Righteous', cursive;
            font-size: 1.3rem;
            color: var(--white);
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .modal-form-group {
            margin-bottom: 1rem;
        }

        .modal-form-group label {
            display: block;
            margin-bottom: 0.4rem;
            color: var(--white);
            font-weight: 600;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
        }

        .modal-form-group input,
        .modal-form-group select,
        .modal-form-group textarea {
            width: 100%;
            padding: 0.8rem;
            background: rgba(255, 255, 255, 0.95);
            border: 3px solid rgba(224, 33, 138, 0.5);
            border-radius: 15px;
            color: #333;
            font-family: 'Poppins', sans-serif;
            font-size: 0.95rem;
            transition: all 0.3s ease;
        }

        .modal-form-group input:focus,
        .modal-form-group select:focus,
        .modal-form-group textarea:focus {
            outline: none;
            border-color: var(--gold);
            box-shadow: 0 0 20px rgba(255, 215, 0, 0.5);
            background: rgba(255, 255, 255, 1);
        }

        .modal-form-group textarea {
            min-height: 100px;
            resize: vertical;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
        }

        .modal-buttons {
            display: flex;
            gap: 1rem;
            margin-top: 2rem;
        }

        .modal-btn {
            flex: 1;
            padding: 1rem;
            border: none;
            border-radius: 25px;
            font-family: 'Fredoka One', cursive;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .modal-btn-primary {
            background: linear-gradient(135deg, var(--gold) 0%, #FFD700 100%);
            color: #333;
            box-shadow: 0 6px 20px rgba(255, 215, 0, 0.5);
        }

        .modal-btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.7);
        }

        .modal-btn-secondary {
            background: rgba(255, 255, 255, 0.3);
            color: var(--white);
            border: 2px solid rgba(255, 255, 255, 0.5);
        }

        .modal-btn-secondary:hover {
            background: rgba(255, 255, 255, 0.4);
            transform: translateY(-3px);
        }

        .modal-disclaimer {
            margin-top: 1.5rem;
            padding: 1rem;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            font-size: 0.85rem;
            text-align: center;
            color: var(--white);
        }

        .close-modal {
            position: absolute;
            top: 1rem;
            right: 1rem;
            background: rgba(255, 255, 255, 0.3);
            border: none;
            color: var(--white);
            font-size: 1.8rem;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }

        .close-modal:hover {
            background: rgba(255, 255, 255, 0.5);
            transform: rotate(90deg);
        }

        @media (max-width: 768px) {
            .form-row {
                grid-template-columns: 1fr;
            }
            
            .modal-content {
                padding: 1.5rem;
            }
            
            .modal-buttons {
                flex-direction: column;
            }
        }
    </style>
<style>
            @font-face {
                font-family: 'Roboto';
                font-style: normal;
                font-weight: 400;
                src: url('chrome-extension://cakcmeinnmdkbpbjbfhfahocdcpgcghi/fonts/Roboto/roboto-400.woff') format('woff');
            }
        </style><style>
            @font-face {
                font-family: 'Roboto';
                font-style: normal;
                font-weight: 500;
                src: url('chrome-extension://cakcmeinnmdkbpbjbfhfahocdcpgcghi/fonts/Roboto/roboto-500.woff') format('woff');
            }
        </style></head>
<body>
    <!-- Animated stars background -->
    <div class="stars" id="stars"><div class="star" style="left: 92.7033%; top: 26.6128%; width: 2.97285px; height: 2.97285px; animation-delay: 1.15097s;"></div><div class="star" style="left: 46.0991%; top: 85.823%; width: 2.11197px; height: 2.11197px; animation-delay: 0.530241s;"></div><div class="star" style="left: 8.74684%; top: 12.3371%; width: 1.22054px; height: 1.22054px; animation-delay: 0.364763s;"></div><div class="star" style="left: 45.1731%; top: 79.6121%; width: 2.56185px; height: 2.56185px; animation-delay: 1.23571s;"></div><div class="star" style="left: 9.03374%; top: 89.9046%; width: 2.43084px; height: 2.43084px; animation-delay: 1.80509s;"></div><div class="star" style="left: 62.1353%; top: 15.6149%; width: 2.30839px; height: 2.30839px; animation-delay: 1.57091s;"></div><div class="star" style="left: 14.203%; top: 22.517%; width: 2.50016px; height: 2.50016px; animation-delay: 0.31075s;"></div><div class="star" style="left: 51.5751%; top: 25.016%; width: 1.90399px; height: 1.90399px; animation-delay: 0.891424s;"></div><div class="star" style="left: 73.6909%; top: 98.3882%; width: 2.74276px; height: 2.74276px; animation-delay: 1.60323s;"></div><div class="star" style="left: 8.05385%; top: 1.51939%; width: 3.75112px; height: 3.75112px; animation-delay: 0.109459s;"></div><div class="star" style="left: 73.0817%; top: 43.5113%; width: 2.79724px; height: 2.79724px; animation-delay: 2.37735s;"></div><div class="star" style="left: 14.9947%; top: 46.7171%; width: 1.5822px; height: 1.5822px; animation-delay: 0.407526s;"></div><div class="star" style="left: 11.255%; top: 6.04255%; width: 1.82747px; height: 1.82747px; animation-delay: 0.892922s;"></div><div class="star" style="left: 83.1244%; top: 92.1526%; width: 2.86268px; height: 2.86268px; animation-delay: 1.60632s;"></div><div class="star" style="left: 15.1192%; top: 69.7962%; width: 1.84092px; height: 1.84092px; animation-delay: 0.238114s;"></div><div class="star" style="left: 53.2741%; top: 27.4402%; width: 2.42841px; height: 2.42841px; animation-delay: 1.07219s;"></div><div class="star" style="left: 3.38875%; top: 38.1967%; width: 3.40699px; height: 3.40699px; animation-delay: 0.716898s;"></div><div class="star" style="left: 91.6922%; top: 46.5871%; width: 2.85577px; height: 2.85577px; animation-delay: 0.443119s;"></div><div class="star" style="left: 33.3623%; top: 56.8979%; width: 3.80194px; height: 3.80194px; animation-delay: 0.609555s;"></div><div class="star" style="left: 7.39749%; top: 39.3348%; width: 1.62909px; height: 1.62909px; animation-delay: 1.41769s;"></div><div class="star" style="left: 95.3873%; top: 92.6303%; width: 3.92068px; height: 3.92068px; animation-delay: 2.32026s;"></div><div class="star" style="left: 46.1795%; top: 72.877%; width: 2.84341px; height: 2.84341px; animation-delay: 2.98298s;"></div><div class="star" style="left: 29.8222%; top: 13.3019%; width: 2.49329px; height: 2.49329px; animation-delay: 0.0315615s;"></div><div class="star" style="left: 8.39489%; top: 49.5418%; width: 2.19949px; height: 2.19949px; animation-delay: 2.83992s;"></div><div class="star" style="left: 61.3333%; top: 99.3756%; width: 2.28538px; height: 2.28538px; animation-delay: 1.37138s;"></div><div class="star" style="left: 29.8923%; top: 66.9705%; width: 2.4856px; height: 2.4856px; animation-delay: 0.689491s;"></div><div class="star" style="left: 3.4562%; top: 10.2875%; width: 2.18639px; height: 2.18639px; animation-delay: 2.62534s;"></div><div class="star" style="left: 11.9608%; top: 27.6645%; width: 2.97494px; height: 2.97494px; animation-delay: 2.96394s;"></div><div class="star" style="left: 4.91239%; top: 92.8744%; width: 2.74527px; height: 2.74527px; animation-delay: 0.189749s;"></div><div class="star" style="left: 86.775%; top: 82.1276%; width: 3.79993px; height: 3.79993px; animation-delay: 0.299699s;"></div><div class="star" style="left: 13.7064%; top: 37.8763%; width: 3.09976px; height: 3.09976px; animation-delay: 0.438977s;"></div><div class="star" style="left: 48.1226%; top: 29.1747%; width: 2.85089px; height: 2.85089px; animation-delay: 0.63448s;"></div><div class="star" style="left: 96.2032%; top: 76.8861%; width: 1.31934px; height: 1.31934px; animation-delay: 1.05504s;"></div><div class="star" style="left: 18.9346%; top: 3.04029%; width: 2.78452px; height: 2.78452px; animation-delay: 2.28684s;"></div><div class="star" style="left: 40.2349%; top: 75.737%; width: 2.75684px; height: 2.75684px; animation-delay: 0.038905s;"></div><div class="star" style="left: 46.0758%; top: 45.9828%; width: 3.37752px; height: 3.37752px; animation-delay: 0.615531s;"></div><div class="star" style="left: 54.0007%; top: 98.3541%; width: 2.42689px; height: 2.42689px; animation-delay: 1.10115s;"></div><div class="star" style="left: 96.7546%; top: 46.2979%; width: 3.33571px; height: 3.33571px; animation-delay: 2.15484s;"></div><div class="star" style="left: 54.4858%; top: 70.381%; width: 3.44114px; height: 3.44114px; animation-delay: 1.08092s;"></div><div class="star" style="left: 20.8034%; top: 60.3747%; width: 2.51889px; height: 2.51889px; animation-delay: 1.56709s;"></div><div class="star" style="left: 5.17268%; top: 30.8922%; width: 3.53195px; height: 3.53195px; animation-delay: 0.765851s;"></div><div class="star" style="left: 45.1807%; top: 50.7209%; width: 1.64809px; height: 1.64809px; animation-delay: 1.4046s;"></div><div class="star" style="left: 93.3058%; top: 59.1562%; width: 3.40444px; height: 3.40444px; animation-delay: 1.62633s;"></div><div class="star" style="left: 93.2663%; top: 22.7424%; width: 2.02484px; height: 2.02484px; animation-delay: 2.65937s;"></div><div class="star" style="left: 87.284%; top: 11.3816%; width: 2.71886px; height: 2.71886px; animation-delay: 0.547267s;"></div><div class="star" style="left: 66.6954%; top: 43.8024%; width: 1.85989px; height: 1.85989px; animation-delay: 0.872606s;"></div><div class="star" style="left: 34.9072%; top: 71.8433%; width: 1.38301px; height: 1.38301px; animation-delay: 2.20325s;"></div><div class="star" style="left: 43.703%; top: 72.6867%; width: 2.35194px; height: 2.35194px; animation-delay: 0.944744s;"></div><div class="star" style="left: 21.62%; top: 79.0594%; width: 3.29322px; height: 3.29322px; animation-delay: 2.45157s;"></div><div class="star" style="left: 58.7848%; top: 66.4044%; width: 1.24257px; height: 1.24257px; animation-delay: 0.274266s;"></div><div class="star" style="left: 69.2126%; top: 79.0223%; width: 3.63983px; height: 3.63983px; animation-delay: 1.95588s;"></div><div class="star" style="left: 8.93102%; top: 86.8487%; width: 1.25491px; height: 1.25491px; animation-delay: 0.256593s;"></div><div class="star" style="left: 69.2278%; top: 98.5707%; width: 2.93195px; height: 2.93195px; animation-delay: 1.64112s;"></div><div class="star" style="left: 87.1231%; top: 77.6282%; width: 1.30527px; height: 1.30527px; animation-delay: 1.19856s;"></div><div class="star" style="left: 60.9967%; top: 69.0847%; width: 3.45216px; height: 3.45216px; animation-delay: 1.60142s;"></div><div class="star" style="left: 99.7785%; top: 47.172%; width: 3.54831px; height: 3.54831px; animation-delay: 1.23874s;"></div><div class="star" style="left: 38.8034%; top: 49.1927%; width: 1.95225px; height: 1.95225px; animation-delay: 0.277779s;"></div><div class="star" style="left: 89.9086%; top: 55.6083%; width: 2.57449px; height: 2.57449px; animation-delay: 2.59675s;"></div><div class="star" style="left: 62.6913%; top: 55.4036%; width: 3.89689px; height: 3.89689px; animation-delay: 1.9693s;"></div><div class="star" style="left: 26.6192%; top: 48.1205%; width: 3.1355px; height: 3.1355px; animation-delay: 1.70651s;"></div><div class="star" style="left: 12.9089%; top: 49.1678%; width: 1.11087px; height: 1.11087px; animation-delay: 2.18717s;"></div><div class="star" style="left: 97.4037%; top: 9.29459%; width: 2.73794px; height: 2.73794px; animation-delay: 2.50897s;"></div><div class="star" style="left: 80.6903%; top: 92.6567%; width: 3.13368px; height: 3.13368px; animation-delay: 2.99775s;"></div><div class="star" style="left: 18.1606%; top: 63.5342%; width: 2.97684px; height: 2.97684px; animation-delay: 1.67798s;"></div><div class="star" style="left: 22.7263%; top: 27.9681%; width: 1.95361px; height: 1.95361px; animation-delay: 0.70688s;"></div><div class="star" style="left: 24.8018%; top: 57.5951%; width: 3.50731px; height: 3.50731px; animation-delay: 0.451584s;"></div><div class="star" style="left: 7.90311%; top: 26.8005%; width: 1.02045px; height: 1.02045px; animation-delay: 2.35474s;"></div><div class="star" style="left: 21.0903%; top: 95.9074%; width: 1.02623px; height: 1.02623px; animation-delay: 1.37666s;"></div><div class="star" style="left: 58.7461%; top: 59.5806%; width: 3.61719px; height: 3.61719px; animation-delay: 0.693097s;"></div><div class="star" style="left: 94.6448%; top: 7.14564%; width: 3.56755px; height: 3.56755px; animation-delay: 1.66868s;"></div><div class="star" style="left: 8.23597%; top: 86.9724%; width: 1.66307px; height: 1.66307px; animation-delay: 2.0002s;"></div><div class="star" style="left: 81.7207%; top: 68.8526%; width: 2.18303px; height: 2.18303px; animation-delay: 0.292186s;"></div><div class="star" style="left: 28.5503%; top: 97.3904%; width: 3.61629px; height: 3.61629px; animation-delay: 2.24006s;"></div><div class="star" style="left: 45.1389%; top: 16.4708%; width: 1.9537px; height: 1.9537px; animation-delay: 0.251632s;"></div><div class="star" style="left: 64.146%; top: 84.8222%; width: 2.55734px; height: 2.55734px; animation-delay: 1.55022s;"></div><div class="star" style="left: 50.2913%; top: 93.575%; width: 2.34508px; height: 2.34508px; animation-delay: 1.36671s;"></div><div class="star" style="left: 40.4033%; top: 2.06171%; width: 1.18303px; height: 1.18303px; animation-delay: 0.744915s;"></div><div class="star" style="left: 54.3864%; top: 43.2614%; width: 3.13747px; height: 3.13747px; animation-delay: 2.68385s;"></div><div class="star" style="left: 94.787%; top: 64.2502%; width: 1.14352px; height: 1.14352px; animation-delay: 0.463721s;"></div><div class="star" style="left: 22.8428%; top: 57.4846%; width: 2.64361px; height: 2.64361px; animation-delay: 0.745319s;"></div><div class="star" style="left: 66.1933%; top: 3.9538%; width: 1.28939px; height: 1.28939px; animation-delay: 0.123872s;"></div><div class="star" style="left: 15.2057%; top: 19.9894%; width: 1.98869px; height: 1.98869px; animation-delay: 1.52281s;"></div><div class="star" style="left: 42.0647%; top: 96.8133%; width: 3.53563px; height: 3.53563px; animation-delay: 2.12907s;"></div><div class="star" style="left: 0.730937%; top: 29.612%; width: 2.1956px; height: 2.1956px; animation-delay: 2.52475s;"></div><div class="star" style="left: 28.603%; top: 0.886376%; width: 1.25187px; height: 1.25187px; animation-delay: 0.257642s;"></div><div class="star" style="left: 42.1895%; top: 82.8899%; width: 1.20413px; height: 1.20413px; animation-delay: 1.03236s;"></div><div class="star" style="left: 9.93103%; top: 61.5282%; width: 1.39504px; height: 1.39504px; animation-delay: 2.56455s;"></div><div class="star" style="left: 20.6104%; top: 31.3537%; width: 2.15152px; height: 2.15152px; animation-delay: 2.48348s;"></div><div class="star" style="left: 81.559%; top: 20.5135%; width: 1.23319px; height: 1.23319px; animation-delay: 1.03099s;"></div><div class="star" style="left: 43.6016%; top: 66.5121%; width: 1.98141px; height: 1.98141px; animation-delay: 0.0226922s;"></div><div class="star" style="left: 54.7334%; top: 59.8352%; width: 1.5188px; height: 1.5188px; animation-delay: 0.964745s;"></div><div class="star" style="left: 80.8883%; top: 80.7149%; width: 2.2038px; height: 2.2038px; animation-delay: 2.05054s;"></div><div class="star" style="left: 83.3227%; top: 68.3452%; width: 3.57241px; height: 3.57241px; animation-delay: 2.66626s;"></div><div class="star" style="left: 35.4429%; top: 90.262%; width: 3.21492px; height: 3.21492px; animation-delay: 0.434469s;"></div><div class="star" style="left: 23.3933%; top: 50.6034%; width: 3.9024px; height: 3.9024px; animation-delay: 1.51621s;"></div><div class="star" style="left: 80.9185%; top: 96.5236%; width: 1.06424px; height: 1.06424px; animation-delay: 0.341104s;"></div><div class="star" style="left: 41.8992%; top: 54.8181%; width: 3.46235px; height: 3.46235px; animation-delay: 0.493192s;"></div><div class="star" style="left: 81.0906%; top: 95.072%; width: 2.81009px; height: 2.81009px; animation-delay: 1.52449s;"></div><div class="star" style="left: 71.1634%; top: 19.1339%; width: 3.78421px; height: 3.78421px; animation-delay: 2.63686s;"></div><div class="star" style="left: 18.0181%; top: 4.26874%; width: 1.0723px; height: 1.0723px; animation-delay: 2.76445s;"></div></div>

    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <div class="logo">✨ Astro Barbie Tarot ✨</div>
            <ul class="nav-links" id="navLinks">
                <li><a href="#home">Home</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <button class="mobile-menu-btn" id="mobileMenuBtn">☰</button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="moon"></div>
        <div class="hero-content">
            <h1>Astro Barbie Tarot</h1>
            <p class="tagline">✨ Connecting You with Spirit Guides &amp; the Universe ✨</p>
            <p class="welcome">
                Welcome to a magical space where cosmic wisdom meets divine guidance. 
                Let me help you find clarity, direction, and insight through the ancient art of tarot 
                and the mystical language of the stars.
            </p>
            <div class="cta-buttons">
                <a href="#services" class="btn btn-primary">Explore Services</a>
                <a href="#about" class="btn btn-secondary">Learn More</a>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="services">
        <div class="section-header">
            <h2>Mystical Services</h2>
            <p>Choose from a variety of readings and cosmic guidance options</p>
            <div class="divider"></div>
        </div>

        <div class="services-container">
            <!-- General Tarot Readings -->
            <div class="service-category">
                <h3 class="category-title">General Tarot Readings</h3>
                <div class="services-grid">
                    <div class="service-card">
                        <div class="service-icon">🔮</div>
                        <h3>Single Card Pull Reading</h3>
                        <p>Quick guidance and insight from the universe. Perfect for daily direction or a specific question.</p>
                        <div class="service-price">$15</div>
                        <button class="book-btn" onclick="openModal('Single Card Pull Reading', '$15')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🌟</div>
                        <h3>Three Card Spread</h3>
                        <p>Explore your past, present, and future. Understand the journey you're on and where it's leading.</p>
                        <div class="service-price">$33</div>
                        <button class="book-btn" onclick="openModal('Three Card Spread', '$33')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🎴</div>
                        <h3>Celtic Cross Reading</h3>
                        <p>Comprehensive 10-card spread providing deep insight into your situation, obstacles, and outcomes.</p>
                        <div class="service-price">$55</div>
                        <button class="book-btn" onclick="openModal('Celtic Cross Reading', '$55')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">💖</div>
                        <h3>Relationship Reading</h3>
                        <p>Gain clarity on love, partnerships, and connections. Understand the dynamics and future potential.</p>
                        <div class="service-price">$44</div>
                        <button class="book-btn" onclick="openModal('Relationship Reading', '$44')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">💼</div>
                        <h3>Career Path Reading</h3>
                        <p>Professional guidance for your career journey. Discover your true calling and next steps.</p>
                        <div class="service-price">$44</div>
                        <button class="book-btn" onclick="openModal('Career Path Reading', '$44')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">⚖️</div>
                        <h3>Decision Making Reading</h3>
                        <p>Clarity on important choices. See the outcomes of different paths before you choose.</p>
                        <div class="service-price">$33</div>
                        <button class="book-btn" onclick="openModal('Decision Making Reading', '$33')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">📅</div>
                        <h3>Year Ahead Reading</h3>
                        <p>12-month forecast covering all areas of your life. Plan your year with cosmic guidance.</p>
                        <div class="service-price">$111</div>
                        <button class="book-btn" onclick="openModal('Year Ahead Reading', '$111')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🌑</div>
                        <h3>Shadow Work Reading</h3>
                        <p>Deep inner healing and self-discovery. Face your shadows and embrace your light.</p>
                        <div class="service-price">$55</div>
                        <button class="book-btn" onclick="openModal('Shadow Work Reading', '$55')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🕊️</div>
                        <h3>Spiritual Guidance Reading</h3>
                        <p>Connect with your higher self and spirit guides. Receive divine messages and wisdom.</p>
                        <div class="service-price">$44</div>
                        <button class="book-btn" onclick="openModal('Spiritual Guidance Reading', '$44')">💖 Book &amp; Pay Now 💖</button>
                    </div>
                </div>
            </div>

            <!-- Specialized Readings -->
            <div class="service-category">
                <h3 class="category-title">Specialized Cosmic Readings</h3>
                <div class="services-grid">
                    <div class="service-card">
                        <div class="service-icon">⭐</div>
                        <h3>Birth Chart Reading</h3>
                        <p>Full natal chart interpretation revealing your cosmic blueprint and life purpose.</p>
                        <div class="service-price">$88</div>
                        <button class="book-btn" onclick="openModal('Birth Chart Reading', '$88', true)">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">💕</div>
                        <h3>Compatibility Reading</h3>
                        <p>Synastry analysis between two people. Perfect for romantic or business partnerships.</p>
                        <div class="service-price">$77</div>
                        <button class="book-btn" onclick="openModal('Compatibility Reading', '$77', true)">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🎂</div>
                        <h3>Solar Return Reading</h3>
                        <p>Birthday year forecast based on your solar return chart. What does your new year hold?</p>
                        <div class="service-price">$66</div>
                        <button class="book-btn" onclick="openModal('Solar Return Reading', '$66', true)">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🌙</div>
                        <h3>New Moon Intention Setting</h3>
                        <p>Harness new moon energy to set powerful intentions and manifest your desires.</p>
                        <div class="service-price">$33</div>
                        <button class="book-btn" onclick="openModal('New Moon Intention Setting', '$33')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🌕</div>
                        <h3>Full Moon Release Reading</h3>
                        <p>Release what no longer serves you during the full moon. Let go and make space for new blessings.</p>
                        <div class="service-price">$33</div>
                        <button class="book-btn" onclick="openModal('Full Moon Release Reading', '$33')">💖 Book &amp; Pay Now 💖</button>
                    </div>
                </div>
            </div>

            <!-- Subscription Services -->
            <div class="service-category">
                <h3 class="category-title">Subscription Services</h3>
                <div class="services-grid">
                    <div class="service-card">
                        <div class="service-icon">📖</div>
                        <h3>Monthly Horoscope Subscription</h3>
                        <p>Personalized monthly insights based on your birth chart. Know what cosmic energies are at play.</p>
                        <div class="service-price">$44/mo</div>
                        <button class="book-btn" onclick="openModal('Monthly Horoscope Subscription', '$44/month', true)">💖 Subscribe Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🃏</div>
                        <h3>Weekly Tarot Guidance</h3>
                        <p>Weekly card pulls and messages to guide you through each week with clarity and confidence.</p>
                        <div class="service-price">$55/mo</div>
                        <button class="book-btn" onclick="openModal('Weekly Tarot Guidance', '$55/month')">💖 Subscribe Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">👑</div>
                        <h3>VIP Cosmic Package</h3>
                        <p>Combination of monthly horoscopes and weekly tarot readings. Full cosmic support all month long.</p>
                        <div class="service-price">$88/mo</div>
                        <button class="book-btn" onclick="openModal('VIP Cosmic Package', '$88/month', true)">💖 Subscribe Now 💖</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="section-header">
            <h2>About Your Guide</h2>
            <p>Meet the cosmic connector behind the cards</p>
            <div class="divider"></div>
        </div>

        <div class="about-container">
            <div class="about-content">
                <p>
                    I have been practicing tarot for 5 years and wanted to do something to help people 
                    who are lacking direction or need clarity, insight, or advice but don't know who to ask!
                </p>
                <p>
                    Who's better than asking your spirit guides, or the universe, or higher power for answers? 
                    I connect with those energies and deliver messages through tarot.
                </p>
                <div class="mission">
                    <h3>✨ My Mission ✨</h3>
                    <p>
                        My purpose is to bridge the gap between you and the divine wisdom that surrounds us all. 
                        Through tarot and cosmic guidance, I help you unlock the answers that already exist within 
                        and around you. Every reading is a sacred conversation with the universe, tailored specifically 
                        to illuminate your unique path.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="section-header">
            <h2>Connect with the Cosmos</h2>
            <p>Ready to receive your guidance? Let's connect!</p>
            <div class="divider"></div>
        </div>

        <div class="contact-container">
            <form class="contact-form" id="contactForm">
                <div class="form-group">
                    <label for="name">Name *</label>
                    <input type="text" id="name" name="name" required="" placeholder="Your full name">
                </div>

                <div class="form-group">
                    <label for="email">Email Address *</label>
                    <input type="email" id="email" name="email" required="" placeholder="your@email.com">
                </div>

                <div class="form-group">
                    <label for="phone">Phone Number</label>
                    <input type="tel" id="phone" name="phone" placeholder="(555) 123-4567">
                </div>

                <div class="form-group">
                    <label for="service">Service Interested In *</label>
                    <select id="service" name="service" required="">
                        <option value="">-- Select a Service --</option>
                        <option value="Single Card Pull Reading">Single Card Pull Reading</option>
                        <option value="Three Card Spread">Three Card Spread</option>
                        <option value="Celtic Cross Reading">Celtic Cross Reading</option>
                        <option value="Relationship Reading">Relationship Reading</option>
                        <option value="Career Path Reading">Career Path Reading</option>
                        <option value="Decision Making Reading">Decision Making Reading</option>
                        <option value="Year Ahead Reading">Year Ahead Reading</option>
                        <option value="Shadow Work Reading">Shadow Work Reading</option>
                        <option value="Spiritual Guidance Reading">Spiritual Guidance Reading</option>
                        <option value="Birth Chart Reading">Birth Chart Reading</option>
                        <option value="Compatibility Reading">Compatibility Reading</option>
                        <option value="Solar Return Reading">Solar Return Reading</option>
                        <option value="New Moon Intention Setting">New Moon Intention Setting</option>
                        <option value="Full Moon Release Reading">Full Moon Release Reading</option>
                        <option value="Monthly Horoscope Subscription">Monthly Horoscope Subscription</option>
                        <option value="Weekly Tarot Guidance">Weekly Tarot Guidance</option>
                        <option value="VIP Cosmic Package">VIP Cosmic Package</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="message">Message *</label>
                    <textarea id="message" name="message" required="" placeholder="Tell me about what guidance you're seeking..."></textarea>
                </div>

                <button type="submit" class="submit-btn">Send Message ✨</button>
                <div class="success-message" id="successMessage">
                    ✨ Thank you! Your message has been received. I'll connect with you soon! ✨
                </div>
            </form>

            <div class="contact-info">
                <p style="color: var(--light-pink); margin-top: 2rem;">
                    <strong>Email:</strong> <a href="mailto:astrobarbietarot@email.com" style="color: var(--gold);">astrobarbietarot@email.com</a>
                </p>
                <div class="social-links">
                    <a href="https://instagram.com" target="_blank" title="Instagram">📷</a>
                    <a href="https://tiktok.com" target="_blank" title="TikTok">🎵</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Booking Modal -->
    <div class="modal-overlay" id="bookingModal">
        <div class="modal-content">
            <button class="close-modal" onclick="closeModal()">×</button>
            <div class="modal-header">
                <h3 id="modalServiceName"></h3>
                <div class="modal-price" id="modalServicePrice"></div>
            </div>

            <form id="bookingForm">
                <!-- Payment Information -->
                <div class="modal-section">
                    <h4>💳 Payment Information</h4>
                    <div class="modal-form-group">
                        <label for="cardName">Cardholder Name *</label>
                        <input type="text" id="cardName" name="cardName" required="" placeholder="Name on card">
                    </div>
                    <div class="modal-form-group">
                        <label for="cardNumber">Card Number *</label>
                        <input type="text" id="cardNumber" name="cardNumber" required="" placeholder="1234 5678 9012 3456" maxlength="19">
                    </div>
                    <div class="form-row">
                        <div class="modal-form-group">
                            <label for="expiration">Expiration *</label>
                            <input type="text" id="expiration" name="expiration" required="" placeholder="MM/YY" maxlength="5">
                        </div>
                        <div class="modal-form-group">
                            <label for="cvv">CVV *</label>
                            <input type="text" id="cvv" name="cvv" required="" placeholder="123" maxlength="4">
                        </div>
                    </div>
                    <div class="modal-form-group">
                        <label for="zipCode">Zip Code *</label>
                        <input type="text" id="zipCode" name="zipCode" required="" placeholder="12345" maxlength="10">
                    </div>
                </div>

                <!-- Contact Information -->
                <div class="modal-section">
                    <h4>📧 Contact Information</h4>
                    <div class="modal-form-group">
                        <label for="clientName">Your Name *</label>
                        <input type="text" id="clientName" name="clientName" required="" placeholder="Full name">
                    </div>
                    <div class="modal-form-group">
                        <label for="clientEmail">Email Address *</label>
                        <input type="email" id="clientEmail" name="clientEmail" required="" placeholder="your@email.com">
                    </div>
                    <div class="modal-form-group">
                        <label for="clientPhone">Phone Number *</label>
                        <input type="tel" id="clientPhone" name="clientPhone" required="" placeholder="(555) 123-4567">
                    </div>
                    <div class="modal-form-group">
                        <label for="contactMethod">Preferred Contact Method *</label>
                        <select id="contactMethod" name="contactMethod" required="">
                            <option value="">-- Select --</option>
                            <option value="email">Email</option>
                            <option value="phone">Phone</option>
                            <option value="text">Text Message</option>
                        </select>
                    </div>
                </div>

                <!-- Birth Chart Information (conditional) -->
                <div class="modal-section" id="birthChartSection" style="display: none;">
                    <h4>🌟 Birth Chart Information</h4>
                    <div class="modal-form-group">
                        <label for="birthDate">Birth Date *</label>
                        <input type="date" id="birthDate" name="birthDate">
                    </div>
                    <div class="modal-form-group">
                        <label for="birthTime">Birth Time *</label>
                        <input type="time" id="birthTime" name="birthTime">
                    </div>
                    <div class="modal-form-group">
                        <label for="birthPlace">Birth Place (City, State/Country) *</label>
                        <input type="text" id="birthPlace" name="birthPlace" placeholder="Los Angeles, CA">
                    </div>
                </div>

                <!-- Question/Guidance -->
                <div class="modal-section">
                    <h4>✨ Your Question or Area of Focus</h4>
                    <div class="modal-form-group">
                        <label for="question">What guidance are you seeking? *</label>
                        <textarea id="question" name="question" required="" placeholder="Share what you'd like clarity or insight on..."></textarea>
                    </div>
                </div>

                <!-- Buttons -->
                <div class="modal-buttons">
                    <button type="button" class="modal-btn modal-btn-secondary" onclick="closeModal()">Cancel</button>
                    <button type="submit" class="modal-btn modal-btn-primary">Complete Booking ✨</button>
                </div>

                <div class="modal-disclaimer">
                    🔮 Your reading will be delivered within 24-48 hours via your preferred contact method. All information is kept confidential.
                </div>
            </form>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <p>✨ Astro Barbie Tarot © 2025 | Connecting You with Divine Guidance ✨</p>
        <p style="margin-top: 0.5rem; font-size: 0.8rem;">All readings are for entertainment and spiritual guidance purposes.</p>
    </footer>

    <script>
        // Generate animated stars
        function createStars() {
            const starsContainer = document.getElementById('stars');
            const numberOfStars = 100;

            for (let i = 0; i < numberOfStars; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.width = Math.random() * 3 + 1 + 'px';
                star.style.height = star.style.width;
                star.style.animationDelay = Math.random() * 3 + 's';
                starsContainer.appendChild(star);
            }
        }

        // Mobile menu toggle
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const navLinks = document.getElementById('navLinks');

        mobileMenuBtn.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });

        // Close mobile menu when clicking a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
            });
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    const navHeight = document.querySelector('nav').offsetHeight;
                    const targetPosition = target.offsetTop - navHeight;
                    window.scrollTo({
                        top: targetPosition,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Scroll to contact with service pre-selected
        function scrollToContact(serviceName) {
            const serviceSelect = document.getElementById('service');
            serviceSelect.value = serviceName;
            
            const contactSection = document.getElementById('contact');
            const navHeight = document.querySelector('nav').offsetHeight;
            const targetPosition = contactSection.offsetTop - navHeight;
            
            window.scrollTo({
                top: targetPosition,
                behavior: 'smooth'
            });
        }

        // Form submission handler
        const contactForm = document.getElementById('contactForm');
        const successMessage = document.getElementById('successMessage');

        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            // Show success message
            successMessage.style.display = 'block';
            
            // Reset form
            contactForm.reset();
            
            // Hide success message after 5 seconds
            setTimeout(() => {
                successMessage.style.display = 'none';
            }, 5000);
        });

        // Initialize stars on page load
        window.addEventListener('load', createStars);

        // Modal functionality
        let currentService = '';
        let currentPrice = '';
        let requiresBirthChart = false;

        function openModal(serviceName, price, needsBirthChart = false) {
            currentService = serviceName;
            currentPrice = price;
            requiresBirthChart = needsBirthChart;

            document.getElementById('modalServiceName').textContent = serviceName;
            document.getElementById('modalServicePrice').textContent = price;
            document.getElementById('bookingModal').classList.add('active');
            document.body.style.overflow = 'hidden';

            // Show/hide birth chart section
            const birthChartSection = document.getElementById('birthChartSection');
            if (needsBirthChart) {
                birthChartSection.style.display = 'block';
                document.getElementById('birthDate').required = true;
                document.getElementById('birthTime').required = true;
                document.getElementById('birthPlace').required = true;
            } else {
                birthChartSection.style.display = 'none';
                document.getElementById('birthDate').required = false;
                document.getElementById('birthTime').required = false;
                document.getElementById('birthPlace').required = false;
            }
        }

        function closeModal() {
            document.getElementById('bookingModal').classList.remove('active');
            document.body.style.overflow = 'auto';
            document.getElementById('bookingForm').reset();
        }

        // Close modal when clicking outside
        document.getElementById('bookingModal').addEventListener('click', (e) => {
            if (e.target.id === 'bookingModal') {
                closeModal();
            }
        });

        // Format card number with spaces
        document.getElementById('cardNumber').addEventListener('input', (e) => {
            let value = e.target.value.replace(/\s/g, '');
            let formattedValue = value.match(/.{1,4}/g)?.join(' ') || value;
            e.target.value = formattedValue;
        });

        // Format expiration date
        document.getElementById('expiration').addEventListener('input', (e) => {
            let value = e.target.value.replace(/\D/g, '');
            if (value.length >= 2) {
                value = value.slice(0, 2) + '/' + value.slice(2, 4);
            }
            e.target.value = value;
        });

        // Only allow numbers in CVV and zip
        document.getElementById('cvv').addEventListener('input', (e) => {
            e.target.value = e.target.value.replace(/\D/g, '');
        });

        document.getElementById('zipCode').addEventListener('input', (e) => {
            e.target.value = e.target.value.replace(/[^0-9-]/g, '');
        });

        // Booking form submission
        document.getElementById('bookingForm').addEventListener('submit', (e) => {
            e.preventDefault();
            
            // In a real application, this would process the payment and send booking details
            alert(`✨ Booking Confirmed! ✨\n\nService: ${currentService}\nPrice: ${currentPrice}\n\nThank you for booking with Astro Barbie Tarot! You will receive your reading within 24-48 hours via your preferred contact method. Check your email for confirmation details.`);
            
            closeModal();
        });
    </script>


                <div id="cepMain" class="cepHidden">
                    <div class="cepOpenBtn" style="display: none;">
                        <span>
                            <img alt="Show coupons" class="cepBtnLogo" src="chrome-extension://cakcmeinnmdkbpbjbfhfahocdcpgcghi/img/logo/logo256.png">
                        </span>
                    </div>
                    <div id="cepCont" style="display: none;">

                    <div class="noContent"><h1>Coupons not found</h1><p>Right now there are no coupons for this site, please check later</p></div></div>
                </div>
            </body></html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Astro Barbie Tarot | Celestial Guidance &amp; Mystical Readings</title>
    <link href="https://fonts.googleapis.com/css2?family=Pacifico&amp;family=Fredoka+One&amp;family=Righteous&amp;family=Poppins:wght@300;400;500;600&amp;display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --hot-pink: #E0218A;
            --barbie-pink: #FF1493;
            --light-pink: #FF69B4;
            --soft-pink: #FFB6D9;
            --pink-glow: #FFB6C1;
            --gold: #FFD700;
            --purple: #DA70D6;
            --white: #FFFFFF;
            --cream: #FFF8F0;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #FF1493 0%, #FF69B4 25%, #FFB6D9 50%, #FF69B4 75%, #FF1493 100%);
            color: var(--white);
            overflow-x: hidden;
            position: relative;
        }

        /* Animated starry background */
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }

        .star {
            position: absolute;
            background: white;
            border-radius: 50%;
            animation: twinkle 3s infinite;
        }

        @keyframes twinkle {
            0%, 100% { opacity: 0.3; transform: scale(1); }
            50% { opacity: 1; transform: scale(1.2); }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            background: linear-gradient(135deg, #E0218A 0%, #FF1493 100%);
            backdrop-filter: blur(10px);
            padding: 1rem 2rem;
            z-index: 1000;
            box-shadow: 0 6px 30px rgba(224, 33, 138, 0.6), 0 0 40px rgba(255, 105, 180, 0.4);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-family: 'Fredoka One', cursive;
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--white);
            text-shadow: 3px 3px 6px rgba(224, 33, 138, 0.6), 0 0 20px rgba(255, 182, 217, 0.8);
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            color: var(--white);
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: var(--gold);
            text-shadow: 0 0 10px rgba(255, 215, 0, 0.5);
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gold);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--white);
            font-size: 1.5rem;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 6rem 2rem 4rem;
            position: relative;
            background: radial-gradient(circle at 50% 50%, rgba(255, 20, 147, 0.4) 0%, rgba(255, 105, 180, 0.3) 50%, transparent 70%);
        }

        .hero-content {
            position: relative;
            z-index: 10;
            max-width: 900px;
        }

        .hero h1 {
            font-family: 'Pacifico', cursive;
            font-size: 5rem;
            font-weight: 700;
            color: var(--white);
            margin-bottom: 1rem;
            text-shadow: 4px 4px 8px rgba(224, 33, 138, 0.8), 0 0 60px rgba(255, 182, 217, 0.9), 0 0 80px rgba(255, 20, 147, 0.6);
            animation: float 4s ease-in-out infinite;
        }

        .hero .tagline {
            font-family: 'Righteous', cursive;
            font-size: 1.5rem;
            color: var(--white);
            margin-bottom: 1.5rem;
            font-weight: 400;
            letter-spacing: 2px;
            text-shadow: 2px 2px 4px rgba(224, 33, 138, 0.6);
        }

        .hero .welcome {
            font-size: 1.1rem;
            line-height: 1.8;
            margin-bottom: 2.5rem;
            color: var(--cream);
            max-width: 700px;
            margin-left: auto;
            margin-right: auto;
        }

        .cta-buttons {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 1rem 2.5rem;
            font-size: 1.1rem;
            font-weight: 600;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            position: relative;
            overflow: hidden;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--barbie-pink), var(--purple));
            color: var(--white);
            box-shadow: 0 4px 20px rgba(255, 105, 180, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 30px rgba(255, 105, 180, 0.6);
        }

        .btn-secondary {
            background: transparent;
            color: var(--gold);
            border: 2px solid var(--gold);
            box-shadow: 0 4px 20px rgba(255, 215, 0, 0.2);
        }

        .btn-secondary:hover {
            background: var(--gold);
            color: var(--deep-blue);
            transform: translateY(-3px);
            box-shadow: 0 6px 30px rgba(255, 215, 0, 0.4);
        }

        /* Moon decoration */
        .moon {
            position: absolute;
            top: 15%;
            right: 10%;
            width: 150px;
            height: 150px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--soft-pink) 0%, var(--light-pink) 100%);
            box-shadow: 0 0 60px rgba(255, 182, 193, 0.6), inset -10px -10px 30px rgba(0, 0, 0, 0.2);
            animation: float 6s ease-in-out infinite;
        }

        /* Section Styling */
        section {
            padding: 5rem 2rem;
            position: relative;
            z-index: 10;
        }

        .section-header {
            text-align: center;
            margin-bottom: 3rem;
        }

        .section-header h2 {
            font-family: 'Fredoka One', cursive;
            font-size: 3.5rem;
            color: var(--white);
            margin-bottom: 1rem;
            text-shadow: 3px 3px 6px rgba(224, 33, 138, 0.7), 0 0 30px rgba(255, 182, 217, 0.8);
        }

        .section-header p {
            font-size: 1.1rem;
            color: var(--light-pink);
            max-width: 700px;
            margin: 0 auto;
        }

        .divider {
            width: 100px;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--gold), transparent);
            margin: 2rem auto;
        }

        /* Services Section */
        .services {
            background: radial-gradient(circle at 30% 50%, rgba(255, 20, 147, 0.25) 0%, rgba(255, 105, 180, 0.15) 50%, transparent 70%);
        }

        .services-container {
            max-width: 1200px;
            margin: 0 auto;
        }

        .service-category {
            margin-bottom: 4rem;
        }

        .category-title {
            font-family: 'Righteous', cursive;
            font-size: 2.3rem;
            color: var(--white);
            margin-bottom: 2rem;
            text-align: center;
            position: relative;
            text-shadow: 2px 2px 4px rgba(224, 33, 138, 0.7), 0 0 20px rgba(255, 105, 180, 0.6);
        }

        .category-title::before {
            content: '✨';
            margin-right: 0.5rem;
        }

        .category-title::after {
            content: '✨';
            margin-left: 0.5rem;
        }

        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .service-card {
            background: linear-gradient(135deg, rgba(255, 20, 147, 0.3) 0%, rgba(255, 105, 180, 0.25) 100%);
            border: 3px solid rgba(224, 33, 138, 0.6);
            border-radius: 25px;
            padding: 2rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
            box-shadow: 0 8px 25px rgba(224, 33, 138, 0.4), inset 0 0 30px rgba(255, 182, 217, 0.2);
        }

        .service-card::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255, 215, 0, 0.1) 0%, transparent 70%);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .service-card:hover::before {
            opacity: 1;
        }

        .service-card:hover {
            transform: translateY(-10px) scale(1.02);
            border-color: var(--hot-pink);
            box-shadow: 0 15px 50px rgba(224, 33, 138, 0.6), 0 0 60px rgba(255, 105, 180, 0.4), inset 0 0 40px rgba(255, 182, 217, 0.3);
        }

        .service-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .service-card h3 {
            font-family: 'Righteous', cursive;
            font-size: 1.6rem;
            color: var(--white);
            margin-bottom: 0.5rem;
            text-shadow: 2px 2px 4px rgba(224, 33, 138, 0.5);
        }

        .service-card p {
            color: var(--white);
            line-height: 1.6;
            margin-bottom: 1rem;
        }

        .service-price {
            font-family: 'Fredoka One', cursive;
            font-size: 1.8rem;
            color: var(--gold);
            text-align: center;
            margin: 1rem 0;
            text-shadow: 2px 2px 4px rgba(224, 33, 138, 0.6), 0 0 15px rgba(255, 215, 0, 0.4);
        }

        .book-btn {
            padding: 0.9rem 1.8rem;
            background: linear-gradient(135deg, #E0218A 0%, #FF1493 100%);
            color: var(--white);
            border: none;
            border-radius: 30px;
            cursor: pointer;
            font-family: 'Fredoka One', cursive;
            font-size: 1rem;
            font-weight: 600;
            transition: all 0.3s ease;
            width: 100%;
            box-shadow: 0 6px 20px rgba(224, 33, 138, 0.5), inset 0 -2px 8px rgba(0, 0, 0, 0.2);
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.3);
        }

        .book-btn:hover {
            transform: scale(1.08);
            box-shadow: 0 10px 35px rgba(224, 33, 138, 0.7), 0 0 40px rgba(255, 105, 180, 0.6);
            background: linear-gradient(135deg, #FF1493 0%, #FF69B4 100%);
        }

        /* About Section */
        .about {
            background: radial-gradient(circle at 70% 50%, rgba(255, 20, 147, 0.3) 0%, rgba(255, 105, 180, 0.2) 50%, transparent 70%);
        }

        .about-container {
            max-width: 900px;
            margin: 0 auto;
            background: linear-gradient(135deg, rgba(255, 20, 147, 0.3) 0%, rgba(255, 105, 180, 0.25) 100%);
            border: 3px solid var(--gold);
            border-radius: 30px;
            padding: 3rem;
            position: relative;
            box-shadow: 0 15px 40px rgba(224, 33, 138, 0.4), inset 0 0 30px rgba(255, 182, 217, 0.3);
        }

        .about-container::before {
            content: '🌙';
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 3rem;
        }

        .about-content {
            font-size: 1.15rem;
            line-height: 1.9;
            color: var(--cream);
            text-align: center;
        }

        .about-content p {
            margin-bottom: 1.5rem;
        }

        .mission {
            margin-top: 2rem;
            padding: 2rem;
            background: rgba(255, 20, 147, 0.25);
            border: 3px solid var(--gold);
            border-radius: 20px;
            box-shadow: 0 8px 20px rgba(224, 33, 138, 0.3);
        }

        .mission h3 {
            font-family: 'Righteous', cursive;
            color: var(--white);
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(224, 33, 138, 0.6);
        }

        /* Contact Section */
        .contact {
            background: radial-gradient(circle at 50% 50%, rgba(255, 20, 147, 0.3) 0%, rgba(255, 105, 180, 0.2) 50%, transparent 70%);
        }

        .contact-container {
            max-width: 700px;
            margin: 0 auto;
        }

        .contact-form {
            background: linear-gradient(135deg, rgba(255, 20, 147, 0.3) 0%, rgba(255, 105, 180, 0.25) 100%);
            border: 3px solid var(--hot-pink);
            border-radius: 25px;
            padding: 2.5rem;
            box-shadow: 0 12px 35px rgba(224, 33, 138, 0.4), inset 0 0 30px rgba(255, 182, 217, 0.2);
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: var(--white);
            font-weight: 600;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
        }

        .form-group input,
        .form-group select,
        .form-group textarea {
            width: 100%;
            padding: 0.9rem;
            background: rgba(255, 255, 255, 0.9);
            border: 3px solid rgba(224, 33, 138, 0.5);
            border-radius: 15px;
            color: #333;
            font-family: 'Poppins', sans-serif;
            font-size: 1rem;
            transition: all 0.3s ease;
        }

        .form-group input:focus,
        .form-group select:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: var(--gold);
            box-shadow: 0 0 20px rgba(255, 215, 0, 0.6);
            background: rgba(255, 255, 255, 1);
        }

        .form-group textarea {
            min-height: 150px;
            resize: vertical;
        }

        .form-group select option {
            background: var(--deep-blue);
            color: var(--cream);
        }

        .submit-btn {
            width: 100%;
            padding: 1.2rem;
            background: linear-gradient(135deg, #E0218A 0%, #FF1493 100%);
            color: var(--white);
            border: none;
            border-radius: 30px;
            font-family: 'Fredoka One', cursive;
            font-size: 1.2rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 8px 25px rgba(224, 33, 138, 0.6), inset 0 -2px 8px rgba(0, 0, 0, 0.2);
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.3);
        }

        .submit-btn:hover {
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 12px 40px rgba(224, 33, 138, 0.8), 0 0 50px rgba(255, 105, 180, 0.6);
            background: linear-gradient(135deg, #FF1493 0%, #FF69B4 100%);
        }

        .contact-info {
            margin-top: 3rem;
            text-align: center;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
        }

        .social-links a {
            color: var(--light-pink);
            font-size: 2rem;
            transition: all 0.3s ease;
        }

        .social-links a:hover {
            color: var(--gold);
            transform: scale(1.2);
            filter: drop-shadow(0 0 10px rgba(255, 215, 0, 0.5));
        }

        /* Footer */
        footer {
            background: rgba(255, 105, 180, 0.2);
            padding: 2rem;
            text-align: center;
            position: relative;
            z-index: 10;
            border-top: 2px solid rgba(255, 215, 0, 0.3);
        }

        footer p {
            color: var(--light-pink);
            font-size: 0.9rem;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                position: fixed;
                top: 70px;
                right: -100%;
                flex-direction: column;
                background: rgba(255, 105, 180, 0.98);
                width: 200px;
                padding: 2rem;
                border-radius: 10px 0 0 10px;
                transition: right 0.3s ease;
                box-shadow: -5px 5px 20px rgba(0, 0, 0, 0.3);
            }

            .nav-links.active {
                right: 0;
            }

            .mobile-menu-btn {
                display: block;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero .tagline {
                font-size: 1rem;
            }

            .hero .welcome {
                font-size: 1rem;
            }

            .moon {
                width: 80px;
                height: 80px;
                top: 10%;
                right: 5%;
            }

            .section-header h2 {
                font-size: 2rem;
            }

            .services-grid {
                grid-template-columns: 1fr;
            }

            .cta-buttons {
                flex-direction: column;
            }

            .btn {
                width: 100%;
                max-width: 300px;
            }
        }

        /* Success message */
        .success-message {
            display: none;
            padding: 1rem;
            background: rgba(147, 112, 219, 0.3);
            border: 2px solid var(--gold);
            border-radius: 10px;
            color: var(--gold);
            text-align: center;
            margin-top: 1rem;
            animation: fadeIn 0.5s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(-10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* Modal Styles */
        .modal-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(224, 33, 138, 0.7);
            backdrop-filter: blur(8px);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            padding: 1rem;
            overflow-y: auto;
        }

        .modal-overlay.active {
            display: flex;
        }

        .modal-content {
            background: linear-gradient(135deg, #FF1493 0%, #FF69B4 100%);
            border: 4px solid var(--gold);
            border-radius: 30px;
            padding: 2.5rem;
            max-width: 600px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.5), 0 0 80px rgba(255, 182, 217, 0.6), inset 0 0 40px rgba(255, 255, 255, 0.2);
            animation: modalSlideIn 0.4s ease;
        }

        @keyframes modalSlideIn {
            from {
                opacity: 0;
                transform: scale(0.8) translateY(-50px);
            }
            to {
                opacity: 1;
                transform: scale(1) translateY(0);
            }
        }

        .modal-header {
            text-align: center;
            margin-bottom: 2rem;
            border-bottom: 3px solid rgba(255, 215, 0, 0.5);
            padding-bottom: 1rem;
        }

        .modal-header h3 {
            font-family: 'Fredoka One', cursive;
            font-size: 2rem;
            color: var(--white);
            margin-bottom: 0.5rem;
            text-shadow: 3px 3px 6px rgba(0, 0, 0, 0.4);
        }

        .modal-price {
            font-family: 'Pacifico', cursive;
            font-size: 2.5rem;
            color: var(--gold);
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5), 0 0 20px rgba(255, 215, 0, 0.5);
        }

        .modal-section {
            margin-bottom: 2rem;
        }

        .modal-section h4 {
            font-family: 'Righteous', cursive;
            font-size: 1.3rem;
            color: var(--white);
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        .modal-form-group {
            margin-bottom: 1rem;
        }

        .modal-form-group label {
            display: block;
            margin-bottom: 0.4rem;
            color: var(--white);
            font-weight: 600;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
        }

        .modal-form-group input,
        .modal-form-group select,
        .modal-form-group textarea {
            width: 100%;
            padding: 0.8rem;
            background: rgba(255, 255, 255, 0.95);
            border: 3px solid rgba(224, 33, 138, 0.5);
            border-radius: 15px;
            color: #333;
            font-family: 'Poppins', sans-serif;
            font-size: 0.95rem;
            transition: all 0.3s ease;
        }

        .modal-form-group input:focus,
        .modal-form-group select:focus,
        .modal-form-group textarea:focus {
            outline: none;
            border-color: var(--gold);
            box-shadow: 0 0 20px rgba(255, 215, 0, 0.5);
            background: rgba(255, 255, 255, 1);
        }

        .modal-form-group textarea {
            min-height: 100px;
            resize: vertical;
        }

        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 1rem;
        }

        .modal-buttons {
            display: flex;
            gap: 1rem;
            margin-top: 2rem;
        }

        .modal-btn {
            flex: 1;
            padding: 1rem;
            border: none;
            border-radius: 25px;
            font-family: 'Fredoka One', cursive;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .modal-btn-primary {
            background: linear-gradient(135deg, var(--gold) 0%, #FFD700 100%);
            color: #333;
            box-shadow: 0 6px 20px rgba(255, 215, 0, 0.5);
        }

        .modal-btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.7);
        }

        .modal-btn-secondary {
            background: rgba(255, 255, 255, 0.3);
            color: var(--white);
            border: 2px solid rgba(255, 255, 255, 0.5);
        }

        .modal-btn-secondary:hover {
            background: rgba(255, 255, 255, 0.4);
            transform: translateY(-3px);
        }

        .modal-disclaimer {
            margin-top: 1.5rem;
            padding: 1rem;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            font-size: 0.85rem;
            text-align: center;
            color: var(--white);
        }

        .close-modal {
            position: absolute;
            top: 1rem;
            right: 1rem;
            background: rgba(255, 255, 255, 0.3);
            border: none;
            color: var(--white);
            font-size: 1.8rem;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
        }

        .close-modal:hover {
            background: rgba(255, 255, 255, 0.5);
            transform: rotate(90deg);
        }

        @media (max-width: 768px) {
            .form-row {
                grid-template-columns: 1fr;
            }
            
            .modal-content {
                padding: 1.5rem;
            }
            
            .modal-buttons {
                flex-direction: column;
            }
        }
    </style>
<style>
            @font-face {
                font-family: 'Roboto';
                font-style: normal;
                font-weight: 400;
                src: url('chrome-extension://cakcmeinnmdkbpbjbfhfahocdcpgcghi/fonts/Roboto/roboto-400.woff') format('woff');
            }
        </style><style>
            @font-face {
                font-family: 'Roboto';
                font-style: normal;
                font-weight: 500;
                src: url('chrome-extension://cakcmeinnmdkbpbjbfhfahocdcpgcghi/fonts/Roboto/roboto-500.woff') format('woff');
            }
        </style></head>
        <body>
    <!-- Animated stars background -->
    <div class="stars" id="stars"><div class="star" style="left: 92.7033%; top: 26.6128%; width: 2.97285px; height: 2.97285px; animation-delay: 1.15097s;"></div><div class="star" style="left: 46.0991%; top: 85.823%; width: 2.11197px; height: 2.11197px; animation-delay: 0.530241s;"></div><div class="star" style="left: 8.74684%; top: 12.3371%; width: 1.22054px; height: 1.22054px; animation-delay: 0.364763s;"></div><div class="star" style="left: 45.1731%; top: 79.6121%; width: 2.56185px; height: 2.56185px; animation-delay: 1.23571s;"></div><div class="star" style="left: 9.03374%; top: 89.9046%; width: 2.43084px; height: 2.43084px; animation-delay: 1.80509s;"></div><div class="star" style="left: 62.1353%; top: 15.6149%; width: 2.30839px; height: 2.30839px; animation-delay: 1.57091s;"></div><div class="star" style="left: 14.203%; top: 22.517%; width: 2.50016px; height: 2.50016px; animation-delay: 0.31075s;"></div><div class="star" style="left: 51.5751%; top: 25.016%; width: 1.90399px; height: 1.90399px; animation-delay: 0.891424s;"></div><div class="star" style="left: 73.6909%; top: 98.3882%; width: 2.74276px; height: 2.74276px; animation-delay: 1.60323s;"></div><div class="star" style="left: 8.05385%; top: 1.51939%; width: 3.75112px; height: 3.75112px; animation-delay: 0.109459s;"></div><div class="star" style="left: 73.0817%; top: 43.5113%; width: 2.79724px; height: 2.79724px; animation-delay: 2.37735s;"></div><div class="star" style="left: 14.9947%; top: 46.7171%; width: 1.5822px; height: 1.5822px; animation-delay: 0.407526s;"></div><div class="star" style="left: 11.255%; top: 6.04255%; width: 1.82747px; height: 1.82747px; animation-delay: 0.892922s;"></div><div class="star" style="left: 83.1244%; top: 92.1526%; width: 2.86268px; height: 2.86268px; animation-delay: 1.60632s;"></div><div class="star" style="left: 15.1192%; top: 69.7962%; width: 1.84092px; height: 1.84092px; animation-delay: 0.238114s;"></div><div class="star" style="left: 53.2741%; top: 27.4402%; width: 2.42841px; height: 2.42841px; animation-delay: 1.07219s;"></div><div class="star" style="left: 3.38875%; top: 38.1967%; width: 3.40699px; height: 3.40699px; animation-delay: 0.716898s;"></div><div class="star" style="left: 91.6922%; top: 46.5871%; width: 2.85577px; height: 2.85577px; animation-delay: 0.443119s;"></div><div class="star" style="left: 33.3623%; top: 56.8979%; width: 3.80194px; height: 3.80194px; animation-delay: 0.609555s;"></div><div class="star" style="left: 7.39749%; top: 39.3348%; width: 1.62909px; height: 1.62909px; animation-delay: 1.41769s;"></div><div class="star" style="left: 95.3873%; top: 92.6303%; width: 3.92068px; height: 3.92068px; animation-delay: 2.32026s;"></div><div class="star" style="left: 46.1795%; top: 72.877%; width: 2.84341px; height: 2.84341px; animation-delay: 2.98298s;"></div><div class="star" style="left: 29.8222%; top: 13.3019%; width: 2.49329px; height: 2.49329px; animation-delay: 0.0315615s;"></div><div class="star" style="left: 8.39489%; top: 49.5418%; width: 2.19949px; height: 2.19949px; animation-delay: 2.83992s;"></div><div class="star" style="left: 61.3333%; top: 99.3756%; width: 2.28538px; height: 2.28538px; animation-delay: 1.37138s;"></div><div class="star" style="left: 29.8923%; top: 66.9705%; width: 2.4856px; height: 2.4856px; animation-delay: 0.689491s;"></div><div class="star" style="left: 3.4562%; top: 10.2875%; width: 2.18639px; height: 2.18639px; animation-delay: 2.62534s;"></div><div class="star" style="left: 11.9608%; top: 27.6645%; width: 2.97494px; height: 2.97494px; animation-delay: 2.96394s;"></div><div class="star" style="left: 4.91239%; top: 92.8744%; width: 2.74527px; height: 2.74527px; animation-delay: 0.189749s;"></div><div class="star" style="left: 86.775%; top: 82.1276%; width: 3.79993px; height: 3.79993px; animation-delay: 0.299699s;"></div><div class="star" style="left: 13.7064%; top: 37.8763%; width: 3.09976px; height: 3.09976px; animation-delay: 0.438977s;"></div><div class="star" style="left: 48.1226%; top: 29.1747%; width: 2.85089px; height: 2.85089px; animation-delay: 0.63448s;"></div><div class="star" style="left: 96.2032%; top: 76.8861%; width: 1.31934px; height: 1.31934px; animation-delay: 1.05504s;"></div><div class="star" style="left: 18.9346%; top: 3.04029%; width: 2.78452px; height: 2.78452px; animation-delay: 2.28684s;"></div><div class="star" style="left: 40.2349%; top: 75.737%; width: 2.75684px; height: 2.75684px; animation-delay: 0.038905s;"></div><div class="star" style="left: 46.0758%; top: 45.9828%; width: 3.37752px; height: 3.37752px; animation-delay: 0.615531s;"></div><div class="star" style="left: 54.0007%; top: 98.3541%; width: 2.42689px; height: 2.42689px; animation-delay: 1.10115s;"></div><div class="star" style="left: 96.7546%; top: 46.2979%; width: 3.33571px; height: 3.33571px; animation-delay: 2.15484s;"></div><div class="star" style="left: 54.4858%; top: 70.381%; width: 3.44114px; height: 3.44114px; animation-delay: 1.08092s;"></div><div class="star" style="left: 20.8034%; top: 60.3747%; width: 2.51889px; height: 2.51889px; animation-delay: 1.56709s;"></div><div class="star" style="left: 5.17268%; top: 30.8922%; width: 3.53195px; height: 3.53195px; animation-delay: 0.765851s;"></div><div class="star" style="left: 45.1807%; top: 50.7209%; width: 1.64809px; height: 1.64809px; animation-delay: 1.4046s;"></div><div class="star" style="left: 93.3058%; top: 59.1562%; width: 3.40444px; height: 3.40444px; animation-delay: 1.62633s;"></div><div class="star" style="left: 93.2663%; top: 22.7424%; width: 2.02484px; height: 2.02484px; animation-delay: 2.65937s;"></div><div class="star" style="left: 87.284%; top: 11.3816%; width: 2.71886px; height: 2.71886px; animation-delay: 0.547267s;"></div><div class="star" style="left: 66.6954%; top: 43.8024%; width: 1.85989px; height: 1.85989px; animation-delay: 0.872606s;"></div><div class="star" style="left: 34.9072%; top: 71.8433%; width: 1.38301px; height: 1.38301px; animation-delay: 2.20325s;"></div><div class="star" style="left: 43.703%; top: 72.6867%; width: 2.35194px; height: 2.35194px; animation-delay: 0.944744s;"></div><div class="star" style="left: 21.62%; top: 79.0594%; width: 3.29322px; height: 3.29322px; animation-delay: 2.45157s;"></div><div class="star" style="left: 58.7848%; top: 66.4044%; width: 1.24257px; height: 1.24257px; animation-delay: 0.274266s;"></div><div class="star" style="left: 69.2126%; top: 79.0223%; width: 3.63983px; height: 3.63983px; animation-delay: 1.95588s;"></div><div class="star" style="left: 8.93102%; top: 86.8487%; width: 1.25491px; height: 1.25491px; animation-delay: 0.256593s;"></div><div class="star" style="left: 69.2278%; top: 98.5707%; width: 2.93195px; height: 2.93195px; animation-delay: 1.64112s;"></div><div class="star" style="left: 87.1231%; top: 77.6282%; width: 1.30527px; height: 1.30527px; animation-delay: 1.19856s;"></div><div class="star" style="left: 60.9967%; top: 69.0847%; width: 3.45216px; height: 3.45216px; animation-delay: 1.60142s;"></div><div class="star" style="left: 99.7785%; top: 47.172%; width: 3.54831px; height: 3.54831px; animation-delay: 1.23874s;"></div><div class="star" style="left: 38.8034%; top: 49.1927%; width: 1.95225px; height: 1.95225px; animation-delay: 0.277779s;"></div><div class="star" style="left: 89.9086%; top: 55.6083%; width: 2.57449px; height: 2.57449px; animation-delay: 2.59675s;"></div><div class="star" style="left: 62.6913%; top: 55.4036%; width: 3.89689px; height: 3.89689px; animation-delay: 1.9693s;"></div><div class="star" style="left: 26.6192%; top: 48.1205%; width: 3.1355px; height: 3.1355px; animation-delay: 1.70651s;"></div><div class="star" style="left: 12.9089%; top: 49.1678%; width: 1.11087px; height: 1.11087px; animation-delay: 2.18717s;"></div><div class="star" style="left: 97.4037%; top: 9.29459%; width: 2.73794px; height: 2.73794px; animation-delay: 2.50897s;"></div><div class="star" style="left: 80.6903%; top: 92.6567%; width: 3.13368px; height: 3.13368px; animation-delay: 2.99775s;"></div><div class="star" style="left: 18.1606%; top: 63.5342%; width: 2.97684px; height: 2.97684px; animation-delay: 1.67798s;"></div><div class="star" style="left: 22.7263%; top: 27.9681%; width: 1.95361px; height: 1.95361px; animation-delay: 0.70688s;"></div><div class="star" style="left: 24.8018%; top: 57.5951%; width: 3.50731px; height: 3.50731px; animation-delay: 0.451584s;"></div><div class="star" style="left: 7.90311%; top: 26.8005%; width: 1.02045px; height: 1.02045px; animation-delay: 2.35474s;"></div><div class="star" style="left: 21.0903%; top: 95.9074%; width: 1.02623px; height: 1.02623px; animation-delay: 1.37666s;"></div><div class="star" style="left: 58.7461%; top: 59.5806%; width: 3.61719px; height: 3.61719px; animation-delay: 0.693097s;"></div><div class="star" style="left: 94.6448%; top: 7.14564%; width: 3.56755px; height: 3.56755px; animation-delay: 1.66868s;"></div><div class="star" style="left: 8.23597%; top: 86.9724%; width: 1.66307px; height: 1.66307px; animation-delay: 2.0002s;"></div><div class="star" style="left: 81.7207%; top: 68.8526%; width: 2.18303px; height: 2.18303px; animation-delay: 0.292186s;"></div><div class="star" style="left: 28.5503%; top: 97.3904%; width: 3.61629px; height: 3.61629px; animation-delay: 2.24006s;"></div><div class="star" style="left: 45.1389%; top: 16.4708%; width: 1.9537px; height: 1.9537px; animation-delay: 0.251632s;"></div><div class="star" style="left: 64.146%; top: 84.8222%; width: 2.55734px; height: 2.55734px; animation-delay: 1.55022s;"></div><div class="star" style="left: 50.2913%; top: 93.575%; width: 2.34508px; height: 2.34508px; animation-delay: 1.36671s;"></div><div class="star" style="left: 40.4033%; top: 2.06171%; width: 1.18303px; height: 1.18303px; animation-delay: 0.744915s;"></div><div class="star" style="left: 54.3864%; top: 43.2614%; width: 3.13747px; height: 3.13747px; animation-delay: 2.68385s;"></div><div class="star" style="left: 94.787%; top: 64.2502%; width: 1.14352px; height: 1.14352px; animation-delay: 0.463721s;"></div><div class="star" style="left: 22.8428%; top: 57.4846%; width: 2.64361px; height: 2.64361px; animation-delay: 0.745319s;"></div><div class="star" style="left: 66.1933%; top: 3.9538%; width: 1.28939px; height: 1.28939px; animation-delay: 0.123872s;"></div><div class="star" style="left: 15.2057%; top: 19.9894%; width: 1.98869px; height: 1.98869px; animation-delay: 1.52281s;"></div><div class="star" style="left: 42.0647%; top: 96.8133%; width: 3.53563px; height: 3.53563px; animation-delay: 2.12907s;"></div><div class="star" style="left: 0.730937%; top: 29.612%; width: 2.1956px; height: 2.1956px; animation-delay: 2.52475s;"></div><div class="star" style="left: 28.603%; top: 0.886376%; width: 1.25187px; height: 1.25187px; animation-delay: 0.257642s;"></div><div class="star" style="left: 42.1895%; top: 82.8899%; width: 1.20413px; height: 1.20413px; animation-delay: 1.03236s;"></div><div class="star" style="left: 9.93103%; top: 61.5282%; width: 1.39504px; height: 1.39504px; animation-delay: 2.56455s;"></div><div class="star" style="left: 20.6104%; top: 31.3537%; width: 2.15152px; height: 2.15152px; animation-delay: 2.48348s;"></div><div class="star" style="left: 81.559%; top: 20.5135%; width: 1.23319px; height: 1.23319px; animation-delay: 1.03099s;"></div><div class="star" style="left: 43.6016%; top: 66.5121%; width: 1.98141px; height: 1.98141px; animation-delay: 0.0226922s;"></div><div class="star" style="left: 54.7334%; top: 59.8352%; width: 1.5188px; height: 1.5188px; animation-delay: 0.964745s;"></div><div class="star" style="left: 80.8883%; top: 80.7149%; width: 2.2038px; height: 2.2038px; animation-delay: 2.05054s;"></div><div class="star" style="left: 83.3227%; top: 68.3452%; width: 3.57241px; height: 3.57241px; animation-delay: 2.66626s;"></div><div class="star" style="left: 35.4429%; top: 90.262%; width: 3.21492px; height: 3.21492px; animation-delay: 0.434469s;"></div><div class="star" style="left: 23.3933%; top: 50.6034%; width: 3.9024px; height: 3.9024px; animation-delay: 1.51621s;"></div><div class="star" style="left: 80.9185%; top: 96.5236%; width: 1.06424px; height: 1.06424px; animation-delay: 0.341104s;"></div><div class="star" style="left: 41.8992%; top: 54.8181%; width: 3.46235px; height: 3.46235px; animation-delay: 0.493192s;"></div><div class="star" style="left: 81.0906%; top: 95.072%; width: 2.81009px; height: 2.81009px; animation-delay: 1.52449s;"></div><div class="star" style="left: 71.1634%; top: 19.1339%; width: 3.78421px; height: 3.78421px; animation-delay: 2.63686s;"></div><div class="star" style="left: 18.0181%; top: 4.26874%; width: 1.0723px; height: 1.0723px; animation-delay: 2.76445s;"></div></div>

    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <div class="logo">✨ Astro Barbie Tarot ✨</div>
            <ul class="nav-links" id="navLinks">
                <li><a href="#home">Home</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
            <button class="mobile-menu-btn" id="mobileMenuBtn">☰</button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="moon"></div>
        <div class="hero-content">
            <h1>Astro Barbie Tarot</h1>
            <p class="tagline">✨ Connecting You with Spirit Guides &amp; the Universe ✨</p>
            <p class="welcome">
                Welcome to a magical space where cosmic wisdom meets divine guidance. 
                Let me help you find clarity, direction, and insight through the ancient art of tarot 
                and the mystical language of the stars.
            </p>
            <div class="cta-buttons">
                <a href="#services" class="btn btn-primary">Explore Services</a>
                <a href="#about" class="btn btn-secondary">Learn More</a>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="services">
        <div class="section-header">
            <h2>Mystical Services</h2>
            <p>Choose from a variety of readings and cosmic guidance options</p>
            <div class="divider"></div>
        </div>

        <div class="services-container">
            <!-- General Tarot Readings -->
            <div class="service-category">
                <h3 class="category-title">General Tarot Readings</h3>
                <div class="services-grid">
                    <div class="service-card">
                        <div class="service-icon">🔮</div>
                        <h3>Single Card Pull Reading</h3>
                        <p>Quick guidance and insight from the universe. Perfect for daily direction or a specific question.</p>
                        <div class="service-price">$15</div>
                        <button class="book-btn" onclick="openModal('Single Card Pull Reading', '$15')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🌟</div>
                        <h3>Three Card Spread</h3>
                        <p>Explore your past, present, and future. Understand the journey you're on and where it's leading.</p>
                        <div class="service-price">$33</div>
                        <button class="book-btn" onclick="openModal('Three Card Spread', '$33')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🎴</div>
                        <h3>Celtic Cross Reading</h3>
                        <p>Comprehensive 10-card spread providing deep insight into your situation, obstacles, and outcomes.</p>
                        <div class="service-price">$55</div>
                        <button class="book-btn" onclick="openModal('Celtic Cross Reading', '$55')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">💖</div>
                        <h3>Relationship Reading</h3>
                        <p>Gain clarity on love, partnerships, and connections. Understand the dynamics and future potential.</p>
                        <div class="service-price">$44</div>
                        <button class="book-btn" onclick="openModal('Relationship Reading', '$44')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">💼</div>
                        <h3>Career Path Reading</h3>
                        <p>Professional guidance for your career journey. Discover your true calling and next steps.</p>
                        <div class="service-price">$44</div>
                        <button class="book-btn" onclick="openModal('Career Path Reading', '$44')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">⚖️</div>
                        <h3>Decision Making Reading</h3>
                        <p>Clarity on important choices. See the outcomes of different paths before you choose.</p>
                        <div class="service-price">$33</div>
                        <button class="book-btn" onclick="openModal('Decision Making Reading', '$33')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">📅</div>
                        <h3>Year Ahead Reading</h3>
                        <p>12-month forecast covering all areas of your life. Plan your year with cosmic guidance.</p>
                        <div class="service-price">$111</div>
                        <button class="book-btn" onclick="openModal('Year Ahead Reading', '$111')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🌑</div>
                        <h3>Shadow Work Reading</h3>
                        <p>Deep inner healing and self-discovery. Face your shadows and embrace your light.</p>
                        <div class="service-price">$55</div>
                        <button class="book-btn" onclick="openModal('Shadow Work Reading', '$55')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🕊️</div>
                        <h3>Spiritual Guidance Reading</h3>
                        <p>Connect with your higher self and spirit guides. Receive divine messages and wisdom.</p>
                        <div class="service-price">$44</div>
                        <button class="book-btn" onclick="openModal('Spiritual Guidance Reading', '$44')">💖 Book &amp; Pay Now 💖</button>
                    </div>
                </div>
            </div>

            <!-- Specialized Readings -->
            <div class="service-category">
                <h3 class="category-title">Specialized Cosmic Readings</h3>
                <div class="services-grid">
                    <div class="service-card">
                        <div class="service-icon">⭐</div>
                        <h3>Birth Chart Reading</h3>
                        <p>Full natal chart interpretation revealing your cosmic blueprint and life purpose.</p>
                        <div class="service-price">$88</div>
                        <button class="book-btn" onclick="openModal('Birth Chart Reading', '$88', true)">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">💕</div>
                        <h3>Compatibility Reading</h3>
                        <p>Synastry analysis between two people. Perfect for romantic or business partnerships.</p>
                        <div class="service-price">$77</div>
                        <button class="book-btn" onclick="openModal('Compatibility Reading', '$77', true)">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🎂</div>
                        <h3>Solar Return Reading</h3>
                        <p>Birthday year forecast based on your solar return chart. What does your new year hold?</p>
                        <div class="service-price">$66</div>
                        <button class="book-btn" onclick="openModal('Solar Return Reading', '$66', true)">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🌙</div>
                        <h3>New Moon Intention Setting</h3>
                        <p>Harness new moon energy to set powerful intentions and manifest your desires.</p>
                        <div class="service-price">$33</div>
                        <button class="book-btn" onclick="openModal('New Moon Intention Setting', '$33')">💖 Book &amp; Pay Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🌕</div>
                        <h3>Full Moon Release Reading</h3>
                        <p>Release what no longer serves you during the full moon. Let go and make space for new blessings.</p>
                        <div class="service-price">$33</div>
                        <button class="book-btn" onclick="openModal('Full Moon Release Reading', '$33')">💖 Book &amp; Pay Now 💖</button>
                    </div>
                </div>
            </div>

            <!-- Subscription Services -->
            <div class="service-category">
                <h3 class="category-title">Subscription Services</h3>
                <div class="services-grid">
                    <div class="service-card">
                        <div class="service-icon">📖</div>
                        <h3>Monthly Horoscope Subscription</h3>
                        <p>Personalized monthly insights based on your birth chart. Know what cosmic energies are at play.</p>
                        <div class="service-price">$44/mo</div>
                        <button class="book-btn" onclick="openModal('Monthly Horoscope Subscription', '$44/month', true)">💖 Subscribe Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">🃏</div>
                        <h3>Weekly Tarot Guidance</h3>
                        <p>Weekly card pulls and messages to guide you through each week with clarity and confidence.</p>
                        <div class="service-price">$55/mo</div>
                        <button class="book-btn" onclick="openModal('Weekly Tarot Guidance', '$55/month')">💖 Subscribe Now 💖</button>
                    </div>

                    <div class="service-card">
                        <div class="service-icon">👑</div>
                        <h3>VIP Cosmic Package</h3>
                        <p>Combination of monthly horoscopes and weekly tarot readings. Full cosmic support all month long.</p>
                        <div class="service-price">$88/mo</div>
                        <button class="book-btn" onclick="openModal('VIP Cosmic Package', '$88/month', true)">💖 Subscribe Now 💖</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="section-header">
            <h2>About Your Guide</h2>
            <p>Meet the cosmic connector behind the cards</p>
            <div class="divider"></div>
        </div>

        <div class="about-container">
            <div class="about-content">
                <p>
                    I have been practicing tarot for 5 years and wanted to do something to help people 
                    who are lacking direction or need clarity, insight, or advice but don't know who to ask!
                </p>
                <p>
                    Who's better than asking your spirit guides, or the universe, or higher power for answers? 
                    I connect with those energies and deliver messages through tarot.
                </p>
                <div class="mission">
                    <h3>✨ My Mission ✨</h3>
                    <p>
                        My purpose is to bridge the gap between you and the divine wisdom that surrounds us all. 
                        Through tarot and cosmic guidance, I help you unlock the answers that already exist within 
                        and around you. Every reading is a sacred conversation with the universe, tailored specifically 
                        to illuminate your unique path.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="section-header">
            <h2>Connect with the Cosmos</h2>
            <p>Ready to receive your guidance? Let's connect!</p>
            <div class="divider"></div>
        </div>

        <div class="contact-container">
            <form class="contact-form" id="contactForm">
                <div class="form-group">
                    <label for="name">Name *</label>
                    <input type="text" id="name" name="name" required="" placeholder="Your full name">
                </div>

                <div class="form-group">
                    <label for="email">Email Address *</label>
                    <input type="email" id="email" name="email" required="" placeholder="your@email.com">
                </div>

                <div class="form-group">
                    <label for="phone">Phone Number</label>
                    <input type="tel" id="phone" name="phone" placeholder="(555) 123-4567">
                </div>

                <div class="form-group">
                    <label for="service">Service Interested In *</label>
                    <select id="service" name="service" required="">
                        <option value="">-- Select a Service --</option>
                        <option value="Single Card Pull Reading">Single Card Pull Reading</option>
                        <option value="Three Card Spread">Three Card Spread</option>
                        <option value="Celtic Cross Reading">Celtic Cross Reading</option>
                        <option value="Relationship Reading">Relationship Reading</option>
                        <option value="Career Path Reading">Career Path Reading</option>
                        <option value="Decision Making Reading">Decision Making Reading</option>
                        <option value="Year Ahead Reading">Year Ahead Reading</option>
                        <option value="Shadow Work Reading">Shadow Work Reading</option>
                        <option value="Spiritual Guidance Reading">Spiritual Guidance Reading</option>
                        <option value="Birth Chart Reading">Birth Chart Reading</option>
                        <option value="Compatibility Reading">Compatibility Reading</option>
                        <option value="Solar Return Reading">Solar Return Reading</option>
                        <option value="New Moon Intention Setting">New Moon Intention Setting</option>
                        <option value="Full Moon Release Reading">Full Moon Release Reading</option>
                        <option value="Monthly Horoscope Subscription">Monthly Horoscope Subscription</option>
                        <option value="Weekly Tarot Guidance">Weekly Tarot Guidance</option>
                        <option value="VIP Cosmic Package">VIP Cosmic Package</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="message">Message *</label>
                    <textarea id="message" name="message" required="" placeholder="Tell me about what guidance you're seeking..."></textarea>
                </div>

                <button type="submit" class="submit-btn">Send Message ✨</button>
                <div class="success-message" id="successMessage">
                    ✨ Thank you! Your message has been received. I'll connect with you soon! ✨
                </div>
            </form>

            <div class="contact-info">
                <p style="color: var(--light-pink); margin-top: 2rem;">
                    <strong>Email:</strong> <a href="mailto:astrobarbietarot@email.com" style="color: var(--gold);">astrobarbietarot@email.com</a>
                </p>
                <div class="social-links">
                    <a href="https://instagram.com" target="_blank" title="Instagram">📷</a>
                    <a href="https://tiktok.com" target="_blank" title="TikTok">🎵</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Booking Modal -->
    <div class="modal-overlay" id="bookingModal">
        <div class="modal-content">
            <button class="close-modal" onclick="closeModal()">×</button>
            <div class="modal-header">
                <h3 id="modalServiceName"></h3>
                <div class="modal-price" id="modalServicePrice"></div>
            </div>

            <form id="bookingForm">
                <!-- Payment Information -->
                <div class="modal-section">
                    <h4>💳 Payment Information</h4>
                    <div class="modal-form-group">
                        <label for="cardName">Cardholder Name *</label>
                        <input type="text" id="cardName" name="cardName" required="" placeholder="Name on card">
                    </div>
                    <div class="modal-form-group">
                        <label for="cardNumber">Card Number *</label>
                        <input type="text" id="cardNumber" name="cardNumber" required="" placeholder="1234 5678 9012 3456" maxlength="19">
                    </div>
                    <div class="form-row">
                        <div class="modal-form-group">
                            <label for="expiration">Expiration *</label>
                            <input type="text" id="expiration" name="expiration" required="" placeholder="MM/YY" maxlength="5">
                        </div>
                        <div class="modal-form-group">
                            <label for="cvv">CVV *</label>
                            <input type="text" id="cvv" name="cvv" required="" placeholder="123" maxlength="4">
                        </div>
                    </div>
                    <div class="modal-form-group">
                        <label for="zipCode">Zip Code *</label>
                        <input type="text" id="zipCode" name="zipCode" required="" placeholder="12345" maxlength="10">
                    </div>
                </div>

                <!-- Contact Information -->
                <div class="modal-section">
                    <h4>📧 Contact Information</h4>
                    <div class="modal-form-group">
                        <label for="clientName">Your Name *</label>
                        <input type="text" id="clientName" name="clientName" required="" placeholder="Full name">
                    </div>
                    <div class="modal-form-group">
                        <label for="clientEmail">Email Address *</label>
                        <input type="email" id="clientEmail" name="clientEmail" required="" placeholder="your@email.com">
                    </div>
                    <div class="modal-form-group">
                        <label for="clientPhone">Phone Number *</label>
                        <input type="tel" id="clientPhone" name="clientPhone" required="" placeholder="(555) 123-4567">
                    </div>
                    <div class="modal-form-group">
                        <label for="contactMethod">Preferred Contact Method *</label>
                        <select id="contactMethod" name="contactMethod" required="">
                            <option value="">-- Select --</option>
                            <option value="email">Email</option>
                            <option value="phone">Phone</option>
                            <option value="text">Text Message</option>
                        </select>
                    </div>
                </div>

                <!-- Birth Chart Information (conditional) -->
                <div class="modal-section" id="birthChartSection" style="display: none;">
                    <h4>🌟 Birth Chart Information</h4>
                    <div class="modal-form-group">
                        <label for="birthDate">Birth Date *</label>
                        <input type="date" id="birthDate" name="birthDate">
                    </div>
                    <div class="modal-form-group">
                        <label for="birthTime">Birth Time *</label>
                        <input type="time" id="birthTime" name="birthTime">
                    </div>
                    <div class="modal-form-group">
                        <label for="birthPlace">Birth Place (City, State/Country) *</label>
                        <input type="text" id="birthPlace" name="birthPlace" placeholder="Los Angeles, CA">
                    </div>
                </div>

                <!-- Question/Guidance -->
                <div class="modal-section">
                    <h4>✨ Your Question or Area of Focus</h4>
                    <div class="modal-form-group">
                        <label for="question">What guidance are you seeking? *</label>
                        <textarea id="question" name="question" required="" placeholder="Share what you'd like clarity or insight on..."></textarea>
                    </div>
                </div>

                <!-- Buttons -->
                <div class="modal-buttons">
                    <button type="button" class="modal-btn modal-btn-secondary" onclick="closeModal()">Cancel</button>
                    <button type="submit" class="modal-btn modal-btn-primary">Complete Booking ✨</button>
                </div>

                <div class="modal-disclaimer">
                    🔮 Your reading will be delivered within 24-48 hours via your preferred contact method. All information is kept confidential.
                </div>
            </form>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <p>✨ Astro Barbie Tarot © 2025 | Connecting You with Divine Guidance ✨</p>
        <p style="margin-top: 0.5rem; font-size: 0.8rem;">All readings are for entertainment and spiritual guidance purposes.</p>
    </footer>

    <script>
        // Generate animated stars
        function createStars() {
            const starsContainer = document.getElementById('stars');
            const numberOfStars = 100;

            for (let i = 0; i < numberOfStars; i++) {
                const star = document.createElement('div');
                star.className = 'star';
                star.style.left = Math.random() * 100 + '%';
                star.style.top = Math.random() * 100 + '%';
                star.style.width = Math.random() * 3 + 1 + 'px';
                star.style.height = star.style.width;
                star.style.animationDelay = Math.random() * 3 + 's';
                starsContainer.appendChild(star);
            }
        }

        // Mobile menu toggle
        const mobileMenuBtn = document.getElementById('mobileMenuBtn');
        const navLinks = document.getElementById('navLinks');

        mobileMenuBtn.addEventListener('click', () => {
            navLinks.classList.toggle('active');
        });

        // Close mobile menu when clicking a link
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
            });
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    const navHeight = document.querySelector('nav').offsetHeight;
                    const targetPosition = target.offsetTop - navHeight;
                    window.scrollTo({
                        top: targetPosition,
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Scroll to contact with service pre-selected
        function scrollToContact(serviceName) {
            const serviceSelect = document.getElementById('service');
            serviceSelect.value = serviceName;
            
            const contactSection = document.getElementById('contact');
            const navHeight = document.querySelector('nav').offsetHeight;
            const targetPosition = contactSection.offsetTop - navHeight;
            
            window.scrollTo({
                top: targetPosition,
                behavior: 'smooth'
            });
        }

        // Form submission handler
        const contactForm = document.getElementById('contactForm');
        const successMessage = document.getElementById('successMessage');

        contactForm.addEventListener('submit', (e) => {
            e.preventDefault();
            
            // Show success message
            successMessage.style.display = 'block';
            
            // Reset form
            contactForm.reset();
            
            // Hide success message after 5 seconds
            setTimeout(() => {
                successMessage.style.display = 'none';
            }, 5000);
        });

        // Initialize stars on page load
        window.addEventListener('load', createStars);

        // Modal functionality
        let currentService = '';
        let currentPrice = '';
        let requiresBirthChart = false;

        function openModal(serviceName, price, needsBirthChart = false) {
            currentService = serviceName;
            currentPrice = price;
            requiresBirthChart = needsBirthChart;

            document.getElementById('modalServiceName').textContent = serviceName;
            document.getElementById('modalServicePrice').textContent = price;
            document.getElementById('bookingModal').classList.add('active');
            document.body.style.overflow = 'hidden';

            // Show/hide birth chart section
            const birthChartSection = document.getElementById('birthChartSection');
            if (needsBirthChart) {
                birthChartSection.style.display = 'block';
                document.getElementById('birthDate').required = true;
                document.getElementById('birthTime').required = true;
                document.getElementById('birthPlace').required = true;
            } else {
                birthChartSection.style.display = 'none';
                document.getElementById('birthDate').required = false;
                document.getElementById('birthTime').required = false;
                document.getElementById('birthPlace').required = false;
            }
        }

        function closeModal() {
            document.getElementById('bookingModal').classList.remove('active');
            document.body.style.overflow = 'auto';
            document.getElementById('bookingForm').reset();
        }

        // Close modal when clicking outside
        document.getElementById('bookingModal').addEventListener('click', (e) => {
            if (e.target.id === 'bookingModal') {
                closeModal();
            }
        });

        // Format card number with spaces
        document.getElementById('cardNumber').addEventListener('input', (e) => {
            let value = e.target.value.replace(/\s/g, '');
            let formattedValue = value.match(/.{1,4}/g)?.join(' ') || value;
            e.target.value = formattedValue;
        });

        // Format expiration date
        document.getElementById('expiration').addEventListener('input', (e) => {
            let value = e.target.value.replace(/\D/g, '');
            if (value.length >= 2) {
                value = value.slice(0, 2) + '/' + value.slice(2, 4);
            }
            e.target.value = value;
        });

        // Only allow numbers in CVV and zip
        document.getElementById('cvv').addEventListener('input', (e) => {
            e.target.value = e.target.value.replace(/\D/g, '');
        });

        document.getElementById('zipCode').addEventListener('input', (e) => {
            e.target.value = e.target.value.replace(/[^0-9-]/g, '');
        });

        // Booking form submission
        document.getElementById('bookingForm').addEventListener('submit', (e) => {
            e.preventDefault();
            
            // In a real application, this would process the payment and send booking details
            alert(`✨ Booking Confirmed! ✨\n\nService: ${currentService}\nPrice: ${currentPrice}\n\nThank you for booking with Astro Barbie Tarot! You will receive your reading within 24-48 hours via your preferred contact method. Check your email for confirmation details.`);
            
            closeModal();
        });
    </script>


                <div id="cepMain" class="cepHidden">
                    <div class="cepOpenBtn" style="display: none;">
                        <span>
                            <img alt="Show coupons" class="cepBtnLogo" src="chrome-extension://cakcmeinnmdkbpbjbfhfahocdcpgcghi/img/logo/logo256.png">
                        </span>
                    </div>
                    <div id="cepCont" style="display: none;">

                    <div class="noContent"><h1>Coupons not found</h1><p>Right now there are no coupons for this site, please check later</p></div></div>
                </div>
            </body>
