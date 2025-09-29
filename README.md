<!DOCTYPE html>
<html lang="pt-BR">
<!--
🚀 GUIA DE EDIÇÃO RÁPIDA - SITE B2B AUTOFLOW PRO

📝 COMO EDITAR TEXTOS:
   - Vá até a seção "SITE_CONFIG" no JavaScript (linha ~529)
   - Edite company.name, hero.title, contact.email, etc.

🎨 COMO TROCAR CORES:
   - Vá até ":root" no CSS (linha ~14) e edite as variáveis --primary-color, etc.
   - OU use as paletas pré-definidas descomentando uma linha no JavaScript (linha ~638)

🖼️ COMO TROCAR LOGO:
   - Substitua "AF" por suas iniciais na variável company.initials
   - OU descomente a linha da imagem e adicione sua logo (linha ~116)

📱 COMO ADICIONAR ÍCONES:
   - Use os SVGs existentes como modelo
   - Ou substitua por Font Awesome: <i class="fas fa-icon-name"></i>

🌐 DEPLOY NO GITHUB:
   1. Crie um repositório no GitHub
   2. Faça upload deste arquivo como index.html
   3. Ative GitHub Pages nas configurações
   4. Seu site estará online!
-->
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AutoFlow Pro - Automação e Tráfego Pago</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        /* ========================================
           🎨 CONFIGURAÇÕES EDITÁVEIS DA MARCA
        ======================================== */
        
        :root {
            /* CORES DA MARCA - Edite aqui suas cores */
            --primary-color: #667eea;      /* Azul principal */
            --secondary-color: #764ba2;    /* Roxo secundário */
            --accent-color: #fbbf24;       /* Amarelo destaque */
            --text-dark: #1f2937;          /* Texto escuro */
            --text-light: #6b7280;         /* Texto claro */
            --background-light: #f9fafb;   /* Fundo claro */
            --white: #ffffff;              /* Branco */
            
            /* TIPOGRAFIA - Edite as fontes aqui */
            --font-primary: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            --font-secondary: 'Poppins', sans-serif;
        }
        
        /* Importar fontes do Google Fonts */
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Poppins:wght@300;400;500;600;700;800&display=swap');
        
        body {
            box-sizing: border-box;
            font-family: var(--font-primary);
        }
        
        /* ========================================
           📝 TEXTOS EDITÁVEIS
           Encontre e edite os textos nas variáveis JS abaixo
        ======================================== */
        
        .gradient-bg {
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
        }
        
        /* Aplicar cores da marca */
        .brand-primary { color: var(--primary-color) !important; }
        .brand-secondary { color: var(--secondary-color) !important; }
        .brand-accent { color: var(--accent-color) !important; }
        .bg-brand-primary { background-color: var(--primary-color) !important; }
        .bg-brand-secondary { background-color: var(--secondary-color) !important; }
        .bg-brand-accent { background-color: var(--accent-color) !important; }
        .border-brand-primary { border-color: var(--primary-color) !important; }
        
        .card-hover {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .card-hover:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
        }
        
        .fade-in {
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 0.6s ease forwards;
        }
        
        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .nav-link {
            position: relative;
            transition: color 0.3s ease;
        }
        
        .nav-link::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background-color: #667eea;
            transition: width 0.3s ease;
        }
        
        .nav-link:hover::after {
            width: 100%;
        }
        
        .stats-counter {
            font-size: 2.5rem;
            font-weight: bold;
            color: #667eea;
        }
    </style>
</head>
<body class="bg-gray-50">
    <!-- Header -->
    <header class="bg-white shadow-lg fixed w-full top-0 z-50">
        <nav class="container mx-auto px-6 py-4">
            <div class="flex justify-between items-center">
                <div class="flex items-center space-x-2">
                    <!-- 🖼️ LOGO DA EMPRESA - Substitua por sua logo -->
                    <div id="company-logo" class="w-10 h-10 bg-gradient-to-r from-blue-500 to-purple-600 rounded-lg flex items-center justify-center">
                        <!-- Opção 1: Iniciais da empresa (atual) -->
                        <span class="text-white font-bold text-xl" id="logo-initials">AF</span>
                        
                        <!-- Opção 2: Descomente para usar imagem da logo
                        <img src="SUA_LOGO_AQUI.png" alt="Logo da Empresa" class="w-8 h-8 object-contain">
                        -->
                    </div>
                    <span class="text-2xl font-bold text-gray-800" id="company-name">AutoFlow Pro</span>
                </div>
                
                <div class="hidden md:flex space-x-8">
                    <a href="#home" class="nav-link text-gray-700 hover:text-blue-600">Início</a>
                    <a href="#services" class="nav-link text-gray-700 hover:text-blue-600">Serviços</a>
                    <a href="#about" class="nav-link text-gray-700 hover:text-blue-600">Sobre</a>
                    <a href="#contact" class="nav-link text-gray-700 hover:text-blue-600">Contato</a>
                </div>
                
                <button class="bg-gradient-to-r from-blue-500 to-purple-600 text-white px-6 py-2 rounded-lg hover:shadow-lg transition-all duration-300">
                    Solicitar Proposta
                </button>
                
                <!-- Mobile menu button -->
                <button id="mobile-menu-btn" class="md:hidden text-gray-700">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
                    </svg>
                </button>
            </div>
            
            <!-- Mobile menu -->
            <div id="mobile-menu" class="hidden md:hidden mt-4 pb-4">
                <a href="#home" class="block py-2 text-gray-700 hover:text-blue-600">Início</a>
                <a href="#services" class="block py-2 text-gray-700 hover:text-blue-600">Serviços</a>
                <a href="#about" class="block py-2 text-gray-700 hover:text-blue-600">Sobre</a>
                <a href="#contact" class="block py-2 text-gray-700 hover:text-blue-600">Contato</a>
            </div>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="gradient-bg text-white pt-24 pb-16">
        <div class="container mx-auto px-6">
            <div class="flex flex-col lg:flex-row items-center">
                <div class="lg:w-1/2 mb-8 lg:mb-0 fade-in">
                    <h1 class="text-5xl lg:text-6xl font-bold mb-6 leading-tight">
                        Automatize seu <span class="text-yellow-300">Crescimento</span> Digital
                    </h1>
                    <p class="text-xl mb-8 text-gray-200">
                        Transformamos sua estratégia digital com automação inteligente e campanhas de tráfego pago que geram resultados reais para seu negócio B2B.
                    </p>
                    <div class="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4">
                        <button class="bg-yellow-400 text-gray-900 px-8 py-4 rounded-lg font-semibold hover:bg-yellow-300 transition-colors duration-300">
                            Começar Agora
                        </button>
                        <button class="border-2 border-white text-white px-8 py-4 rounded-lg font-semibold hover:bg-white hover:text-gray-900 transition-all duration-300">
                            Ver Cases de Sucesso
                        </button>
                    </div>
                </div>
                
                <div class="lg:w-1/2 lg:pl-12 fade-in">
                    <div class="bg-white/10 backdrop-blur-lg rounded-2xl p-8 border border-white/20">
                        <div class="grid grid-cols-2 gap-6">
                            <div class="text-center">
                                <div class="stats-counter text-yellow-300">300%</div>
                                <p class="text-gray-200">ROI Médio</p>
                            </div>
                            <div class="text-center">
                                <div class="stats-counter text-yellow-300">150+</div>
                                <p class="text-gray-200">Clientes Ativos</p>
                            </div>
                            <div class="text-center">
                                <div class="stats-counter text-yellow-300">2M+</div>
                                <p class="text-gray-200">Leads Gerados</p>
                            </div>
                            <div class="text-center">
                                <div class="stats-counter text-yellow-300">98%</div>
                                <p class="text-gray-200">Satisfação</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="py-20 bg-white">
        <div class="container mx-auto px-6">
            <div class="text-center mb-16 fade-in">
                <h2 class="text-4xl font-bold text-gray-800 mb-4">Nossos Serviços</h2>
                <p class="text-xl text-gray-600 max-w-3xl mx-auto">
                    Oferecemos soluções completas para acelerar o crescimento do seu negócio através de tecnologia e estratégia digital.
                </p>
            </div>
            
            <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- Service 1 -->
                <div class="card-hover bg-white rounded-xl shadow-lg p-8 border border-gray-100">
                    <div class="w-16 h-16 bg-blue-100 rounded-lg flex items-center justify-center mb-6">
                        <svg class="w-8 h-8 text-blue-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9.663 17h4.673M12 3v1m6.364 1.636l-.707.707M21 12h-1M4 12H3m3.343-5.657l-.707-.707m2.828 9.9a5 5 0 117.072 0l-.548.547A3.374 3.374 0 0014 18.469V19a2 2 0 11-4 0v-.531c0-.895-.356-1.754-.988-2.386l-.548-.547z"></path>
                        </svg>
                    </div>
                    <h3 class="text-2xl font-bold text-gray-800 mb-4">Automação de Marketing</h3>
                    <p class="text-gray-600 mb-6">
                        Criamos fluxos automatizados que nutrem seus leads e convertem prospects em clientes, 24/7.
                    </p>
                    <ul class="text-gray-600 space-y-2">
                        <li>• Email Marketing Automatizado</li>
                        <li>• Lead Scoring Inteligente</li>
                        <li>• Segmentação Avançada</li>
                        <li>• CRM Integration</li>
                    </ul>
                </div>
                
                <!-- Service 2 -->
                <div class="card-hover bg-white rounded-xl shadow-lg p-8 border border-gray-100">
                    <div class="w-16 h-16 bg-purple-100 rounded-lg flex items-center justify-center mb-6">
                        <svg class="w-8 h-8 text-purple-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7h8m0 0v8m0-8l-8 8-4-4-6 6"></path>
                        </svg>
                    </div>
                    <h3 class="text-2xl font-bold text-gray-800 mb-4">Tráfego Pago</h3>
                    <p class="text-gray-600 mb-6">
                        Campanhas otimizadas no Google Ads, Facebook e LinkedIn para maximizar seu ROI.
                    </p>
                    <ul class="text-gray-600 space-y-2">
                        <li>• Google Ads & Shopping</li>
                        <li>• Facebook & Instagram Ads</li>
                        <li>• LinkedIn Ads B2B</li>
                        <li>• Remarketing Avançado</li>
                    </ul>
                </div>
                
                <!-- Service 3 -->
                <div class="card-hover bg-white rounded-xl shadow-lg p-8 border border-gray-100">
                    <div class="w-16 h-16 bg-green-100 rounded-lg flex items-center justify-center mb-6">
                        <svg class="w-8 h-8 text-green-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z"></path>
                        </svg>
                    </div>
                    <h3 class="text-2xl font-bold text-gray-800 mb-4">Analytics & BI</h3>
                    <p class="text-gray-600 mb-6">
                        Dashboards personalizados e relatórios detalhados para tomada de decisão baseada em dados.
                    </p>
                    <ul class="text-gray-600 space-y-2">
                        <li>• Dashboards Personalizados</li>
                        <li>• Relatórios Automatizados</li>
                        <li>• Análise de Performance</li>
                        <li>• Insights Estratégicos</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-20 bg-gray-100">
        <div class="container mx-auto px-6">
            <div class="flex flex-col lg:flex-row items-center">
                <div class="lg:w-1/2 mb-12 lg:mb-0 lg:pr-12 fade-in">
                    <h2 class="text-4xl font-bold text-gray-800 mb-6">Por que escolher a AutoFlow Pro?</h2>
                    <p class="text-lg text-gray-600 mb-8">
                        Somos especialistas em transformar negócios B2B através de automação inteligente e estratégias de tráfego pago comprovadas. Nossa abordagem data-driven garante resultados mensuráveis e crescimento sustentável.
                    </p>
                    
                    <div class="space-y-6">
                        <div class="flex items-start space-x-4">
                            <div class="w-8 h-8 bg-blue-500 rounded-full flex items-center justify-center flex-shrink-0 mt-1">
                                <svg class="w-4 h-4 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                                </svg>
                            </div>
                            <div>
                                <h4 class="text-xl font-semibold text-gray-800 mb-2">Expertise Comprovada</h4>
                                <p class="text-gray-600">Mais de 5 anos de experiência com empresas B2B de diversos segmentos.</p>
                            </div>
                        </div>
                        
                        <div class="flex items-start space-x-4">
                            <div class="w-8 h-8 bg-blue-500 rounded-full flex items-center justify-center flex-shrink-0 mt-1">
                                <svg class="w-4 h-4 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                                </svg>
                            </div>
                            <div>
                                <h4 class="text-xl font-semibold text-gray-800 mb-2">Resultados Garantidos</h4>
                                <p class="text-gray-600">ROI médio de 300% e satisfação de 98% dos nossos clientes.</p>
                            </div>
                        </div>
                        
                        <div class="flex items-start space-x-4">
                            <div class="w-8 h-8 bg-blue-500 rounded-full flex items-center justify-center flex-shrink-0 mt-1">
                                <svg class="w-4 h-4 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
                                </svg>
                            </div>
                            <div>
                                <h4 class="text-xl font-semibold text-gray-800 mb-2">Suporte Dedicado</h4>
                                <p class="text-gray-600">Equipe especializada disponível para otimizar continuamente seus resultados.</p>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="lg:w-1/2 fade-in">
                    <div class="bg-white rounded-2xl shadow-xl p-8">
                        <h3 class="text-2xl font-bold text-gray-800 mb-6 text-center">Nosso Processo</h3>
                        <div class="space-y-6">
                            <div class="flex items-center space-x-4">
                                <div class="w-10 h-10 bg-blue-500 text-white rounded-full flex items-center justify-center font-bold">1</div>
                                <div>
                                    <h4 class="font-semibold text-gray-800">Análise & Estratégia</h4>
                                    <p class="text-gray-600 text-sm">Mapeamos seu negócio e definimos objetivos claros</p>
                                </div>
                            </div>
                            
                            <div class="flex items-center space-x-4">
                                <div class="w-10 h-10 bg-purple-500 text-white rounded-full flex items-center justify-center font-bold">2</div>
                                <div>
                                    <h4 class="font-semibold text-gray-800">Implementação</h4>
                                    <p class="text-gray-600 text-sm">Configuramos automações e campanhas otimizadas</p>
                                </div>
                            </div>
                            
                            <div class="flex items-center space-x-4">
                                <div class="w-10 h-10 bg-green-500 text-white rounded-full flex items-center justify-center font-bold">3</div>
                                <div>
                                    <h4 class="font-semibold text-gray-800">Otimização</h4>
                                    <p class="text-gray-600 text-sm">Monitoramos e ajustamos para máxima performance</p>
                                </div>
                            </div>
                            
                            <div class="flex items-center space-x-4">
                                <div class="w-10 h-10 bg-yellow-500 text-white rounded-full flex items-center justify-center font-bold">4</div>
                                <div>
                                    <h4 class="font-semibold text-gray-800">Crescimento</h4>
                                    <p class="text-gray-600 text-sm">Escalamos resultados e expandimos estratégias</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="py-20 bg-white">
        <div class="container mx-auto px-6">
            <div class="text-center mb-16 fade-in">
                <h2 class="text-4xl font-bold text-gray-800 mb-4">Vamos Conversar?</h2>
                <p class="text-xl text-gray-600 max-w-3xl mx-auto">
                    Pronto para acelerar o crescimento do seu negócio? Entre em contato conosco e descubra como podemos ajudar.
                </p>
            </div>
            
            <div class="max-w-4xl mx-auto">
                <div class="grid md:grid-cols-2 gap-12">
                    <!-- Contact Form -->
                    <div class="fade-in">
                        <form id="contact-form" class="space-y-6">
                            <div>
                                <label class="block text-gray-700 font-semibold mb-2">Nome Completo</label>
                                <input type="text" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent" placeholder="Seu nome completo">
                            </div>
                            
                            <div>
                                <label class="block text-gray-700 font-semibold mb-2">Email Corporativo</label>
                                <input type="email" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent" placeholder="seu@empresa.com">
                            </div>
                            
                            <div>
                                <label class="block text-gray-700 font-semibold mb-2">Empresa</label>
                                <input type="text" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent" placeholder="Nome da sua empresa">
                            </div>
                            
                            <div>
                                <label class="block text-gray-700 font-semibold mb-2">Telefone</label>
                                <input type="tel" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent" placeholder="(11) 99999-9999">
                            </div>
                            
                            <div>
                                <label class="block text-gray-700 font-semibold mb-2">Como podemos ajudar?</label>
                                <textarea rows="4" class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent" placeholder="Conte-nos sobre seus desafios e objetivos..."></textarea>
                            </div>
                            
                            <button type="submit" class="w-full bg-gradient-to-r from-blue-500 to-purple-600 text-white py-4 rounded-lg font-semibold hover:shadow-lg transition-all duration-300">
                                Solicitar Proposta Gratuita
                            </button>
                        </form>
                    </div>
                    
                    <!-- Contact Info -->
                    <div class="fade-in">
                        <div class="bg-gradient-to-br from-blue-500 to-purple-600 text-white rounded-2xl p-8">
                            <h3 class="text-2xl font-bold mb-6">Informações de Contato</h3>
                            
                            <div class="space-y-6">
                                <div class="flex items-center space-x-4">
                                    <div class="w-10 h-10 bg-white/20 rounded-lg flex items-center justify-center">
                                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 4.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path>
                                        </svg>
                                    </div>
                                    <div>
                                        <p class="font-semibold">Email</p>
                                        <p class="text-blue-100" data-contact="email">contato@autoflowpro.com</p>
                                    </div>
                                </div>
                                
                                <div class="flex items-center space-x-4">
                                    <div class="w-10 h-10 bg-white/20 rounded-lg flex items-center justify-center">
                                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z"></path>
                                        </svg>
                                    </div>
                                    <div>
                                        <p class="font-semibold">Telefone</p>
                                        <p class="text-blue-100" data-contact="phone">(11) 3000-0000</p>
                                    </div>
                                </div>
                                
                                <div class="flex items-center space-x-4">
                                    <div class="w-10 h-10 bg-white/20 rounded-lg flex items-center justify-center">
                                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path>
                                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path>
                                        </svg>
                                    </div>
                                    <div>
                                        <p class="font-semibold">Endereço</p>
                                        <p class="text-blue-100" data-contact="address">São Paulo, SP - Brasil</p>
                                    </div>
                                </div>
                            </div>
                            
                            <div class="mt-8 pt-8 border-t border-white/20">
                                <p class="text-blue-100 mb-4">Siga-nos nas redes sociais:</p>
                                <div class="flex space-x-4">
                                    <a href="#" class="w-10 h-10 bg-white/20 rounded-lg flex items-center justify-center hover:bg-white/30 transition-colors">
                                        <span class="text-sm font-bold">Li</span>
                                    </a>
                                    <a href="#" class="w-10 h-10 bg-white/20 rounded-lg flex items-center justify-center hover:bg-white/30 transition-colors">
                                        <span class="text-sm font-bold">Ig</span>
                                    </a>
                                    <a href="#" class="w-10 h-10 bg-white/20 rounded-lg flex items-center justify-center hover:bg-white/30 transition-colors">
                                        <span class="text-sm font-bold">Fb</span>
                                    </a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer class="bg-gray-900 text-white py-12">
        <div class="container mx-auto px-6">
            <div class="grid md:grid-cols-4 gap-8">
                <div>
                    <div class="flex items-center space-x-2 mb-4">
                        <!-- 🖼️ LOGO NO FOOTER - Mesma configuração do header -->
                        <div class="w-8 h-8 bg-gradient-to-r from-blue-500 to-purple-600 rounded-lg flex items-center justify-center">
                            <span class="text-white font-bold" id="footer-logo-initials">AF</span>
                        </div>
                        <span class="text-xl font-bold" id="footer-company-name">AutoFlow Pro</span>
                    </div>
                    <p class="text-gray-400">
                        Transformando negócios B2B através de automação inteligente e tráfego pago estratégico.
                    </p>
                </div>
                
                <div>
                    <h4 class="text-lg font-semibold mb-4">Serviços</h4>
                    <ul class="space-y-2 text-gray-400">
                        <li><a href="#" class="hover:text-white transition-colors">Automação de Marketing</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Tráfego Pago</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Analytics & BI</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Consultoria Digital</a></li>
                    </ul>
                </div>
                
                <div>
                    <h4 class="text-lg font-semibold mb-4">Empresa</h4>
                    <ul class="space-y-2 text-gray-400">
                        <li><a href="#" class="hover:text-white transition-colors">Sobre Nós</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Cases de Sucesso</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Blog</a></li>
                        <li><a href="#" class="hover:text-white transition-colors">Carreiras</a></li>
                    </ul>
                </div>
                
                <div>
                    <h4 class="text-lg font-semibold mb-4">Contato</h4>
                    <ul class="space-y-2 text-gray-400">
                        <li data-contact="email">contato@autoflowpro.com</li>
                        <li data-contact="phone">(11) 3000-0000</li>
                        <li data-contact="address">São Paulo, SP</li>
                    </ul>
                </div>
            </div>
            
            <div class="border-t border-gray-800 mt-8 pt-8 text-center text-gray-400">
                <p>&copy; 2024 AutoFlow Pro. Todos os direitos reservados.</p>
            </div>
        </div>
    </footer>

    <script>
        /* ========================================
           📝 CONFIGURAÇÕES DE TEXTO EDITÁVEIS
           Edite os textos do seu site aqui
        ======================================== */
        
        const SITE_CONFIG = {
            // INFORMAÇÕES DA EMPRESA
            company: {
                name: "AutoFlow Pro",
                initials: "AF",
                tagline: "Automação e Tráfego Pago",
                description: "Transformando negócios B2B através de automação inteligente e tráfego pago estratégico."
            },
            
            // HERO SECTION
            hero: {
                title: "Automatize seu",
                titleHighlight: "Crescimento",
                titleEnd: "Digital",
                subtitle: "Transformamos sua estratégia digital com automação inteligente e campanhas de tráfego pago que geram resultados reais para seu negócio B2B.",
                ctaPrimary: "Começar Agora",
                ctaSecondary: "Ver Cases de Sucesso"
            },
            
            // ESTATÍSTICAS
            stats: {
                roi: { value: "300%", label: "ROI Médio" },
                clients: { value: "150+", label: "Clientes Ativos" },
                leads: { value: "2M+", label: "Leads Gerados" },
                satisfaction: { value: "98%", label: "Satisfação" }
            },
            
            // CONTATO
            contact: {
                email: "contato@autoflowpro.com",
                phone: "(11) 3000-0000",
                address: "São Paulo, SP - Brasil",
                whatsapp: "5511999999999" // Apenas números
            },
            
            // REDES SOCIAIS
            social: {
                linkedin: "https://linkedin.com/company/sua-empresa",
                instagram: "https://instagram.com/sua-empresa",
                facebook: "https://facebook.com/sua-empresa"
            }
        };
        
        // APLICAR CONFIGURAÇÕES AO CARREGAR A PÁGINA
        document.addEventListener('DOMContentLoaded', function() {
            // Aplicar nome da empresa
            document.getElementById('company-name').textContent = SITE_CONFIG.company.name;
            document.getElementById('logo-initials').textContent = SITE_CONFIG.company.initials;
            document.getElementById('footer-company-name').textContent = SITE_CONFIG.company.name;
            document.getElementById('footer-logo-initials').textContent = SITE_CONFIG.company.initials;
            document.title = `${SITE_CONFIG.company.name} - ${SITE_CONFIG.company.tagline}`;
            
            // Aplicar textos do hero
            const heroTitle = document.querySelector('#home h1');
            if (heroTitle) {
                heroTitle.innerHTML = `${SITE_CONFIG.hero.title} <span class="text-yellow-300">${SITE_CONFIG.hero.titleHighlight}</span> ${SITE_CONFIG.hero.titleEnd}`;
            }
            
            const heroSubtitle = document.querySelector('#home p');
            if (heroSubtitle) {
                heroSubtitle.textContent = SITE_CONFIG.hero.subtitle;
            }
            
            // Aplicar informações de contato
            const contactElements = document.querySelectorAll('[data-contact="email"]');
            contactElements.forEach(el => el.textContent = SITE_CONFIG.contact.email);
            
            const phoneElements = document.querySelectorAll('[data-contact="phone"]');
            phoneElements.forEach(el => el.textContent = SITE_CONFIG.contact.phone);
            
            const addressElements = document.querySelectorAll('[data-contact="address"]');
            addressElements.forEach(el => el.textContent = SITE_CONFIG.contact.address);
        });
        
        /* ========================================
           🎨 FUNÇÃO PARA TROCAR CORES DA MARCA
           Use esta função para alterar as cores
        ======================================== */
        
        function updateBrandColors(primary, secondary, accent) {
            const root = document.documentElement;
            root.style.setProperty('--primary-color', primary);
            root.style.setProperty('--secondary-color', secondary);
            root.style.setProperty('--accent-color', accent);
        }
        
        // EXEMPLOS DE PALETAS DE CORES PRÉ-DEFINIDAS
        const COLOR_PALETTES = {
            blue: {
                primary: '#667eea',
                secondary: '#764ba2',
                accent: '#fbbf24'
            },
            green: {
                primary: '#10b981',
                secondary: '#059669',
                accent: '#f59e0b'
            },
            purple: {
                primary: '#8b5cf6',
                secondary: '#7c3aed',
                accent: '#06b6d4'
            },
            red: {
                primary: '#ef4444',
                secondary: '#dc2626',
                accent: '#f97316'
            }
        };
        
        // Para trocar a paleta, descomente uma das linhas abaixo:
        // updateBrandColors(COLOR_PALETTES.green.primary, COLOR_PALETTES.green.secondary, COLOR_PALETTES.green.accent);
        // updateBrandColors(COLOR_PALETTES.purple.primary, COLOR_PALETTES.purple.secondary, COLOR_PALETTES.purple.accent);
        // updateBrandColors(COLOR_PALETTES.red.primary, COLOR_PALETTES.red.secondary, COLOR_PALETTES.red.accent);
        
        // Mobile menu toggle
        document.getElementById('mobile-menu-btn').addEventListener('click', function() {
            const mobileMenu = document.getElementById('mobile-menu');
            mobileMenu.classList.toggle('hidden');
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        // Form submission
        document.getElementById('contact-form').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Get form data
            const formData = new FormData(this);
            const formObject = {};
            formData.forEach((value, key) => {
                formObject[key] = value;
            });
            
            // Show success message
            alert('Obrigado pelo seu interesse! Entraremos em contato em breve.');
            
            // Reset form
            this.reset();
        });

        // Fade in animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animationDelay = '0.2s';
                    entry.target.classList.add('fade-in');
                }
            });
        }, observerOptions);

        // Observe all sections for animation
        document.querySelectorAll('section > div').forEach(section => {
            observer.observe(section);
        });

        // Counter animation for stats
        function animateCounters() {
            const counters = document.querySelectorAll('.stats-counter');
            counters.forEach(counter => {
                const target = counter.textContent;
                const isPercentage = target.includes('%');
                const isPlus = target.includes('+');
                const numericValue = parseInt(target.replace(/[^\d]/g, ''));
                
                let current = 0;
                const increment = numericValue / 50;
                
                const timer = setInterval(() => {
                    current += increment;
                    if (current >= numericValue) {
                        current = numericValue;
                        clearInterval(timer);
                    }
                    
                    let displayValue = Math.floor(current);
                    if (isPercentage) displayValue += '%';
                    if (isPlus) displayValue += '+';
                    if (target.includes('M')) displayValue = (displayValue / 1000000).toFixed(1) + 'M+';
                    
                    counter.textContent = displayValue;
                }, 50);
            });
        }

        // Trigger counter animation when hero section is visible
        const heroObserver = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    animateCounters();
                    heroObserver.unobserve(entry.target);
                }
            });
        });

        heroObserver.observe(document.querySelector('#home'));
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'986dc88875643559',t:'MTc1OTE3MzA1NS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
