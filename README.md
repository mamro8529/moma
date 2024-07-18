<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login and Video Page</title>
    <style>
        /* Your existing styles */
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
            margin: 0;
            transition: background-color 0.5s, color 0.5s;
        }
        .container {
            background-color: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 0 15px rgba(0,0,0,0.2);
            text-align: center;
            width: 100%;
            max-width: 1000px; /* Increase the max-width to make the container wider */
            transition: background-color 0.5s, color 0.5s;
            overflow-y: auto;
            height: 100vh;
        }
        .container img {
            width: 180px;
            height: auto;
            margin-bottom: 20px;
        }
        .container h2, .container h1 {
            margin-bottom: 20px;
        }
        .container input {
            width: 100%;
            padding: 12px;
            margin: 12px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        .container button {
            width: 100%;
            padding: 12px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        .container button:hover {
            background-color: #45a049;
        }
        .hidden {
            display: none;
        }
        .icon {
            width: 50px;
            height: 50px;
            cursor: pointer;
            margin-top: 20px;
        }
        .footer-text {
            margin-top: 20px;
            font-size: 16px;
            color: #888;
        }
        .contact-icons {
            margin-top: 10px;
        }
        .contact-icons a {
            display: inline-block;
            margin: 0 10px;
        }
        .contact-icons img {
            width: 30px;
            height: 30px;
        }
        .contact-message {
            font-size: 18px;
            color: black; /* Default color for light mode */
            margin-top: 10px; /* Adjusted margin-top to remove extra space */
            margin-bottom: 10px; /* Keep the bottom margin */
        }
        body.dark-mode .contact-message {
            color: #f0f0f0; /* Color for dark mode */
        }
        body.dark-mode {
            background-color: #2c2c2c;
            color: #f0f0f0;
        }
        body.dark-mode .container {
            background-color: #3c3c3c;
            color: #f0f0f0;
        }
        body.dark-mode input {
            background-color: #5c5c5c;
            color: #f0f0f0;
            border: 1px solid #7c7c7c;
        }
        body.dark-mode button {
            background-color: #45a049;
        }
        body.dark-mode button:hover {
            background-color: #3a8b3e;
        }

        #welcome-container {
            position: absolute;
            top: 10px;
            left: 10px;
            font-size: 20px;
            color: #888;
            background-color: rgba(0, 0, 0, 0.6);
            padding: 12px 18px;
            border-radius: 4px;
        }
        body.dark-mode #welcome-container {
            color: #f0f0f0;
            background-color: rgba(255, 255, 255, 0.3);
        }
        .medallion {
            width: 180px;
            height: auto;
            margin: 0 auto 20px;
            display: block;
        }
        .video-container {
            padding: 10px 0; /* Adjust padding to add space around the title and video */
            position: relative;
            margin-bottom: 0; /* Remove space between video containers */
            text-align: center; /* Center align the text */
        }
        .video-title {
            font-size: 17px; /* Adjust the font size for the video title */
            margin-bottom: 10px; /* Add space between the title and the video */
        }
        .video-container iframe {
            width: 90%; /* Make the iframe take the full width of the container */
            height: 600px; /* Set a fixed height for the iframe */
            border-radius: 8px; /* Add border-radius to match the design */
        }
        .video-footer-text {
            margin-top: 20px;
            font-size: 16px;
            color: #888;
        }
        body.dark-mode .video-footer-text {
            color: #f0f0f0;
        }

        .theme-switch-wrapper {
            position: absolute;
            top: 20px;
            right: 20px;
            display: flex;
            align-items: center;
        }

        .theme-switch {
            display: none;
        }

        .theme-switch-label {
            display: flex;
            align-items: center;
            cursor: pointer;
        }

        .theme-switch-label .sun-icon,
        .theme-switch-label .moon-icon {
            font-size: 24px;
            transition: opacity 0.5s;
        }

        .theme-switch:checked + .theme-switch-label .sun-icon {
            opacity: 0;
        }

        .theme-switch:not(:checked) + .theme-switch-label .moon-icon {
            opacity: 0;
        }

        .menu-content {
            background-color: #2c2c2c;
            color: white;
            padding: 10px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        .menu-button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px 20px;
            cursor: pointer;
            border-radius: 4px;
            margin-bottom: 20px;
        }
        .menu-button:hover {
            background-color: #45a049;
        }

        .logout-button {
            background-color: #e74c3c;
            color: white;
            border: none;
            padding: 2px 5px;
            font-size: 15px;
            cursor: pointer;
            border-radius: 4px;
            margin: 20px 0 0 0;
        }
        .logout-button:hover {
            background-color: #c0392b;
        }
        .menu-content ul {
            list-style-type: none;
            padding: 0;
            margin: 0;
        }

        .menu-content ul li {
            padding: 10px 15px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .menu-content ul li:hover {
            background-color: #444;
            border-radius: 4px;
        }
    </style>
</head>
<body>
    <div class="container" id="login-container">
        <img src="https://i.ibb.co/t4dBqr9/26015241-c430-4b73-926a-4c46642063f0-removebg.png" alt="Medal Image">
        <h2>The Process platform</h2>
        <input type="text" id="username" placeholder="Enter Username" onkeydown="handleEnterKey(event)">
        <button onclick="login()">Login</button>
        <p class="contact-message">لو واجهتك مشكلة ابعتلي</p>
        <div class="contact-icons">
            <a href="https://www.facebook.com/mamro8529?mibextid=ZbWKwL" title="Facebook">
                <img src="https://upload.wikimedia.org/wikipedia/commons/5/51/Facebook_f_logo_%282019%29.svg" alt="Facebook Icon">
            </a>
            <a href="https://wa.me/message/5LRM2DVHPZQFM1" target="_blank" title="WhatsApp">
                <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp Icon">
            </a>
        </div>
        <p class="footer-text">Developed by Eng: Mora</p>
    </div>

    <div class="container hidden" id="video-container">
        <img src="https://i.ibb.co/t4dBqr9/26015241-c430-4b73-926a-4c46642063f0-removebg.png" alt="Medal Image" class="medallion">
        <div id="welcome-container" class="hidden"></div>
        
        <!-- Menu Button -->
        <button class="menu-button" onclick="document.getElementById('video-menu').classList.toggle('hidden')">Select Video</button>
        <div id="video-menu" class="menu-content hidden">
            <ul>
                <li onclick="showVideo('video1')">Amr Diab - El Ta'ama</li>
                <li onclick="showVideo('video2')">Amr Diab - Tetehabi</li>
                <li onclick="showVideo('video3')">Magd El Qasem - Qasswet Albak</li>
                <li onclick="showVideo('video4')">Amr Diab - El Ta'ama (Maqsoum Remix)</li>
                <li onclick="showVideo('video5')">اه يا زمن</li>
            </ul>
        </div>

        <!-- Video Section -->
        <div id="video1" class="video-container hidden">
            <h1 class="video-title">Amr Diab - El Ta'ama عمرو دياب - الطعامه</h1>
            <iframe src="https://www.youtube.com/embed/zrTT4CJAvZs?si=2OVur3UJKSbsJvpM" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - El Ta'ama"></iframe>
        </div>
        
        <div id="video2" class="video-container hidden">
            <h1 class="video-title">Amr Diab - Tetehabi عمرو دياب - تتحبي</h1>
            <iframe src="https://www.youtube.com/embed/fDaHi6t9y9k?si=iYTIaiR3khSskU46" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - Tetehabi"></iframe>
        </div>
        
        <div id="video3" class="video-container hidden">
            <h1 class="video-title">Magd El Qasem - Qasswet Albak| مجد القاسم - قسوة قلبك</h1>
            <iframe src="https://www.youtube.com/embed/Spo8ijT3WKI?si=_j0KJVMSUUKYq6ft" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Magd El Qasem - Qasswet Albak"></iframe>
        </div>
        
        <div id="video4" class="video-container hidden">
            <h1 class="video-title">Amr Diab - El Ta'ama (Maqsoum Remix عمرو دياب - الطعامه (ريميكس مقسوم</h1>
            <iframe src="https://www.youtube.com/embed/9KRVRzErIOg?si=j76ruz-bxIPa5ehu" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="Amr Diab - El Ta'ama (Maqsoum Remix"></iframe>
        </div>
        
        
        <div id="video5" class="video-container hidden">
            <h1 class="video-title">اه يا زمن</h1>
            <iframe src="https://fast.wistia.net/embed/iframe/iu5pz1rqv3?videoFoam=true" frameborder="0" allow="autoplay; fullscreen; picture-in-picture; clipboard-write" title="اه يا زمن"></iframe>
        </div>

        <!-- Contact Icons -->
        <p class="contact-message">لو واجهتك مشكلة ابعتلي</p>
        <div class="contact-icons">
            <a href="https://www.facebook.com/mamro8529?mibextid=ZbWKwL" title="Facebook">
                <img src="https://upload.wikimedia.org/wikipedia/commons/5/51/Facebook_f_logo_%282019%29.svg" alt="Facebook Icon">
            </a>
            <a href="https://wa.me/message/5LRM2DVHPZQFM1" target="_blank" title="WhatsApp">
                <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp Icon">
            </a>
        </div>
        <p class="video-footer-text">Developed by Eng: Mora</p>
        <button class="logout-button" onclick="logout()">Logout</button>
    </div>

    <div class="theme-switch-wrapper">
        <input type="checkbox" id="theme-switch" class="theme-switch" onclick="toggleDarkMode()">
        <label for="theme-switch" class="theme-switch-label">
            <span class="sun-icon">🌞</span>
            <span class="moon-icon">🌚</span>
        </label>
    </div>
    <script>
        let activeUsers = {};

        function login() {
            const username = document.getElementById('username').value.trim();
            const welcomeContainer = document.getElementById('welcome-container');
            if (username === '') {
                alert('Please enter a username.');
                return;
            }

            if (username === '45455' || username === '45454') {
                if (Object.keys(activeUsers).length > 0) {
                    alert('Another user is already logged in. Please log out first.');
                    return;
                }

                activeUsers[username] = true;
                document.getElementById('login-container').classList.add('hidden');
                document.getElementById('video-container').classList.remove('hidden');

                if (username === '45455') {
                    welcomeContainer.textContent = 'Welcome, Teto 🤩!';
                } else if (username === '45454') {
                    welcomeContainer.textContent = 'Welcome, Eng: Mora 🤩!';
                }

                welcomeContainer.classList.remove('hidden');
                setTimeout(() => {
                    welcomeContainer.classList.add('hidden');
                }, 7000);  

                // Save the logged-in state to localStorage
                localStorage.setItem('loggedInUser', username);
            } else {
                alert('Invalid username');
            }
        }

        function handleEnterKey(event) {
            if (event.key === 'Enter') {
                login();
            }
        }

        function showVideo(videoId) {
            document.querySelectorAll('.video-container').forEach(video => {
                video.classList.add('hidden');
            });
            document.getElementById(videoId).classList.remove('hidden');
        }

        function logout() {
            document.getElementById('video-container').classList.add('hidden');
            document.getElementById('login-container').classList.remove('hidden');
            document.getElementById('username').value = '';
            // Clear the active users object
            activeUsers = {};
            localStorage.removeItem('loggedInUser'); // Clear the logged-in user from localStorage
        }

        function toggleDarkMode() {
            document.body.classList.toggle('dark-mode');
        }

        // Check the localStorage for a logged-in user when the page loads
        window.addEventListener('load', () => {
            const username = localStorage.getItem('loggedInUser');
            if (username === '45455' || username === '45454') {
                activeUsers[username] = true;
                document.getElementById('login-container').classList.add('hidden');
                document.getElementById('video-container').classList.remove('hidden');
                const welcomeContainer = document.getElementById('welcome-container');
                if (username === '45455') {
                    welcomeContainer.textContent = 'Welcome, Teto 🤩!';
                } else if (username === '45454') {
                    welcomeContainer.textContent = 'Welcome, Eng: Mora 🤩!';
                }
                welcomeContainer.classList.remove('hidden');
                setTimeout(() => {
                    welcomeContainer.classList.add('hidden');
                }, 7000);  
            }
        });

        // Remove the logged-in user from localStorage on beforeunload
        window.addEventListener('beforeunload', () => {
            const username = localStorage.getItem('loggedInUser');
            if (username === '45455' || username === '45454') {
                delete activeUsers[username];
            }
        });
    </script>
