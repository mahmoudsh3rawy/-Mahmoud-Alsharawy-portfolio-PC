# -Mahmoud-Alsharawy-portfolio-PC
Professional portfolio website
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mahmoud Alsharawy | Senior IT Project Manager</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <style>
        :root {
            --primary: #0f172a;
            --accent: #3b82f6;
            --accent-light: #60a5fa;
            --gold: #f59e0b;
            --surface: #f8fafc;
        }
        
        body {
            font-family: 'Inter', sans-serif;
            background: var(--primary);
            color: white;
            overflow-x: hidden;
        }
        
        .serif {
            font-family: 'Playfair Display', serif;
        }
        
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #0f172a;
        }
        ::-webkit-scrollbar-thumb {
            background: #334155;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #475569;
        }

        .glass {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
        
        .glass-card {
            background: rgba(255, 255, 255, 0.02);
            backdrop-filter: blur(16px);
            border: 1px solid rgba(255, 255, 255, 0.08);
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        }
        
        .glass-card:hover {
            background: rgba(255, 255, 255, 0.05);
            border-color: rgba(59, 130, 246, 0.3);
            transform: translateY(-4px);
            box-shadow: 0 20px 40px -15px rgba(59, 130, 246, 0.2);
        }

        .bg-grid {
            background-size: 50px 50px;
            background-image: linear-gradient(to right, rgba(255,255,255,0.02) 1px, transparent 1px),
                              linear-gradient(to bottom, rgba(255,255,255,0.02) 1px, transparent 1px);
            mask-image: radial-gradient(circle at center, black 40%, transparent 100%);
        }

        .reveal-text {
            clip-path: polygon(0 0, 100% 0, 100% 100%, 0% 100%);
        }
        
        .char {
            display: inline-block;
            opacity: 0;
            transform: translateY(100%);
        }

        .skill-track {
            background: rgba(255,255,255,0.05);
            border-radius: 999px;
            overflow: hidden;
        }
        
        .skill-fill {
            height: 100%;
            background: linear-gradient(90deg, #3b82f6, #60a5fa);
            border-radius: 999px;
            width: 0;
            transition: width 1.5s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }
        
        .skill-fill::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            animation: shimmer 2s infinite;
        }
        
        @keyframes shimmer {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        .float {
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .timeline-line {
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(to bottom, #3b82f6, transparent);
            transform: translateX(-50%);
        }
        
        .timeline-dot {
            width: 16px;
            height: 16px;
            background: #3b82f6;
            border: 3px solid #0f172a;
            border-radius: 50%;
            position: absolute;
            left: 50%;
            transform: translateX(-50%);
            box-shadow: 0 0 20px rgba(59, 130, 246, 0.5);
        }

        .strength-card {
            position: relative;
            overflow: hidden;
        }
        
        .strength-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.05), transparent);
            transition: left 0.7s;
        }
        
        .strength-card:hover::before {
            left: 100%;
        }

        .counter {
            font-variant-numeric: tabular-nums;
        }

        .nav-blur {
            background: rgba(15, 23, 42, 0.8);
            backdrop-filter: blur(12px);
        }

        .cursor-glow {
            width: 20px;
            height: 20px;
            background: rgba(59, 130, 246, 0.5);
            border-radius: 50%;
            position: fixed;
            pointer-events: none;
            z-index: 9999;
            transition: transform 0.1s;
            mix-blend-mode: screen;
        }

        .section-fade {
            opacity: 0;
            transform: translateY(30px);
        }

        .badge {
            display: inline-flex;
            align-items: center;
            padding: 0.25rem 0.75rem;
            border-radius: 9999px;
            font-size: 0.75rem;
            font-weight: 600;
            letter-spacing: 0.05em;
            text-transform: uppercase;
        }
        
        .badge-blue {
            background: rgba(59, 130, 246, 0.1);
            color: #60a5fa;
            border: 1px solid rgba(59, 130, 246, 0.2);
        }

        .testimonial-card {
            background: linear-gradient(135deg, rgba(255,255,255,0.05) 0%, rgba(255,255,255,0.01) 100%);
            border: 1px solid rgba(255,255,255,0.08);
        }

        .progress-ring-circle {
            transition: stroke-dashoffset 1.5s ease-in-out;
            transform: rotate(-90deg);
            transform-origin: 50% 50%;
        }

        .mobile-menu {
            transform: translateX(100%);
            transition: transform 0.3s ease-in-out;
        }
        
        .mobile-menu.active {
            transform: translateX(0);
        }

        html {
            scroll-behavior: smooth;
        }

        ::selection {
            background: rgba(59, 130, 246, 0.3);
            color: white;
        }

        .cert-badge {
            background: rgba(255,255,255,0.03);
            border: 1px solid rgba(255,255,255,0.08);
            transition: all 0.3s ease;
        }
        
        .cert-badge:hover {
            background: rgba(59, 130, 246, 0.1);
            border-color: rgba(59, 130, 246, 0.3);
            transform: translateY(-2px);
        }

        .project-card {
            position: relative;
            overflow: hidden;
        }
        
        .project-card::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            height: 2px;
            background: linear-gradient(90deg, transparent, #3b82f6, transparent);
            transform: scaleX(0);
            transition: transform 0.4s ease;
        }
        
        .project-card:hover::after {
            transform: scaleX(1);
        }

        .experience-card {
            border-left: 2px solid rgba(59, 130, 246, 0.2);
            transition: all 0.3s ease;
        }
        
        .experience-card:hover {
            border-left-color: #3b82f6;
            background: rgba(255,255,255,0.02);
        }

        .value-highlight {
            background: linear-gradient(135deg, rgba(59,130,246,0.1), rgba(139,92,246,0.1));
            border: 1px solid rgba(59,130,246,0.2);
        }
    </style>
</head>
<body class="antialiased">

    <!-- Custom Cursor -->
    <div class="cursor-glow hidden md:block" id="cursor"></div>

    <!-- Navigation -->
    <nav class="fixed top-0 w-full z-50 nav-blur border-b border-white/5">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-16">
                <div class="flex items-center space-x-2">
                    <div class="w-8 h-8 bg-blue-500 rounded-lg flex items-center justify-center">
                        <i data-lucide="hexagon" class="w-5 h-5 text-white"></i>
                    </div>
                    <span class="font-bold text-lg tracking-tight">MA<span class="text-blue-400">Portfolio</span></span>
                </div>
                
                <div class="hidden md:flex items-center space-x-8">
                    <a href="#overview" class="text-sm text-gray-400 hover:text-white transition-colors">Overview</a>
                    <a href="#strengths" class="text-sm text-gray-400 hover:text-white transition-colors">Strengths</a>
                    <a href="#experience" class="text-sm text-gray-400 hover:text-white transition-colors">Experience</a>
                    <a href="#metrics" class="text-sm text-gray-400 hover:text-white transition-colors">Impact</a>
                    <a href="#contact" class="px-4 py-2 bg-blue-500 hover:bg-blue-600 text-white text-sm font-medium rounded-lg transition-all">Get in Touch</a>
                </div>

                <button class="md:hidden text-white" onclick="toggleMobileMenu()">
                    <i data-lucide="menu" class="w-6 h-6"></i>
                </button>
            </div>
        </div>
        
        <!-- Mobile Menu -->
        <div class="mobile-menu fixed top-0 right-0 w-64 h-full bg-slate-900 z-50 p-6 md:hidden" id="mobileMenu">
            <button class="absolute top-4 right-4 text-white" onclick="toggleMobileMenu()">
                <i data-lucide="x" class="w-6 h-6"></i>
            </button>
            <div class="mt-12 space-y-6">
                <a href="#overview" class="block text-lg text-gray-300 hover:text-white" onclick="toggleMobileMenu()">Overview</a>
                <a href="#strengths" class="block text-lg text-gray-300 hover:text-white" onclick="toggleMobileMenu()">Strengths</a>
                <a href="#experience" class="block text-lg text-gray-300 hover:text-white" onclick="toggleMobileMenu()">Experience</a>
                <a href="#metrics" class="block text-lg text-gray-300 hover:text-white" onclick="toggleMobileMenu()">Impact</a>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="relative min-h-screen flex items-center justify-center overflow-hidden pt-16">
        <div class="absolute inset-0 bg-grid"></div>
        <div class="absolute top-20 left-10 w-72 h-72 bg-blue-500/10 rounded-full blur-3xl float"></div>
        <div class="absolute bottom-20 right-10 w-96 h-96 bg-purple-500/10 rounded-full blur-3xl float" style="animation-delay: 2s;"></div>
        
        <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
            <div class="inline-flex items-center space-x-2 px-4 py-2 rounded-full glass mb-8 opacity-0" id="heroBadge">
                <span class="w-2 h-2 bg-green-400 rounded-full animate-pulse"></span>
                <span class="text-sm text-gray-300">PMP Certified • Cairo, Egypt</span>
            </div>
            
            <h1 class="serif text-5xl md:text-7xl lg:text-8xl font-bold mb-6 leading-tight" id="heroTitle">
                <span class="block text-transparent bg-clip-text bg-gradient-to-r from-white via-blue-100 to-gray-400">Mahmoud</span>
                <span class="block text-transparent bg-clip-text bg-gradient-to-r from-blue-400 to-purple-400">Alsharawy</span>
            </h1>
            
            <p class="text-xl md:text-2xl text-gray-400 max-w-3xl mx-auto mb-12 leading-relaxed opacity-0" id="heroSub">
                Senior IT Project Manager with 10+ years delivering complex infrastructure, 
                data center, and government mega-projects across Egypt and Saudi Arabia. 
                PMP | MBA | CCNP | Six Sigma Green Belt
            </p>
            
            <div class="flex flex-col sm:flex-row items-center justify-center gap-4 opacity-0" id="heroCta">
                <a href="#experience" class="px-8 py-4 bg-blue-500 hover:bg-blue-600 text-white font-semibold rounded-xl transition-all transform hover:scale-105 shadow-lg shadow-blue-500/25 flex items-center space-x-2">
                    <span>View My Track Record</span>
                    <i data-lucide="arrow-down" class="w-5 h-5"></i>
                </a>
                <a href="#contact" class="px-8 py-4 glass hover:bg-white/5 text-white font-semibold rounded-xl transition-all flex items-center space-x-2">
                    <span>Contact Me</span>
                    <i data-lucide="mail" class="w-5 h-5"></i>
                </a>
            </div>

            <!-- Stats Row -->
            <div class="mt-20 grid grid-cols-2 md:grid-cols-4 gap-8 max-w-4xl mx-auto opacity-0" id="heroStats">
                <div class="text-center">
                    <div class="text-3xl md:text-4xl font-bold text-white counter" data-target="10">0</div>
                    <div class="text-sm text-gray-500 mt-1">Years Experience</div>
                </div>
                <div class="text-center">
                    <div class="text-3xl md:text-4xl font-bold text-white counter" data-target="130">0</div>
                    <div class="text-sm text-gray-500 mt-1">$M+ Portfolio Value</div>
                </div>
                <div class="text-center">
                    <div class="text-3xl md:text-4xl font-bold text-white counter" data-target="6">0</div>
                    <div class="text-sm text-gray-500 mt-1">Certifications</div>
                </div>
                <div class="text-center">
                    <div class="text-3xl md:text-4xl font-bold text-white counter" data-target="2">0</div>
                    <div class="text-sm text-gray-500 mt-1">Countries Delivered</div>
                </div>
            </div>
        </div>

        <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
            <i data-lucide="chevron-down" class="w-6 h-6 text-gray-500"></i>
        </div>
    </section>

    <!-- Overview Section -->
    <section id="overview" class="py-24 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid lg:grid-cols-2 gap-16 items-center">
                <div class="section-fade">
                    <span class="badge badge-blue mb-4">Professional Profile</span>
                    <h2 class="serif text-4xl md:text-5xl font-bold mb-6">Engineering Foundation<br><span class="text-blue-400">Business Leadership</span></h2>
                    <p class="text-gray-400 text-lg leading-relaxed mb-6">
                        Electrical and Communication Engineering graduate (2014) who started as a Network Engineer in Saudi Arabia, mastering low-current systems, CCTV, switching, and network infrastructure before transitioning into project management.
                    </p>
                    <p class="text-gray-400 text-lg leading-relaxed mb-8">
                        My MBA (GPA 3.8/4.0, Excellent) from the Arab Academy for Science, Technology, and Maritime Transport strengthened my strategic thinking and leadership capabilities. Today, I manage government mega-projects at Honeywell, including correctional facilities and high-speed rail initiatives.
                    </p>
                    
                    <div class="flex flex-wrap gap-3">
                        <span class="px-4 py-2 rounded-lg bg-white/5 border border-white/10 text-sm text-gray-300">PMP Methodologies</span>
                        <span class="px-4 py-2 rounded-lg bg-white/5 border border-white/10 text-sm text-gray-300">Data Center Infrastructure</span>
                        <span class="px-4 py-2 rounded-lg bg-white/5 border border-white/10 text-sm text-gray-300">Government Projects</span>
                        <span class="px-4 py-2 rounded-lg bg-white/5 border border-white/10 text-sm text-gray-300">Cost Control & Forecasting</span>
                        <span class="px-4 py-2 rounded-lg bg-white/5 border border-white/10 text-sm text-gray-300">Cross-functional Teams</span>
                        <span class="px-4 py-2 rounded-lg bg-white/5 border border-white/10 text-sm text-gray-300">Vendor Management</span>
                    </div>
                </div>
                
                <div class="relative section-fade">
                    <div class="glass-card rounded-2xl p-8 relative z-10">
                        <h3 class="text-xl font-bold mb-6">Certifications & Credentials</h3>
                        <div class="space-y-4">
                            <div class="cert-badge rounded-xl p-4 flex items-start space-x-4">
                                <div class="w-12 h-12 rounded-xl bg-blue-500/10 flex items-center justify-center flex-shrink-0">
                                    <i data-lucide="award" class="w-6 h-6 text-blue-400"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold text-sm mb-1">Project Management Professional (PMP)</h4>
                                    <p class="text-gray-500 text-xs">Credential #2768092</p>
                                </div>
                            </div>
                            
                            <div class="cert-badge rounded-xl p-4 flex items-start space-x-4">
                                <div class="w-12 h-12 rounded-xl bg-purple-500/10 flex items-center justify-center flex-shrink-0">
                                    <i data-lucide="graduation-cap" class="w-6 h-6 text-purple-400"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold text-sm mb-1">MBA - Excellent (3.8/4.0)</h4>
                                    <p class="text-gray-500 text-xs">Arab Academy for Science, Technology & Maritime Transport</p>
                                </div>
                            </div>
                            
                            <div class="cert-badge rounded-xl p-4 flex items-start space-x-4">
                                <div class="w-12 h-12 rounded-xl bg-amber-500/10 flex items-center justify-center flex-shrink-0">
                                    <i data-lucide="network" class="w-6 h-6 text-amber-400"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold text-sm mb-1">CCNP Enterprise (ENCOR)</h4>
                                    <p class="text-gray-500 text-xs">CSCO12942389 | CCNA Routing & Switching</p>
                                </div>
                            </div>
                            
                            <div class="cert-badge rounded-xl p-4 flex items-start space-x-4">
                                <div class="w-12 h-12 rounded-xl bg-emerald-500/10 flex items-center justify-center flex-shrink-0">
                                    <i data-lucide="sigma" class="w-6 h-6 text-emerald-400"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold text-sm mb-1">Six Sigma Green Belt</h4>
                                    <p class="text-gray-500 text-xs">Process Optimization & Quality Management</p>
                                </div>
                            </div>

                            <div class="cert-badge rounded-xl p-4 flex items-start space-x-4">
                                <div class="w-12 h-12 rounded-xl bg-rose-500/10 flex items-center justify-center flex-shrink-0">
                                    <i data-lucide="sparkles" class="w-6 h-6 text-rose-400"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold text-sm mb-1">Generative AI for PMs</h4>
                                    <p class="text-gray-500 text-xs">AI-Enhanced Project Management</p>
                                </div>
                            </div>

                            <div class="cert-badge rounded-xl p-4 flex items-start space-x-4">
                                <div class="w-12 h-12 rounded-xl bg-cyan-500/10 flex items-center justify-center flex-shrink-0">
                                    <i data-lucide="scroll-text" class="w-6 h-6 text-cyan-400"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold text-sm mb-1">Scrum Fundamental Certified</h4>
                                    <p class="text-gray-500 text-xs">Agile Framework Mastery</p>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <div class="absolute -top-4 -right-4 w-24 h-24 bg-blue-500/20 rounded-full blur-2xl"></div>
                    <div class="absolute -bottom-4 -left-4 w-32 h-32 bg-purple-500/20 rounded-full blur-2xl"></div>
                </div>
            </div>
        </div>
    </section>

    <!-- Key Strengths -->
    <section id="strengths" class="py-24 relative bg-slate-900/50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16 section-fade">
                <span class="badge badge-blue mb-4">Core Competencies</span>
                <h2 class="serif text-4xl md:text-5xl font-bold mb-4">Project Management Strengths</h2>
                <p class="text-gray-400 max-w-2xl mx-auto">The capabilities that drive consistent delivery across $130M+ in infrastructure and government projects.</p>
            </div>

            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
                <!-- Strength 1 -->
                <div class="glass-card rounded-2xl p-8 strength-card section-fade group cursor-pointer" onclick="toggleCard(this)">
                    <div class="w-14 h-14 rounded-2xl bg-blue-500/10 flex items-center justify-center mb-6 group-hover:bg-blue-500/20 transition-colors">
                        <i data-lucide="landmark" class="w-7 h-7 text-blue-400"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Government Mega-Project Delivery</h3>
                    <p class="text-gray-400 text-sm leading-relaxed mb-4">Proven expertise managing Egypt's National Mega Projects including the $80M Government District in the New Administrative Capital and $50M MOI correctional facilities.</p>
                    <div class="flex items-center text-blue-400 text-sm font-medium opacity-0 group-hover:opacity-100 transition-opacity">
                        <span>View details</span>
                        <i data-lucide="arrow-right" class="w-4 h-4 ml-2"></i>
                    </div>
                    <div class="hidden mt-4 pt-4 border-t border-white/5 text-sm text-gray-500">
                        Led ICT integration across 9 data centers via Honeywell EBI. Managed security directorate networks with $850K budget. Coordinated with ministries and central authorities.
                    </div>
                </div>

                <!-- Strength 2 -->
                <div class="glass-card rounded-2xl p-8 strength-card section-fade group cursor-pointer" onclick="toggleCard(this)">
                    <div class="w-14 h-14 rounded-2xl bg-purple-500/10 flex items-center justify-center mb-6 group-hover:bg-purple-500/20 transition-colors">
                        <i data-lucide="server" class="w-7 h-7 text-purple-400"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Data Center Infrastructure</h3>
                    <p class="text-gray-400 text-sm leading-relaxed mb-4">End-to-end delivery of data center projects for National Commercial Bank ($375K), Prince Sultan Military Medical City ($120K), and Al Yamama Royal Palace.</p>
                    <div class="flex items-center text-purple-400 text-sm font-medium opacity-0 group-hover:opacity-100 transition-opacity">
                        <span>View details</span>
                        <i data-lucide="arrow-right" class="w-4 h-4 ml-2"></i>
                    </div>
                    <div class="hidden mt-4 pt-4 border-t border-white/5 text-sm text-gray-500">
                        Designed and implemented scalable, high-availability systems. Enhanced operational reliability through structured cabling, switching, and core/access network deployment.
                    </div>
                </div>

                <!-- Strength 3 -->
                <div class="glass-card rounded-2xl p-8 strength-card section-fade group cursor-pointer" onclick="toggleCard(this)">
                    <div class="w-14 h-14 rounded-2xl bg-amber-500/10 flex items-center justify-center mb-6 group-hover:bg-amber-500/20 transition-colors">
                        <i data-lucide="dollar-sign" class="w-7 h-7 text-amber-400"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Financial Control & Forecasting</h3>
                    <p class="text-gray-400 text-sm leading-relaxed mb-4">Rigorous cost optimization, variation order management, and monthly forecasting that protects profitability and improves revenue visibility.</p>
                    <div class="flex items-center text-amber-400 text-sm font-medium opacity-0 group-hover:opacity-100 transition-opacity">
                        <span>View details</span>
                        <i data-lucide="arrow-right" class="w-4 h-4 ml-2"></i>
                    </div>
                    <div class="hidden mt-4 pt-4 border-t border-white/5 text-sm text-gray-500">
                        Managed cost variations and contractual claims. Enforced strict schedule control to ensure on-time, within-budget delivery across all portfolio projects.
                    </div>
                </div>

                <!-- Strength 4 -->
                <div class="glass-card rounded-2xl p-8 strength-card section-fade group cursor-pointer" onclick="toggleCard(this)">
                    <div class="w-14 h-14 rounded-2xl bg-emerald-500/10 flex items-center justify-center mb-6 group-hover:bg-emerald-500/20 transition-colors">
                        <i data-lucide="users" class="w-7 h-7 text-emerald-400"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Cross-Functional Leadership</h3>
                    <p class="text-gray-400 text-sm leading-relaxed mb-4">Leading global vendors (Cisco, Dell, F5, Prolink) and internal teams to resolve critical issues and ensure high-performance system operations.</p>
                    <div class="flex items-center text-emerald-400 text-sm font-medium opacity-0 group-hover:opacity-100 transition-opacity">
                        <span>View details</span>
                        <i data-lucide="arrow-right" class="w-4 h-4 ml-2"></i>
                    </div>
                    <div class="hidden mt-4 pt-4 border-t border-white/5 text-sm text-gray-500">
                        Coordinated with clients, contractors, and site teams across Saudi Arabia and Egypt. Supervised installation activities and reviewed technical drawings for successful delivery.
                    </div>
                </div>

                <!-- Strength 5 -->
                <div class="glass-card rounded-2xl p-8 strength-card section-fade group cursor-pointer" onclick="toggleCard(this)">
                    <div class="w-14 h-14 rounded-2xl bg-rose-500/10 flex items-center justify-center mb-6 group-hover:bg-rose-500/20 transition-colors">
                        <i data-lucide="shield" class="w-7 h-7 text-rose-400"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Risk & Quality Management</h3>
                    <p class="text-gray-400 text-sm leading-relaxed mb-4">Six Sigma Green Belt approach to identifying, assessing, and mitigating project risks before they impact timelines or quality standards.</p>
                    <div class="flex items-center text-rose-400 text-sm font-medium opacity-0 group-hover:opacity-100 transition-opacity">
                        <span>View details</span>
                        <i data-lucide="arrow-right" class="w-4 h-4 ml-2"></i>
                    </div>
                    <div class="hidden mt-4 pt-4 border-t border-white/5 text-sm text-gray-500">
                        Applied PMP methodologies and Six Sigma principles to maintain quality across low-current systems, CCTV, and network infrastructure projects.
                    </div>
                </div>

                <!-- Strength 6 -->
                <div class="glass-card rounded-2xl p-8 strength-card section-fade group cursor-pointer" onclick="toggleCard(this)">
                    <div class="w-14 h-14 rounded-2xl bg-cyan-500/10 flex items-center justify-center mb-6 group-hover:bg-cyan-500/20 transition-colors">
                        <i data-lucide="globe" class="w-7 h-7 text-cyan-400"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Multi-Market Expertise</h3>
                    <p class="text-gray-400 text-sm leading-relaxed mb-4">Deep experience across Saudi Arabia (Royal Palaces, Military Medical, Banking) and Egypt (Government District, Correctional Facilities, High-Speed Rail).</p>
                    <div class="flex items-center text-cyan-400 text-sm font-medium opacity-0 group-hover:opacity-100 transition-opacity">
                        <span>View details</span>
                        <i data-lucide="arrow-right" class="w-4 h-4 ml-2"></i>
                    </div>
                    <div class="hidden mt-4 pt-4 border-t border-white/5 text-sm text-gray-500">
                        Network Engineer at Alnmozajy Consulting (Saudi Arabia, 2015-2019) before transitioning to PM roles at Golden Technology, Click-ITS, and Honeywell.
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Experience Timeline -->
    <section id="experience" class="py-24 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16 section-fade">
                <span class="badge badge-blue mb-4">Career Progression</span>
                <h2 class="serif text-4xl md:text-5xl font-bold mb-4">Professional Experience</h2>
                <p class="text-gray-400 max-w-2xl mx-auto">From Network Engineer to Senior IT Project Manager — a decade of infrastructure and project delivery excellence.</p>
            </div>

            <div class="space-y-8">
                <!-- Honeywell -->
                <div class="glass-card rounded-2xl p-8 experience-card section-fade">
                    <div class="flex flex-col md:flex-row md:items-start justify-between mb-6">
                        <div>
                            <div class="flex items-center space-x-3 mb-2">
                                <h3 class="text-2xl font-bold">Program Specialist Manager</h3>
                                <span class="px-3 py-1 rounded-full bg-blue-500/10 text-blue-400 text-xs font-semibold">Current</span>
                            </div>
                            <div class="flex items-center space-x-4 text-gray-400 text-sm">
                                <span class="flex items-center space-x-1">
                                    <i data-lucide="building-2" class="w-4 h-4"></i>
                                    <span>Honeywell</span>
                                </span>
                                <span class="flex items-center space-x-1">
                                    <i data-lucide="map-pin" class="w-4 h-4"></i>
                                    <span>Egypt</span>
                                </span>
                                <span class="flex items-center space-x-1">
                                    <i data-lucide="calendar" class="w-4 h-4"></i>
                                    <span>Jan 2023 - Present</span>
                                </span>
                            </div>
                        </div>
                        <div class="mt-4 md:mt-0 text-right">
                            <div class="text-2xl font-bold text-blue-400">$50M</div>
                            <div class="text-xs text-gray-500">Project Value</div>
                        </div>
                    </div>
                    
                    <div class="grid md:grid-cols-2 gap-4">
                        <div class="value-highlight rounded-xl p-4">
                            <div class="flex items-start space-x-3">
                                <i data-lucide="check-circle-2" class="w-5 h-5 text-blue-400 mt-0.5 flex-shrink-0"></i>
                                <p class="text-sm text-gray-300">Led delivery of MOI mega project (Correction & Rehabilitation Facilities) with fully integrated ICT systems and centralized operations via Honeywell EBI controlling <strong>9 data centers</strong></p>
                            </div>
                        </div>
                        <div class="value-highlight rounded-xl p-4">
                            <div class="flex items-start space-x-3">
                                <i data-lucide="check-circle-2" class="w-5 h-5 text-blue-400 mt-0.5 flex-shrink-0"></i>
                                <p class="text-sm text-gray-300">Drove on-time, within-budget delivery through strict schedule control, cost optimization, and alignment with technical/client requirements</p>
                            </div>
                        </div>
                        <div class="value-highlight rounded-xl p-4">
                            <div class="flex items-start space-x-3">
                                <i data-lucide="check-circle-2" class="w-5 h-5 text-blue-400 mt-0.5 flex-shrink-0"></i>
                                <p class="text-sm text-gray-300">Protected profitability by managing cost variations, contractual claims, Variation Orders, and monthly forecasting</p>
                            </div>
                        </div>
                        <div class="value-highlight rounded-xl p-4">
                            <div class="flex items-start space-x-3">
                                <i data-lucide="check-circle-2" class="w-5 h-5 text-blue-400 mt-0.5 flex-shrink-0"></i>
                                <p class="text-sm text-gray-300">Led cross-functional teams and global vendors: <strong>Cisco, Dell, F5, Prolink</strong> — resolving critical issues across all sites</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Click-ITS -->
                <div class="glass-card rounded-2xl p-8 experience-card section-fade">
                    <div class="flex flex-col md:flex-row md:items-start justify-between mb-6">
                        <div>
                            <h3 class="text-2xl font-bold mb-2">IT Project Manager</h3>
                            <div class="flex items-center space-x-4 text-gray-400 text-sm">
                                <span class="flex items-center space-x-1">
                                    <i data-lucide="building-2" class="w-4 h-4"></i>
                                    <span>Click-ITS</span>
                                </span>
                                <span class="flex items-center space-x-1">
                                    <i data-lucide="map-pin" class="w-4 h-4"></i>
                                    <span>Egypt</span>
                                </span>
                                <span class="flex items-center space-x-1">
                                    <i data-lucide="calendar" class="w-4 h-4"></i>
                                    <span>Nov 2021 - Jan 2023</span>
                                </span>
                            </div>
                        </div>
                        <div class="mt-4 md:mt-0 text-right">
                            <div class="text-2xl font-bold text-purple-400">$80M</div>
                            <div class="text-xs text-gray-500">Portfolio Value</div>
                        </div>
                    </div>
                    
                    <div class="grid md:grid-cols-2 gap-4">
                        <div class="value-highlight rounded-xl p-4">
                            <div class="flex items-start space-x-3">
                                <i data-lucide="check-circle-2" class="w-5 h-5 text-purple-400 mt-0.5 flex-shrink-0"></i>
                                <p class="text-sm text-gray-300">Led <strong>$80M Government District network project</strong> (New Administrative Capital), connecting ministries and authorities to central data center</p>
                            </div>
                        </div>
                        <div class="value-highlight rounded-xl p-4">
                            <div class="flex items-start space-x-3">
                                <i data-lucide="check-circle-2" class="w-5 h-5 text-purple-400 mt-0.5 flex-shrink-0"></i>
                                <p class="text-sm text-gray-300">Delivered Egyptian Security Directorate project with <strong>$850K budget</strong> on time and within budget</p>
                            </div>
                        </div>
                        <div class="value-highlight rounded-xl p-4 md:col-span-2">
                            <div class="flex items-start space-x-3">
                                <i data-lucide="check-circle-2" class="w-5 h-5 text-purple-400 mt-0.5 flex-shrink-0"></i>
                                <p class="text-sm text-gray-300">Oversaw deployment of core/access networks and district-wide Wi-Fi, enabling secure, high-performance connectivity across government facilities</p>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Golden Technology -->
                <div class="glass-card rounded-2xl p-8 experience-card section-fade">
                    <div class="flex flex-col md:flex-row md:items-start justify-between mb-6">
                        <div>
                            <h3 class="text-2xl font-bold mb-2">Project Manager</h3>
                            <div class="flex items-center space-x-4 text-gray-400 text-sm">
                                <span class="flex items-center space-x-1">
                                    <i data-lucide="building-2" class="w-4 h-4"></i>
                                    <span>Golden Technology</span>
                                </span>
                                <span class="flex items-center space-x-1">
                                    <i data-lucide="map-pin" class="w-4 h-4"></i>
                                    <span>Saudi Arabia</span>
                                </span>
                                <span class="flex items-center space-x-1">
                                    <i data-lucide="calendar" class="w-4 h-4"></i>
                                    <span>Jan 2020 - Oct 2021</span>
                                </span>
                            </div>
                        </div>
                        <div class="mt-4 md:mt-0 text-right">
                            <div class="text-2xl font-bold text-amber-400">$495K</div>
                            <div class="text-xs text-gray-500">Total Portfolio</div>
                        </div>
                    </div>
                    
                    <div class="grid md:grid-cols-3 gap-4">
                        <div class="value-highlight rounded-xl p-4">
                            <div class="flex items-start space-x-3">
                                <i data-lucide="crown" class="w-5 h-5 text-amber-400 mt-0.5 flex-shrink-0"></i>
                                <div>
                                    <p class="text-sm font-semibold text-gray-200 mb-1">Al Yamama Royal Palace</p>
                                    <p class="text-xs text-gray-400">Cabling infrastructure and Wi-Fi deployment for secure, reliable connectivity across the palace</p>
                                </div>
                            </div>
                        </div>
                        <div class="value-highlight rounded-xl p-4">
                            <div class="flex items-start space-x-3">
                                <i data-lucide="landmark" class="w-5 h-5 text-amber-400 mt-0.5 flex-shrink-0"></i>
                                <div>
                                    <p class="text-sm font-semibold text-gray-200 mb-1">National Commercial Bank</p>
                                    <p class="text-xs text-gray-400"><strong>$375K</strong> data center project at KAEC — enhanced performance and operational reliability</p>
                                </div>
                            </div>
                        </div>
                        <div class="value-highlight rounded-xl p-4">
                            <div class="flex items-start space-x-3">
                                <i data-lucide="heart-pulse" class="w-5 h-5 text-amber-400 mt-0.5 flex-shrink-0"></i>
                                <div>
                                    <p class="text-sm font-semibold text-gray-200 mb-1">Prince Sultan Military Medical</p>
                                    <p class="text-xs text-gray-400"><strong>$120K</strong> data center infrastructure — scalable, high-availability systems</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Alnmozajy -->
                <div class="glass-card rounded-2xl p-8 experience-card section-fade">
                    <div class="flex flex-col md:flex-row md:items-start justify-between mb-6">
                        <div>
                            <h3 class="text-2xl font-bold mb-2">Network Engineer</h3>
                            <div class="flex items-center space-x-4 text-gray-400 text-sm">
                                <span class="flex items-center space-x-1">
                                    <i data-lucide="building-2" class="w-4 h-4"></i>
                                    <span>Alnmozajy for Consulting</span>
                                </span>
                                <span class="flex items-center space-x-1">
                                    <i data-lucide="map-pin" class="w-4 h-4"></i>
                                    <span>Saudi Arabia</span>
                                </span>
                                <span class="flex items-center space-x-1">
                                    <i data-lucide="calendar" class="w-4 h-4"></i>
                                    <span>Oct 2015 - Dec 2019</span>
                                </span>
                            </div>
                        </div>
                    </div>
                    
                    <div class="grid md:grid-cols-2 gap-4">
                        <div class="value-highlight rounded-xl p-4">
                            <div class="flex items-start space-x-3">
                                <i data-lucide="check-circle-2" class="w-5 h-5 text-emerald-400 mt-0.5 flex-shrink-0"></i>
                                <p class="text-sm text-gray-300">Designed low-current and network infrastructure systems including <strong>CCTV, switching, and structured cabling</strong> layouts based on client requirements</p>
                            </div>
                        </div>
                        <div class="value-highlight rounded-xl p-4">
                            <div class="flex items-start space-x-3">
                                <i data-lucide="check-circle-2" class="w-5 h-5 text-emerald-400 mt-0.5 flex-shrink-0"></i>
                                <p class="text-sm text-gray-300">Coordinated with clients, contractors, and site teams to supervise installation, review technical drawings, and ensure successful project delivery</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Metrics & Impact -->
    <section id="metrics" class="py-24 relative bg-slate-900/50">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16 section-fade">
                <span class="badge badge-blue mb-4">Quantified Impact</span>
                <h2 class="serif text-4xl md:text-5xl font-bold mb-4">Portfolio Metrics</h2>
                <p class="text-gray-400 max-w-2xl mx-auto">Measurable scale and consistency across government, banking, healthcare, and royal infrastructure projects.</p>
            </div>

            <div class="grid md:grid-cols-2 gap-8 mb-16">
                <!-- Technical Skills -->
                <div class="glass-card rounded-2xl p-8 section-fade">
                    <h3 class="text-xl font-bold mb-8">Technical Proficiency</h3>
                    
                    <div class="space-y-6">
                        <div>
                            <div class="flex justify-between mb-2">
                                <span class="text-sm font-medium text-gray-300">Network Infrastructure (CCNP/CCNA)</span>
                                <span class="text-sm text-gray-500">95%</span>
                            </div>
                            <div class="skill-track h-2">
                                <div class="skill-fill" data-width="95%"></div>
                            </div>
                        </div>
                        
                        <div>
                            <div class="flex justify-between mb-2">
                                <span class="text-sm font-medium text-gray-300">Data Center Design & Implementation</span>
                                <span class="text-sm text-gray-500">92%</span>
                            </div>
                            <div class="skill-track h-2">
                                <div class="skill-fill" data-width="92%"></div>
                            </div>
                        </div>
                        
                        <div>
                            <div class="flex justify-between mb-2">
                                <span class="text-sm font-medium text-gray-300">PMP / Project Management</span>
                                <span class="text-sm text-gray-500">90%</span>
                            </div>
                            <div class="skill-track h-2">
                                <div class="skill-fill" data-width="90%"></div>
                            </div>
                        </div>
                        
                        <div>
                            <div class="flex justify-between mb-2">
                                <span class="text-sm font-medium text-gray-300">Cost Control & Forecasting</span>
                                <span class="text-sm text-gray-500">88%</span>
                            </div>
                            <div class="skill-track h-2">
                                <div class="skill-fill" data-width="88%"></div>
                            </div>
                        </div>
                        
                        <div>
                            <div class="flex justify-between mb-2">
                                <span class="text-sm font-medium text-gray-300">Vendor & Stakeholder Management</span>
                                <span class="text-sm text-gray-500">90%</span>
                            </div>
                            <div class="skill-track h-2">
                                <div class="skill-fill" data-width="90%"></div>
                            </div>
                        </div>

                        <div>
                            <div class="flex justify-between mb-2">
                                <span class="text-sm font-medium text-gray-300">Six Sigma / Process Optimization</span>
                                <span class="text-sm text-gray-500">85%</span>
                            </div>
                            <div class="skill-track h-2">
                                <div class="skill-fill" data-width="85%"></div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Circular Progress -->
                <div class="glass-card rounded-2xl p-8 section-fade">
                    <h3 class="text-xl font-bold mb-8">Delivery Excellence</h3>
                    
                    <div class="grid grid-cols-2 gap-8">
                        <div class="flex flex-col items-center">
                            <div class="relative w-32 h-32">
                                <svg class="w-full h-full" viewBox="0 0 100 100">
                                    <circle cx="50" cy="50" r="45" fill="none" stroke="rgba(255,255,255,0.05)" stroke-width="8"/>
                                    <circle cx="50" cy="50" r="45" fill="none" stroke="#3b82f6" stroke-width="8" 
                                            stroke-dasharray="283" stroke-dashoffset="283" stroke-linecap="round"
                                            class="progress-ring-circle" data-percent="100"/>
                                </svg>
                                <div class="absolute inset-0 flex items-center justify-center">
                                    <span class="text-2xl font-bold counter" data-target="130">0</span><span class="text-lg">M+</span>
                                </div>
                            </div>
                            <span class="mt-4 text-sm text-gray-400 text-center">$ Portfolio<br>Managed</span>
                        </div>

                        <div class="flex flex-col items-center">
                            <div class="relative w-32 h-32">
                                <svg class="w-full h-full" viewBox="0 0 100 100">
                                    <circle cx="50" cy="50" r="45" fill="none" stroke="rgba(255,255,255,0.05)" stroke-width="8"/>
                                    <circle cx="50" cy="50" r="45" fill="none" stroke="#8b5cf6" stroke-width="8" 
                                            stroke-dasharray="283" stroke-dashoffset="283" stroke-linecap="round"
                                            class="progress-ring-circle" data-percent="100"/>
                                </svg>
                                <div class="absolute inset-0 flex items-center justify-center">
                                    <span class="text-2xl font-bold counter" data-target="9">0</span>
                                </div>
                            </div>
                            <span class="mt-4 text-sm text-gray-400 text-center">Data Centers<br>Controlled</span>
                        </div>

                        <div class="flex flex-col items-center">
                            <div class="relative w-32 h-32">
                                <svg class="w-full h-full" viewBox="0 0 100 100">
                                    <circle cx="50" cy="50" r="45" fill="none" stroke="rgba(255,255,255,0.05)" stroke-width="8"/>
                                    <circle cx="50" cy="50" r="45" fill="none" stroke="#f59e0b" stroke-width="8" 
                                            stroke-dasharray="283" stroke-dashoffset="283" stroke-linecap="round"
                                            class="progress-ring-circle" data-percent="100"/>
                                </svg>
                                <div class="absolute inset-0 flex items-center justify-center">
                                    <span class="text-2xl font-bold counter" data-target="4">0</span>
                                </div>
                            </div>
                            <span class="mt-4 text-sm text-gray-400 text-center">Major<br>Organizations</span>
                        </div>

                        <div class="flex flex-col items-center">
                            <div class="relative w-32 h-32">
                                <svg class="w-full h-full" viewBox="0 0 100 100">
                                    <circle cx="50" cy="50" r="45" fill="none" stroke="rgba(255,255,255,0.05)" stroke-width="8"/>
                                    <circle cx="50" cy="50" r="45" fill="none" stroke="#10b981" stroke-width="8" 
                                            stroke-dasharray="283" stroke-dashoffset="283" stroke-linecap="round"
                                            class="progress-ring-circle" data-percent="100"/>
                                </svg>
                                <div class="absolute inset-0 flex items-center justify-center">
                                    <span class="text-2xl font-bold counter" data-target="6">0</span>
                                </div>
                            </div>
                            <span class="mt-4 text-sm text-gray-400 text-center">Professional<br>Certifications</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Key Achievements -->
            <div class="grid md:grid-cols-3 gap-6">
                <div class="glass-card rounded-2xl p-6 section-fade border-l-4 border-blue-500">
                    <div class="text-3xl font-bold text-white mb-2">$80M</div>
                    <div class="text-gray-400 text-sm">Government District network project connecting ministries to the New Administrative Capital central data center</div>
                </div>
                <div class="glass-card rounded-2xl p-6 section-fade border-l-4 border-purple-500">
                    <div class="text-3xl font-bold text-white mb-2">9 Sites</div>
                    <div class="text-gray-400 text-sm">Integrated correctional facilities controlled via Honeywell EBI enterprise building integrator</div>
                </div>
                <div class="glass-card rounded-2xl p-6 section-fade border-l-4 border-amber-500">
                    <div class="text-3xl font-bold text-white mb-2">Royal</div>
                    <div class="text-gray-400 text-sm">Delivered network infrastructure for Al Yamama Royal Palace and Prince Sultan Military Medical City</div>
                </div>
            </div>
        </div>
    </section>

    <!-- Education -->
    <section class="py-24 relative">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center mb-16 section-fade">
                <span class="badge badge-blue mb-4">Academic Foundation</span>
                <h2 class="serif text-4xl md:text-5xl font-bold mb-4">Education</h2>
            </div>

            <div class="grid md:grid-cols-3 gap-6">
                <div class="glass-card rounded-2xl p-8 section-fade">
                    <div class="w-12 h-12 rounded-xl bg-blue-500/10 flex items-center justify-center mb-4">
                        <i data-lucide="graduation-cap" class="w-6 h-6 text-blue-400"></i>
                    </div>
                    <h3 class="text-lg font-bold mb-2">MBA</h3>
                    <p class="text-gray-400 text-sm mb-3">Arab Academy for Science, Technology & Maritime Transport, Egypt</p>
                    <div class="flex items-center space-x-2">
                        <span class="px-3 py-1 rounded-full bg-blue-500/10 text-blue-400 text-xs font-semibold">GPA 3.8/4.0</span>
                        <span class="px-3 py-1 rounded-full bg-blue-500/10 text-blue-400 text-xs font-semibold">Excellent</span>
                    </div>
                    <p class="text-gray-500 text-xs mt-3">Jan 2022 - April 2024</p>
                </div>

                <div class="glass-card rounded-2xl p-8 section-fade">
                    <div class="w-12 h-12 rounded-xl bg-purple-500/10 flex items-center justify-center mb-4">
                        <i data-lucide="cpu" class="w-6 h-6 text-purple-400"></i>
                    </div>
                    <h3 class="text-lg font-bold mb-2">B.Eng. Communication Engineering</h3>
                    <p class="text-gray-400 text-sm mb-3">Higher Technological Institute, Tenth of Ramadan, Egypt</p>
                    <div class="flex items-center space-x-2">
                        <span class="px-3 py-1 rounded-full bg-purple-500/10 text-purple-400 text-xs font-semibold">2009-2014</span>
                    </div>
                    <p class="text-gray-500 text-xs mt-3">Foundation in electrical systems and network infrastructure</p>
                </div>

                <div class="glass-card rounded-2xl p-8 section-fade">
                    <div class="w-12 h-12 rounded-xl bg-amber-500/10 flex items-center justify-center mb-4">
                        <i data-lucide="globe" class="w-6 h-6 text-amber-400"></i>
                    </div>
                    <h3 class="text-lg font-bold mb-2">BS Electrical Engineering Equivalency</h3>
                    <p class="text-gray-400 text-sm mb-3">University of Toronto School of Continuing Studies, Canada</p>
                    <div class="flex items-center space-x-2">
                        <span class="px-3 py-1 rounded-full bg-amber-500/10 text-amber-400 text-xs font-semibold">International</span>
                    </div>
                    <p class="text-gray-500 text-xs mt-3">Canadian credential recognition</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact / CTA -->
    <section id="contact" class="py-24 relative">
        <div class="absolute inset-0 bg-gradient-to-b from-blue-500/5 to-transparent"></div>
        <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center relative">
            <div class="section-fade">
                <h2 class="serif text-4xl md:text-6xl font-bold mb-6">Ready to Deliver<br><span class="text-blue-400">Your Next Mega Project</span></h2>
                <p class="text-xl text-gray-400 mb-12 max-w-2xl mx-auto">
                    Senior IT Project Manager with proven government, data center, and infrastructure delivery experience across Egypt and Saudi Arabia.
                </p>
                
                <div class="flex flex-col sm:flex-row items-center justify-center gap-4 mb-12">
                    <a href="mailto:mahmoudsh3rawy3@gmail.com" class="px-8 py-4 bg-blue-500 hover:bg-blue-600 text-white font-semibold rounded-xl transition-all transform hover:scale-105 shadow-lg shadow-blue-500/25 flex items-center space-x-2">
                        <i data-lucide="mail" class="w-5 h-5"></i>
                        <span>mahmoudsh3rawy3@gmail.com</span>
                    </a>
                    <a href="tel:+201114939992" class="px-8 py-4 glass hover:bg-white/5 text-white font-semibold rounded-xl transition-all flex items-center space-x-2">
                        <i data-lucide="phone" class="w-5 h-5"></i>
                        <span>+20 111 493 9992</span>
                    </a>
                </div>

                <div class="flex items-center justify-center space-x-8 text-gray-500">
                    <div class="flex items-center space-x-2">
                        <i data-lucide="map-pin" class="w-4 h-4"></i>
                        <span class="text-sm">Cairo, Egypt</span>
                    </div>
                    <div class="flex items-center space-x-2">
                        <i data-lucide="award" class="w-4 h-4"></i>
                        <span class="text-sm">PMP #2768092</span>
                    </div>
                    <div class="flex items-center space-x-2">
                        <i data-lucide="briefcase" class="w-4 h-4"></i>
                        <span class="text-sm">Open to Opportunities</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="border-t border-white/5 py-12">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row justify-between items-center">
            <div class="flex items-center space-x-2 mb-4 md:mb-0">
                <div class="w-6 h-6 bg-blue-500 rounded flex items-center justify-center">
                    <i data-lucide="hexagon" class="w-4 h-4 text-white"></i>
                </div>
                <span class="font-semibold text-sm">Mahmoud Alsharawy</span>
            </div>
            <div class="text-sm text-gray-500">
                 2026 Portfolio. Senior IT Project Manager.
            </div>
        </div>
    </footer>

    <script>
        // Initialize Lucide Icons
        lucide.createIcons();

        // Custom Cursor
        const cursor = document.getElementById('cursor');
        document.addEventListener('mousemove', (e) => {
            cursor.style.left = e.clientX - 10 + 'px';
            cursor.style.top = e.clientY - 10 + 'px';
        });

        document.addEventListener('mousedown', () => {
            cursor.style.transform = 'scale(0.8)';
        });

        document.addEventListener('mouseup', () => {
            cursor.style.transform = 'scale(1)';
        });

        // Mobile Menu Toggle
        function toggleMobileMenu() {
            document.getElementById('mobileMenu').classList.toggle('active');
        }

        // Toggle Card Details
        function toggleCard(card) {
            const details = card.querySelector('.hidden');
            const arrow = card.querySelector('[data-lucide="arrow-right"]');
            if (details.classList.contains('hidden')) {
                details.classList.remove('hidden');
                if (arrow) arrow.style.transform = 'rotate(90deg)';
            } else {
                details.classList.add('hidden');
                if (arrow) arrow.style.transform = 'rotate(0deg)';
            }
        }

        // GSAP Animations
        gsap.registerPlugin(ScrollTrigger);

        // Hero Animations
        const heroTl = gsap.timeline();
        heroTl.to('#heroBadge', { opacity: 1, y: 0, duration: 0.8, ease: 'power3.out' })
              .to('#heroTitle', { opacity: 1, y: 0, duration: 1, ease: 'power3.out' }, '-=0.4')
              .to('#heroSub', { opacity: 1, y: 0, duration: 0.8, ease: 'power3.out' }, '-=0.6')
              .to('#heroCta', { opacity: 1, y: 0, duration: 0.8, ease: 'power3.out' }, '-=0.4')
              .to('#heroStats', { opacity: 1, y: 0, duration: 0.8, ease: 'power3.out' }, '-=0.4');

        // Section Fade Ins
        gsap.utils.toArray('.section-fade').forEach(element => {
            gsap.to(element, {
                opacity: 1,
                y: 0,
                duration: 0.8,
                ease: 'power3.out',
                scrollTrigger: {
                    trigger: element,
                    start: 'top 85%',
                    toggleActions: 'play none none none'
                }
            });
        });

        // Counter Animation
        const counters = document.querySelectorAll('.counter');
        counters.forEach(counter => {
            const target = parseInt(counter.getAttribute('data-target'));
            
            ScrollTrigger.create({
                trigger: counter,
                start: 'top 85%',
                onEnter: () => {
                    gsap.to(counter, {
                        innerHTML: target,
                        duration: 2,
                        snap: { innerHTML: 1 },
                        ease: 'power2.out'
                    });
                }
            });
        });

        // Skill Bars Animation
        const skillFills = document.querySelectorAll('.skill-fill');
        skillFills.forEach(fill => {
            const width = fill.getAttribute('data-width');
            
            ScrollTrigger.create({
                trigger: fill,
                start: 'top 85%',
                onEnter: () => {
                    fill.style.width = width;
                }
            });
        });

        // Progress Rings Animation
        const progressCircles = document.querySelectorAll('.progress-ring-circle');
      
