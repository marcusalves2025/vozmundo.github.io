<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>VozMundo - Conectando Idiomas, Unindo Pessoas</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #2563eb;
            --primary-dark: #1d4ed8;
            --secondary: #10b981;
            --dark: #1e293b;
            --light: #f8fafc;
            --gray: #64748b;
            --border: #e2e8f0;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f1f5f9;
            color: var(--dark);
            line-height: 1.6;
        }
        
        /* Header */
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 1rem 5%;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
        }
        
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo h1 {
            font-size: 1.8rem;
            font-weight: 700;
        }
        
        .logo i {
            font-size: 2rem;
        }
        
        .nav-links {
            display: flex;
            gap: 2rem;
        }
        
        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: opacity 0.3s;
        }
        
        .nav-links a:hover {
            opacity: 0.8;
        }
        
        .nav-buttons {
            display: flex;
            gap: 1rem;
        }
        
        .btn {
            padding: 0.6rem 1.5rem;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            border: none;
        }
        
        .btn-primary {
            background-color: white;
            color: var(--primary);
        }
        
        .btn-outline {
            background-color: transparent;
            border: 2px solid white;
            color: white;
        }
        
        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 4rem 5%;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiPjxkZWZzPjxwYXR0ZXJuIGlkPSJwYXR0ZXJuIiB3aWR0aD0iNDAiIGhlaWdodD0iNDAiIHBhdHRlcm5Vbml0cz0idXNlclNwYWNlT25Vc2UiIHBhdHRlcm5UcmFuc2Zvcm09InJvdGF0ZSg0NSkiPjxjaXJjbGUgY3g9IjIwIiBjeT0iMjAiIHI9IjAuNSIgZmlsbD0iI2ZmZiIgZmlsbC1vcGFjaXR5PSIwLjEiLz48L3BhdHRlcm4+PC9kZWZzPjxyZWN0IHdpZHRoPSIxMDAlIiBoZWlnaHQ9IjEwMCUiIGZpbGw9InVybCgjcGF0dGVybikiLz48L3N2Zz4=');
            opacity: 0.2;
        }
        
        .hero-content {
            max-width: 900px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }
        
        .hero h2 {
            font-size: 3.5rem;
            margin-bottom: 1.5rem;
            line-height: 1.2;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
            opacity: 0.9;
        }
        
        .slogan {
            font-size: 1.5rem;
            font-weight: 500;
            margin-bottom: 3rem;
            font-style: italic;
        }
        
        /* Command Prompt */
        .command-prompt {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 2rem;
            max-width: 800px;
            margin: 0 auto;
            text-align: left;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }
        
        .command-header {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 1.5rem;
        }
        
        .command-header i {
            font-size: 1.5rem;
            color: white;
        }
        
        .command-text {
            font-family: monospace;
            font-size: 1.1rem;
            background: rgba(0, 0, 0, 0.2);
            padding: 1.2rem;
            border-radius: 12px;
            margin-bottom: 1.5rem;
            position: relative;
        }
        
        .command-variables {
            display: flex;
            flex-wrap: wrap;
            gap: 1.5rem;
            margin-top: 1.5rem;
        }
        
        .variable-group {
            flex: 1;
            min-width: 200px;
        }
        
        .variable-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 500;
        }
        
        .select-box, .radio-group {
            width: 100%;
            padding: 0.8rem;
            border-radius: 10px;
            border: none;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            font-size: 1rem;
        }
        
        .select-box option {
            color: var(--dark);
        }
        
        .radio-options {
            display: flex;
            gap: 1rem;
            margin-top: 0.5rem;
        }
        
        .radio-option {
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        .radio-option input {
            margin-right: 5px;
        }
        
        .start-btn {
            background-color: white;
            color: var(--primary);
            font-weight: 600;
            font-size: 1.1rem;
            padding: 1rem 2.5rem;
            border-radius: 50px;
            border: none;
            cursor: pointer;
            margin-top: 1.5rem;
            display: flex;
            align-items: center;
            gap: 10px;
            transition: all 0.3s;
        }
        
        .start-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
        }
        
        /* Features Section */
        .section {
            padding: 5rem 5%;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 3rem;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            color: var(--dark);
            margin-bottom: 1rem;
        }
        
        .section-title p {
            color: var(--gray);
            max-width: 700px;
            margin: 0 auto;
        }
        
        .features {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }
        
        .feature-card {
            background: white;
            border-radius: 16px;
            padding: 2rem;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
            transition: all 0.3s;
        }
        
        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }
        
        .feature-icon {
            width: 70px;
            height: 70px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 1.5rem;
        }
        
        .feature-icon i {
            font-size: 2rem;
            color: white;
        }
        
        .feature-card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: var(--dark);
        }
        
        .feature-card ul {
            list-style-type: none;
            margin-left: 1rem;
        }
        
        .feature-card ul li {
            margin-bottom: 0.8rem;
            position: relative;
            padding-left: 1.5rem;
        }
        
        .feature-card ul li:before {
            content: "✓";
            position: absolute;
            left: 0;
            color: var(--secondary);
            font-weight: bold;
        }
        
        /* How it works */
        .how-it-works {
            background-color: var(--light);
        }
        
        .steps {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .step-card {
            background: white;
            border-radius: 16px;
            padding: 2rem;
            flex: 1;
            min-width: 250px;
            max-width: 300px;
            text-align: center;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
            position: relative;
        }
        
        .step-number {
            position: absolute;
            top: -20px;
            left: 50%;
            transform: translateX(-50%);
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 1.2rem;
        }
        
        .step-card h3 {
            margin: 1.5rem 0 1rem;
            color: var(--dark);
        }
        
        /* Languages */
        .languages {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
        }
        
        .languages .section-title h2,
        .languages .section-title p {
            color: white;
        }
        
        .language-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1.5rem;
            max-width: 1000px;
            margin: 0 auto;
        }
        
        .language-item {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            padding: 1.2rem;
            text-align: center;
            transition: all 0.3s;
        }
        
        .language-item:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 0.2);
        }
        
        .language-item i {
            font-size: 2rem;
            margin-bottom: 0.8rem;
        }
        
        /* Footer */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 4rem 5% 2rem;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 3rem;
            margin-bottom: 3rem;
        }
        
        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 1.5rem;
            position: relative;
        }
        
        .footer-column h3::after {
            content: "";
            position: absolute;
            bottom: -8px;
            left: 0;
            width: 50px;
            height: 3px;
            background: var(--secondary);
            border-radius: 2px;
        }
        
        .footer-links {
            list-style-type: none;
        }
        
        .footer-links li {
            margin-bottom: 0.8rem;
        }
        
        .footer-links a {
            color: #cbd5e1;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-links a:hover {
            color: white;
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.1);
            color: white;
            transition: all 0.3s;
        }
        
        .social-links a:hover {
            background: var(--primary);
            transform: translateY(-3px);
        }
        
        .copyright {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #94a3b8;
            font-size: 0.9rem;
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .navbar {
                flex-direction: column;
                gap: 1rem;
            }
            
            .nav-links {
                gap: 1rem;
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .hero h2 {
                font-size: 2.5rem;
            }
            
            .command-variables {
                flex-direction: column;
            }
            
            .section {
                padding: 3rem 5%;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="navbar">
            <div class="logo">
                <i class="fas fa-globe-americas"></i>
                <h1>VozMundo</h1>
            </div>
            <div class="nav-links">
                <a href="#features">Recursos</a>
                <a href="#how-it-works">Como Funciona</a>
                <a href="#languages">Idiomas</a>
                <a href="#pricing">Preços</a>
                <a href="#contact">Contato</a>
            </div>
            <div class="nav-buttons">
                <button class="btn btn-outline">Login</button>
                <button class="btn btn-primary">Começar Gratuitamente</button>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h2>Conectando Idiomas, Unindo Pessoas</h2>
            <p>A plataforma definitiva de tradução de áudios e voz com inteligência artificial</p>
            <div class="slogan">"Sua voz, em todas as línguas."</div>
            
            <div class="command-prompt">
                <div class="command-header">
                    <i class="fas fa-microphone-alt"></i>
                    <h3>Prompt de Comando Inteligente</h3>
                </div>
                <div class="command-text">
                    "Olá, VozMundo! Inicie uma nova tradução de áudio. Quero transcrever, traduzir e exportar este conteúdo com sincronização em tempo real."
                </div>
                
                <div class="command-variables">
                    <div class="variable-group">
                        <label for="source-lang">Idioma de Origem</label>
                        <select id="source-lang" class="select-box">
                            <option value="auto">Detecção Automática</option>
                            <option value="pt">Português</option>
                            <option value="en">Inglês</option>
                            <option value="es">Espanhol</option>
                            <option value="fr">Francês</option>
                            <option value="de">Alemão</option>
                            <option value="zh">Chinês</option>
                        </select>
                    </div>
                    
                    <div class="variable-group">
                        <label for="target-lang">Idioma de Destino</label>
                        <select id="target-lang" class="select-box">
                            <option value="en">Inglês</option>
                            <option value="pt">Português</option>
                            <option value="es">Espanhol</option>
                            <option value="fr">Francês</option>
                            <option value="de">Alemão</option>
                            <option value="zh">Chinês</option>
                            <option value="ja">Japonês</option>
                        </select>
                    </div>
                    
                    <div class="variable-group">
                        <label>Formato de Exportação</label>
                        <div class="radio-group">
                            <div class="radio-options">
                                <div class="radio-option">
                                    <input type="radio" id="text" name="export-format" value="text" checked>
                                    <label for="text">Texto</label>
                                </div>
                                <div class="radio-option">
                                    <input type="radio" id="audio" name="export-format" value="audio">
                                    <label for="audio">Áudio</label>
                                </div>
                                <div class="radio-option">
                                    <input type="radio" id="video" name="export-format" value="video">
                                    <label for="video">Vídeo Legendado</label>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                
                <button class="start-btn">
                    <i class="fas fa-play"></i>
                    Pronto para começar!
                </button>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="section" id="features">
        <div class="section-title">
            <h2>Recursos Inovadores</h2>
            <p>Descubra como a VozMundo revoluciona a comunicação entre idiomas</p>
        </div>
        
        <div class="features">
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-microphone"></i>
                </div>
                <h3>Reconhecimento de Voz</h3>
                <ul>
                    <li>Alta precisão em qualquer ambiente</li>
                    <li>Detecção automática de idioma e sotaque</li>
                    <li>Suporte a termos técnicos e expressões</li>
                    <li>Cancelamento de ruído inteligente</li>
                </ul>
            </div>
            
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-language"></i>
                </div>
                <h3>Tradução em Tempo Real</h3>
                <ul>
                    <li>Análise do sentido completo da frase</li>
                    <li>Tradução neural adaptativa</li>
                    <li>Personalização de formalidade e estilo</li>
                    <li>Sincronização perfeita</li>
                </ul>
            </div>
            
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-file-alt"></i>
                </div>
                <h3>Transcrição e Edição</h3>
                <ul>
                    <li>Texto com pontuação automática</li>
                    <li>Interface de edição intuitiva</li>
                    <li>Sugestões inteligentes de correção</li>
                    <li>Exportação em múltiplos formatos</li>
                </ul>
            </div>
            
            <div class="feature-card">
                <div class="feature-icon">
                    <i class="fas fa-users"></i>
                </div>
                <h3>Ferramentas Profissionais</h3>
                <ul>
                    <li>Modos específicos (reunião, aula, entrevista)</li>
                    <li>Traduções colaborativas em tempo real</li>
                    <li>Histórico completo de projetos</li>
                    <li>Integração com outras plataformas</li>
                </ul>
            </div>
        </div>
    </section>

    <!-- How it Works -->
    <section class="section how-it-works" id="how-it-works">
        <div class="section-title">
            <h2>Como Funciona</h2>
            <p>Traduza qualquer áudio em quatro passos simples</p>
        </div>
        
        <div class="steps">
            <div class="step-card">
                <div class="step-number">1</div>
                <i class="fas fa-upload fa-2x" style="color: var(--primary);"></i>
                <h3>Carregue seu Áudio</h3>
                <p>Envie seu arquivo de áudio ou grave diretamente pelo microfone.</p>
            </div>
            
            <div class="step-card">
                <div class="step-number">2</div>
                <i class="fas fa-cogs fa-2x" style="color: var(--primary);"></i>
                <h3>Configure as Opções</h3>
                <p>Escolha idiomas, formatação e opções de exportação.</p>
            </div>
            
            <div class="step-card">
                <div class="step-number">3</div>
                <i class="fas fa-robot fa-2x" style="color: var(--primary);"></i>
                <h3>Processamento Inteligente</h3>
                <p>Nossa IA transcreve, traduz e sincroniza seu conteúdo.</p>
            </div>
            
            <div class="step-card">
                <div class="step-number">4</div>
                <i class="fas fa-download fa-2x" style="color: var(--primary);"></i>
                <h3>Exporte e Compartilhe</h3>
                <p>Baixe ou compartilhe seu conteúdo traduzido no formato desejado.</p>
            </div>
        </div>
    </section>

    <!-- Languages -->
    <section class="section languages" id="languages">
        <div class="section-title">
            <h2>Suporte Multilíngue</h2>
            <p>Mais de 100 idiomas com suporte ativo</p>
        </div>
        
        <div class="language-grid">
            <div class="language-item">
                <i class="fas fa-language"></i>
                <h4>Português</h4>
            </div>
            <div class="language-item">
                <i class="fas fa-language"></i>
                <h4>Inglês</h4>
            </div>
            <div class="language-item">
                <i class="fas fa-language"></i>
                <h4>Espanhol</h4>
            </div>
            <div class="language-item">
                <i class="fas fa-language"></i>
                <h4>Francês</h4>
            </div>
            <div class="language-item">
                <i class="fas fa-language"></i>
                <h4>Alemão</h4>
            </div>
            <div class="language-item">
                <i class="fas fa-language"></i>
                <h4>Italiano</h4>
            </div>
            <div class="language-item">
                <i class="fas fa-language"></i>
                <h4>Chinês</h4>
            </div>
            <div class="language-item">
                <i class="fas fa-language"></i>
                <h4>Japonês</h4>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-column">
                <h3>VozMundo</h3>
                <p>Sua voz, em todas as línguas. A plataforma definitiva para transcrição e tradução de áudio com inteligência artificial.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-linkedin-in"></i></a>
                </div>
            </div>
            
            <div class="footer-column">
                <h3>Produto</h3>
                <ul class="footer-links">
                    <li><a href="#">Recursos</a></li>
                    <li><a href="#">Planos e Preços</a></li>
                    <li><a href="#">Casos de Uso</a></li>
                    <li><a href="#">API para Desenvolvedores</a></li>
                    <li><a href="#">Downloads</a></li>
                </ul>
            </div>
            
            <div class="footer-column">
                <h3>Suporte</h3>
                <ul class="footer-links">
                    <li><a href="#">Central de Ajuda</a></li>
                    <li><a href="#">Tutoriais</a></li>
                    <li><a href="#">Comunidade</a></li>
                    <li><a href="#">Status do Sistema</a></li>
                    <li><a href="#">Contato</a></li>
                </ul>
            </div>
            
            <div class="footer-column">
                <h3>Empresa</h3>
                <ul class="footer-links">
                    <li><a href="#">Sobre Nós</a></li>
                    <li><a href="#">Blog</a></li>
                    <li><a href="#">Carreiras</a></li>
                    <li><a href="#">Parceiros</a></li>
                    <li><a href="#">Imprensa</a></li>
                </ul>
            </div>
        </div>
        
        <div class="copyright">
            &copy; 2023 VozMundo. Todos os direitos reservados.
        </div>
    </footer>

    <script>
        // Simulação do comando de voz
        document.querySelector('.start-btn').addEventListener('click', function() {
            const sourceLang = document.getElementById('source-lang').value;
            const targetLang = document.getElementById('target-lang').value;
            const exportFormat = document.querySelector('input[name="export-format"]:checked').value;
            
            // Obter o nome dos idiomas selecionados
            const langNames = {
                'auto': 'Detecção Automática',
                'pt': 'Português',
                'en': 'Inglês',
                'es': 'Espanhol',
                'fr': 'Francês',
                'de': 'Alemão',
                'zh': 'Chinês',
                'ja': 'Japonês'
            };
            
            // Obter o nome do formato de exportação
            const formatNames = {
                'text': 'Texto',
                'audio': 'Áudio',
                'video': 'Vídeo Legendado'
            };
            
            // Atualizar o prompt de comando
            const commandText = document.querySelector('.command-text');
            commandText.innerHTML = `
                "Olá, VozMundo! Inicie uma nova tradução de áudio. 
                Quero transcrever, traduzir e exportar este conteúdo com sincronização em tempo real. 
                Idioma de origem: ${langNames[sourceLang]}. 
                Idioma de destino: ${langNames[targetLang]}. 
                Exportação em ${formatNames[exportFormat]}. 
                Pronto para começar!"
            `;
            
            // Efeito visual de confirmação
            this.innerHTML = '<i class="fas fa-check"></i> Processando...';
            this.style.backgroundColor = '#10b981';
            
            setTimeout(() => {
                alert('Tradução iniciada com sucesso! Em uma implementação real, o processamento começaria agora.');
                this.innerHTML = '<i class="fas fa-play"></i> Pronto para começar!';
                this.style.backgroundColor = '';
            }, 1500);
        });
    </script>
</body>
</html>
