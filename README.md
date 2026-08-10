body {
    background-color: var(--bg-color);
    color: var(--text-dark);
    line-height: 1.7;
    min-height: 2000px; /* Isso força a página a ficar gigante para testar a rolagem! */
}

<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portal do Novo Ensino Médio - Paraná em Foco</title>
    <style>
        :root {
            --primary-color: #0d3b66;
            --secondary-color: #0077b6;
            --accent-color: #f4a261;
            --success-color: #2a9d8f;
            --bg-color: #f8f9fa;
            --text-dark: #212529;
            --text-light: #6c757d;
            --card-bg: #ffffff;
            --border-color: #dee2e6;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-dark);
            line-height: 1.7;
        }

        /* Topbar de Alerta / Contexto */
        .top-notice {
            background-color: var(--primary-color);
            color: white;
            text-align: center;
            padding: 10px;
            font-size: 0.9rem;
            font-weight: 500;
            letter-spacing: 0.5px;
        }

        /* Header Principal */
        header {
            background: linear-gradient(135deg, #023e8a, #0077b6, #00b4d8);
            color: white;
            padding: 60px 20px;
            text-align: center;
            position: relative;
        }

        header h1 {
            font-size: 3rem;
            font-weight: 800;
            margin-bottom: 15px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }

        header p {
            font-size: 1.3rem;
            max-width: 800px;
            margin: 0 auto;
            opacity: 0.9;
        }

        /* Layout Principal em Duas Colunas */
        .main-wrapper {
            max-width: 1400px;
            margin: 40px auto;
            padding: 0 20px;
            display: grid;
            grid-template-columns: 1fr 320px;
            gap: 40px;
        }

        @media (max-width: 1024px) {
            .main-wrapper {
                grid-template-columns: 1fr;
            }
            .sidebar {
                position: static !important;
            }
        }

        /* Conteúdo Esquerdo */
        .content-area {
            display: flex;
            flex-direction: column;
            gap: 40px;
        }

        /* Seções de Texto Grandes */
        .section-block {
            background-color: var(--card-bg);
            padding: 40px;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.03);
            border: 1px solid var(--border-color);
        }

        .section-block h2 {
            color: var(--primary-color);
            font-size: 2rem;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
            border-bottom: 3px solid var(--secondary-color);
            padding-bottom: 10px;
        }

        .section-block p {
            margin-bottom: 20px;
            text-align: justify;
            color: #333;
        }

        /* Box de Destaque / Citação */
        .highlight-box {
            background-color: #e2eafc;
            border-left: 6px solid var(--secondary-color);
            padding: 20px;
            border-radius: 0 8px 8px 0;
            margin: 25px 0;
            font-style: italic;
        }

        /* Estrutura dos Grandes Tópicos (Geografia, Arte, História) */
        .topic-header-image {
            width: 100%;
            height: 350px;
            object-fit: cover;
            border-radius: 8px;
            margin-bottom: 25px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }

        .sub-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 25px;
            margin-top: 25px;
        }

        @media (max-width: 768px) {
            .sub-grid {
                grid-template-columns: 1fr;
            }
        }

        .info-pane {
            background-color: #f8f9fa;
            padding: 25px;
            border-radius: 8px;
            border-top: 4px solid var(--success-color);
        }

        .info-pane.pane-alt {
            border-top-color: var(--accent-color);
        }

        .info-pane h3 {
            color: #1d3557;
            margin-bottom: 12px;
            font-size: 1.25rem;
        }

        /* Tabelas de Dados Históricos/Geográficos */
        .data-table {
            width: 100%;
            border-collapse: collapse;
            margin: 25px 0;
            font-size: 0.95rem;
        }

        .data-table th, .data-table td {
            padding: 12px 15px;
            border: 1px solid var(--border-color);
            text-align: left;
        }

        .data-table th {
            background-color: var(--primary-color);
            color: white;
        }

        .data-table tr:nth-child(even) {
            background-color: #f1f5f9;
        }

        /* Listas Customizadas */
        .custom-list {
            list-style: none;
            margin: 20px 0;
        }

        .custom-list li {
            position: relative;
            padding-left: 25px;
            margin-bottom: 12px;
        }

        .custom-list li::before {
            content: "✓";
            position: absolute;
            left: 0;
            color: var(--success-color);
            font-weight: bold;
        }

        /* Sidebar Direita (Painel de Controle Escolar) */
        .sidebar {
            display: flex;
            flex-direction: column;
            gap: 30px;
        }

        .sticky-box {
            position: sticky;
            top: 30px;
            background-color: var(--card-bg);
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.03);
            border: 1px solid var(--border-color);
        }

        .sidebar h3 {
            color: var(--primary-color);
            font-size: 1.4rem;
            margin-bottom: 15px;
            border-bottom: 2px solid var(--border-color);
            padding-bottom: 8px;
        }

        .sidebar-links {
            list-style: none;
        }

        .sidebar-links li {
            margin-bottom: 12px;
        }

        .sidebar-links a {
            color: var(--secondary-color);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.2s;
        }

        .sidebar-links a:hover {
            color: var(--primary-color);
            text-decoration: underline;
        }

        .stat-tag {
            display: inline-block;
            background-color: #e1ecf4;
            color: #39739d;
            padding: 4px 8px;
            border-radius: 4px;
            font-size: 0.85rem;
            font-weight: bold;
            margin-top: 5px;
        }

        /* Footer */
        footer {
            background-color: #1d3557;
            color: white;
            text-align: center;
            padding: 40px 20px;
            margin-top: 60px;
        }

        footer p {
            margin-bottom: 10px;
            font-size: 1rem;
        }

        footer span {
            color: var(--accent-color);
            font-weight: bold;
        }
    </style>
</head>
<body>

    <div class="top-notice">
        DIRETRIZES DA SECRETARIA DE ESTADO DA EDUCAÇÃO DO PARANÁ (SEED-PR) — REFERENCIAL CURRICULAR ATUALIZADO
    </div>

    <header>
        <h1>Diretrizes do Novo Ensino Médio</h1>
        <p>Uma imersão profunda nos componentes obrigatórios de base regional: a formação territorial, a construção socioeconômica e a expressão artística do Paraná.</p>
    </header>

    <div class="main-wrapper">
        
        <!-- COLUNA ESQUERDA: AMPLO CONTEÚDO TEÓRICO -->
        <main class="content-area">
            
            <!-- INTRODUÇÃO REESTRUTURAÇÃO -->
            <section class="section-block">
                <h2>O Modelo Curricular Paranaense</h2>
                <p>A implementação do Novo...</p>
            </section>
        </main>
    </div>

</body>
</html>

       

