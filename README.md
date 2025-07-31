<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mishab KP - Portfolio</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts - Poppins for a modern look -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        /* Custom styles for Poppins font */
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            color: #e0e0e0; /* Light text for dark background */
            overflow: hidden; /* Prevent scrollbar from background animation */
            position: relative;
        }

        /* Animated Background - Subtle gradient shift */
        body::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #1a202c 0%, #2d3748 50%, #1a202c 100%); /* Darker, subtle gradient */
            background-size: 200% 200%; /* Make gradient larger than viewport */
            animation: gradientShift 15s ease infinite alternate; /* Smooth, looping animation */
            z-index: -1; /* Send to background */
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Main content container styling */
        .main-content {
            background-color: rgba(30, 41, 59, 0.9); /* Slightly transparent dark background */
            padding: 2.5rem; /* Equivalent to p-10 */
            border-radius: 1rem; /* Equivalent to rounded-xl */
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.3), 0 10px 10px -5px rgba(0, 0, 0, 0.1); /* Stronger shadow */
            max-width: 900px; /* Wider max-width */
            width: 95%; /* Responsive width */
            text-align: center;
            backdrop-filter: blur(8px); /* Frosted glass effect */
            -webkit-backdrop-filter: blur(8px); /* For Safari */
            border: 1px solid rgba(255, 255, 255, 0.1); /* Subtle border */
            transform: translateY(0); /* Initial position */
            animation: fadeInScale 1s ease-out forwards; /* Fade in and slightly scale up on load */
        }

        @keyframes fadeInScale {
            from {
                opacity: 0;
                transform: translateY(20px) scale(0.98);
            }
            to {
                opacity: 1;
                transform: translateY(0) scale(1);
            }
        }

        /* Heading styles */
        h1 {
            font-size: 3.5rem; /* Larger font size */
            font-weight: 700; /* Extra bold */
            color: #66b3ff; /* Lighter blue for emphasis */
            margin-bottom: 1.5rem;
            line-height: 1.2;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3); /* Text shadow for depth */
        }

        h1 span {
            color: #a0c4ff; /* Even lighter blue for name */
        }

        /* Paragraph styles */
        p {
            font-size: 1.25rem; /* Larger paragraph font */
            line-height: 1.8;
            margin-bottom: 2rem;
            color: #c0c0c0; /* Slightly lighter gray */
        }

        /* Skills section heading */
        h2 {
            font-size: 2.5rem; /* Larger skills heading */
            font-weight: 600;
            color: #66b3ff;
            margin-bottom: 1.5rem;
        }

        /* Skill list container */
        .skill-container {
            min-height: 50px; /* Ensure space for skills to appear */
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* Individual skill item animation */
        .skill-item {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.8s ease-out, transform 0.8s ease-out;
            display: inline-block; /* Keep them in a line */
            background-color: #3f51b5; /* Darker blue skill tag */
            color: #ffffff;
            padding: 0.75rem 1.5rem;
            border-radius: 9999px; /* Fully rounded */
            font-weight: 600;
            margin: 0.5rem; /* Space between tags */
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
            white-space: nowrap; /* Prevent wrapping */
        }

        .skill-item.show {
            opacity: 1;
            transform: translateY(0);
        }

        /* Contact text styling */
        .contact-text {
            font-size: 1.1rem;
            color: #b0b0b0;
            margin-top: 2.5rem;
        }

        .contact-text span {
            color: #a0c4ff;
            font-weight: 700;
        }

        /* Media queries for responsiveness */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            p {
                font-size: 1rem;
            }
            h2 {
                font-size: 2rem;
            }
            .main-content {
                padding: 1.5rem;
            }
            .skill-item {
                padding: 0.5rem 1rem;
                font-size: 0.9rem;
            }
        }
    </style>
</head>
<body>
    <div class="main-content">
        <h1>Hey Everyone, I'm <span class="text-blue-300">Mishab K.P.</span></h1>
        <p>I am studying Computer Science Engineering at MGM College of Engineering.</p>
        
        <h2>My Skills</h2>
        <div class="skill-container">
            <ul class="skill-list flex justify-center flex-wrap">
                <li class="skill-item">Programming: C</li>
                <li class="skill-item">Programming: C++</li>
                <li class="skill-item">Programming: Python</li>
            </ul>
        </div>

        <p class="contact-text">
            Please <span class="font-bold">contact me</span> for more inquiries.
        </p>
    </div>

    <script>
        const skills = document.querySelectorAll('.skill-item');

        function showSkills() {
            skills.forEach((skill, index) => {
                setTimeout(() => {
                    
                    skill.classList.add('show');
                }, 400 * index); // Slightly faster delay for appearance
            });
        }

        // Ensure skills animate when the page loads
        document.addEventListener('DOMContentLoaded', showSkills);
    </script>
</body>
</html>
