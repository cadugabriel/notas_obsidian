# SOBRE

Esse documento contêm como está o curriculum atualmente na versão inglês.

>[!Importante]
>O Curriculum sempre deverá estar em HTML, pois assim flexibiliza mais sua utilização.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Resume - Carlos Eduardo Romeiro Gabriel</title>
    <style>
        :root {
            --primary-color: #1A365D; /* Corporate Navy Blue */
            --secondary-color: #2D3748; /* Dark Gray for Text */
            --accent-color: #3182CE; /* Highlight Blue */
            --bg-light: #F7FAFC; /* Secondary Background */
            --border-color: #E2E8F0; /* Soft Borders */
            --highlight-bg: #EBF8FF; /* Highlight/Impact Background */
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

        /* HEADER */
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

        /* SUMMARY */
        .summary {
            font-size: 14px;
            text-align: justify;
            margin-bottom: 25px;
        }

        .summary p {
            margin-bottom: 10px;
        }

        /* SECTIONS */
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

        /* SKILLS GRID */
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

        /* EXPERIENCE */
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

        /* HIGHLIGHT BOX */
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

        /* SELECTED PROJECTS */
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

        /* EDUCATION & LANGUAGES */
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

        /* PRINT MEDIA STYLES */
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

    <!-- HEADER -->
    <header>
        <div class="header-main">
            <div>
                <h1>Carlos Eduardo Romeiro Gabriel</h1>
                <div class="headline">Principal Data Engineer | Cloud Solutions Architect</div>
            </div>
        </div>
        <div class="contact-info">
            <div class="contact-item"><strong>Location:</strong> Peruíbe, SP, Brazil</div>
            <div class="contact-item"><strong>WhatsApp:</strong> (11) 98781-5091</div>
            <div class="contact-item"><strong>Email:</strong> <a href="mailto:carloseduardo.gabriel@gmail.com">carloseduardo.gabriel@gmail.com</a></div>
            <div class="contact-item"><strong>LinkedIn:</strong> <a href="https://linkedin.com/in/cadugabriel" target="_blank">linkedin.com/in/cadugabriel</a></div>
            <div class="contact-item"><strong>GitHub:</strong> <a href="https://github.com/cadugabriel" target="_blank">github.com/cadugabriel</a></div>
            <div class="contact-item"><strong>Blog:</strong> <a href="http://bitstechhub.blogspot.com" target="_blank">bitstechhub.blogspot.com</a></div>
        </div>
    </header>

    <!-- PROFESSIONAL SUMMARY -->
    <section class="summary">
        <p>
            Principal Data Engineer and Data Architect with more than 17 years of dedicated experience in Data Engineering and over 25 years of proven success in Information Technology. Specialized in designing, modernizing, and delivering enterprise-scale cloud-native data platforms, Data Lakehouse architectures, and high-performance analytical environments across Microsoft Azure, Amazon Web Services (AWS), and Databricks.
        </p>
        <p>
            Extensive experience implementing Medallion Architecture, developing scalable ETL/ELT pipelines, and building distributed Batch and Streaming data processing solutions using Apache Spark and Databricks. Proven track record leading engineering teams and delivering mission-critical Data Engineering, Business Intelligence, and Big Data projects for Financial Services (Open Finance and Open Insurance), Telecommunications, Retail, and Government organizations.
        </p>
    </section>

    <!-- CORE COMPETENCIES -->
    <section>
        <h2>Core Competencies & Skills</h2>
        <div class="skills-grid">
            <div class="skill-category">
                <h3>Data Engineering & Cloud</h3>
                <p>Microsoft Azure, Amazon Web Services (AWS), Databricks, Apache Spark, Apache Kafka (Real-Time Streaming), Delta Lake, Data Lakehouse, Data Warehouse, Medallion Architecture, ETL / ELT, Batch Processing, Streaming Processing.</p>
            </div>
            <div class="skill-category">
                <h3>Programming & DevOps</h3>
                <p>Python, JavaScript, Shell Script, .NET, Docker, Kubernetes, GitHub Actions, Git, Linux.</p>
            </div>
            <div class="skill-category">
                <h3>AI & Prompt Engineering</h3>
                <p>Generative AI, Large Language Models (LLMs), Prompt Engineering, AI-Assisted Development, Prompt Chaining, AI Code Review, Retrieval-Augmented Generation (RAG), Semi-Agentic Squads with AI Assistants, Orchestration of Multi-Agent AI Systems.</p>
            </div>
            <div class="skill-category">
                <h3>Cloud FinOps & Cost Optimization</h3>
                <p>Cloud Cost Optimization, Azure Cost Management, AWS Cost Explorer, Architecture Assessment, Performance Optimization, Cloud Governance.</p>
            </div>
            <div class="skill-category">
                <h3>Databases & Analytics</h3>
                <p>Microsoft SQL Server, Oracle Database, Teradata, T-SQL, PL/SQL, Dimensional Modeling, Performance Tuning, Query Optimization.</p>
            </div>
            <div class="skill-category">
                <h3>Business Intelligence</h3>
                <p>Power BI, Power BI Embedded, Tableau, Enterprise Analytics, Business Intelligence, Analytical Data Integration.</p>
            </div>
            <div class="skill-category" style="grid-column: span 2;">
                <h3>Leadership & Management</h3>
                <p>Technical Leadership, Solution Architecture, Project Leadership, Technical Mentoring, Cross-functional Team Leadership, Infrastructure & Architecture Assessments.</p>
            </div>
        </div>
    </section>

    <!-- PROFESSIONAL EXPERIENCE -->
    <section class="page-break">
        <h2>Professional Experience</h2>

        <div class="experience-item">
            <div class="experience-header">
                <span class="company-name">Carlos E R Gabriel Informática (Consulting)</span>
                <span class="period">01/2024 – Present</span>
            </div>
            <div class="role-title">Principal Data Engineer & Cloud Data Architect (Independent Consultant)</div>
            <ul class="experience-details">
                <li>Lead strategic initiatives focused on modernizing enterprise-scale cloud data platforms across Microsoft Azure and Amazon Web Services (AWS).</li>
                <li>Designed and implemented modern Data Lakehouse architectures based on the Medallion Architecture, enabling scalable ingestion, processing, governance, and analytics.</li>
                <li>Architected enterprise-grade ETL/ELT pipelines supporting batch and streaming workloads using Databricks, Apache Spark, and cloud-native services.</li>
                <li>Active role in Data Engineering integrated with Semi-Agentic Squads, orchestrating workflows and automations assisted by intelligent virtual agents for pipeline validation and optimization.</li>
                <li>Applied Artificial Intelligence (Generative AI) to accelerate software development, engineering productivity, documentation, architecture analysis, code reviews, and solution design.</li>
            </ul>
            <div class="highlight-box">
                🏆 <strong>Senior Impact Highlight:</strong> Technical leadership on strategic Open Finance and Open Insurance initiatives and cloud architecture optimizations resulting in infrastructure cost reductions of up to 60%.
            </div>
        </div>

        <div class="experience-item">
            <div class="experience-header">
                <span class="company-name">Remay</span>
                <span class="period">02/2014 – 12/2023</span>
            </div>
            <div class="role-title">Senior Data Engineer | Cloud Data Architect (Consultant)</div>
            <ul class="experience-details">
                <li>Served as a senior technical reference for enterprise data architecture, cloud modernization, and advanced analytics solutions.</li>
                <li>Designed dimensional models and enterprise Data Warehouse architectures supporting large-scale analytical environments.</li>
                <li>Developed highly scalable data pipelines using Databricks, Apache Spark, Apache Kafka, SQL Server, Oracle, and Teradata.</li>
                <li>Led architecture reviews, performance assessments, cloud optimization initiatives, and infrastructure modernization projects.</li>
            </ul>
            <div class="highlight-box">
                🏆 <strong>Key Achievement:</strong> Reduced analytical processing workloads from several days to approximately 2 hours through architecture redesign and query optimization.
            </div>
        </div>

        <div class="experience-item">
            <div class="experience-header">
                <span class="company-name">Global System Desenvolvimento de Sistemas</span>
                <span class="period">02/2011 – 12/2013</span>
            </div>
            <div class="role-title">Technical Lead & BI Project Manager (PJ)</div>
            <ul class="experience-details">
                <li>Led end-to-end Business Intelligence projects, from requirements gathering and architecture design through delivery and production support.</li>
                <li>Designed dimensional models and enterprise ETL solutions integrating multiple legacy systems.</li>
                <li>Managed multidisciplinary technical teams responsible for enterprise BI initiatives.</li>
            </ul>
            <div class="highlight-box">
                🏆 <strong>Key Achievement:</strong> Led a multidisciplinary engineering team of 10 professionals and reduced billing analysis processing time by approximately 60%.
            </div>
        </div>

        <div class="experience-item">
            <div class="experience-header">
                <span class="company-name">Previous Consolidated Experience</span>
                <span class="period">2000 – 2011</span>
            </div>
            <div class="role-title">Keyrus (Senior Consultant), Fundação Vanzolini (Consultant), Masterdom (Technical Consultant)</div>
            <ul class="experience-details" style="list-style-type: none; padding-left: 0;">
                <li>Built a strong foundation in Data Engineering, Database Administration, Business Intelligence, SQL Server, enterprise software development, and large-scale database environments. Finalist in the IBM Best Choice Award (2004) for technical excellence.</li>
            </ul>
        </div>
    </section>

    <!-- SELECTED PROJECTS -->
    <section class="page-break">
        <h2>Selected Projects</h2>
        <div class="projects-grid">
            
            <div class="project-item">
                <div class="project-header">
                    <span>Data Platform with Semi-Agentic Squads and AI Assistants</span>
                    <span>2025 – Present</span>
                </div>
                <p class="project-desc">
                    Development of ETL/ELT pipelines integrating Semi-Agentic Squads architectures assisted by intelligent agents for automation, analysis, and data quality monitoring.
                </p>
                <p class="project-desc">
                    Main Activities: Structured data engineering; advanced ETL/ELT development and maintenance; direct active role as a Data Engineer within Semi-Agentic Squad frameworks; implementation and orchestration of AI assistants (focusing on frameworks such as CrewAI or LangGraph) to automate testing and schema validations.
                </p>
                <div class="project-tech"><strong>Technologies:</strong> Python, pySpark, CrewAI, LangGraph, LLMs, AI Assistants.</div>
                <div class="highlight-box"><strong>Results:</strong> Streamlined development lifecycle and reduced pipeline delivery time through integrated agentic automation.</div>
            </div>

            <div class="project-item">
                <div class="project-header">
                    <span>Open Insurance Platform – Enterprise Financial Institution</span>
                    <span>2024</span>
                </div>
                <p class="project-desc">Designed and led the modernization of a mission-critical insurance platform by implementing a real-time streaming architecture capable of processing high-volume insurance data with improved scalability, governance, and performance.</p>
                <div class="highlight-box"><strong>Financial Impact:</strong> Reduced cloud infrastructure and operational costs by more than 40% while increasing platform scalability and reliability.</div>
            </div>

            <div class="project-item">
                <div class="project-header">
                    <span>Enterprise Architecture & Performance Assessments</span>
                    <span>2019 – 2024</span>
                </div>
                <p class="project-desc">Conducted comprehensive architecture assessments for enterprise customers, identifying performance bottlenecks, scalability limitations, cloud optimization opportunities, and modernization strategies across large-scale data platforms.</p>
                <div class="highlight-box"><strong>Technical Impact:</strong> Performed more than 50 enterprise architecture assessments improving scalability, stability, governance, and operational efficiency.</div>
            </div>

            <div class="project-item">
                <div class="project-header">
                    <span>Advanced Data Pipeline Optimization – São Paulo Metro</span>
                    <span>2022</span>
                </div>
                <p class="project-desc">Tuning and performance optimization applied to National/State wide critical transportation systems.</p>
                <div class="highlight-box"><strong>Operational Impact:</strong> Reduced processing time from 3 days to approximately 2 hours.</div>
            </div>

            <div class="project-item">
                <div class="project-header">
                    <span>Hybrid Enterprise Infrastructure Consolidation</span>
                    <span>2019</span>
                </div>
                <p class="project-desc">Designed and executed a large-scale hybrid infrastructure consolidation involving more than 30 servers and over 500 databases, optimizing workloads between on-premises and cloud environments.</p>
                <div class="highlight-box"><strong>Financial Impact:</strong> Generated estimated annual savings exceeding R$600,000.</div>
            </div>
            
        </div>
    </section>

    <!-- EDUCATION -->
    <section>
        <h2>Education</h2>
        <div class="academic-item">
            <strong>Postgraduate Degree in Executive Management</strong><br>
            Universidade Nove de Julho (UNINOVE) | Concluded: 06/2019
        </div>
        <div class="academic-item">
            <strong>Bachelor of Computer Science</strong><br>
            Universidade São Judas Tadeu (USJT) | Concluded: 12/2008
        </div>
    </section>

    <!-- LANGUAGES -->
    <section>
        <h2>Languages</h2>
        <div class="languages-list">
            <div><strong>Portuguese:</strong> Native</div>
            <div><strong>English:</strong> Intermediate (B1)</div>
            <div><strong>Spanish:</strong> Basic (A1)</div>
        </div>
    </section>

</div>

</body>
</html>
```
