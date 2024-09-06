<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Career Development & Skill Matching</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            color: #333;
            background-color: #f4f4f4;
        }

        header {
            background: linear-gradient(to right, #007BFF, #00C6FF);
            color: #fff;
            padding: 50px 0;
            text-align: center;
            position: relative;
        }

        header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.5);
            z-index: 1;
        }

        header h1 {
            margin: 0;
            font-size: 3em;
            z-index: 2;
            position: relative;
        }

        section {
            padding: 40px;
            background-color: #fff;
            margin: 20px 0;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease-in-out;
        }

        section:hover {
            transform: translateY(-10px);
        }

        section h2 {
            border-bottom: 3px solid #007BFF;
            padding-bottom: 10px;
            margin-bottom: 20px;
        }

        .container {
            width: 85%;
            margin: 0 auto;
            max-width: 1200px;
        }

        .step {
            display: none;
            animation: fadeIn 0.5s ease;
        }

        .step.active {
            display: block;
        }

        .form-step {
            margin-bottom: 20px;
        }

        .form-step label {
            display: block;
            margin-bottom: 10px;
        }

        .checkbox-group label {
            display: block;
            margin-bottom: 10px;
        }

        form input[type="button"] {
            background-color: #FF6F61;
            color: #fff;
            border: none;
            padding: 40px 100px; /* Doubled size */
            font-size: 2.5em; /* Increased font size */
            cursor: pointer;
            border-radius: 10px;
            transition: background-color 0.3s ease, transform 0.3s ease;
            margin-top: 40px;
            display: inline-block;
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.2);
            text-transform: uppercase;
            letter-spacing: 1.5px;
        }

        form input[type="button"]:hover {
            background-color: #E75A4D;
            transform: translateY(-10px);
        }

        .job-recommendations, .study-recommendations {
            margin-top: 30px;
            padding: 20px;
            background-color: #e9ecef;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        .job-recommendations ul,
        .study-recommendations ul {
            list-style: none;
            padding: 0;
        }

        .job-recommendations li,
        .study-recommendations li {
            background-color: #fff;
            border-radius: 5px;
            padding: 10px;
            margin: 8px 0;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.05);
            transition: transform 0.2s;
        }

        .job-recommendations li:hover,
        .study-recommendations li:hover {
            transform: translateY(-5px);
        }

        .job-recommendations h3,
        .study-recommendations h3 {
            margin-top: 0;
            font-size: 1.5em;
            color: #007BFF;
        }

        .step-navigation {
            text-align: center;
            margin-top: 20px;
        }

        .step-navigation button {
            background-color: #007BFF;
            color: #fff;
            border: none;
            padding: 10px 20px;
            font-size: 1.2em;
            cursor: pointer;
            border-radius: 5px;
            margin: 0 10px;
        }

        .step-navigation button:hover {
            background-color: #0056b3;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }

            to {
                opacity: 1;
            }
        }
    </style>
</head>

<body>
    <header>
        <div class="container">
            <h1>Career Development & Skill Matching</h1>
        </div>
    </header>

    <section id="main-content">
        <div class="container">
            <div id="start-step" class="step active">
                <h2>Welcome to Career Development & Skill Matching</h2>
                <p>Ready to find your perfect career match? Click "Get Started" to begin.</p>
                <input type="button" value="Get Started" onclick="showStep('basic-info-step')">
            </div>

            <div id="basic-info-step" class="step">
                <h2>Step 1: Basic Information</h2>
                <form id="basic-info-form">
                    <div class="form-step">
                        <label for="name">Full Name:</label>
                        <input type="text" id="name" name="name" required>
                    </div>
                    <div class="form-step">
                        <label for="education">Highest Level of Education:</label>
                        <input type="text" id="education" name="education" required>
                    </div>
                    <div class="form-step">
                        <label for="year-gap">Do you have any year gaps in your education?</label>
                        <select id="year-gap" name="year-gap" onchange="handleYearGapChange()" required>
                            <option value="">Select</option>
                            <option value="none">None</option>
                            <option value="1-year">1 Year</option>
                            <option value="2-years">2 Years</option>
                            <option value="3-years">3 Years or More</option>
                        </select>
                    </div>
                    <div class="step-navigation">
                        <button type="button" onclick="showStep('skills-step')">Next</button>
                    </div>
                </form>
            </div>

            <div id="skills-step" class="step">
                <h2>Step 2: Select Your Skills</h2>
                <p>Select the skills that you possess:</p>
                <form id="skills-form">
                    <div class="form-step checkbox-group">
                        <div>
                            <label><input type="checkbox" name="skills" value="Programming"> Programming</label>
                            <label><input type="checkbox" name="skills" value="Web Development"> Web Development</label>
                            <label><input type="checkbox" name="skills" value="AI and Machine Learning"> AI and Machine Learning</label>
                            <label><input type="checkbox" name="skills" value="Cloud Computing"> Cloud Computing</label>
                            <label><input type="checkbox" name="skills" value="Cybersecurity"> Cybersecurity</label>
                        </div>
                        <div>
                            <label><input type="checkbox" name="skills" value="Design"> Design</label>
                            <label><input type="checkbox" name="skills" value="Graphic Design"> Graphic Design</label>
                            <label><input type="checkbox" name="skills" value="Data Science"> Data Science</label>
                            <label><input type="checkbox" name="skills" value="Database Management"> Database Management</label>
                            <label><input type="checkbox" name="skills" value="Networking"> Networking</label>
                        </div>
                        <div>
                            <label><input type="checkbox" name="skills" value="Project Management"> Project Management</label>
                            <label><input type="checkbox" name="skills" value="Marketing"> Marketing</label>
                            <label><input type="checkbox" name="skills" value="Sales"> Sales</label>
                            <label><input type="checkbox" name="skills" value="Leadership"> Leadership</label>
                            <label><input type="checkbox" name="skills" value="Communication"> Communication</label>
                        </div>
                    </div>
                    <div class="step-navigation">
                        <button type="button" onclick="showStep('recommendations-step')">Get Recommendations</button>
                    </div>
                </form>
            </div>

            <div id="recommendations-step" class="step">
                <h2>Step 3: Job and Study Recommendations</h2>
                <div id="job-recommendations" class="job-recommendations"></div>
                <div id="study-recommendations" class="study-recommendations"></div>
                <div class="step-navigation">
                    <button type="button" onclick="showStep('start-step')">Start Over</button>
                </div>
            </div>
        </div>
    </section>

    <script>
        function showStep(stepId) {
            document.querySelectorAll('.step').forEach(step => step.classList.remove('active'));
            document.getElementById(stepId).classList.add('active');
        }

        function handleYearGapChange() {
            const yearGap = document.getElementById('year-gap').value;
            const jobRecommendations = document.getElementById('job-recommendations');
            const studyRecommendations = document.getElementById('study-recommendations');

            if (yearGap !== "none") {
                jobRecommendations.innerHTML = "<h3>Job Recommendations</h3><ul><li>Freelance Web Developer</li><li>Remote Content Creator</li><li>Part-Time Customer Support</li></ul>";
                studyRecommendations.innerHTML = "<h3>Study Recommendations</h3><ul><li>Online Certification in Digital Marketing</li><li>Part-Time Data Science Course</li></ul>";
            } else {
                jobRecommendations.innerHTML = "<h3>Job Recommendations</h3><ul><li>Software Engineer</li><li>Full-Stack Developer</li><li>Data Analyst</li></ul>";
                studyRecommendations.innerHTML = "<h3>Study Recommendations</h3><ul><li>Master's in AI and Machine Learning</li><li>Certification in Cybersecurity</li></ul>";
            }
        }
    </script>
</body>

</html>
