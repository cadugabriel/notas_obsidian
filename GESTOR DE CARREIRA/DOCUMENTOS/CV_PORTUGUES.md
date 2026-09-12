# SOBRE

Esse documento contêm como está o curriculum atualmente na versão português.

>[!Importante]
>O Curriculum sempre deverá estar em HTML, pois assim flexibiliza mais sua utilização.

```html

<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Currículo - Carlos Eduardo Romeiro Gabriel</title>
    <style>
        :root {
            --primary-color: #1A365D; /* Azul Marinho Corporativo */
            --secondary-color: #2D3748; /* Cinza Escuro para Texto */
            --accent-color: #3182CE; /* Azul de Destaque */
            --bg-light: #F7FAFC; /* Fundo Secundário */
            --border-color: #E2E8F0; /* Bordas Suaves */
            --highlight-bg: #EBF8FF; /* Fundo de Destaques/Impacto */
            --highlight-border: #90CDF4;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
            color: var(--secondary-color);
            background-color: #FFFFFF;
            line-height: 1.6;
            padding: 40px;
        }

        .container {
            max-width: 900px;
            margin: 0 auto;
        }

        /* CABEÇALHO */
        header {
            border-bottom: 3px solid var(--primary-color);
            padding-bottom: 20px;
            margin-bottom: 25px;
        }

        .header-main {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            flex-wrap: wrap;
        }

        h1 {
            font-size: 28px;
            color: var(--primary-color);
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            margin-bottom: 5px;
        }

        .headline {
            font-size: 16px;
            color: var(--accent-color);
            font-weight: 600;
            margin-bottom: 15px;
        }

        .contact-info {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 8px 20px;
            font-size: 13px;
        }

        .contact-item {
            display: flex;
            align-items: center;
        }

        .contact-item strong {
            color: var(--primary-color);
            margin-right: 5px;
        }

        .contact-item a {
            color: var(--secondary-color);
            text-decoration: none;
        }

        .contact-item a:hover {
            text-decoration: underline;
            color: var(--accent-color);
        }

        /* RESUMO PROFISSIONAL */
        .summary {
            font-size: 14px;
            text-align: justify;
            margin-bottom: 25px;
        }

        .summary p {
            margin-bottom: 10px;
        }

        /* SEÇÕES DO CURRÍCULO */
        section {
            margin-bottom: 30px;
        }

        h2 {
            font-size: 18px;
            color: var(--primary-color);
            border-bottom: 1.5px solid var(--primary-color);
            padding-bottom: 5px;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            margin-bottom: 15px;
        }

        /* MATRIZ DE COMPETÊNCIAS */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 15px;
            font-size: 13px;
        }

        @media (max-width: 600px) {
            .skills-grid {
                grid-template-columns: 1fr;
            }
        }

        .skill-category {
            background-color: var(--bg-light);
            padding: 12px;
            border-radius: 5px;
            border-left: 3px solid var(--accent-color);
        }

        .skill-category h3 {
            font-size: 13px;
            color: var(--primary-color);
            margin-bottom: 6px;
            font-weight: 700;
        }

        /* EXPERIÊNCIA PROFISSIONAL */
        .experience-item {
            margin-bottom: 20px;
        }

        .experience-header {
            display: flex;
            justify-content: space-between;
            align-items: baseline;
            flex-wrap: wrap;
            margin-bottom: 5px;
        }

        .company-name {
            font-size: 15px;
            font-weight: 700;
            color: var(--primary-color);
        }

        .period {
            font-size: 13px;
            font-weight: 600;
            color: var(--accent-color);
        }

        .role-title {
            font-size: 13.5px;
            font-style: italic;
            font-weight: 600;
            margin-bottom: 8px;
        }

        .experience-details {
            list-style-type: none;
            padding-left: 0;
            font-size: 13px;
        }

        .experience-details li {
            position: relative;
            padding-left: 15px;
            margin-bottom: 5px;
            text-align: justify;
        }

        .experience-details li::before {
            content: "•";
            position: absolute;
            left: 0;
            color: var(--accent-color);
            font-weight: bold;
        }

        /* DESTAQUE / IMPACTO */
        .highlight-box {
            background-color: var(--highlight-bg);
            border: 1px solid var(--highlight-border);
            padding: 10px 15px;
            border-radius: 4px;
            font-size: 13px;
            margin-top: 10px;
            font-weight: 500;
        }

        .highlight-box strong {
            color: var(--primary-color);
        }

        /* PROJETOS SELECIONADOS */
        .projects-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
        }

        .project-item {
            border: 1px solid var(--border-color);
            padding: 15px;
            border-radius: 5px;
            background-color: #FFFFFF;
        }

        .project-header {
            display: flex;
            justify-content: space-between;
            font-size: 14px;
            font-weight: 700;
            color: var(--primary-color);
            margin-bottom: 8px;
        }

        .project-desc {
            font-size: 13px;
            text-align: justify;
            margin-bottom: 8px;
        }

        .project-tech {
            font-size: 12px;
            color: var(--secondary-color);
            margin-bottom: 8px;
        }

        .project-tech strong {
            color: var(--primary-color);
        }

        /* FORMAÇÃO E IDIOMAS */
        .academic-item {
            margin-bottom: 12px;
            font-size: 13px;
        }

        .academic-item strong {
            color: var(--primary-color);
            font-size: 14px;
        }

        .languages-list {
            display: flex;
            gap: 30px;
            font-size: 13px;
        }

        /* CONFIGURAÇÕES DE IMPRESSÃO */
        @media print {
            body {
                padding: 0;
                font-size: 12px;
                color: #000000;
            }

            .container {
                max-width: 100%;
            }

            .skill-category {
                background-color: #F8F9FA !important;
                border-left: 3px solid #000000 !important;
                -webkit-print-color-adjust: exact;
                print-color-adjust: exact;
            }

            .highlight-box {
                background-color: #F0F4F8 !important;
                border: 1px solid #CBD5E0 !important;
                -webkit-print-color-adjust: exact;
                print-color-adjust: exact;
            }

            h2 {
                border-bottom: 1.5px solid #000000 !important;
                color: #000000 !important;
            }

            h1, .company-name, .project-header {
                color: #000000 !important;
            }

            .period, .role-title {
                color: #333333 !important;
            }
            
            .page-break {
                page-break-before: always;
            }
        }
    </style>
</head>
<body>

<div class="container">

    <!-- CABEÇALHO -->
    <header>
        <div class="header-main">
            <div>
                <h1>Carlos Eduardo Romeiro Gabriel</h1>
                <div class="headline">Engenheiro de Dados Principal | Arquiteto de Soluções Cloud</div>
            </div>
        </div>
        <div class="contact-info">
            <div class="contact-item"><strong>Localização:</strong> Peruíbe, SP</div>
            <div class="contact-item"><strong>WhatsApp:</strong> (11) 98781-5091</div>
            <div class="contact-item"><strong>Email:</strong> <a href="mailto:carloseduardo.gabriel@gmail.com">carloseduardo.gabriel@gmail.com</a></div>
            <div class="contact-item"><strong>LinkedIn:</strong> <a href="https://linkedin.com/in/cadugabriel" target="_blank">linkedin.com/in/cadugabriel</a></div>
            <div class="contact-item"><strong>GitHub:</strong> <a href="https://github.com/cadugabriel" target="_blank">github.com/cadugabriel</a></div>
            <div class="contact-item"><strong>Blog:</strong> <a href="http://bitstechhub.blogspot.com" target="_blank">bitstechhub.blogspot.com</a></div>
        </div>
    </header>

    <!-- RESUMO PROFISSIONAL -->
    <section class="summary">
        <p>
            Engenheiro de Dados Sênior com mais de 17 anos de experiência dedicada à área de dados e mais de 25 anos de trajetória consolidada em TI. Especialista no desenho e implementação de arquiteturas modernas de dados em larga escala (Data Lakehouse, Data Warehouse), com sólida atuação em ambientes de Nuvem Azure e AWS.
        </p>
        <p>
            Sólido domínio na estruturação de dados utilizando a Arquitetura Medallion, desenvolvimento de pipelines escaláveis de ETL/ELT e processamento distribuído (batch/streaming) nativos. Histórico comprovado liderando squads técnicas e entregando soluções críticas de BI e Big Data para os setores Financeiro (Open Finance/Open Insurance), Telecomunicações, Varejo e Governamental, sempre com foco em alta performance e otimização de custos.
        </p>
    </section>

    <!-- MATRIZ DE COMPETÊNCIAS -->
    <section>
        <h2>Matriz de Competências & Habilidades Completa</h2>
        <div class="skills-grid">
            <div class="skill-category">
                <h3>Engenharia de Dados & Cloud</h3>
                <p>Azure Cloud, AWS, Databricks, Apache Spark, Apache Kafka (Real-Time Streaming), Delta Lake, ETL/ELT, Arquitetura Medallion.</p>
            </div>
            <div class="skill-category">
                <h3>Linguagens & DevOps</h3>
                <p>Python, JavaScript, Shell Script, .NET, Docker, Kubernetes, GitHub Actions, Linux, Git.</p>
            </div>
            <div class="skill-category">
                <h3>IA & Engenharia de Prompt</h3>
                <p>AI-Assisted Development, Automação com LLMs, Prompt Engineering, Prompt Chaining, Debugging/Code Review assistido por IA, Squads Semi-Agênticas com Assistentes de IA, Orquestração de Multi-Agentes de IA.</p>
            </div>
            <div class="skill-category">
                <h3>Cloud FinOps & Cost Optimization</h3>
                <p>Azure Cost Management & Invoicing, AWS Cost Explorer & FinOps Tools, Cost Modeling, Architectural Optimization for Cost.</p>
            </div>
            <div class="skill-category">
                <h3>Bancos de Dados & Analytics</h3>
                <p>SQL Server, Oracle, Teradata, Azure SQL Database, T-SQL, PL/SQL, Modelagem Dimensional, Otimização de Queries Complexas, Tuning e Performance.</p>
            </div>
            <div class="skill-category">
                <h3>Business Intelligence</h3>
                <p>Análise de Dados, BI, Power BI, Power BI Embedded, Tableau, Integração de Dados Analíticos.</p>
            </div>
            <div class="skill-category" style="grid-column: span 2;">
                <h3>Liderança & Gestão</h3>
                <p>Gestão de Projetos de Ponta a Ponta (Inception ao Delivery), Liderança de Equipes Multidisciplinares, Mentoria Técnica e Assessments de Infraestrutura.</p>
            </div>
        </div>
    </section>

    <!-- EXPERIÊNCIA PROFISSIONAL -->
    <section class="page-break">
        <h2>Experiência Profissional</h2>

        <div class="experience-item">
            <div class="experience-header">
                <span class="company-name">Carlos E R Gabriel Informática (Consultoria)</span>
                <span class="period">01/2024 – Atual</span>
            </div>
            <div class="role-title">Engenheiro de Dados Principal & Arquiteto Cloud (PJ)</div>
            <ul class="experience-details">
                <li>Atuação estratégica na modernização de plataformas corporativas em larga escala (Azure e AWS).</li>
                <li>Implementação de arquiteturas Data Lakehouse baseadas na Medallion, suportando ingestão massiva e processamento automatizado.</li>
                <li>Liderança técnica e mentoria de squads em processos críticos de migração e inovação em engenharia de dados auxiliada por IA.</li>
                <li>Atuação em Engenharia de Dados integrada a Squads Semi-Agênticas, orquestrando fluxos e automações assistidos por agentes virtuais de IA para a validação e otimização de pipelines de dados.</li>
                <li>Utilização de IA Generativa para revisão de código, automação, validação de pipelines e aumento de produtividade.</li>
            </ul>
            <div class="highlight-box">
                🏆 <strong>Destaque de Impacto Sênior:</strong> Liderança técnica em projetos críticos de OpenFinance/Open Insurance e redução de até 60% em custos de nuvem.
            </div>
        </div>

        <div class="experience-item">
            <div class="experience-header">
                <span class="company-name">Remay</span>
                <span class="period">02/2014 – 12/2023</span>
            </div>
            <div class="role-title">Engenheiro de Dados Sênior | Arquiteto Cloud (PJ)</div>
            <ul class="experience-details">
                <li>Referência técnica no desenho e sustentação de arquiteturas analíticas para grandes corporações.</li>
                <li>Modelagem dimensional, desenvolvimento de pipelines críticos e workloads distribuídos (Databricks, Kafka).</li>
                <li>Condução de assessments aprofundados para otimização operacional e tuning de performance.</li>
            </ul>
            <div class="highlight-box">
                🏆 <strong>Destaque:</strong> Reestruturação de queries analíticas reduzindo processamentos de dias para ~2 horas.
            </div>
        </div>

        <div class="experience-item">
            <div class="experience-header">
                <span class="company-name">Global System Desenvolvimento de Sistemas</span>
                <span class="period">02/2011 – 12/2013</span>
            </div>
            <div class="role-title">Líder Técnico & Gestor de Projetos BI (PJ)</div>
            <ul class="experience-details">
                <li>Liderança ponta a ponta do ciclo de vida de projetos de Business Intelligence focados em dados financeiros.</li>
                <li>Modelagem dimensional e desenvolvimento estável de ETL integrando diversos sistemas legados.</li>
            </ul>
            <div class="highlight-box">
                🏆 <strong>Destaque:</strong> Liderança técnica de equipe multidisciplinar de 10 profissionais e redução de 60% no tempo de resposta para análise de cobrança.
            </div>
        </div>

        <div class="experience-item">
            <div class="experience-header">
                <span class="company-name">Experiências Anteriores Consolidadas</span>
                <span class="period">2000 – 2011</span>
            </div>
            <div class="role-title">Keyrus (Analista Sênior), Fundação Vanzolini (Consultor), Masterdom (Consultor Técnico)</div>
            <ul class="experience-details" style="list-style-type: none; padding-left: 0;">
                <li>Atuação consolidada como Engenheiro de Banco de Dados, Administrador SQL Server e Desenvolvedor em projetos de grande volumetria para os setores público e privado. Finalista nacional do prêmio IBM Best Choice (2004).</li>
            </ul>
        </div>
    </section>

    <!-- PROJETOS RELEVANTES SELECIONADOS -->
    <section class="page-break">
        <h2>Projetos Relevantes Selecionados</h2>
        <div class="projects-grid">
            
            <div class="project-item">
                <div class="project-header">
                    <span>Plataforma de Dados com Squads Semi-Agênticas e Assistentes de IA</span>
                    <span>2025 – Atual</span>
                </div>
                <p class="project-desc">
                    Desenvolvimento de pipelines de ETL/ELT integrando arquiteturas de Squads Semi-Agênticas assistidas por agentes inteligentes para automação, análise e monitoramento de qualidade de dados.
                </p>
                <p class="project-desc">
                    Atividades principais: Engenharia de dados estruturada; desenvolvimento e manutenção avançada de ETL/ELT; atuação direta como Engenheiro de Dados em estrutura de Squads Semi-Agênticas; implementação e orquestração de assistentes inteligentes utilizando CrewAI ou LangGraph para automação de testes e validações de schemas.
                </p>
                <div class="project-tech"><strong>Tecnologias:</strong> Python, pySpark, CrewAI, LangGraph, LLMs, Assistentes de IA.</div>
                <div class="highlight-box"><strong>Resultados:</strong> Otimização do fluxo de desenvolvimento e redução do tempo de entrega de pipelines por meio da automação agêntica integrada.</div>
            </div>

            <div class="project-item">
                <div class="project-header">
                    <span>Open Insurance – Instituição Bancária de Seguros</span>
                    <span>2024</span>
                </div>
                <p class="project-desc">Refatoração completa para Arquitetura Real Time (Streaming) para suporte a grandes volumes de dados de seguros.</p>
                <div class="highlight-box"><strong>Impacto Financeiro:</strong> Economia superior a 40% nos custos operacionais e de infraestrutura.</div>
            </div>

            <div class="project-item">
                <div class="project-header">
                    <span>Assessment de Arquitetura e Performance</span>
                    <span>2019 – 2024</span>
                </div>
                <p class="project-desc">Análise técnica profunda de ambientes críticos, focando em performance de bancos de dados e otimização de pipelines de dados.</p>
                <div class="highlight-box"><strong>Impacto Técnico:</strong> Execução de mais de 50 assessments garantindo estabilidade e escalabilidade.</div>
            </div>

            <div class="project-item">
                <div class="project-header">
                    <span>Otimização Avançada de Pipelines aplicados ao Metrô-SP</span>
                    <span>2022</span>
                </div>
                <p class="project-desc">Tuning e desenvolvimento de queries de performance aplicada a sistemas críticos de repercussão nacional.</p>
                <div class="highlight-box"><strong>Impacto Operacional:</strong> Redução de processamento pesado de 3 dias para apenas 2 horas.</div>
            </div>

            <div class="project-item">
                <div class="project-header">
                    <span>Reestruturação e Consolidação de Ambientes Híbridos</span>
                    <span>2019</span>
                </div>
                <p class="project-desc">Arquitetura de consolidação contendo +30 servidores e +500 bancos de dados, separando workloads on-premise e cloud.</p>
                <div class="highlight-box"><strong>Impacto Financeiro:</strong> Economia estimada de R$ 600.000,00 no primeiro ano fiscal.</div>
            </div>
            
        </div>
    </section>

    <!-- FORMAÇÃO ACADÊMICA -->
    <section>
        <h2>Formação Acadêmica</h2>
        <div class="academic-item">
            <strong>Pós-graduação Executiva em Gestão</strong><br>
            Universidade Nove de Julho (Uninove) | Conclusão: 06/2019
        </div>
        <div class="academic-item">
            <strong>Bacharelado em Ciência da Computação</strong><br>
            Universidade São Judas Tadeu (USJT) | Conclusão: 12/2008
        </div>
    </section>

    <!-- IDIOMAS -->
    <section>
        <h2>Idiomas</h2>
        <div class="languages-list">
            <div><strong>Português:</strong> Nativo</div>
            <div><strong>Inglês:</strong> Independente (B1)</div>
            <div><strong>Espanhol:</strong> Básico (A1)</div>
        </div>
    </section>

</div>

</body>
</html>
```
