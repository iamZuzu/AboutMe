<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Profile</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        .profile-section {
            transition: all 0.3s ease;
        }
        .hidden {
            display: none;
            opacity: 0;
        }
        .toggle-container {
            background-color: rgba(237, 233, 254);
            backdrop-filter: blur(5px);
        }
        .toggle-option {
            transition: all 0.3s ease;
            z-index: 1;
        }
        .toggle-checkbox:checked ~ .toggle-label .toggle-option.active {
            color: white;
            font-weight: 600;
        }
        .toggle-checkbox:not(:checked) ~ .toggle-label .toggle-option:not(.active) {
            color: white;
            font-weight: 600;
        }
        .toggle-slider {
            transition: all 0.3s ease;
            z-index: 0;
            background-color: rgba(124, 58, 237, 0.3);
        }
        .toggle-checkbox:checked ~ .toggle-label .toggle-slider {
            transform: translateX(100%);
        }
        .hobby-card:hover, .skill-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            cursor: pointer;
        }
        .profile-header {
            transition: all 0.3s ease;
        }
        .project-detail {
            display: none;
        }
        .project-detail.active {
            display: block;
            animation: fadeIn 0.3s ease-in-out;
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .back-button {
            transition: all 0.3s ease;
        }
        .back-button:hover {
            transform: translateX(-3px);
        }
        .social-icon {
            transition: all 0.3s ease;
        }
        .social-icon:hover {
            transform: translateY(-3px);
        }
    </style>
</head>
<body class="bg-gray-50 min-h-screen font-sans">
    <div class="container mx-auto px-4 py-8 max-w-6xl">
        <!-- Work Profile Header -->
        <div id="workHeader" class="profile-header flex flex-col items-center mb-12">
            <img src="https://about.me/cdn-cgi/image/q=80,dpr=1,f=auto,fit=cover,w=1200,h=630,gravity=0.237x0.185/https://assets.about.me/background/users/z/u/b/zubinsubawalla_1515083910_126.jpg"
                 alt="Professional Headshot" 
                 class="w-32 h-32 rounded-full object-cover border-4 border-white shadow-lg mb-4">
            <h1 class="text-4xl font-bold text-gray-800 mb-2">Alex Johnson</h1>
            <p class="text-xl text-gray-600 mb-6">Digital Creator & Problem Solver</p>
            <a href="#" class="download-btn inline-flex items-center px-6 py-3 bg-purple-600 text-white rounded-lg hover:bg-purple-700 transition-colors mb-6">
                <i class="fas fa-download mr-2"></i> Download Resume
            </a>
        </div>

        <!-- Passion Profile Header -->
        <div id="passionHeader" class="profile-header hidden flex flex-col items-center mb-12">
            <img src="https://custom-images.strikinglycdn.com/res/hrscywv4p/image/upload/c_limit,fl_lossy,h_1440,w_720,f_auto,q_auto/441466/IMG_20151207_102107_fvjp2f.jpg"
                 alt="Casual Photo" 
                 class="w-32 h-32 rounded-full object-cover border-4 border-white shadow-lg mb-4">
            <h1 class="text-4xl font-bold text-gray-800 mb-2">Alex</h1>
            <p class="text-xl text-gray-600 mb-6">Photographer & Food Explorer</p>
            
            <!-- Social Media Links -->
            <div class="flex space-x-4 mb-6">
                <a href="#" class="social-icon text-2xl text-purple-600 hover:text-purple-800">
                    <i class="fab fa-instagram"></i>
                </a>
                <a href="#" class="social-icon text-2xl text-blue-600 hover:text-blue-800">
                    <i class="fab fa-twitter"></i>
                </a>
                <a href="#" class="social-icon text-2xl text-red-600 hover:text-red-800">
                    <i class="fab fa-youtube"></i>
                </a>
                <a href="#" class="social-icon text-2xl text-gray-800 hover:text-black">
                    <i class="fab fa-github"></i>
                </a>
            </div>
        </div>
            
        <!-- Centered Toggle Switch -->
        <div class="flex justify-center mb-8">
            <div class="relative inline-block w-64">
                <input type="checkbox" id="profileToggle" class="toggle-checkbox absolute opacity-0 w-0 h-0">
                <label for="profileToggle" class="toggle-label relative block w-full h-12 rounded-full cursor-pointer overflow-hidden toggle-container">
                    <div class="absolute inset-0 flex items-center justify-center">
                        <span class="toggle-option active flex-1 flex items-center justify-center text-purple-800">Work</span>
                        <span class="toggle-option flex-1 flex items-center justify-center text-purple-800">Passion</span>
                    </div>
                    <div class="toggle-slider absolute left-0 top-0 w-1/2 h-full rounded-full"></div>
                </label>
            </div>
        </div>

        <!-- Work Profile -->
        <div id="workProfile" class="profile-section">
            <!-- Professional Summary -->
            <div class="bg-white rounded-xl shadow-md p-8 mb-8">
                <h2 class="text-2xl font-bold text-gray-800 mb-4">Professional Summary</h2>
                <p class="text-gray-600 leading-relaxed">
                    Seasoned professional with 8+ years of experience in digital product development. 
                    Specializing in creating user-centered designs and scalable solutions for enterprise clients. 
                    Passionate about bridging the gap between business objectives and technical implementation.
                </p>
            </div>

            <!-- Skills -->
            <div class="bg-white rounded-xl shadow-md p-8 mb-8">
                <h2 class="text-2xl font-bold text-gray-800 mb-6">Skills & Projects</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
                    <div class="skill-card bg-purple-50 p-4 rounded-lg transition-all duration-300" data-project="product-strategy">
                        <h3 class="font-semibold text-purple-700 mb-2">Product Strategy</h3>
                        <p class="text-gray-600 text-sm">Roadmapping, Market Analysis, Competitive Research</p>
                        <div class="mt-2 text-purple-600 text-xs font-medium">Click to view project</div>
                    </div>
                    <div class="skill-card bg-purple-50 p-4 rounded-lg transition-all duration-300" data-project="ux-design">
                        <h3 class="font-semibold text-purple-700 mb-2">UX/UI Design</h3>
                        <p class="text-gray-600 text-sm">Wireframing, Prototyping, User Testing</p>
                        <div class="mt-2 text-purple-600 text-xs font-medium">Click to view project</div>
                    </div>
                    <div class="skill-card bg-purple-50 p-4 rounded-lg transition-all duration-300" data-project="frontend-dev">
                        <h3 class="font-semibold text-purple-700 mb-2">Frontend Development</h3>
                        <p class="text-gray-600 text-sm">React, Vue.js, TailwindCSS</p>
                        <div class="mt-2 text-purple-600 text-xs font-medium">Click to view project</div>
                    </div>
                    <div class="skill-card bg-purple-50 p-4 rounded-lg transition-all duration-300" data-project="project-management">
                        <h3 class="font-semibold text-purple-700 mb-2">Project Management</h3>
                        <p class="text-gray-600 text-sm">Agile, Scrum, Kanban</p>
                        <div class="mt-2 text-purple-600 text-xs font-medium">Click to view project</div>
                    </div>
                    <div class="skill-card bg-purple-50 p-4 rounded-lg transition-all duration-300" data-project="data-analysis">
                        <h3 class="font-semibold text-purple-700 mb-2">Data Analysis</h3>
                        <p class="text-gray-600 text-sm">SQL, Google Analytics, A/B Testing</p>
                        <div class="mt-2 text-purple-600 text-xs font-medium">Click to view project</div>
                    </div>
                    <div class="skill-card bg-purple-50 p-4 rounded-lg transition-all duration-300" data-project="technical-writing">
                        <h3 class="font-semibold text-purple-700 mb-2">Technical Writing</h3>
                        <p class="text-gray-600 text-sm">Documentation, API Guides, Tutorials</p>
                        <div class="mt-2 text-purple-600 text-xs font-medium">Click to view project</div>
                    </div>
                </div>
            </div>

            <!-- Project Details (hidden by default) -->
            <div id="projectDetails" class="hidden">
                <!-- Product Strategy Project -->
                <div id="product-strategy" class="project-detail bg-white rounded-xl shadow-md p-8 mb-8">
                    <button class="back-button mb-6 flex items-center text-purple-600 font-medium">
                        <i class="fas fa-arrow-left mr-2"></i> Back to Skills
                    </button>
                    <h2 class="text-2xl font-bold text-gray-800 mb-4">Enterprise SaaS Product Strategy</h2>
                    <div class="flex items-center text-sm text-gray-500 mb-6">
                        <span class="mr-4">TechSolutions Inc.</span>
                        <span>2019 - Present</span>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Challenge</h3>
                        <p class="text-gray-600">
                            The company needed to pivot its product offerings to address emerging market needs in the 
                            post-pandemic digital transformation space. Our existing roadmap wasn't aligned with 
                            shifting customer priorities.
                        </p>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">My Role</h3>
                        <p class="text-gray-600">
                            As the lead product strategist, I conducted extensive market research, analyzed competitor 
                            offerings, and facilitated workshops with stakeholders to redefine our product vision and 
                            3-year roadmap.
                        </p>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Skills Applied</h3>
                        <ul class="list-disc list-inside text-gray-600 space-y-1">
                            <li>Market analysis using Porter's Five Forces framework</li>
                            <li>Customer journey mapping and opportunity identification</li>
                            <li>Stakeholder alignment through collaborative workshops</li>
                            <li>Roadmap prioritization using RICE scoring model</li>
                        </ul>
                    </div>
                    
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Outcome</h3>
                        <p class="text-gray-600">
                            The new strategy resulted in a 35% increase in customer acquisition and positioned the company 
                            as a leader in hybrid work solutions. We successfully launched 3 new product lines within 
                            18 months based on this strategy.
                        </p>
                    </div>
                </div>
                
                <!-- UX/UI Design Project -->
                <div id="ux-design" class="project-detail bg-white rounded-xl shadow-md p-8 mb-8">
                    <button class="back-button mb-6 flex items-center text-purple-600 font-medium">
                        <i class="fas fa-arrow-left mr-2"></i> Back to Skills
                    </button>
                    <h2 class="text-2xl font-bold text-gray-800 mb-4">Healthcare Portal Redesign</h2>
                    <div class="flex items-center text-sm text-gray-500 mb-6">
                        <span class="mr-4">Digital Innovations Co.</span>
                        <span>2017 - 2018</span>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Challenge</h3>
                        <p class="text-gray-600">
                            A major healthcare provider's patient portal had a 65% drop-off rate during the registration 
                            process and poor mobile usability scores. Users found the interface confusing and 
                            overwhelming.
                        </p>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">My Role</h3>
                        <p class="text-gray-600">
                            As the lead UX designer, I conducted user research, created wireframes and prototypes, 
                            and led usability testing sessions to completely redesign the portal experience.
                        </p>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Skills Applied</h3>
                        <ul class="list-disc list-inside text-gray-600 space-y-1">
                            <li>User interviews and persona development</li>
                            <li>Information architecture restructuring</li>
                            <li>Interactive prototyping with Figma</li>
                            <li>Accessibility compliance (WCAG 2.1)</li>
                            <li>Usability testing with medical professionals</li>
                        </ul>
                    </div>
                    
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Outcome</h3>
                        <p class="text-gray-600">
                            The redesigned portal reduced registration drop-off by 52% and improved mobile satisfaction 
                            scores from 2.8 to 4.3/5. The client reported a 40% decrease in support calls related to 
                            portal navigation issues.
                        </p>
                    </div>
                </div>
                
                <!-- Frontend Development Project -->
                <div id="frontend-dev" class="project-detail bg-white rounded-xl shadow-md p-8 mb-8">
                    <button class="back-button mb-6 flex items-center text-purple-600 font-medium">
                        <i class="fas fa-arrow-left mr-2"></i> Back to Skills
                    </button>
                    <h2 class="text-2xl font-bold text-gray-800 mb-4">E-commerce Platform Migration</h2>
                    <div class="flex items-center text-sm text-gray-500 mb-6">
                        <span class="mr-4">TechSolutions Inc.</span>
                        <span>2020</span>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Challenge</h3>
                        <p class="text-gray-600">
                            Our legacy jQuery-based e-commerce platform couldn't support the growing complexity of 
                            product configurations and real-time inventory updates needed for the business.
                        </p>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">My Role</h3>
                        <p class="text-gray-600">
                            As the frontend tech lead, I architected and implemented the migration to a React-based 
                            single-page application with Vue.js for admin interfaces, while ensuring zero downtime 
                            during the transition.
                        </p>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Skills Applied</h3>
                        <ul class="list-disc list-inside text-gray-600 space-y-1">
                            <li>React component architecture with hooks</li>
                            <li>State management with Context API</li>
                            <li>Performance optimization techniques</li>
                            <li>Responsive design with TailwindCSS</li>
                            <li>API integration with GraphQL</li>
                        </ul>
                    </div>
                    
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Outcome</h3>
                        <p class="text-gray-600">
                            The new platform reduced page load times by 68% and increased mobile conversion rates by 
                            22%. The modular architecture allowed for faster feature development, reducing time-to-market 
                            for new capabilities by 40%.
                        </p>
                    </div>
                </div>
                
                <!-- Add similar project detail sections for other skills -->
                <div id="project-management" class="project-detail bg-white rounded-xl shadow-md p-8 mb-8">
                    <button class="back-button mb-6 flex items-center text-purple-600 font-medium">
                        <i class="fas fa-arrow-left mr-2"></i> Back to Skills
                    </button>
                    <h2 class="text-2xl font-bold text-gray-800 mb-4">Global Product Launch</h2>
                    <div class="flex items-center text-sm text-gray-500 mb-6">
                        <span class="mr-4">TechSolutions Inc.</span>
                        <span>2021</span>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Challenge</h3>
                        <p class="text-gray-600">
                            Coordinating a simultaneous product launch across 12 countries with regulatory requirements, 
                            localization needs, and distributed teams in 5 time zones.
                        </p>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">My Role</h3>
                        <p class="text-gray-600">
                            As project manager, I established agile processes, facilitated cross-team collaboration, 
                            and implemented tracking mechanisms to ensure all dependencies were managed effectively.
                        </p>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Skills Applied</h3>
                        <ul class="list-disc list-inside text-gray-600 space-y-1">
                            <li>Agile Scrum methodology implementation</li>
                            <li>Risk management and mitigation planning</li>
                            <li>Stakeholder communication strategies</li>
                            <li>JIRA workflow customization</li>
                            <li>Release planning and coordination</li>
                        </ul>
                    </div>
                    
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Outcome</h3>
                        <p class="text-gray-600">
                            The product launched on schedule in all markets with zero critical issues. The project 
                            management framework developed became the company standard for future global launches.
                        </p>
                    </div>
                </div>
                
                <div id="data-analysis" class="project-detail bg-white rounded-xl shadow-md p-8 mb-8">
                    <button class="back-button mb-6 flex items-center text-purple-600 font-medium">
                        <i class="fas fa-arrow-left mr-2"></i> Back to Skills
                    </button>
                    <h2 class="text-2xl font-bold text-gray-800 mb-4">Customer Retention Analysis</h2>
                    <div class="flex items-center text-sm text-gray-500 mb-6">
                        <span class="mr-4">TechSolutions Inc.</span>
                        <span>2022</span>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Challenge</h3>
                        <p class="text-gray-600">
                            The company was experiencing higher than expected customer churn (28% annually) but lacked 
                            clear insights into the drivers of attrition or predictive indicators.
                        </p>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">My Role</h3>
                        <p class="text-gray-600">
                            I led a cross-functional team to analyze customer usage patterns, support interactions, and 
                            satisfaction metrics to identify churn risk factors and recommend intervention strategies.
                        </p>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Skills Applied</h3>
                        <ul class="list-disc list-inside text-gray-600 space-y-1">
                            <li>SQL queries for customer behavior analysis</li>
                            <li>Google Analytics event tracking setup</li>
                            <li>A/B testing design and interpretation</li>
                            <li>Data visualization with Tableau</li>
                            <li>Predictive modeling techniques</li>
                        </ul>
                    </div>
                    
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Outcome</h3>
                        <p class="text-gray-600">
                            Identified 5 key churn indicators and implemented targeted interventions that reduced 
                            annual churn to 18%. The predictive model achieved 82% accuracy in flagging at-risk 
                            customers 90 days before churn.
                        </p>
                    </div>
                </div>
                
                <div id="technical-writing" class="project-detail bg-white rounded-xl shadow-md p-8 mb-8">
                    <button class="back-button mb-6 flex items-center text-purple-600 font-medium">
                        <i class="fas fa-arrow-left mr-2"></i> Back to Skills
                    </button>
                    <h2 class="text-2xl font-bold text-gray-800 mb-4">Developer Portal Documentation</h2>
                    <div class="flex items-center text-sm text-gray-500 mb-6">
                        <span class="mr-4">TechSolutions Inc.</span>
                        <span="2021 - 2022</span>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Challenge</h3>
                        <p class="text-gray-600">
                            Our API documentation was fragmented, outdated, and frequently cited as a pain point by 
                            developers integrating with our platform. Support tickets related to documentation issues 
                            accounted for 35% of all developer support requests.
                        </p>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">My Role</h3>
                        <p class="text-gray-600">
                            I overhauled the entire developer portal, creating comprehensive, standardized documentation 
                            with interactive examples, and implemented processes to keep content current with product 
                            updates.
                        </p>
                    </div>
                    
                    <div class="mb-6">
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Skills Applied</h3>
                        <ul class="list-disc list-inside text-gray-600 space-y-1">
                            <li>Technical documentation best practices</li>
                            <li>API reference documentation</li>
                            <li>Tutorial and quickstart guide creation</li>
                            <li>Swagger/OpenAPI specification</li>
                            <li>Documentation versioning strategy</li>
                        </ul>
                    </div>
                    
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-2">Outcome</h3>
                        <p class="text-gray-600">
                            Developer satisfaction with documentation improved from 3.1 to 4.6/5, and support tickets 
                            related to documentation issues dropped by 78%. The portal became a key differentiator 
                            in sales conversations with technical buyers.
                        </p>
                    </div>
                </div>
            </div>

            <!-- My Journey -->
            <div id="journeySection" class="bg-white rounded-xl shadow-md p-8 mb-8">
                <h2 class="text-2xl font-bold text-gray-800 mb-6">My Professional Journey</h2>
                <div class="space-y-8">
                    <div class="flex flex-col md:flex-row gap-6">
                        <div class="md:w-1/4">
                            <p class="text-purple-600 font-semibold">2019 - Present</p>
                        </div>
                        <div class="md:w-3/4">
                            <h3 class="text-xl font-semibold text-gray-800 mb-1">Senior Product Designer</h3>
                            <p class="text-purple-600 mb-2">TechSolutions Inc.</p>
                            <p class="text-gray-600">Leading design initiatives for enterprise SaaS products, mentoring junior designers, and collaborating with cross-functional teams to deliver innovative solutions.</p>
                        </div>
                    </div>
                    <div class="flex flex-col md:flex-row gap-6">
                        <div class="md:w-1/4">
                            <p class="text-purple-600 font-semibold">2016 - 2019</p>
                        </div>
                        <div class="md:w-3/4">
                            <h3 class="text-xl font-semibold text-gray-800 mb-1">UX Designer</h3>
                            <p class="text-purple-600 mb-2">Digital Innovations Co.</p>
                            <p class="text-gray-600">Designed and tested user interfaces for mobile and web applications, conducted user research, and created design systems for consistent product experiences.</p>
                        </div>
                    </div>
                    <div class="flex flex-col md:flex-row gap-6">
                        <div class="md:w-1/4">
                            <p class="text-purple-600 font-semibold">2014 - 2016</p>
                        </div>
                        <div class="md:w-3/4">
                            <h3 class="text-xl font-semibold text-gray-800 mb-1">Junior Designer</h3>
                            <p class="text-purple-600 mb-2">Creative Studio</p>
                            <p class="text-gray-600">Assisted senior designers with various projects, created marketing materials, and developed foundational design skills.</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Get in Touch Section -->
            <div class="bg-white rounded-xl shadow-md p-8">
                <h2 class="text-2xl font-bold text-gray-800 mb-6">Get in Touch</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    <div class="bg-purple-50 p-6 rounded-lg">
                        <div class="flex items-center mb-4">
                            <div class="bg-purple-100 p-3 rounded-full mr-4">
                                <i class="fas fa-envelope text-purple-600"></i>
                            </div>
                            <div>
                                <h3 class="font-semibold text-gray-800">Email</h3>
                                <p class="text-purple-600">alex.johnson@example.com</p>
                            </div>
                        </div>
                        <p class="text-gray-600 text-sm">For professional inquiries and collaboration opportunities</p>
                    </div>
                    <div class="bg-purple-50 p-6 rounded-lg">
                        <div class="flex items-center mb-4">
                            <div class="bg-purple-100 p-3 rounded-full mr-4">
                                <i class="fas fa-phone-alt text-purple-600"></i>
                            </div>
                            <div>
                                <h3 class="font-semibold text-gray-800">Phone</h3>
                                <p class="text-purple-600">+1 (555) 123-4567</p>
                            </div>
                        </div>
                        <p class="text-gray-600 text-sm">Available Monday to Friday, 9am - 5pm EST</p>
                    </div>
                    <div class="bg-purple-50 p-6 rounded-lg">
                        <div class="flex items-center mb-4">
                            <div class="bg-purple-100 p-3 rounded-full mr-4">
                                <i class="fab fa-linkedin-in text-purple-600"></i>
                            </div>
                            <div>
                                <h3 class="font-semibold text-gray-800">LinkedIn</h3>
                                <p class="text-purple-600">linkedin.com/in/alexjohnson</p>
                            </div>
                        </div>
                        <p class="text-gray-600 text-sm">Connect for professional networking</p>
                    </div>
                    <div class="bg-purple-50 p-6 rounded-lg">
                        <div class="flex items-center mb-4">
                            <div class="bg-purple-100 p-3 rounded-full mr-4">
                                <i class="fas fa-map-marker-alt text-purple-600"></i>
                            </div>
                            <div>
                                <h3 class="font-semibold text-gray-800">Location</h3>
                                <p class="text-purple-600">New York, NY</p>
                            </div>
                        </div>
                        <p class="text-gray-600 text-sm">Open to remote work or local opportunities</p>
                    </div>
                </div>
                <div class="mt-8">
                    <a href="#" class="inline-flex items-center px-6 py-3 bg-purple-600 text-white rounded-lg hover:bg-purple-700 transition-colors">
                        <i class="fas fa-paper-plane mr-2"></i> Send Message
                    </a>
                </div>
            </div>
        </div>

        <!-- Passion Projects Profile -->
        <div id="passionProfile" class="profile-section hidden">
            <!-- Personal Introduction -->
            <div class="bg-white rounded-xl shadow-md p-8 mb-8">
                <h2 class="text-2xl font-bold text-gray-800 mb-4">The Real Me</h2>
                <p class="text-gray-600 leading-relaxed">
                    When I'm not in professional mode, you'll find me exploring creative outlets that fuel my soul. 
                    I believe life is too short to be serious all the time, so I fill my free time with activities that 
                    spark joy, challenge my perspective, and connect me with amazing people. Here's a glimpse into 
                    what makes me tick when the workday ends!
                </p>
            </div>

            <!-- Hobbies -->
            <div class="bg-white rounded-xl shadow-md p-8 mb-8">
                <h2 class="text-2xl font-bold text-gray-800 mb-6">My Hobbies & Creative Outlets</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                    <div class="hobby-card bg-gradient-to-br from-purple-50 to-pink-50 p-6 rounded-xl transition-all duration-300">
                        <div class="text-purple-600 text-3xl mb-3">
                            <i class="fas fa-camera"></i>
                        </div>
                        <h3 class="font-semibold text-gray-800 text-lg mb-2">Street Photography</h3>
                        <p class="text-gray-600 text-sm">
                            Capturing raw, unscripted moments of urban life. My camera is my constant companion on city walks.
                        </p>
                    </div>
                    <div class="hobby-card bg-gradient-to-br from-blue-50 to-cyan-50 p-6 rounded-xl transition-all duration-300">
                        <div class="text-blue-600 text-3xl mb-3">
                            <i class="fas fa-utensils"></i>
                        </div>
                        <h3 class="font-semibold text-gray-800 text-lg mb-2">Experimental Cooking</h3>
                        <p class="text-gray-600 text-sm">
                            My kitchen is a lab where I fuse flavors from different cultures. Current obsession: Korean-Mexican fusion!
                        </p>
                    </div>
                    <div class="hobby-card bg-gradient-to-br from-red-50 to-pink-50 p-6 rounded-xl transition-all duration-300">
                        <div class="text-red-600 text-3xl mb-3">
                            <i class="fas fa-hiking"></i>
                        </div>
                        <h3 class="font-semibold text-gray-800 text-lg mb-2">Urban Exploration</h3>
                        <p class="text-gray-600 text-sm">
                            Discovering hidden gems and forgotten spaces in the city. Every alley has a story to tell.
                        </p>
                    </div>
                </div>
            </div>

            <!-- Follow Me Section -->
            <div class="bg-white rounded-xl shadow-md p-8 mb-8">
                <h2 class="text-2xl font-bold text-gray-800 mb-6">Follow My Adventures</h2>
                <p class="text-gray-600 mb-6">
                    I share my creative projects and daily discoveries on these platforms. Let's connect!
                </p>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    <div class="bg-gradient-to-r from-purple-50 to-pink-50 p-6 rounded-lg flex items-center">
                        <div class="bg-white p-3 rounded-full mr-4 shadow-sm">
                            <i class="fab fa-instagram text-2xl text-pink-600"></i>
                        </div>
                        <div>
                            <h3 class="font-semibold text-gray-800">Instagram</h3>
                            <p class="text-purple-600">@alex.explores</p>
                            <p class="text-gray-600 text-sm mt-1">Daily photography and food adventures</p>
                        </div>
                    </div>
                    <div class="bg-gradient-to-r from-blue-50 to-cyan-50 p-6 rounded-lg flex items-center">
                        <div class="bg-white p-3 rounded-full mr-4 shadow-sm">
                            <i class="fab fa-youtube text-2xl text-red-600"></i>
                        </div>
                        <div>
                            <h3 class="font-semibold text-gray-800">YouTube</h3>
                            <p class="text-purple-600">Alex's Creative Kitchen</p>
                            <p class="text-gray-600 text-sm mt-1">Cooking tutorials and recipe experiments</p>
                        </div>
                    </div>
                    <div class="bg-gradient-to-r from-green-50 to-teal-50 p-6 rounded-lg flex items-center">
                        <div class="bg-white p-3 rounded-full mr-4 shadow-sm">
                            <i class="fab fa-twitter text-2xl text-blue-400"></i>
                        </div>
                        <div>
                            <h3 class="font-semibold text-gray-800">Twitter</h3>
                            <p class="text-purple-600">@alexthoughts</p>
                            <p class="text-gray-600 text-sm mt-1">Random musings and creative ideas</p>
                        </div>
                    </div>
                    <div class="bg-gradient-to-r from-yellow-50 to-orange-50 p-6 rounded-lg flex items-center">
                        <div class="bg-white p-3 rounded-full mr-4 shadow-sm">
                            <i class="fab fa-tiktok text-2xl text-black"></i>
                        </div>
                        <div>
                            <h3 class="font-semibold text-gray-800">TikTok</h3>
                            <p class="text-purple-600">@urbanexplorer</p>
                            <p class="text-gray-600 text-sm mt-1">Short videos of hidden city spots</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Blog -->
            <div class="bg-white rounded-xl shadow-md p-8">
                <h2 class="text-2xl font-bold text-gray-800 mb-6">Thoughts & Musings</h2>
                <div class="space-y-6">
                    <div class="border-b border-gray-100 pb-6">
                        <h3 class="text-xl font-semibold text-gray-800 mb-2">Why Imperfections Make Better Art</h3>
                        <p class="text-purple-600 mb-3">June 12, 2023 • 5 min read</p>
                        <p class="text-gray-600 mb-3">
                            Exploring how flaws and accidents often lead to the most interesting creative breakthroughs...
                        </p>
                        <a href="#" class="text-purple-600 font-medium hover:text-purple-800 transition-colors">Read more →</a>
                    </div>
                    <div class="border-b border-gray-100 pb-6">
                        <h3 class="text-xl font-semibold text-gray-800 mb-2">The Hidden Beauty of Urban Decay</h3>
                        <p class="text-purple-600 mb-3">April 28, 2023 • 7 min read</p>
                        <p class="text-gray-600 mb-3">
                            A photographic journey through abandoned spaces and what they teach us about time and memory...
                        </p>
                        <a href="#" class="text-purple-600 font-medium hover:text-purple-800 transition-colors">Read more →</a>
                    </div>
                    <div class="pb-2">
                        <h3 class="text-xl font-semibold text-gray-800 mb-2">Fusion Cooking: When Cultures Collide Deliciously</h3>
                        <p class="text-purple-600 mb-3">March 15, 2023 • 4 min read</p>
                        <p class="text-gray-600 mb-3">
                            My experiments with combining unexpected culinary traditions and the surprising results...
                        </p>
                        <a href="#" class="text-purple-600 font-medium hover:text-purple-800 transition-colors">Read more →</a>
                    </div>
                </div>
                <div class="mt-8">
                    <a href="#" class="inline-flex items-center px-6 py-3 bg-purple-600 text-white rounded-lg hover:bg-purple-700 transition-colors">
                        View All Posts
                        <i class="fas fa-arrow-right ml-2"></i>
                    </a>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Toggle between work and passion profiles
        document.getElementById('profileToggle').addEventListener('change', function() {
            const workProfile = document.getElementById('workProfile');
            const passionProfile = document.getElementById('passionProfile');
            const workHeader = document.getElementById('workHeader');
            const passionHeader = document.getElementById('passionHeader');
            
            if (this.checked) {
                workProfile.classList.add('hidden');
                passionProfile.classList.remove('hidden');
                workHeader.classList.add('hidden');
                passionHeader.classList.remove('hidden');
            } else {
                workProfile.classList.remove('hidden');
                passionProfile.classList.add('hidden');
                workHeader.classList.remove('hidden');
                passionHeader.classList.add('hidden');
            }
        });

        // Handle skill card clicks to show project details
        document.querySelectorAll('.skill-card').forEach(card => {
            card.addEventListener('click', function() {
                const projectId = this.getAttribute('data-project');
                const projectDetails = document.getElementById('projectDetails');
                const journeySection = document.getElementById('journeySection');
                
                // Hide all project details first
                document.querySelectorAll('.project-detail').forEach(detail => {
                    detail.classList.remove('active');
                });
                
                // Show the selected project
                document.getElementById(projectId).classList.add('active');
                
                // Show project details container and hide journey section
                projectDetails.classList.remove('hidden');
                journeySection.classList.add('hidden');
                
                // Scroll to project details
                projectDetails.scrollIntoView({ behavior: 'smooth' });
            });
        });

        // Handle back button clicks
        document.querySelectorAll('.back-button').forEach(button => {
            button.addEventListener('click', function() {
                const projectDetails = document.getElementById('projectDetails');
                const journeySection = document.getElementById('journeySection');
                
                // Hide project details and show journey section
                projectDetails.classList.add('hidden');
                journeySection.classList.remove('hidden');
                
                // Scroll to journey section
                journeySection.scrollIntoView({ behavior: 'smooth' });
            });
        });

        // Handle download resume button click
        document.querySelector('.download-btn').addEventListener('click', function(e) {
            e.preventDefault();
            alert('Downloading resume...');
            // In a real implementation, this would link to an actual PDF file
        });
    </script>
</body>
</html>
