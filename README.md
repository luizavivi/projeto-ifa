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
                <p>A implementação do Novo Ensino Médio no estado do Paraná buscou equilibrar a Formação Geral Básica (FGB), alinhada à BNCC, com os Itinerários Formativos. Em resposta às demandas pedagógicas locais, a rede estadual focou esforços na recomposição de conteúdos fundamentais de matriz regional. Isso significa que, independentemente da trilha escolhida pelo estudante, os fundamentos de <strong>Geografia</strong>, <strong>História</strong> e <strong>Cultura local</strong> são trabalhados de forma transversal e aprofundada.</p>
                
                <div class="highlight-box">
                    "O objetivo primordial não é apenas preparar o estudante para avaliações externas como o ENEM ou o Vestibular da UFPR, mas sim construir uma consciência cidadã ligada diretamente à infraestrutura, economia e herança histórica de seu próprio estado."
                </div>
                
                <p>Abaixo, detalhamos extensivamente os três pilares que sustentam os cadernos de Ciências Humanas e Linguagens do estado.</p>
            </section>

            <!-- SEÇÃO 1: GEOGRAFIA DO PARANÁ -->
            <section class="section-block" id="geografia">
                <h2>1. Geografia do Paraná: Espaço, Fronteiras e Produção</h2>
                <img src="https://images.unsplash.com/photo-1619546813926-a78fa6372cd2?auto=format&fit=crop&w=1200&q=80" alt="Campos de agricultura mecanizada no Paraná" class="topic-header-image">
                
                <p>O estudo geográfico do Paraná compreende a análise crítica de um território de transição física e econômica. O estado serve de elo entre a pujança industrial do Sudeste e a força agropecuária do Sul do Brasil, estruturando-se através de sistemas modernos de logística e biomas altamente modificados pela ação antrópica.</p>
                
                <div class="sub-grid">
                    <div class="info-pane">
                        <h3>Para que serve?</h3>
                        <p>Serve para decodificar os arranjos espaciais e os vetores de desenvolvimento regional. Ao compreender a morfologia do relevo paranaense, o aluno entende por que o agronegócio se fixou fortemente no Norte e Oeste do estado, bem como a importância da preservação das poucas áreas remanescentes da Mata de Araucárias e da Mata Atlântica na Serra do Mar.</p>
                    </div>
                    <div class="info-pane pane-alt">
                        <h3>Como é o conteúdo nas salas?</h3>
                        <p>O conteúdo debruça-se sobre dados geomorfológicos, demográficos e estatísticos do Ipardes. Estuda-se a classificação do relevo feita por Reinhard Maack (Litoral, Primeiro, Segundo e Terceiro Planalto), as principais malhas rochosas que originaram a famosa 'Terra Roxa' fértil, e a inserção das cooperativas agroindustriais na economia globalizada.</p>
                    </div>
                </div>

                <h3 style="margin-top:30px; color: var(--primary-color);">Tabela de Perfil da Divisão Territorial Geográfica</h3>
                <table class="data-table">
                    <thead>
                        <tr>
                            <th>Unidade de Relevo</th>
                            <th>Principais Cidades Polo</th>
                            <th>Características Econômicas Dominantes</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td><strong>Litoral e Baixada</strong></td>
                            <td>Paranaguá, Matinhos, Guaratuba</td>
                            <td>Atividade portuária internacional, turismo e pesca regional.</td>
                        </tr>
                        <tr>
                            <td><strong>Primeiro Planalto</strong></td>
                            <td>Curitiba, Região Metropolitana, Lapa</td>
                            <td>Polo industrial metal-mecânico, setor de serviços e administração pública.</td>
                        </tr>
                        <tr>
                            <td><strong>Segundo Planalto</strong></td>
                            <td>Ponta Grossa, Castro, Telêmaco Borba</td>
                            <td>Pecuária leiteira de alta tecnologia, indústria de papel/celulose e turismo mineral.</td>
                        </tr>
                        <tr>
                            <td><strong>Terceiro Planalto</strong></td>
                            <td>Londrina, Maringá, Cascavel, Foz do Iguaçu</td>
                            <td>Agronegócio de exportação (soja e milho), agroindústrias e turismo internacional (Cataratas).</td>
                        </tr>
                    </tbody>
                </table>
            </section>

            <!-- SEÇÃO 2: ARTE PARANAENSE -->
            <section class="section-block" id="arte">
                <h2>2. Arte Paranaense: Identidade Visual e Movimentos Históricos</h2>
                <img src="https://images.unsplash.com/photo-1579783902614-a3fb3927b6a5?auto=format&fit=crop&w=1200&q=80" alt="Pinturas e paleta de cores artísticas" class="topic-header-image">
                
                <p>A cultura e as manifestações artísticas do Paraná não se limitam ao artesanato folclórico. O currículo estadual explora a consolidação de academias de artes plásticas, escolas de música e o design modernista que redefiniram o panorama urbano, com fortes traços das comunidades de imigrantes europeus, asiáticos e da cultura afro-brasileira/indígena.</p>
                
                <div class="sub-grid">
                    <div class="info-pane">
                        <h3>Para que serve?</h3>
                        <p>Serve para expandir o repertório crítico dos estudantes, criando uma ponte entre o patrimônio histórico edificado e as artes visuais contemporâneas. Analisar a arte local faz com que os alunos valorizem monumentos públicos, identifiquem estilos arquitetônicos em suas cidades e entendam como a propaganda identitária usou elementos da fauna e flora para criar a imagem mítica do Paraná.</p>
                    </div>
                    <div class="info-pane pane-alt">
                        <h3>Como é o conteúdo nas salas?</h3>
                        <p>Os professores de Linguagens trabalham com análises de obras de arte, visitas virtuais ou presenciais a museus como o MON (Museu Oscar Niemeyer) e o MAE (Museu de Arqueologia e Etnologia). Destaca-se a evolução do academicismo tradicional até o abstracionismo e a arte urbana/grafite moderna.</p>
                    </div>
                </div>

                <h3 style="margin-top:30px; color: var(--primary-color);">Principais Eixos Artísticos Estudados</h3>
                <ul class="custom-list">
                    <li><strong>O Movimento Paranista:</strong> Liderado por intelectuais e artistas na década de 1920 (como João Turin), utilizou as formas do pinhão, das folhas da araucária e a figura da ave grimpa para desenhar fachadas, esculturas e calçadas, fixando um estilo visual único para o estado.</li>
                    <li><strong>Precursores das Belas Artes:</strong> O legado de Alfredo Andersen (considerado o pai da pintura paranaense) e de suas discípulas pioneiras, como Antonieta de Barros, que consolidaram o ensino formal de desenho e pintura.</li>
                    <li><strong>A Gravura e o Muralismo:</strong> O trabalho icônico de Poty Lazzarotto, cujos traços em azulejos e concreto contam a história do trabalhador, dos ciclos econômicos e estão cravados em praças públicas de dezenas de municípios paranaenses.</li>
                </ul>
            </section>

            <!-- SEÇÃO 3: HISTÓRIA DO PARANÁ -->
            <section class="section-block" id="historia">
                <h2>3. História do Paraná: Conflitos, Ocupação e Emancipação</h2>
                <img src="https://images.unsplash.com/photo-1543783207-ec64e4d95325?auto=format&fit=crop&w=1200&q=80" alt="Documento histórico antigo simbolizando registro do passado" class="topic-header-image">
                
                <p>A historiografia paranaense é marcada por disputas geopolíticas intensas, que vão desde os limites territoriais coloniais traçados por tratados entre Portugal e Espanha até sangrentas revoltas populares no século XX. Estudar esse processo desmistifica a ideia de uma ocupação pacífica e puramente europeia.</p>
                
                <div class="sub-grid">
                    <div class="info-pane">
                        <h3>Para que serve?</h3>
                        <p>Serve para combater o anacronismo e o esquecimento histórico. Entender o papel das frentes de expansão paulistas, a escravização das populações indígenas nas missões jesuíticas, e a importância da mão de obra negra nos caminhos das tropas e engenhos de mate permite compreender as profundas desigualdades estruturais que ainda persistem na sociedade.</p>
                    </div>
                    <div class="info-pane pane-alt">
                        <h3>Como é o conteúdo nas salas?</h3>
                        <p>O foco pedagógico está na análise de fontes documentais, mapas históricos e relatos orais. Debate-se de que forma as elites agrárias do café e do mate articularam a emancipação política da Província em 1853 (separando-se de São Paulo) e como o Estado promoveu a colonização planejada do Norte e Oeste.</p>
                    </div>
                </div>

                <h3 style="margin-top:30px; color: var(--primary-color);">Linha do Tempo dos Ciclos e Conflitos Decisivos</h3>
                <table class="data-table">
                    <thead>
                        <tr>
                            <th>Período Histórico</th>
                            <th>Evento / Ciclo Econômico</th>
                            <th>Impacto Social e Político</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>Séculos XVI - XVII</td>
                            <td>Guairá e Missões Jesuíticas</td>
                            <td>Disputas hispano-lusitanas; destruição das reduções por bandeirantes paulistas à caça de indígenas.</td>
                        </tr>
                        <tr>
                            <td>Séculos XVIII - XIX</td>
                            <td>O Tropeirismo e Caminho das Tropas</td>
                            <td>Fundação de vilas nos campos gerais (Castro, Lapa, Ponta Grossa) e abastecimento de feiras paulistas com gado e muares.</td>
                        </tr>
                        <tr>
                            <td>1853</td>
                            <td>Emancipação Política do Paraná</td>
                            <td>Desmembramento da antiga Comarca de Paranaguá da Província de São Paulo; instalação do primeiro presidente, Zacarias de Góis.</td>
                        </tr>
                        <tr>
                            <td>1912 - 1916</td>
                            <td>A Guerra do Contestado</td>
                            <td>Guerra civil camponesa messiânica na fronteira com Santa Catarina contra grandes empresas ferroviárias estrangeiras e forças estatais.</td>
                        </tr>
                        <tr>
                            <td>Meados do Século XX</td>
                            <td>A Marcha para o Norte e a Epopeia do Café</td>
                            <td>Colonização massiva atraindo mineiros, paulistas e imigrantes; explosão demográfica de cidades planejadas como Londrina e Maringá.</td>
                        </tr>
                    </tbody>
                </table>
            </section>

        </main>

        <!-- COLUNA DIREITA: SIDEBAR INFORMATIVA -->
        <aside class="sidebar">
            <div class="sticky-box">
                <h3>Navegação Rápida</h3>
                <ul class="sidebar-links">
                    <li><a href="#geografia"># Geografia Territorial</a></li>
                    <li><a href="#arte"># Expressão e Movimento Paranista</a></li>
                    <li><a href="#historia"># Ciclos de Ocupação Histórica</a></li>
                </ul>

                <h3 style="margin-top: 30px;">Estrutura Complementar</h3>
                <p style="font-size: 0.9rem; margin-bottom: 15px;">Os temas regionais também ganham força em avaliações internas e projetos eletivos organizados pelas escolas:</p>
                
                <div>
                    <strong>Prova Paraná</strong>
                    <p style="font-size: 0.85rem; color: var(--text-light)">Avaliação diagnóstica bimestral aplicada em toda a rede pública estadual para medir a absorção dos conteúdos de Ciências Humanas.</p>
                    <span class="stat-tag">Foco em Leitura de Gráficos e Fontes</span>
                </div>

                <div style="margin-top: 20px;">
                    <strong>Itinerários de Humanas</strong>
                    <p style="font-size: 0.85rem; color: var(--text-light)">Aprofundamentos voltados a debates sociopolíticos, geopolítica global vs. local e estudos ambientais das bacias hidrográficas paranaenses.</p>
                    <span class="stat-tag">Matriz Curricular Obrigatória</span>
                </div>
            </div>
        </aside>

    </div>

    <footer>
        <p>Portal Técnico de Estudos Educacionais — Diretrizes Curriculares do Paraná</p>
        <p>Desenvolvido para uso acadêmico e suporte no editor de código <span>Visual Studio Code</span>.</p>
    </footer>

</body>
</html>
