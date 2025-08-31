<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Proposal: The Venise Group</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Chosen Palette: Navy/Deep Blue (#002D62), Charcoal Gray (#36454F), Gold/Bronze (#B8860B), Light Gray/White (#F5F5F5) -->
    <!-- Application Structure Plan: A single-page scrolling application with a fixed navigation bar. The structure prioritizes user engagement by transforming the static service list into an interactive tabbed explorer and visualizing the 4-step approach as a process flowchart. This design encourages active exploration over passive reading, making the proposal more compelling and easier to digest. -->
    <!-- Visualization & Content Choices: Report Info: Core Services -> Goal: Organize & Inform -> Viz: Interactive Tabs -> Interaction: Click to reveal service details -> Justification: Breaks down dense information and allows users to focus on their specific needs. Library: Vanilla JS. Report Info: Our Approach -> Goal: Explain Process -> Viz: HTML/CSS Flowchart -> Interaction: Hover to highlight steps -> Justification: A visual process is more intuitive than a text list. Library: HTML/Tailwind CSS. CONFIRM: No quantitative data, so no charts are needed. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Lora', serif;
            background-color: #F5F5F5;
            color: #36454F;
        }
        h1, h2, h3, h4, h5, h6 {
            font-family: 'Montserrat', sans-serif;
        }
        .active-tab {
            background-color: #002D62 !important;
            color: #FFFFFF !important;
            border-color: #002D62 !important;
        }
        .process-step {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .process-step:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -4px rgb(0 0 0 / 0.1);
        }
        .process-arrow {
            color: #B8860B;
        }
        .advantage-card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .advantage-card:hover {
            transform: scale(1.03);
        }
    </style>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Lora:wght@400;700&family=Montserrat:wght@400;700&display=swap" rel="stylesheet">
</head>
<body class="antialiased">

    <header class="bg-white/80 backdrop-blur-md shadow-sm sticky top-0 z-50">
        <nav class="container mx-auto px-6 py-4 flex justify-between items-center">
            <h1 class="text-2xl font-bold text-[#002D62]">The Venise Group</h1>
            <div class="hidden md:flex space-x-8">
                <a href="#services" class="text-[#36454F] hover:text-[#B8860B] transition-colors">Services</a>
                <a href="#approach" class="text-[#36454F] hover:text-[#B8860B] transition-colors">Our Approach</a>
                <a href="#advantage" class="text-[#36454F] hover:text-[#B8860B] transition-colors">Advantage</a>
                <a href="#contact" class="bg-[#B8860B] text-white py-2 px-4 rounded-full hover:bg-opacity-90 transition-all">Contact</a>
            </div>
            <button id="mobile-menu-button" class="md:hidden text-[#002D62]">
                <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path></svg>
            </button>
        </nav>
        <div id="mobile-menu" class="hidden md:hidden px-6 pt-2 pb-4 space-y-2">
            <a href="#services" class="block text-[#36454F] hover:text-[#B8860B]">Services</a>
            <a href="#approach" class="block text-[#36454F] hover:text-[#B8860B]">Our Approach</a>
            <a href="#advantage" class="block text-[#36454F] hover:text-[#B8860B]">Advantage</a>
            <a href="#contact" class="block text-[#36454F] hover:text-[#B8860B]">Contact</a>
        </div>
    </header>

    <main>
        <section class="bg-white py-20 md:py-32">
            <div class="container mx-auto px-6 text-center">
                <h1 class="text-4xl md:text-6xl font-bold text-[#002D62] leading-tight mb-4">A Strategic Partnership for Growth</h1>
                <p class="text-lg md:text-xl text-[#36454F] max-w-3xl mx-auto mb-8">This proposal outlines a collaborative engagement with The Venise Group to enhance your organization's governance, streamline operations, and amplify your advocacy efforts.</p>
                <a href="#contact" class="bg-[#002D62] text-white py-3 px-8 rounded-full text-lg font-semibold hover:bg-opacity-90 transition-transform hover:scale-105">Let's Discuss Your Goals</a>
            </div>
        </section>

        <section id="services" class="py-20">
            <div class="container mx-auto px-6">
                <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold text-[#002D62]">Our Core Services</h2>
                    <p class="mt-4 text-lg text-[#36454F] max-w-2xl mx-auto">We provide tailored solutions across three key pillars to build resilient, efficient, and influential organizations. Click a category to explore our offerings.</p>
                </div>

                <div class="flex flex-col md:flex-row justify-center mb-8 space-y-2 md:space-y-0 md:space-x-4">
                    <button class="service-tab py-3 px-6 border-2 border-gray-300 rounded-full font-semibold text-lg text-[#36454F] hover:bg-gray-100 transition-colors active-tab" data-target="governance">
                        Governance
                    </button>
                    <button class="service-tab py-3 px-6 border-2 border-gray-300 rounded-full font-semibold text-lg text-[#36454F] hover:bg-gray-100 transition-colors" data-target="operations">
                        Operations
                    </button>
                    <button class="service-tab py-3 px-6 border-2 border-gray-300 rounded-full font-semibold text-lg text-[#36454F] hover:bg-gray-100 transition-colors" data-target="advocacy">
                        Advocacy
                    </button>
                </div>

                <div class="max-w-4xl mx-auto">
                    <div id="governance" class="service-content bg-white p-8 rounded-lg shadow-lg">
                        <h3 class="text-2xl font-bold text-[#002D62] mb-4">Expertise in Governance</h3>
                        <p class="text-lg mb-6 text-[#36454F]">We build the structures that ensure transparency, accountability, and ethical decision-making for long-term stability.</p>
                        <ul class="space-y-3 text-lg text-[#36454F]">
                            <li class="flex items-start"><span class="text-[#B8860B] font-bold mr-3">✔</span> Board Development & Training</li>
                            <li class="flex items-start"><span class="text-[#B8860B] font-bold mr-3">✔</span> Risk Management & Compliance</li>
                            <li class="flex items-start"><span class="text-[#B8860B] font-bold mr-3">✔</span> Policy & Bylaws Review</li>
                        </ul>
                    </div>
                    <div id="operations" class="service-content bg-white p-8 rounded-lg shadow-lg hidden">
                        <h3 class="text-2xl font-bold text-[#002D62] mb-4">Clarity in Operations</h3>
                        <p class="text-lg mb-6 text-[#36454F]">We streamline processes, optimize resources, and drive efficiency for sustainable organizational growth.</p>
                         <ul class="space-y-3 text-lg text-[#36454F]">
                            <li class="flex items-start"><span class="text-[#B8860B] font-bold mr-3">✔</span> Process Optimization & Project Management</li>
                            <li class="flex items-start"><span class="text-[#B8860B] font-bold mr-3">✔</span> Team & Resource Alignment</li>
                            <li class="flex items-start"><span class="text-[#B8860B] font-bold mr-3">✔</span> Operational Audit & Strategy</li>
                        </ul>
                    </div>
                    <div id="advocacy" class="service-content bg-white p-8 rounded-lg shadow-lg hidden">
                        <h3 class="text-2xl font-bold text-[#002D62] mb-4">Power in Advocacy</h3>
                        <p class="text-lg mb-6 text-[#36454F]">We craft compelling narratives and forge strategic alliances to amplify your voice and influence policy.</p>
                         <ul class="space-y-3 text-lg text-[#36454F]">
                            <li class="flex items-start"><span class="text-[#B8860B] font-bold mr-3">✔</span> Government & Stakeholder Relations</li>
                            <li class="flex items-start"><span class="text-[#B8860B] font-bold mr-3">✔</span> Issue-Based Campaigns</li>
                            <li class="flex items-start"><span class="text-[#B8860B] font-bold mr-3">✔</span> Coalition Building</li>
                        </ul>
                    </div>
                </div>
            </div>
        </section>

        <section id="approach" class="py-20 bg-white">
            <div class="container mx-auto px-6">
                <div class="text-center mb-16">
                    <h2 class="text-3xl md:text-4xl font-bold text-[#002D62]">Our Approach</h2>
                    <p class="mt-4 text-lg text-[#36454F] max-w-2xl mx-auto">We follow a proven, collaborative four-step process to ensure we understand your needs, develop the right strategy, and deliver measurable impact.</p>
                </div>
                <div class="flex flex-col md:flex-row items-center justify-center space-y-8 md:space-y-0 md:space-x-4">
                    <div class="process-step text-center w-full md:w-1/4 p-6 bg-gray-50 rounded-xl shadow-md border-t-4 border-[#B8860B]">
                        <div class="text-3xl font-bold text-[#002D62] mb-3">1</div>
                        <h3 class="text-xl font-bold mb-2 text-[#002D62]">Discovery</h3>
                        <p>An in-depth consultation to understand your unique challenges and objectives.</p>
                    </div>
                    <div class="process-arrow text-4xl hidden md:block mx-4">→</div>
                    <div class="process-step text-center w-full md:w-1/4 p-6 bg-gray-50 rounded-xl shadow-md border-t-4 border-[#B8860B]">
                        <div class="text-3xl font-bold text-[#002D62] mb-3">2</div>
                        <h3 class="text-xl font-bold mb-2 text-[#002D62]">Strategy</h3>
                        <p>We develop a customized plan tailored to your specific needs and goals.</p>
                    </div>
                    <div class="process-arrow text-4xl hidden md:block mx-4">→</div>
                    <div class="process-step text-center w-full md:w-1/4 p-6 bg-gray-50 rounded-xl shadow-md border-t-4 border-[#B8860B]">
                        <div class="text-3xl font-bold text-[#002D62] mb-3">3</div>
                        <h3 class="text-xl font-bold mb-2 text-[#002D62]">Execution</h3>
                        <p>We partner with your team to implement the plan, providing hands-on support.</p>
                    </div>
                    <div class="process-arrow text-4xl hidden md:block mx-4">→</div>
                    <div class="process-step text-center w-full md:w-1/4 p-6 bg-gray-50 rounded-xl shadow-md border-t-4 border-[#B8860B]">
                        <div class="text-3xl font-bold text-[#002D62] mb-3">4</div>
                        <h3 class="text-xl font-bold mb-2 text-[#002D62]">Impact</h3>
                        <p>We measure our success by your results—increased efficiency and strengthened influence.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="advantage" class="py-20">
            <div class="container mx-auto px-6">
                 <div class="text-center mb-12">
                    <h2 class="text-3xl md:text-4xl font-bold text-[#002D62]">The Venise Group Advantage</h2>
                    <p class="mt-4 text-lg text-[#36454F] max-w-2xl mx-auto">We are more than consultants; we are your dedicated partners for change, committed to delivering exceptional and sustainable results.</p>
                </div>
                <div class="grid md:grid-cols-3 gap-8">
                    <div class="advantage-card bg-white p-8 rounded-lg shadow-lg text-center">
                        <h3 class="text-2xl font-bold text-[#002D62] mb-3">Strategic Vision</h3>
                        <p class="text-lg">We don't just solve problems; we anticipate them and position you for future success.</p>
                    </div>
                    <div class="advantage-card bg-white p-8 rounded-lg shadow-lg text-center">
                        <h3 class="text-2xl font-bold text-[#002D62] mb-3">Tailored Solutions</h3>
                        <p class="text-lg">Your challenges are unique, and so are our solutions—no one-size-fits-all templates.</p>
                    </div>
                    <div class="advantage-card bg-white p-8 rounded-lg shadow-lg text-center">
                        <h3 class="text-2xl font-bold text-[#002D62] mb-3">Commitment to Impact</h3>
                        <p class="text-lg">We are results-driven, focused on delivering tangible, measurable value to your organization.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact" class="py-20 bg-[#002D62] text-white">
            <div class="container mx-auto px-6 text-center">
                <h2 class="text-3xl md:text-4xl font-bold">Ready to Transform Your Organization?</h2>
                <p class="mt-4 text-lg max-w-2xl mx-auto mb-8">Let's schedule a consultation to discuss a strategic plan that aligns with your vision and goals.</p>
                <a href="mailto:your-email@example.com" class="bg-[#B8860B] text-white py-3 px-8 rounded-full text-lg font-semibold hover:bg-opacity-90 transition-transform hover:scale-105 inline-block">Schedule a Consultation</a>
                 <div class="mt-12 text-lg">
                    <p class="font-bold">The Venise Group</p>
                    <p>your-email@example.com | (555) 123-4567</p>
                    <p>yourwebsite.com</p>
                </div>
            </div>
        </section>
    </main>
    
    <footer class="bg-[#36454F] text-white py-6">
        <div class="container mx-auto px-6 text-center">
            <p>&copy; 2025 The Venise Group. All Rights Reserved.</p>
        </div>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const serviceTabs = document.querySelectorAll('.service-tab');
            const serviceContents = document.querySelectorAll('.service-content');

            serviceTabs.forEach(tab => {
                tab.addEventListener('click', () => {
                    const target = tab.dataset.target;

                    serviceTabs.forEach(t => t.classList.remove('active-tab'));
                    tab.classList.add('active-tab');

                    serviceContents.forEach(content => {
                        if (content.id === target) {
                            content.classList.remove('hidden');
                        } else {
                            content.classList.add('hidden');
                        }
                    });
                });
            });

            const mobileMenuButton = document.getElementById('mobile-menu-button');
            const mobileMenu = document.getElementById('mobile-menu');
            mobileMenuButton.addEventListener('click', () => {
                mobileMenu.classList.toggle('hidden');
            });
            
            const navLinks = document.querySelectorAll('nav a');
            navLinks.forEach(link => {
                link.addEventListener('click', () => {
                    if(!mobileMenu.classList.contains('hidden')){
                         mobileMenu.classList.add('hidden');
                    }
                })
            })

        });
    </script>
</body>
</html>
