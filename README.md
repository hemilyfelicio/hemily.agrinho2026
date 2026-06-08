<!doctype html>
<html lang="pt-BR" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="agrinho" content="Agro forte, futuro sustentável: equilíbrio entre produção e meio ambiente">
  <meta name="description" content="Projeto Agrinho 2025 - Subcategoria Programação Front-End. Site educativo sobre sustentabilidade agrícola, produção responsável e preservação ambiental.">
  <meta name="keywords" content="agrinho, agricultura sustentável, agro, meio ambiente, produção responsável">
  <meta name="author" content="Estudante Ensino Médio - Projeto Agrinho 2025">
  <title>Agro Forte, Futuro Sustentável - Projeto Agrinho 2025</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <script src="https://cdn.jsdelivr.net/npm/lucide@0.263.0/dist/umd/lucide.min.js"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&amp;family=Source+Sans+3:wght@300;400;600;700&amp;display=swap" rel="stylesheet">
  <style>
    html, body { height: 100%; margin: 0; }
    body { font-family: 'Source Sans 3', sans-serif; }
    h1, h2, h3, .heading-font { font-family: 'Playfair Display', serif; }
    
    .hero-bg {
      background: linear-gradient(135deg, #1a472a 0%, #2d5a3f 30%, #3a7d54 60%, #1a472a 100%);
      position: relative;
      overflow: hidden;
    }
    .hero-bg::before {
      content: '';
      position: absolute;
      inset: 0;
      background: radial-gradient(circle at 20% 80%, rgba(76, 175, 80, 0.3) 0%, transparent 50%),
                  radial-gradient(circle at 80% 20%, rgba(139, 195, 74, 0.2) 0%, transparent 40%);
    }
    
    .leaf-pattern {
      position: absolute;
      width: 100%;
      height: 100%;
      opacity: 0.05;
      background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='80' height='80' viewBox='0 0 80 80'%3E%3Cpath d='M40 10 C20 20 10 40 40 70 C70 40 60 20 40 10Z' fill='white'/%3E%3C/svg%3E");
    }

    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    @keyframes scaleIn {
      from { opacity: 0; transform: scale(0.8); }
      to { opacity: 1; transform: scale(1); }
    }
    @keyframes float {
      0%, 100% { transform: translateY(0); }
      50% { transform: translateY(-10px); }
    }
    
    .animate-fade-up { animation: fadeUp 0.8s ease-out forwards; opacity: 0; }
    .animate-fade-in { animation: fadeIn 1s ease-out forwards; opacity: 0; }
    .animate-scale-in { animation: scaleIn 0.6s ease-out forwards; opacity: 0; }
    .animate-float { animation: float 3s ease-in-out infinite; }
    
    .delay-1 { animation-delay: 0.2s; }
    .delay-2 { animation-delay: 0.4s; }
    .delay-3 { animation-delay: 0.6s; }
    .delay-4 { animation-delay: 0.8s; }
    .delay-5 { animation-delay: 1s; }

    .card-hover {
      transition: transform 0.3s ease, box-shadow 0.3s ease;
    }
    .card-hover:hover {
      transform: translateY(-8px);
      box-shadow: 0 20px 40px rgba(0,0,0,0.15);
    }

    .nav-link {
      position: relative;
      transition: color 0.3s;
    }
    .nav-link::after {
      content: '';
      position: absolute;
      bottom: -4px;
      left: 0;
      width: 0;
      height: 2px;
      background: #4CAF50;
      transition: width 0.3s;
    }
    .nav-link:hover::after { width: 100%; }

    .progress-bar {
      background: linear-gradient(90deg, #4CAF50, #8BC34A);
      transition: width 1.5s ease-out;
    }

    .section-divider {
      height: 4px;
      background: linear-gradient(90deg, transparent, #4CAF50, #8BC34A, transparent);
    }

    .quiz-option {
      transition: all 0.3s ease;
      border: 2px solid #e5e7eb;
    }
    .quiz-option:hover { border-color: #4CAF50; background: #f0fdf4; }
    .quiz-option.correct { border-color: #16a34a; background: #dcfce7; }
    .quiz-option.wrong { border-color: #dc2626; background: #fef2f2; }

    .counter-num {
      font-size: 2.5rem;
      font-weight: 900;
      background: linear-gradient(135deg, #2d5a3f, #4CAF50);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
    }

    .scroll-indicator {
      position: fixed;
      top: 0;
      left: 0;
      height: 3px;
      background: linear-gradient(90deg, #4CAF50, #8BC34A);
      z-index: 1000;
      transition: width 0.1s;
    }

    @media (max-width: 768px) {
      .counter-num { font-size: 1.8rem; }
      .mobile-menu { display: none; }
      .mobile-menu.active { display: flex; }
    }
  </style>
  <style>body { box-sizing: border-box; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
 <script src="/_sdk/telemetry_sdk.js"></script></head>
 <body class="h-full bg-stone-50 text-stone-800 overflow-auto">
  <!-- Scroll Progress -->
  <div class="scroll-indicator" id="scrollIndicator"></div><!-- Navigation -->
  <nav class="fixed top-0 w-full z-50 bg-white/95 backdrop-blur-sm shadow-sm" id="navbar">
   <div class="max-w-7xl mx-auto px-4 py-3 flex items-center justify-between">
    <a href="#inicio" class="flex items-center gap-2">
     <svg width="36" height="36" viewbox="0 0 36 36">
      <circle cx="18" cy="18" r="16" fill="#2d5a3f" /> <path d="M18 8 C12 14 10 20 18 28 C26 20 24 14 18 8Z" fill="#8BC34A" /> <path d="M18 12 C15 16 14 20 18 26" stroke="white" stroke-width="1.5" fill="none" />
     </svg><span class="heading-font font-bold text-lg text-green-900">AgroForte</span> </a> <button id="menuToggle" class="md:hidden p-2 rounded-lg hover:bg-green-50"> <i data-lucide="menu" class="w-6 h-6 text-green-800"></i> </button>
    <div class="hidden md:flex items-center gap-6" id="desktopMenu">
     <a href="#inicio" class="nav-link text-stone-700 font-medium">Início</a> <a href="#sobre" class="nav-link text-stone-700 font-medium">Sobre</a> <a href="#pilares" class="nav-link text-stone-700 font-medium">Pilares</a> <a href="#dados" class="nav-link text-stone-700 font-medium">Dados</a> <a href="#quiz" class="nav-link text-stone-700 font-medium">Quiz</a> <a href="#contato" class="nav-link text-stone-700 font-medium">Contato</a>
    </div>
    <div class="mobile-menu fixed inset-0 top-14 bg-white flex-col items-center gap-6 pt-10 md:hidden z-50" id="mobileMenu">
     <a href="#inicio" class="text-xl text-stone-700 font-medium" onclick="closeMobile()">Início</a> <a href="#sobre" class="text-xl text-stone-700 font-medium" onclick="closeMobile()">Sobre</a> <a href="#pilares" class="text-xl text-stone-700 font-medium" onclick="closeMobile()">Pilares</a> <a href="#dados" class="text-xl text-stone-700 font-medium" onclick="closeMobile()">Dados</a> <a href="#quiz" class="text-xl text-stone-700 font-medium" onclick="closeMobile()">Quiz</a> <a href="#contato" class="text-xl text-stone-700 font-medium" onclick="closeMobile()">Contato</a>
    </div>
   </div>
  </nav><!-- Hero Section -->
  <header id="inicio" class="hero-bg min-h-[600px] flex items-center justify-center relative pt-16">
   <div class="leaf-pattern"></div>
   <div class="relative z-10 text-center px-4 max-w-4xl mx-auto py-20">
    <p class="text-green-200 text-sm uppercase tracking-[0.3em] mb-4 animate-fade-in">Projeto Agrinho 2025</p>
    <h1 class="text-4xl md:text-6xl lg:text-7xl font-900 text-white leading-tight mb-6 animate-fade-up" id="heroTitle">Agro Forte,<br><span class="text-green-300">Futuro Sustentável</span></h1>
    <p class="text-lg md:text-xl text-green-100/90 max-w-2xl mx-auto mb-10 animate-fade-up delay-1">Equilíbrio entre produção e meio ambiente: o caminho para alimentar o mundo sem destruir o planeta.</p><a href="#sobre" class="inline-flex items-center gap-2 bg-green-500 hover:bg-green-400 text-white font-semibold px-8 py-4 rounded-full transition-all animate-fade-up delay-2 shadow-lg shadow-green-900/30"> Explorar <i data-lucide="arrow-down" class="w-5 h-5"></i> </a>
    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 animate-float">
     <i data-lucide="chevrons-down" class="w-8 h-8 text-green-300/60"></i>
    </div>
   </div>
  </header><!-- Sobre Section -->
  <section id="sobre" class="py-20 px-4">
   <div class="max-w-6xl mx-auto">
    <div class="text-center mb-16">
     <span class="text-green-600 font-semibold text-sm uppercase tracking-wider">Sobre o Tema</span>
     <h2 class="text-3xl md:text-5xl font-bold text-green-900 mt-2 mb-4">Produção &amp; Preservação</h2>
     <div class="section-divider w-24 mx-auto rounded-full"></div>
    </div>
    <div class="grid md:grid-cols-2 gap-12 items-center">
     <div class="space-y-6">
      <p class="text-lg text-stone-600 leading-relaxed">O Brasil é um dos maiores produtores agrícolas do mundo, alimentando milhões de pessoas. Porém, esse crescimento precisa caminhar junto com a <strong class="text-green-700">preservação ambiental</strong>.</p>
      <p class="text-lg text-stone-600 leading-relaxed">A agricultura sustentável busca o equilíbrio: produzir alimentos em quantidade suficiente, com qualidade, ao mesmo tempo em que conserva os recursos naturais para as futuras gerações.</p>
      <p class="text-lg text-stone-600 leading-relaxed">Tecnologias como agricultura de precisão, manejo integrado de pragas e sistemas agroflorestais mostram que é possível ser <strong class="text-green-700">produtivo e sustentável</strong>.</p>
     </div>
     <div class="relative">
      <div class="bg-gradient-to-br from-green-100 to-emerald-50 rounded-3xl p-8 shadow-xl">
       <svg viewbox="0 0 300 250" class="w-full">
        <rect x="0" y="200" width="300" height="50" fill="#8B6914" rx="4" /> <rect x="0" y="180" width="300" height="25" fill="#5d8a3c" rx="4" /> <circle cx="60" cy="120" r="40" fill="#2d8a4e" /> <circle cx="45" cy="105" r="30" fill="#3da85c" /> <circle cx="75" cy="110" r="35" fill="#34a853" /> <rect x="57" y="155" width="6" height="30" fill="#6b4513" /> <circle cx="180" cy="100" r="50" fill="#2d8a4e" /> <circle cx="160" cy="85" r="38" fill="#3da85c" /> <circle cx="200" cy="90" r="42" fill="#34a853" /> <rect x="177" y="145" width="7" height="40" fill="#6b4513" /> <circle cx="260" cy="140" r="30" fill="#4CAF50" /> <circle cx="248" cy="128" r="22" fill="#66BB6A" /> <rect x="257" y="165" width="5" height="20" fill="#6b4513" /> <circle cx="150" cy="40" r="25" fill="#FFD54F" /> <line x1="150" y1="70" x2="150" y2="85" stroke="#FFD54F" stroke-width="2" /> <line x1="125" y1="45" x2="115" y2="42" stroke="#FFD54F" stroke-width="2" /> <line x1="175" y1="45" x2="185" y2="42" stroke="#FFD54F" stroke-width="2" /> <path d="M20 195 Q40 185 60 195 Q80 185 100 195 Q120 185 140 195" stroke="#4CAF50" stroke-width="2" fill="none" /> <path d="M160 195 Q180 185 200 195 Q220 185 240 195 Q260 185 280 195" stroke="#4CAF50" stroke-width="2" fill="none" /> <!-- Tractor --> <rect x="100" y="185" width="40" height="18" fill="#E53935" rx="3" /> <circle cx="110" cy="207" r="8" fill="#333" /> <circle cx="132" cy="207" r="10" fill="#333" /> <rect x="135" y="188" width="12" height="10" fill="#FFCDD2" rx="2" />
       </svg>
      </div>
     </div>
    </div>
   </div>
  </section><!-- Pilares Section -->
  <section id="pilares" class="py-20 px-4 bg-gradient-to-b from-green-50 to-stone-50">
   <div class="max-w-6xl mx-auto">
    <div class="text-center mb-16">
     <span class="text-green-600 font-semibold text-sm uppercase tracking-wider">Fundamentos</span>
     <h2 class="text-3xl md:text-5xl font-bold text-green-900 mt-2 mb-4">Pilares da Sustentabilidade</h2>
     <div class="section-divider w-24 mx-auto rounded-full"></div>
    </div>
    <div class="grid md:grid-cols-3 gap-8">
     <!-- Card 1 -->
     <div class="card-hover bg-white rounded-2xl p-8 shadow-md border border-green-100 animate-scale-in delay-1" data-animate>
      <div class="w-14 h-14 bg-green-100 rounded-xl flex items-center justify-center mb-5">
       <i data-lucide="sprout" class="w-7 h-7 text-green-600"></i>
      </div>
      <h3 class="text-xl font-bold text-green-900 mb-3">Agricultura de Precisão</h3>
      <p class="text-stone-600 leading-relaxed">Uso de tecnologia (GPS, drones, sensores) para aplicar insumos na quantidade certa, no local certo, reduzindo desperdício e impacto ambiental.</p>
     </div><!-- Card 2 -->
     <div class="card-hover bg-white rounded-2xl p-8 shadow-md border border-green-100 animate-scale-in delay-2" data-animate>
      <div class="w-14 h-14 bg-emerald-100 rounded-xl flex items-center justify-center mb-5">
       <i data-lucide="trees" class="w-7 h-7 text-emerald-600"></i>
      </div>
      <h3 class="text-xl font-bold text-green-900 mb-3">Sistemas Agroflorestais</h3>
      <p class="text-stone-600 leading-relaxed">Combinação de árvores com cultivos agrícolas, promovendo biodiversidade, proteção do solo e captura de carbono enquanto se produz alimentos.</p>
     </div><!-- Card 3 -->
     <div class="card-hover bg-white rounded-2xl p-8 shadow-md border border-green-100 animate-scale-in delay-3" data-animate>
      <div class="w-14 h-14 bg-lime-100 rounded-xl flex items-center justify-center mb-5">
       <i data-lucide="droplets" class="w-7 h-7 text-lime-600"></i>
      </div>
      <h3 class="text-xl font-bold text-green-900 mb-3">Manejo de Recursos Hídricos</h3>
      <p class="text-stone-600 leading-relaxed">Irrigação por gotejamento, reúso de água e proteção de nascentes garantem produtividade sem esgotar os mananciais disponíveis.</p>
     </div><!-- Card 4 -->
     <div class="card-hover bg-white rounded-2xl p-8 shadow-md border border-green-100 animate-scale-in delay-3" data-animate>
      <div class="w-14 h-14 bg-yellow-100 rounded-xl flex items-center justify-center mb-5">
       <i data-lucide="sun" class="w-7 h-7 text-yellow-600"></i>
      </div>
      <h3 class="text-xl font-bold text-green-900 mb-3">Energias Renováveis</h3>
      <p class="text-stone-600 leading-relaxed">Energia solar e biomassa no campo reduzem custos e a pegada de carbono da produção agrícola brasileira.</p>
     </div><!-- Card 5 -->
     <div class="card-hover bg-white rounded-2xl p-8 shadow-md border border-green-100 animate-scale-in delay-4" data-animate>
      <div class="w-14 h-14 bg-teal-100 rounded-xl flex items-center justify-center mb-5">
       <i data-lucide="recycle" class="w-7 h-7 text-teal-600"></i>
      </div>
      <h3 class="text-xl font-bold text-green-900 mb-3">Economia Circular</h3>
      <p class="text-stone-600 leading-relaxed">Resíduos agrícolas viram adubo orgânico, ração ou energia, eliminando o conceito de "lixo" na cadeia produtiva.</p>
     </div><!-- Card 6 -->
     <div class="card-hover bg-white rounded-2xl p-8 shadow-md border border-green-100 animate-scale-in delay-5" data-animate>
      <div class="w-14 h-14 bg-cyan-100 rounded-xl flex items-center justify-center mb-5">
       <i data-lucide="shield-check" class="w-7 h-7 text-cyan-600"></i>
      </div>
      <h3 class="text-xl font-bold text-green-900 mb-3">Manejo Integrado de Pragas</h3>
      <p class="text-stone-600 leading-relaxed">Controle biológico e rotação de culturas reduzem uso de agrotóxicos, protegendo polinizadores e a saúde humana.</p>
     </div>
    </div>
   </div>
  </section><!-- Dados / Counters Section -->
  <section id="dados" class="py-20 px-4 bg-white">
   <div class="max-w-6xl mx-auto">
    <div class="text-center mb-16">
     <span class="text-green-600 font-semibold text-sm uppercase tracking-wider">Números</span>
     <h2 class="text-3xl md:text-5xl font-bold text-green-900 mt-2 mb-4">O Agro em Dados</h2>
     <div class="section-divider w-24 mx-auto rounded-full"></div>
    </div>
    <div class="grid grid-cols-2 md:grid-cols-4 gap-8 mb-16">
     <div class="text-center" data-counter data-target="27">
      <div class="counter-num">
       0
      </div>
      <p class="text-stone-600 mt-1 text-sm font-medium">% do PIB brasileiro</p>
     </div>
     <div class="text-center" data-counter data-target="800">
      <div class="counter-num">
       0
      </div>
      <p class="text-stone-600 mt-1 text-sm font-medium">milhões de pessoas alimentadas</p>
     </div>
     <div class="text-center" data-counter data-target="66">
      <div class="counter-num">
       0
      </div>
      <p class="text-stone-600 mt-1 text-sm font-medium">% de vegetação nativa preservada</p>
     </div>
     <div class="text-center" data-counter data-target="40">
      <div class="counter-num">
       0
      </div>
      <p class="text-stone-600 mt-1 text-sm font-medium">% da energia é renovável no campo</p>
     </div>
    </div><!-- Progress bars -->
    <div class="max-w-3xl mx-auto space-y-6">
     <h3 class="text-xl font-bold text-green-900 mb-4">Avanços na Sustentabilidade Agrícola</h3>
     <div>
      <div class="flex justify-between mb-1">
       <span class="text-sm font-medium text-stone-700">Redução do desmatamento (últimos 10 anos)</span> <span class="text-sm font-semibold text-green-700">72%</span>
      </div>
      <div class="w-full bg-gray-200 rounded-full h-3">
       <div class="progress-bar h-3 rounded-full" data-progress="72" style="width:0%"></div>
      </div>
     </div>
     <div>
      <div class="flex justify-between mb-1">
       <span class="text-sm font-medium text-stone-700">Área com plantio direto</span> <span class="text-sm font-semibold text-green-700">85%</span>
      </div>
      <div class="w-full bg-gray-200 rounded-full h-3">
       <div class="progress-bar h-3 rounded-full" data-progress="85" style="width:0%"></div>
      </div>
     </div>
     <div>
      <div class="flex justify-between mb-1">
       <span class="text-sm font-medium text-stone-700">Produtores com práticas sustentáveis</span> <span class="text-sm font-semibold text-green-700">58%</span>
      </div>
      <div class="w-full bg-gray-200 rounded-full h-3">
       <div class="progress-bar h-3 rounded-full" data-progress="58" style="width:0%"></div>
      </div>
     </div>
    </div>
   </div>
  </section><!-- Quiz Section -->
  <section id="quiz" class="py-20 px-4 bg-gradient-to-b from-stone-50 to-green-50">
   <div class="max-w-3xl mx-auto">
    <div class="text-center mb-12">
     <span class="text-green-600 font-semibold text-sm uppercase tracking-wider">Interativo</span>
     <h2 class="text-3xl md:text-5xl font-bold text-green-900 mt-2 mb-4">Quiz Sustentável</h2>
     <div class="section-divider w-24 mx-auto rounded-full mb-4"></div>
     <p class="text-stone-600">Teste seus conhecimentos sobre agro e sustentabilidade!</p>
    </div>
    <div id="quizContainer" class="bg-white rounded-2xl p-8 shadow-lg border border-green-100">
     <div id="quizContent"></div>
    </div>
   </div>
  </section><!-- Contato Section -->
  <section id="contato" class="py-20 px-4 bg-white">
   <div class="max-w-4xl mx-auto">
    <div class="text-center mb-12">
     <span class="text-green-600 font-semibold text-sm uppercase tracking-wider">Participe</span>
     <h2 class="text-3xl md:text-5xl font-bold text-green-900 mt-2 mb-4">Deixe sua Mensagem</h2>
     <div class="section-divider w-24 mx-auto rounded-full"></div>
    </div>
    <form id="contactForm" class="max-w-xl mx-auto space-y-5">
     <div>
      <label for="nome" class="block text-sm font-medium text-stone-700 mb-1">Nome</label> <input type="text" id="nome" placeholder="Seu nome completo" class="w-full px-4 py-3 border border-gray-300 rounded-xl focus:ring-2 focus:ring-green-500 focus:border-green-500 outline-none transition" required>
     </div>
     <div>
      <label for="email" class="block text-sm font-medium text-stone-700 mb-1">E-mail</label> <input type="email" id="email" placeholder="seu@email.com" class="w-full px-4 py-3 border border-gray-300 rounded-xl focus:ring-2 focus:ring-green-500 focus:border-green-500 outline-none transition" required>
     </div>
     <div>
      <label for="mensagem" class="block text-sm font-medium text-stone-700 mb-1">Mensagem</label> <textarea id="mensagem" rows="4" placeholder="Sua ideia para um futuro mais sustentável..." class="w-full px-4 py-3 border border-gray-300 rounded-xl focus:ring-2 focus:ring-green-500 focus:border-green-500 outline-none transition resize-none" required></textarea>
     </div><button type="submit" class="w-full bg-green-600 hover:bg-green-700 text-white font-semibold py-3 rounded-xl transition-colors flex items-center justify-center gap-2"> <i data-lucide="send" class="w-5 h-5"></i> Enviar Mensagem </button>
     <div id="formSuccess" class="hidden text-center py-4 bg-green-50 rounded-xl border border-green-200">
      <i data-lucide="check-circle" class="w-8 h-8 text-green-600 mx-auto mb-2"></i>
      <p class="text-green-700 font-semibold">Mensagem enviada com sucesso!</p>
     </div>
    </form>
   </div>
  </section><!-- Footer -->
  <footer class="bg-green-900 text-green-100 py-12 px-4">
   <div class="max-w-6xl mx-auto">
    <div class="grid md:grid-cols-3 gap-8 mb-8">
     <div>
      <div class="flex items-center gap-2 mb-4">
       <svg width="30" height="30" viewbox="0 0 36 36">
        <circle cx="18" cy="18" r="16" fill="#4CAF50" /> <path d="M18 8 C12 14 10 20 18 28 C26 20 24 14 18 8Z" fill="white" />
       </svg><span class="heading-font font-bold text-lg">AgroForte</span>
      </div>
      <p class="text-green-300 text-sm leading-relaxed">Agro forte, futuro sustentável: equilíbrio entre produção e meio ambiente.</p>
     </div>
     <div>
      <h4 class="font-semibold text-white mb-3">Links Rápidos</h4>
      <nav class="space-y-2">
       <a href="#inicio" class="block text-green-300 hover:text-white transition text-sm">Início</a> <a href="#sobre" class="block text-green-300 hover:text-white transition text-sm">Sobre</a> <a href="#pilares" class="block text-green-300 hover:text-white transition text-sm">Pilares</a> <a href="#quiz" class="block text-green-300 hover:text-white transition text-sm">Quiz</a>
      </nav>
     </div>
     <div>
      <h4 class="font-semibold text-white mb-3">Projeto Agrinho 2025</h4>
      <p class="text-green-300 text-sm leading-relaxed">Subcategoria: Programação Front-End (HTML, CSS e JavaScript)</p>
      <p class="text-green-300 text-sm mt-2">Tag: <code class="bg-green-800 px-2 py-0.5 rounded text-green-200">#agrinho</code></p><a href="https://github.com" target="_blank" rel="noopener noreferrer" class="inline-flex items-center gap-1 mt-3 text-green-300 hover:text-white transition text-sm"> <i data-lucide="github" class="w-4 h-4"></i> Ver no GitHub </a>
     </div>
    </div>
    <div class="border-t border-green-800 pt-6 text-center">
     <p class="text-green-400 text-sm">© 2025 Projeto Agrinho — Agro Forte, Futuro Sustentável</p>
     <p class="text-green-500 text-xs mt-2">Desenvolvido por estudante do Ensino Médio | Educação Digital e Computação</p>
     <p class="text-green-500 text-xs mt-1">Repositório: <a href="https://github.com" target="_blank" rel="noopener noreferrer" class="text-green-400 hover:text-white transition">github.com</a></p>
    </div>
   </div>
  </footer>
  <script>
    // Element SDK
    const defaultConfig = {
      site_title: 'Agro Forte, Futuro Sustentável',
      background_color: '#1a472a',
      surface_color: '#ffffff',
      text_color: '#1c1917',
      primary_action_color: '#4CAF50',
      secondary_action_color: '#2d5a3f',
      font_family: 'Playfair Display',
      font_size: 16
    };

    window.elementSdk.init({
      defaultConfig,
      onConfigChange: async (config) => {
        const bg = config.background_color || defaultConfig.background_color;
        const surface = config.surface_color || defaultConfig.surface_color;
        const text = config.text_color || defaultConfig.text_color;
        const primary = config.primary_action_color || defaultConfig.primary_action_color;
        const secondary = config.secondary_action_color || defaultConfig.secondary_action_color;
        const font = config.font_family || defaultConfig.font_family;
        const size = config.font_size || defaultConfig.font_size;
        const title = config.site_title || defaultConfig.site_title;

        document.getElementById('heroTitle').innerHTML = title.includes(',') 
          ? title.split(',')[0] + ',<br><span class="text-green-300">' + title.split(',').slice(1).join(',') + '</span>'
          : title;

        document.querySelectorAll('.heading-font, h1, h2, h3').forEach(el => {
          el.style.fontFamily = `${font}, serif`;
        });
        document.body.style.fontSize = size + 'px';

        document.querySelectorAll('.hero-bg').forEach(el => {
          el.style.background = `linear-gradient(135deg, ${bg} 0%, ${secondary} 50%, ${primary}88 100%)`;
        });
        document.querySelectorAll('.card-hover').forEach(el => {
          el.style.backgroundColor = surface;
        });
        document.querySelectorAll('p, span').forEach(el => {
          if (!el.closest('footer') && !el.closest('.hero-bg')) {
            el.style.color = text;
          }
        });
      },
      mapToCapabilities: (config) => ({
        recolorables: [
          { get: () => config.background_color || defaultConfig.background_color, set: (v) => { config.background_color = v; window.elementSdk.setConfig({ background_color: v }); } },
          { get: () => config.surface_color || defaultConfig.surface_color, set: (v) => { config.surface_color = v; window.elementSdk.setConfig({ surface_color: v }); } },
          { get: () => config.text_color || defaultConfig.text_color, set: (v) => { config.text_color = v; window.elementSdk.setConfig({ text_color: v }); } },
          { get: () => config.primary_action_color || defaultConfig.primary_action_color, set: (v) => { config.primary_action_color = v; window.elementSdk.setConfig({ primary_action_color: v }); } },
          { get: () => config.secondary_action_color || defaultConfig.secondary_action_color, set: (v) => { config.secondary_action_color = v; window.elementSdk.setConfig({ secondary_action_color: v }); } }
        ],
        borderables: [],
        fontEditable: { get: () => config.font_family || defaultConfig.font_family, set: (v) => { config.font_family = v; window.elementSdk.setConfig({ font_family: v }); } },
        fontSizeable: { get: () => config.font_size || defaultConfig.font_size, set: (v) => { config.font_size = v; window.elementSdk.setConfig({ font_size: v }); } }
      }),
      mapToEditPanelValues: (config) => new Map([
        ['site_title', config.site_title || defaultConfig.site_title]
      ])
    });

    // Mobile Menu
    const menuToggle = document.getElementById('menuToggle');
    const mobileMenu = document.getElementById('mobileMenu');
    menuToggle.addEventListener('click', () => mobileMenu.classList.toggle('active'));
    function closeMobile() { mobileMenu.classList.remove('active'); }

    // Scroll Progress Indicator
    window.addEventListener('scroll', () => {
      const scrollTop = document.documentElement.scrollTop || document.body.scrollTop;
      const scrollHeight = document.documentElement.scrollHeight - document.documentElement.clientHeight;
      const progress = (scrollTop / scrollHeight) * 100;
      document.getElementById('scrollIndicator').style.width = progress + '%';
    });

    // Counter Animation
    function animateCounters() {
      document.querySelectorAll('[data-counter]').forEach(el => {
        const target = parseInt(el.dataset.target);
        const numEl = el.querySelector('.counter-num');
        let current = 0;
        const increment = target / 60;
        const timer = setInterval(() => {
          current += increment;
          if (current >= target) {
            current = target;
            clearInterval(timer);
          }
          numEl.textContent = Math.round(current) + (target < 100 ? '%' : '+');
        }, 25);
      });
    }

    // Progress Bars Animation
    function animateProgressBars() {
      document.querySelectorAll('[data-progress]').forEach(bar => {
        bar.style.width = bar.dataset.progress + '%';
      });
    }

    // Intersection Observer for animations
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          if (entry.target.id === 'dados') {
            animateCounters();
            animateProgressBars();
          }
          entry.target.classList.add('visible');
          observer.unobserve(entry.target);
        }
      });
    }, { threshold: 0.3 });

    document.getElementById('dados') && observer.observe(document.getElementById('dados'));

    // Quiz
    const quizData = [
      { question: 'O que é agricultura de precisão?', options: ['Plantar apenas em terras planas', 'Usar tecnologia para otimizar insumos no campo', 'Agricultura feita apenas por máquinas', 'Plantio em estufas fechadas'], correct: 1 },
      { question: 'Qual prática ajuda a preservar o solo?', options: ['Queimadas controladas', 'Monocultura intensiva', 'Plantio direto na palha', 'Uso excessivo de arado'], correct: 2 },
      { question: 'O que são sistemas agroflorestais?', options: ['Florestas sem produção agrícola', 'Combinação de árvores com cultivos', 'Desmatamento para pastagem', 'Plantio em áreas urbanas'], correct: 1 },
      { question: 'Quanto da vegetação nativa o Brasil preserva?', options: ['Aproximadamente 30%', 'Aproximadamente 50%', 'Aproximadamente 66%', 'Aproximadamente 80%'], correct: 2 },
      { question: 'O que é manejo integrado de pragas (MIP)?', options: ['Usar apenas agrotóxicos', 'Combinar métodos biológicos e culturais para controle', 'Eliminar todos os insetos', 'Não fazer nenhum controle'], correct: 1 }
    ];

    let currentQuestion = 0;
    let score = 0;
    let answered = false;

    function renderQuiz() {
      const container = document.getElementById('quizContent');
      if (currentQuestion >= quizData.length) {
        container.innerHTML = `
          <div class="text-center py-8">
            <div class="text-6xl mb-4">${score >= 4 ? '🌱' : score >= 2 ? '🌿' : '🍂'}</div>
            <h3 class="text-2xl font-bold text-green-900 mb-2">Resultado: ${score}/${quizData.length}</h3>
            <p class="text-stone-600 mb-6">${score >= 4 ? 'Excelente! Você é um expert em sustentabilidade!' : score >= 2 ? 'Bom trabalho! Continue aprendendo.' : 'Que tal rever o conteúdo acima?'}</p>
            <button onclick="resetQuiz()" class="bg-green-600 hover:bg-green-700 text-white font-semibold px-6 py-3 rounded-xl transition">Jogar Novamente</button>
          </div>`;
        return;
      }

      const q = quizData[currentQuestion];
      container.innerHTML = `
        <div class="mb-4 flex justify-between items-center">
          <span class="text-sm text-stone-500 font-medium">Pergunta ${currentQuestion + 1} de ${quizData.length}</span>
          <span class="text-sm font-semibold text-green-700">Pontos: ${score}</span>
        </div>
        <div class="w-full bg-gray-200 rounded-full h-2 mb-6">
          <div class="bg-green-500 h-2 rounded-full transition-all" style="width:${((currentQuestion) / quizData.length) * 100}%"></div>
        </div>
        <h3 class="text-xl font-bold text-green-900 mb-6">${q.question}</h3>
        <div class="space-y-3" id="quizOptions">
          ${q.options.map((opt, i) => `
            <button onclick="selectAnswer(${i})" class="quiz-option w-full text-left px-5 py-4 rounded-xl font-medium text-stone-700" id="opt${i}">
              <span class="inline-block w-7 h-7 rounded-full bg-green-100 text-green-700 text-center leading-7 text-sm font-bold mr-3">${String.fromCharCode(65 + i)}</span>${opt}
            </button>
          `).join('')}
        </div>
        <div id="quizFeedback" class="mt-4 hidden"></div>
        <button id="nextBtn" onclick="nextQuestion()" class="mt-6 hidden w-full bg-green-600 hover:bg-green-700 text-white font-semibold py-3 rounded-xl transition">Próxima →</button>
      `;
    }

    function selectAnswer(idx) {
      if (answered) return;
      answered = true;
      const q = quizData[currentQuestion];
      const options = document.querySelectorAll('.quiz-option');
      options.forEach((opt, i) => {
        if (i === q.correct) opt.classList.add('correct');
        else if (i === idx) opt.classList.add('wrong');
        opt.style.pointerEvents = 'none';
      });
      if (idx === q.correct) score++;
      const feedback = document.getElementById('quizFeedback');
      feedback.classList.remove('hidden');
      feedback.innerHTML = idx === q.correct
        ? '<p class="text-green-700 font-medium">✅ Correto! Muito bem!</p>'
        : `<p class="text-red-600 font-medium">❌ Incorreto. A resposta certa é: ${q.options[q.correct]}</p>`;
      document.getElementById('nextBtn').classList.remove('hidden');
    }

    function nextQuestion() {
      currentQuestion++;
      answered = false;
      renderQuiz();
    }

    function resetQuiz() {
      currentQuestion = 0;
      score = 0;
      answered = false;
      renderQuiz();
    }

    renderQuiz();

    // Contact Form
    document.getElementById('contactForm').addEventListener('submit', function(e) {
      e.preventDefault();
      this.classList.add('hidden');
      document.getElementById('formSuccess').classList.remove('hidden');
      setTimeout(() => {
        this.classList.remove('hidden');
        this.reset();
        document.getElementById('formSuccess').classList.add('hidden');
      }, 3000);
    });

    // Init Lucide
    lucide.createIcons();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'a087cdce4afbd97a',t:'MTc4MDkyMDczNw=='};var a=document.createElement('script');a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
