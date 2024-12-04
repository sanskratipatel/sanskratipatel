<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sanskrati Patel | Portfolio</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/aos/2.3.4/aos.css">
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background: linear-gradient(to right, #e3f2fd, #bbdefb);
        }
        header {
            text-align: center;
            padding: 2rem;
            background: #2196f3;
            color: white;
        }
        header h1 {
            font-size: 2.5rem;
            margin: 0;
        }
        .section-title {
            text-align: center;
            margin: 2rem 0;
            font-size: 1.8rem;
            color: #1565c0;
            text-transform: uppercase;
        }
        .icon-grid {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 1.5rem;
        }
        .icon-grid div {
            text-align: center;
            font-size: 1.2rem;
            background: #f1f8e9;
            border: 2px solid #c8e6c9;
            border-radius: 8px;
            padding: 1rem;
            width: 120px;
            transition: transform 0.3s ease;
        }
        .icon-grid div:hover {
            transform: scale(1.1);
        }
        .icon-grid div i {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            color: #388e3c;
        }
        footer {
            text-align: center;
            padding: 1rem;
            background: #1e88e5;
            color: white;
        }
    </style>
</head>
<body>

<header>
    <h1 class="animate__animated animate__fadeInDown">👨‍💻 Hello, I'm Sanskrati Patel 👋✨</h1>
    <p class="animate__animated animate__fadeInUp">A passionate Software Developer from Indore, Madhya Pradesh</p>
</header>

<section>
    <h2 class="section-title" data-aos="fade-up">Skills & Expertise</h2>
    <div class="icon-grid" data-aos="zoom-in">
        <div>
            <i class="fab fa-java"></i>
            <p>Java</p>
        </div>
        <div>
            <i class="fab fa-python"></i>
            <p>Python</p>
        </div>
        <div>
            <i class="fab fa-react"></i>
            <p>ReactJS</p>
        </div>
        <div>
            <i class="fas fa-database"></i>
            <p>MySQL</p>
        </div>
        <div>
            <i class="fab fa-html5"></i>
            <p>HTML5</p>
        </div>
        <div>
            <i class="fab fa-css3-alt"></i>
            <p>CSS3</p>
        </div>
    </div>
</section>

<section>
    <h2 class="section-title" data-aos="fade-up">Contact Me</h2>
    <p class="animate__animated animate__fadeInUp" style="text-align: center;">
        📧 <a href="mailto:patelsanskrati05@gmail.com">patelsanskrati05@gmail.com</a><br>
        🔗 <a href="https://linkedin.com/in/sanskrati-patel">LinkedIn</a> | 💻 <a href="https://github.com/SanskratiPatel">GitHub</a>
    </p>
</section>

<footer>
    <p>🌟 Let's build something amazing together! 🚀✨</p>
</footer>

<script src="https://cdnjs.cloudflare.com/ajax/libs/aos/2.3.4/aos.js"></script>
<script>
    AOS.init();
</script>

</body>
</html>

