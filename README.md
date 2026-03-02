8px 24px rgba(0, 0, 0, 0.15);
            padding: 20px;
        }
    </style>
</head>
<body class="min-h-screen flex items-center justify-center p-4 relative">

    <!-- Floating Hearts Container -->
    <div id="hearts-container"></div>

    <!-- Password Screen -->
    <div id="password-screen" class="fixed inset-0 z-50 flex items-center justify-center bg-pink-200">
        <div class="bg-white p-8 rounded-[20px] shadow-[0_10px_30px_rgba(0,0,0,0.1)] text-center max-w-[400px] w-[90%] animate-bounce-in">
            <h2 class="font-handwriting text-3xl text-pink-600 mb-6">Enter the secret code</h2>
            <input type="password" id="secret-input" placeholder="Our special word..." 
                   class="w-full px-4 py-2 border-2 border-pink-200 rounded-lg mb-4 focus:outline-none focus:border-pink-500 text-center">
            <button onclick="checkPassword()" 
                    class="bg-pink-600 text-white px-6 py-2 rounded-full hover:bg-pink-700 transition transform hover:scale-105 shadow-lg">
                Enter
            </button>
            <p id="error-msg" class="text-red-500 text-sm mt-2 hidden">Try again, my love...</p>
        </div>
    </div>

    <!-- Main Content (Hidden initially) -->
    <div id="main-content" class="hidden w-full max-w-3xl relative z-10">
        
        <!-- Welcome Text - LIGHT BLUE COLOR -->
        <div class="text-center mb-8 animate-bounce-in">
            <h1 class="font-handwriting text-4xl md:text-5xl welcome-text">
                Welcome my love, enjoy your stay
            </h1>
        </div>

        <!-- Navigation - Removed Music, only 3 tabs -->
        <div class="flex justify-center gap-2 mb-6 flex-wrap">
            <button onclick="switchTab('letter')" id="btn-letter" class="nav-btn active px-4 py-2 rounded-full bg-white/50 text-pink-700 text-sm font-semibold flex items-center gap-2 hover:bg-white">
                <i class="fas fa-heart text-pink-500"></i> Love Letter
            </button>
            <button onclick="switchTab('notes')" id="btn-notes" class="nav-btn px-4 py-2 rounded-full bg-white/50 text-pink-700 text-sm font-semibold flex items-center gap-2 hover:bg-white">
                <i class="fas fa-sticky-note text-pink-500"></i> Notes
            </button>
            <button onclick="switchTab('gallery')" id="btn-gallery" class="nav-btn px-4 py-2 rounded-full bg-white/50 text-pink-700 text-sm font-semibold flex items-center gap-2 hover:bg-white">
                <i class="fas fa-images text-pink-500"></i> Gallery
            </button>
        </div>

        <!-- Content Container -->
        <div class="bg-white rounded-[20px] shadow-[0_10px_30px_rgba(0,0,0,0.1)] p-6 md:p-8 min-h-[400px]">
            
            <!-- Love Letter Tab -->
            <div id="tab-letter" class="tab-content active">
                <h3 class="text-gray-800 font-semibold mb-4">My Dearest</h3>
                <div class="bg-pink-50 rounded-xl p-4 border border-pink-100">
                    <div class="flex justify-between items-center mb-2 cursor-pointer" onclick="toggleLetter()">
                        <span class="font-handwriting text-2xl text-pink-600">A Letter For You</span>
                        <span class="text-xs text-gray-500 flex items-center gap-1">
                            <i class="fas fa-hand-pointer"></i> Click to open
                        </span>
                    </div>
                    <div id="letter-content" class="hidden mt-4 text-gray-700 text-sm leading-relaxed border-t border-pink-200 pt-4">
                        <p class="mb-2">My love,</p>
                        <p class="mb-2">Every day with you feels like a beautiful dream that I never want to wake up from. Your smile brightens my darkest days, and your laughter is my favorite melody.</p>
                        <p class="mb-2">I cherish every moment we spend together, from our silly inside jokes to our deep conversations under the stars. You've shown me what true happiness feels like, and I'm forever grateful to have you in my life.</p>
                        <p class="mb-2">No matter where life takes us, always remember that my heart belongs to you.</p>
                        <p>Forever yours,<br>Me</p>
                    </div>
                </div>
            </div>

            <!-- Notes Tab -->
            <div id="tab-notes" class="tab-content">
                <h3 class="text-gray-800 font-semibold mb-4">Some reminders</h3>
                <div class="space-y-3">
                    <div class="bg-pink-50 rounded-lg p-4 border-l-4 border-pink-400">
                        <p class="text-gray-700 text-sm">Take care always</p>
                    </div>
                    <div class="bg-pink-50 rounded-lg p-4 border-l-4 border-pink-400">
                        <p class="text-gray-700 text-sm">Eat on time</p>
                    </div>
                    <div class="bg-pink-50 rounded-lg p-4 border-l-4 border-pink-400">
                        <p class="text-gray-700 text-sm">You're mine, always</p>
                    </div>
                    <div class="bg-pink-50 rounded-lg p-4 border-l-4 border-pink-400">
                        <p class="text-gray-700 text-sm">I love you more than yesterday</p>
                    </div>
                </div>
            </div>

            <!-- Gallery Tab with New Images -->
            <div id="tab-gallery" class="tab-content">
                <h3 class="text-gray-800 font-semibold mb-4">Our Memories</h3>
                
                <!-- Image 1: Close Moment Scene -->
                <div class="mb-6 love-image overflow-hidden rounded-lg">
                    <div class="anime-scene">
                        <svg viewBox="0 0 800 600" xmlns="http://www.w3.org/2000/svg" style="width: 100%; height: 100%;">
                            <!-- Background -->
                            <defs>
                                <linearGradient id="skyGrad" x1="0%" y1="0%" x2="0%" y2="100%">
                                    <stop offset="0%" style="stop-color:#e0f2ff;stop-opacity:1" />
                                    <stop offset="30%" style="stop-color:#87ceeb;stop-opacity:1" />
                                    <stop offset="100%" style="stop-color:#4a90e2;stop-opacity:1" />
                                </linearGradient>
                            </defs>
                            <rect width="800" height="600" fill="url(#skyGrad)"/>
                            
                            <!-- Green background -->
                            <rect y="350" width="800" height="250" fill="#2d5016" opacity="0.3"/>
                            
                            <!-- Male Character (Red Hair) - Right side -->
                            <g transform="translate(450, 150)">
                                <!-- Body -->
                                <rect x="-40" y="80" width="80" height="120" fill="#2c3e50" rx="10"/>
                                <!-- Neck -->
                                <rect x="-25" y="60" width="50" height="25" fill="#d4a574"/>
                                <!-- Head -->
                                <circle cx="0" cy="40" r="45" fill="#d4a574"/>
                                <!-- Red spiky hair -->
                                <g fill="#c41e3a">
                                    <path d="M -30 0 Q -35 -35 -15 -45 L -10 -10 Z"/>
                                    <path d="M -10 -8 Q -8 -40 5 -48 L 8 -8 Z"/>
                                    <path d="M 10 -5 Q 15 -38 30 -45 L 28 -5 Z"/>
                                    <path d="M 28 0 Q 38 -30 40 -48 L 35 -5 Z"/>
                                </g>
                                <!-- Eyes -->
                                <ellipse cx="-15" cy="35" rx="8" ry="12" fill="#4a8fd9"/>
                                <circle cx="-15" cy="35" r="5" fill="#2563a3"/>
                                <circle cx="-13" cy="33" r="2.5" fill="white"/>
                                <ellipse cx="15" cy="35" rx="8" ry="12" fill="#4a8fd9"/>
                                <circle cx="15" cy="35" r="5" fill="#2563a3"/>
                                <circle cx="17" cy="33" r="2.5" fill="white"/>
                                <!-- Nose -->
                                <polygon points="0,40 -3,50 3,50" fill="#c89968"/>
                                <!-- Mouth -->
                                <path d="M -8 55 Q 0 60 8 55" stroke="#8b6f47" stroke-width="2" fill="none"/>
                            </g>

                            <!-- Female Character (Purple Hair) - Left side -->
                            <g transform="translate(250, 130)">
                                <!-- Body -->
                                <rect x="-35" y="85" width="70" height="125" fill="#3d2645" rx="10"/>
                                <!-- Neck -->
                                <rect x="-22" y="60" width="44" height="28" fill="#d4a574"/>
                                <!-- Head -->
                                <circle cx="0" cy="40" r="42" fill="#d4a574"/>
                                <!-- Purple hair -->
                                <g fill="#6b4c8a">
                                    <path d="M -35 -5 Q -40 -35 -30 -48 L -25 -8 Z"/>
                                    <path d="M -25 -8 Q -22 -40 -8 -50 L -5 -10 Z"/>
                                    <path d="M -5 -10 Q 0 -42 12 -50 L 15 -10 Z"/>
                                    <path d="M 15 -8 Q 25 -38 35 -48 L 30 -5 Z"/>
                                    <!-- Long hair down -->
                                    <path d="M -30 35 Q -32 80 -28 140"/>
                                    <path d="M -15 38 Q -16 85 -12 145"/>
                                    <path d="M 5 38 Q 5 85 8 145"/>
                                    <path d="M 22 35 Q 24 80 28 140"/>
                                </g>
                                <!-- Eyes - purple -->
                                <ellipse cx="-12" cy="32" rx="9" ry="13" fill="#9370db"/>
                                <circle cx="-12" cy="32" r="6" fill="#6b4c8a"/>
                                <circle cx="-10" cy="30" r="3" fill="white"/>
                                <ellipse cx="12" cy="32" rx="9" ry="13" fill="#9370db"/>
                                <circle cx="12" cy="32" r="6" fill="#6b4c8a"/>
                                <circle cx="14" cy="30" r="3" fill="white"/>
                                <!-- Nose -->
                                <polygon points="0,40 -2.5,50 2.5,50" fill="#c89968"/>
                                <!-- Smile -->
                                <path d="M -6 55 Q 0 58 6 55" stroke="#8b6f47" stroke-width="2" fill="none"/>
                                <!-- Blush -->
                                <circle cx="-25" cy="48" r="6" fill="#ffb3d9" opacity="0.6"/>
                                <circle cx="25" cy="48" r="6" fill="#ffb3d9" opacity="0.6"/>
                            </g>

                            <!-- Heart between them -->
                            <g transform="translate(350, 80)">
                                <path d="M 0,-10 C -8,-18 -20,-18 -20,-8 C -20,0 0,20 0,20 C 0,20 20,0 20,-8 C 20,-18 8,-18 0,-10" fill="#ff69b4" opacity="0.8"/>
                            </g>
                        </svg>
                    </div>
                    <p class="text-center text-pink-600 font-handwriting text-lg mt-2">Our Precious Moment</p>
                </div>

                <!-- Image 2: Hand in Hand Scene -->
                <div class="mb-6 sketch-bg love-image">
                    <h4 class="text-center text-gray-700 font-light text-lg mb-4 tracking-widest">Hand in Hand</h4>
                    <svg viewBox="0 0 600 400" xmlns="http://www.w3.org/2000/svg" class="w-full h-auto">
                        <!-- Background - Warm sunset -->
                        <defs>
                            <linearGradient id="sunsetGrad" x1="0%" y1="0%" x2="0%" y2="100%">
                                <stop offset="0%" style="stop-color:#fff5e1;stop-opacity:1" />
                                <stop offset="40%" style="stop-color:#ffda87;stop-opacity:1" />
                                <stop offset="100%" style="stop-color:#c9956f;stop-opacity:1" />
                            </linearGradient>
                        </defs>
                        <rect width="600" height="400" fill="url(#sunsetGrad)"/>
                        
                        <!-- Male character (Red hair) -->
                        <g transform="translate(200, 120)">
                            <!-- Body -->
                            <rect x="-30" y="60" width="60" height="100" fill="#e86c4a" rx="8"/>
                            <!-- Neck -->
                            <rect x="-20" y="45" width="40" height="20" fill="#d4a574"/>
                            <!-- Head -->
                            <circle cx="0" cy="30" r="35" fill="#d4a574"/>
                            <!-- Red spiky hair -->
                            <g fill="#c41e3a">
                                <path d="M -20 -5 Q -25 -25 -8 -32 L -5 -5 Z"/>
                                <path d="M -5 -8 Q -3 -28 8 -35 L 10 -8 Z"/>
                                <path d="M 10 -5 Q 18 -25 28 -32 L 25 -5 Z"/>
                            </g>
                            <!-- Face -->
                            <ellipse cx="-12" cy="28" rx="7" ry="10" fill="#4a8fd9"/>
                            <circle cx="-12" cy="28" r="4" fill="#2563a3"/>
                            <ellipse cx="12" cy="28" rx="7" ry="10" fill="#4a8fd9"/>
                            <circle cx="12" cy="28" r="4" fill="#2563a3"/>
                            <!-- Left arm extended -->
                            <path d="M -30 80 Q -50 95 -70 110" stroke="#d4a574" stroke-width="10" fill="none" stroke-linecap="round"/>
                            <!-- Hand -->
                            <circle cx="-70" cy="110" r="12" fill="#d4a574"/>
                        </g>

                        <!-- Female character (Purple hair) -->
                        <g transform="translate(400, 100)">
                            <!-- Body -->
                            <rect x="-28" y="65" width="56" height="105" fill="#e0b0ff" rx="8"/>
                            <!-- Neck -->
                            <rect x="-18" y="48" width="36" height="22" fill="#d4a574"/>
                            <!-- Head -->
                            <circle cx="0" cy="32" r="36" fill="#d4a574"/>
                            <!-- Purple hair -->
                            <g fill="#6b4c8a">
                                <path d="M -30 -8 Q -36 -28 -18 -35 L -12 -10 Z"/>
                                <path d="M -12 -10 Q -8 -32 5 -38 L 12 -10 Z"/>
                                <path d="M 12 -8 Q 22 -28 35 -35 L 28 -5 Z"/>
                                <!-- Long flowing hair -->
                                <path d="M -28 25 Q -32 70 -30 160"/>
                                <path d="M -12 32 Q -14 80 -10 165"/>
                                <path d="M 12 32 Q 12 80 15 165"/>
                                <path d="M 28 28 Q 32 70 30 160"/>
                            </g>
                            <!-- Face -->
                            <ellipse cx="-11" cy="25" rx="8" ry="11" fill="#9370db"/>
                            <circle cx="-11" cy="25" r="5" fill="#6b4c8a"/>
                            <ellipse cx="11" cy="25" rx="8" ry="11" fill="#9370db"/>
                            <circle cx="11" cy="25" r="5" fill="#6b4c8a"/>
                            <!-- Right arm extended -->
                            <path d="M -28 85 Q -45 105 -68 125" stroke="#d4a574" stroke-width="10" fill="none" stroke-linecap="round"/>
                            <!-- Hand connecting -->
                            <circle cx="-68" cy="125" r="12" fill="#d4a574"/>
                            <!-- Connected hands -->
                            <g>
                                <path d="M -65 120 L -72 118" stroke="#d4a574" stroke-width="3" stroke-linecap="round"/>
                                <path d="M -65 128 L -72 132" stroke="#d4a574" stroke-width="3" stroke-linecap="round"/>
                            </g>
                        </g>

                        <!-- Decorative stars -->
                        <circle cx="100" cy="80" r="3" fill="#ffeb3b" opacity="0.6"/>
                        <circle cx="480" cy="120" r="3" fill="#ffeb3b" opacity="0.6"/>
                        <circle cx="300" cy="60" r="2" fill="#ffeb3b" opacity="0.4"/>
                    </svg>
                </div>

                <!-- Image 3: Together Under Sky -->
                <div class="mb-6 love-image overflow-hidden rounded-lg bg-gradient-to-b from-blue-300 to-blue-100 p-4">
                    <svg viewBox="0 0 600 500" xmlns="http://www.w3.org/2000/svg" class="w-full h-auto">
                        <!-- Sky background -->
                        <defs>
                            <linearGradient id="skyBlue" x1="0%" y1="0%" x2="0%" y2="100%">
                                <stop offset="0%" style="stop-color:#87ceeb;stop-opacity:1" />
                                <stop offset="100%" style="stop-color:#e0f2ff;stop-opacity:1" />
                            </linearGradient>
                        </defs>
                        <rect width="600" height="500" fill="url(#skyBlue)"/>
                        
                        <!-- Male character -->
                        <g transform="translate(200, 150)">
                            <!-- Body -->
                            <rect x="-35" y="70" width="70" height="120" fill="#3a4a5c" rx="10"/>
                            <!-- Neck -->
                            <rect x="-22" y="50" width="44" height="25" fill="#d4a574"/>
                            <!-- Head -->
                            <circle cx="0" cy="35" r="40" fill="#d4a574"/>
                            <!-- Black hair -->
                            <g fill="#1a1a2e">
                                <path d="M -35 -5 Q -40 -30 -20 -40 L -15 -8 Z"/>
                                <path d="M -15 -10 Q -12 -35 5 -42 L 10 -10 Z"/>
                                <path d="M 10 -8 Q 20 -32 35 -40 L 30 -5 Z"/>
                            </g>
                            <!-- Eyes -->
                            <ellipse cx="-13" cy="30" rx="8" ry="11" fill="#4a8fd9"/>
                            <circle cx="-13" cy="30" r="5" fill="#2563a3"/>
                            <circle cx="-11" cy="28" r="2" fill="white"/>
                            <ellipse cx="13" cy="30" rx="8" ry="11" fill="#4a8fd9"/>
                            <circle cx="13" cy="30" r="5" fill="#2563a3"/>
                            <circle cx="15" cy="28" r="2" fill="white"/>
                        </g>

                        <!-- Female character -->
                        <g transform="translate(400, 130)">
                            <!-- Body -->
                            <rect x="-32" y="75" width="64" height="125" fill="#2d2d4a" rx="10"/>
                            <!-- Neck -->
                            <rect x="-20" y="52" width="40" height="28" fill="#d4a574"/>
                            <!-- Head -->
                            <circle cx="0" cy="38" r="38" fill="#d4a574"/>
                            <!-- Black hair -->
                            <g fill="#1a1a2e">
                                <path d="M -32 0 Q -38 -32 -15 -42 L -10 -5 Z"/>
                                <path d="M -10 -8 Q -6 -36 8 -44 L 14 -8 Z"/>
                                <path d="M 14 -5 Q 26 -32 38 -42 L 32 0 Z"/>
                                <!-- Long hair -->
                                <path d="M -32 32 Q -36 80 -32 160"/>
                                <path d="M -12 38 Q -14 90 -10 170"/>
                                <path d="M 12 38 Q 14 90 18 170"/>
                                <path d="M 32 35 Q 36 80 32 160"/>
                            </g>
                            <!-- Eyes -->
                            <ellipse cx="-11" cy="35" rx="8" ry="11" fill="#4a8fd9"/>
                            <circle cx="-11" cy="35" r="5" fill="#2563a3"/>
                            <circle cx="-9" cy="33" r="2" fill="white"/>
                            <ellipse cx="11" cy="35" rx="8" ry="11" fill="#4a8fd9"/>
                            <circle cx="11" cy="35" r="5" fill="#2563a3"/>
                            <circle cx="13" cy="33" r="2" fill="white"/>
                        </g>

                        <!-- Heart floating above -->
                        <g transform="translate(300, 100)">
                            <path d="M 0,-15 C -12,-25 -28,-25 -28,-12 C -28,5 0,35 0,35 C 0,35 28,5 28,-12 C 28,-25 12,-25 0,-15" fill="#ff69b4" opacity="0.7"/>
                        </g>

                        <!-- Clouds -->
                        <ellipse cx="80" cy="80" rx="60" ry="35" fill="white" opacity="0.4"/>
                        <ellipse cx="500" cy="100" rx="70" ry="40" fill="white" opacity="0.35"/>
                    </svg>
                    <p class="text-center text-pink-600 font-handwriting text-lg mt-2">Together Forever</p>
                </div>

                <!-- Image 4: Romantic Embrace -->
                <div class="mb-6 love-image overflow-hidden rounded-lg bg-gradient-to-b from-purple-200 to-blue-100 p-4">
                    <svg viewBox="0 0 600 500" xmlns="http://www.w3.org/2000/svg" class="w-full h-auto">
                        <!-- Background -->
                        <defs>
                            <linearGradient id="purpleBlue" x1="0%" y1="0%" x2="0%" y2="100%">
                                <stop offset="0%" style="stop-color:#c8b6ff;stop-opacity:1" />
                                <stop offset="100%" style="stop-color:#87ceeb;stop-opacity:1" />
                            </linearGradient>
                        </defs>
                        <rect width="600" height="500" fill="url(#purpleBlue)"/>
                        
                        <!-- Male character (front) -->
                        <g transform="translate(280, 140)">
                            <!-- Body -->
                            <rect x="-40" y="80" width="80" height="130" fill="#f5e6d3" stroke="#8b6f47" stroke-width="2" rx="10"/>
                            <!-- Neck -->
                            <rect x="-25" y="60" width="50" height="25" fill="#d4a574"/>
                            <!-- Head -->
                            <circle cx="0" cy="38" r="42" fill="#d4a574"/>
                            <!-- Dark blue hair -->
                            <g fill="#1a3a52">
                                <path d="M -38 -8 Q -45 -35 -20 -45 L -12 -8 Z"/>
                                <path d="M -12 -12 Q -8 -38 8 -48 L 14 -12 Z"/>
                                <path d="M 14 -10 Q 28 -35 42 -45 L 35 -5 Z"/>
                            </g>
                            <!-- Eyes -->
                            <ellipse cx="-15" cy="32" rx="9" ry="12" fill="#4a8fd9"/>
                            <circle cx="-15" cy="32" r="5" fill="#2563a3"/>
                            <circle cx="-13" cy="30" r="2" fill="white"/>
                            <ellipse cx="15" cy="32" rx="9" ry="12" fill="#4a8fd9"/>
                            <circle cx="15" cy="32" r="5" fill="#2563a3"/>
                            <circle cx="17" cy="30" r="2" fill="white"/>
                            <!-- Smile -->
                            <path d="M -10 50 Q 0 55 10 50" stroke="#8b6f47" stroke-width="2" fill="none"/>
                        </g>

                        <!-- Female character (back, embracing) -->
                        <g transform="translate(320, 120)">
                            <!-- Hair (visible from back) -->
                            <g fill="#4a1a4a">
                                <path d="M -45 -5 Q -52 -35 -25 -48 L -18 -8 Z"/>
                                <path d="M -18 -12 Q -14 -40 5 -50 L 14 -12 Z"/>
                                <path d="M 14 -10 Q 30 -36 48 -48 L 40 -3 Z"/>
                                <!-- Long hair down back -->
                                <path d="M -40 32 Q -42 90 -38 180"/>
                                <path d="M -15 38 Q -16 95 -12 185"/>
                                <path d="M 15 38 Q 16 95 18 185"/>
                                <path d="M 40 32 Q 42 90 40 180"/>
                            </g>
                            <!-- Body (wrapped around) -->
                            <ellipse cx="0" cy="100" rx="48" ry="85" fill="#f0d8e8" opacity="0.9"/>
                            <!-- Arms wrapped -->
                            <path d="M -45 90 Q -65 95 -68 120" stroke="#d4a574" stroke-width="12" fill="none" stroke-linecap="round"/>
                            <path d="M 45 90 Q 65 95 68 120" stroke="#d4a574" stroke-width="12" fill="none" stroke-linecap="round"/>
                        </g>

                        <!-- Hearts around them -->
                        <g transform="translate(150, 100)">
                            <path d="M 0,-8 C -8,-15 -18,-15 -18,-8 C -18,2 0,20 0,20 C 0,20 18,2 18,-8 C 18,-15 8,-15 0,-8" fill="#ff69b4" opacity="0.6"/>
                        </g>
                        <g transform="translate(450, 150)">
                            <path d="M 0,-8 C -8,-15 -18,-15 -18,-8 C -18,2 0,20 0,20 C 0,20 18,2 18,-8 C 18,-15 8,-15 0,-8" fill="#ff69b4" opacity="0.6"/>
                        </g>
                    </svg>
                    <p class="text-center text-pink-600 font-handwriting text-lg mt-2">In Your Arms</p>
                </div>

            </div>

        </div>
    </div>

    <script>
        // Password Check
        function checkPassword() {
            const input = document.getElementById('secret-input').value.toLowerCase();
            if (input === 'love') {
                document.getElementById('password-screen').style.display = 'none';
                document.getElementById('main-content').classList.remove('hidden');
                startHearts();
            } else {
                const errorMsg = document.getElementById('error-msg');
                errorMsg.classList.remove('hidden');
                document.getElementById('secret-input').classList.add('border-red-500');
                setTimeout(() => {
                    errorMsg.classList.add('hidden');
                    document.getElementById('secret-input').classList.remove('border-red-500');
                }, 2000);
            }
        }

        // Allow Enter key to submit
        document.getElementById('secret-input').addEventListener('keypress', function (e) {
            if (e.key === 'Enter') {
                checkPassword();
            }
        });

        // Tab Switching
        function switchTab(tabName) {
            // Hide all tabs
            document.querySelectorAll('.tab-content').forEach(tab => {
                tab.classList.remove('active');
            });
            
            // Remove active class from all buttons
            document.querySelectorAll('.nav-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            
            // Show selected tab
            document.getElementById('tab-' + tabName).classList.add('active');
            document.getElementById('btn-' + tabName).classList.add('active');
        }

        // Toggle Letter
        function toggleLetter() {
            const content = document.getElementById('letter-content');
            content.classList.toggle('hidden');
        }

        // Floating Hearts Animation
        function startHearts() {
            const container = document.getElementById('hearts-container');
            
            setInterval(() => {
                const heart = document.createElement('div');
                heart.className = 'heart fas fa-heart';
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.fontSize = (Math.random() * 20 + 10) + 'px';
                heart.style.animationDuration = (Math.random() * 3 + 3) + 's';
                container.appendChild(heart);
                
                setTimeout(() => {
                    heart.remove();
                }, 6000);
            }, 300);
        }
    </script>
</body>
</html>
