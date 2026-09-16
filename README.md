# Setembro-amarelo
16/09


<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Espaço Acolher - Apoio e Bem-Estar</title>
    <style>
        /* ==========================================================================
           1. DESIGN & USABILIDADE EMPÁTICA (UI/UX)
           Cores suaves, tipografia legível e reset básico.
           ========================================================================== */
        :root {
            --primary-color: #2e7d32;
            --primary-light: #e8f5e9;
            --accent-color: #0288d1;
            --accent-light: #e0f7fa;
            --emergency-color: #d32f2f;
            --emergency-hover: #b71c1c;
            --text-dark: #2c3e50;
            --text-muted: #607d8b;
            --bg-light: #f4f7f6;
            --white: #ffffff;
            --shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
            --radius: 12px;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-light);
            color: var(--text-dark);
            line-height: 1.6;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
        }

        header {
            background-color: var(--white);
            padding: 1.5rem 1rem;
            text-align: center;
            box-shadow: var(--shadow);
        }

        header h1 {
            color: var(--primary-color);
            font-size: 1.8rem;
            margin-bottom: 0.3rem;
        }

        header p {
            color: var(--text-muted);
            font-size: 0.95rem;
        }

        main {
            max-width: 900px;
            width: 100%;
            margin: 2rem auto;
            padding: 0 1rem;
            flex: 1;
        }

        .card {
            background: var(--white);
            border-radius: var(--radius);
            padding: 1.5rem;
            margin-bottom: 1.5rem;
            box-shadow: var(--shadow);
        }

        .card h2 {
            color: var(--primary-color);
            margin-bottom: 1rem;
            font-size: 1.3rem;
            border-bottom: 2px solid var(--primary-light);
            padding-bottom: 0.5rem;
        }

        /* ==========================================================================
           2. DIRECIONAMENTO DE EMERGÊNCIA (CVV)
           ========================================================================== */
        .emergency-banner {
            background-color: #ffebee;
            border-left: 6px solid var(--emergency-color);
            padding: 1.5rem;
            border-radius: var(--radius);
            text-align: center;
            margin-bottom: 1.5rem;
            box-shadow: var(--shadow);
        }

        .emergency-banner h2 {
            color: var(--emergency-color);
            font-size: 1.4rem;
            margin-bottom: 0.5rem;
            border: none;
            padding: 0;
        }

        .emergency-banner p {
            margin-bottom: 1rem;
            color: #5d4037;
        }

        .emergency-actions {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn-emergency {
            background-color: var(--emergency-color);
            color: var(--white);
            padding: 0.8rem 1.5rem;
            text-decoration: none;
            font-weight: bold;
            border-radius: 25px;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            transition: background-color 0.3s ease;
        }

        .btn-emergency:hover {
            background-color: var(--emergency-hover);
        }

        .btn-secondary {
            background-color: var(--white);
            color: var(--emergency-color);
            border: 2px solid var(--emergency-color);
            padding: 0.8rem 1.5rem;
            text-decoration: none;
            font-weight: bold;
            border-radius: 25px;
            transition: background-color 0.3s ease;
        }

        .btn-secondary:hover {
            background-color: #ffebee;
        }

        /* ==========================================================================
           3. RECURSO INTERATIVO: RESPIRAÇÃO GUIADA
           ========================================================================== */
        .breathing-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }

        .circle-wrapper {
            width: 180px;
            height: 180px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 1.5rem 0;
            position: relative;
        }

        .breathing-circle {
            width: 100px;
            height: 100px;
            background-color: var(--accent-light);
            border: 4px solid var(--accent-color);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: transform 4s ease-in-out;
        }

        .breathing-text {
            font-weight: bold;
            color: var(--accent-color);
            font-size: 1.1rem;
        }

        /* Classes de animação via JS */
        .breathing-circle.inhale {
            transform: scale(1.6);
        }

        .breathing-circle.exhale {
            transform: scale(1);
        }

        .btn-action {
            background-color: var(--accent-color);
            color: var(--white);
            border: none;
            padding: 0.7rem 1.5rem;
            border-radius: 20px;
            font-size: 1rem;
            cursor: pointer;
            transition: opacity 0.3s;
        }

        .btn-action:hover {
            opacity: 0.9;
        }

        /* ==========================================================================
           4. MAPEAMENTO DE APOIO E INFORMAÇÃO
           ========================================================================== */
        .support-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1rem;
            margin-top: 1rem;
        }

        .support-item {
            background: var(--bg-light);
            padding: 1rem;
            border-radius: 8px;
            border-left: 4px solid var(--primary-color);
        }

        .support-item h3 {
            font-size: 1.1rem;
            color: var(--primary-color);
            margin-bottom: 0.4rem;
        }

        .support-item p {
            font-size: 0.9rem;
            color: var(--text-dark);
        }

        /* ==========================================================================
           5. AVISO LEGAL / RODAPÉ OBRIGATÓRIO
           ========================================================================== */
        footer {
            background-color: var(--white);
            border-top: 1px solid #e0e0e0;
            text-align: center;
            padding: 1.5rem 1rem;
            margin-top: auto;
        }

        .disclaimer {
            font-size: 0.85rem;
            color: var(--text-muted);
            max-width: 800px;
            margin: 0 auto;
        }

        /* Responsive Tweaks */
        @media (max-width: 600px) {
            header h1 {
                font-size: 1.5rem;
            }
            .emergency-actions {
                flex-direction: column;
            }
            .btn-emergency, .btn-secondary {
                width: 100%;
                text-align: center;
                justify-content: center;
            }
        }
    </style>
</head>
<body>

    <!-- Header / Cabeçalho -->
    <header>
        <h1>Espaço Acolher</h1>
        <p>Um ambiente seguro para o seu momento de pausa e busca de apoio.</p>
    </header>

    <main>
        <!-- REQUISITO 1: Direcionamento de Emergência (Botão CVV) -->
        <section class="emergency-banner" aria-label="Atendimento de Emergência">
            <h2>Precisa conversar agora?</h2>
            <p>Se você está passando por um momento difícil ou precisa de apoio emocional imediato, não hesite em pedir ajuda.</p>
            <div class="emergency-actions">
                <a href="tel:188" class="btn-emergency" title="Ligar para o CVV">
                    📞 Ligue 188 (Gratuito)
                </a>
                <a href="https://www.cvv.org.br" target="_blank" rel="noopener noreferrer" class="btn-secondary">
                    Acessar cvv.org.br
                </a>
            </div>
        </section>

        <!-- REQUISITO 2: Recurso Interativo de Apoio (Exercício de Respiração Guiada) -->
        <section class="card">
            <h2>Exercício de Respiração Guiada</h2>
            <p>Tirar um momento para focar na sua respiração pode ajudar a diminuir a ansiedade e desacelerar a mente.</p>
            
            <div class="breathing-container">
                <div class="circle-wrapper">
                    <div class="breathing-circle" id="breathingCircle">
                        <span class="breathing-text" id="breathingText">Pronto?</span>
                    </div>
                </div>
                <button class="btn-action" id="startBreathingBtn" onclick="toggleBreathing()">Iniciar Exercício</button>
            </div>
        </section>

        <!-- REQUISITO 3: Mapeamento de Apoio e Informação -->
        <section class="card">
            <h2>Onde Encontrar Ajuda Especializada</h2>
            <p>Existem diversos serviços públicos e gratuitos prontos para acolher você:</p>
            
            <div class="support-grid">
                <div class="support-item">
                    <h3>CAPS (Centros de Atenção Psicossocial)</h3>
                    <p>Unidades públicas de saúde mental focadas no atendimento humanizado e gratuito. Procure a unidade mais próxima do seu bairro.</p>
                </div>
                <div class="support-item">
                    <h3>Clínicas-Escola</h3>
                    <p>Atendimentos psicológicos a preços populares ou gratuitos oferecidos por faculdades e universidades que possuem curso de Psicologia.</p>
                </div>
                <div class="support-item">
                    <h3>Unidades Básicas de Saúde (UBS)</h3>
                    <p>O posto de saúde do seu bairro pode fazer o primeiro acolhimento e encaminhá-lo para profissionais de psicologia e psiquiatria.</p>
                </div>
                <div class="support-item">
                    <h3>Apoio Universitário / Institucional</h3>
                    <p>Caso você seja estudante, informe-se sobre os canais internos de escuta e acolhimento psicológico oferecidos pela sua instituição.</p>
                </div>
            </div>
        </section>
    </main>

    <!-- REQUISITO 5: Aviso Legal/Rodapé Obrigatório -->
    <footer>
        <div class="disclaimer">
            <p><strong>Aviso Importante:</strong> Esta aplicação é um <strong>projeto acadêmico</strong> e não substitui o atendimento psicológico ou médico profissional. Se você ou alguém que você conhece está enfrentando uma crise ou emergência de saúde mental, procure imediatamente um serviço de saúde ou ligue para o CVV (188).</p>
        </div>
    </footer>

    <!-- Lógica JavaScript -->
    <script>
        // Lógica do Exercício de Respiração
        let breathingInterval = null;
        let isBreathingActive = false;

        const circle = document.getElementById('breathingCircle');
        const text = document.getElementById('breathingText');
        const btn = document.getElementById('startBreathingBtn');

        function toggleBreathing() {
            if (isBreathingActive) {
                stopBreathing();
            } else {
                startBreathing();
            }
        }

        function startBreathing() {
            isBreathingActive = true;
            btn.textContent = 'Parar Exercício';
            runBreathingCycle(); // Executa o primeiro ciclo de imediato
            
            // Ciclo completo de 8 segundos (4s inspira, 4s expira)
            breathingInterval = setInterval(runBreathingCycle, 8000);
        }

        function runBreathingCycle() {
            // Inspira (4 segundos)
            text.textContent = 'Inspire...';
            circle.classList.remove('exhale');
            circle.classList.add('inhale');

            // Expira (após 4 segundos)
            setTimeout(() => {
                if (isBreathingActive) {
                    text.textContent = 'Expire...';
                    circle.classList.remove('inhale');
                    circle.classList.add('exhale');
                }
            }, 4000);
        }

        function stopBreathing() {
            isBreathingActive = false;
            clearInterval(breathingInterval);
            circle.classList.remove('inhale', 'exhale');
            text.textContent = 'Pronto?';
            btn.textContent = 'Iniciar Exercício';
        }
    </script>
</body>
</html>
