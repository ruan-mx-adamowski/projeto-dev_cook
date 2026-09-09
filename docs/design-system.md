# 🎨 DevCook — Design System

> **Versão:** Beta  
> **Status:** Em Produção  
> **Projeto:** DevCook

---

## 📄 Visão Geral & Princípios
* Neste projeto, utilizamos um framework UI e aplicamos customizações para refletir a identidade visual do DevCook, combinando uma estética gastronômica, acolhedora e moderna com a eficiência e objetividade do universo de desenvolvimento de software.

### 1. Framework Base
Framework escolhido: Bootstrap 5
Motivação: Oferece uma estrutura de grid responsiva e componentes prontos (como Modais para exibição de receitas, Cards para o catálogo e Formulários para cadastro), facilitando a implementação ágil e garantindo compatibilidade no desenvolvimento com jQuery e requisições assíncronas.

### 2. Paleta de Cores (Customização)
* A identidade visual do DevCook utiliza uma base limpa e neutra, combinada com tons quentes vibrantes que despertam o apetite e tons frios de código que organizam a interface.

Cor Primária (Chef Orange): #FF6B35
Uso: Botões principais de ação (como "Cadastrar Receita"), destaques de foco, estados ativos e elementos primários. Transmite energia, culinária e apetite.
Cor Primária Escura: #E85D04
Uso: Estados de hover e interação nos elementos primários.
Cor Secundária (Dev Slate): #1E293B
Uso: Barra de navegação, cabeçalhos, botões secundários, filtros selecionados e elementos que remetem à estrutura de código/desenvolvimento.
Cor de Destaque (Amber Gold): #FFB703
Uso: Ícones de favoritar (estrelas), destaques de avaliações e alertas visuais de atenção.
Cor de Fundo (Background): #F8FAFC
Uso: Fundo principal das telas da aplicação.
Cor de Superfície: #FFFFFF
Uso: Cards de receita, formulários de cadastro, modais e container do painel do usuário.
Cor de Superfície Elevada: #F1F5F9
Uso: Barra de pesquisa de ingredientes, fundo de tags/badges e áreas secundárias dentro dos cards.
Cor de Texto Principal: #0F172A
Uso: Títulos, nomes de receitas e textos de maior relevância visual.
Cor de Texto Secundário: #64748B
Uso: Ingredientes, instruções de preparo, textos auxiliares e labels de formulários.
Cor de Erro: #EF4444
Uso: Mensagens de validação de formulário (como senha fora do padrão ou erro no CEP) e alertas de falha de conexão com a API.

### 3. Tipografia
* A tipografia do DevCook equilibra uma fonte moderna e amigável para a interface geral com uma fonte monoespaçada voltada à exibição rápida de parâmetros técnicos e nutricionais.

Títulos e Destaques: Plus Jakarta Sans, sans-serif (Peso: 700 a 800).
Textos Corridos e Formulários: Inter, sans-serif (Peso: 400 a 500).
Dados e Informações Numéricas: JetBrains Mono, monospace (Peso: 600).
Uso: Tempo de preparo, contagem de calorias (kcal), CEP e valores numéricos dos formulários.
Destaques: Categorias e badges utilizam texto em formato pílula com peso SemiBold para facilitar a leitura rápida (scan-first).

### 4. Diretrizes de Uso de Componentes
* Os componentes foram desenhados para otimizar a experiência de quem precisa decidir rapidamente o que cozinhar com os ingredientes que tem em casa.

Botões: Ações principais utilizam Chef Orange (#FF6B35) com texto claro. Ações secundárias ou de limpeza de filtro utilizam contorno (outline) em Dev Slate (#1E293B). O botão de favoritar utiliza estilo Ghost com o ícone de estrela em Amber Gold (#FFB703).
Cards: Utilizados para exibir as receitas do catálogo e do painel "Minhas Receitas". Possuem imagem de capa, badge de restrição alimentar, tempo de preparo, valor calórico e o ícone de favoritar.
Formulários: Os campos possuem fundo claro, bordas sutis e recebem contorno em Chef Orange quando estão em foco. Campos com máscaras (como o tempo de preparo) e busca automática (como o CEP via ViaCEP) possuem feedback visual integrado.
Chips / Badges: Utilizados para identificar categorias (Massas, Sobremesas) e restrições (Vegano, Low-Carb). Devem utilizar fundo suave com texto em tom escuro contrastante para leitura imediata.
Indicadores Numéricos: Métricas como "25 min" ou "450 kcal" utilizam JetBrains Mono acompanhadas de ícones para reforçar o caráter funcional da aplicação.
Barra de Pesquisa: Localizada em posição de destaque na tela "Explorar", permitindo a digitação dinâmica de ingredientes para consulta em tempo real à API do TheMealDB.
Navbar / Modal: A Navbar utiliza o tom Dev Slate com a marca clara. Os detalhes da receita abrem em um Modal responsivo do Bootstrap com divisões claras entre lista de ingredientes e modo de preparo.

### 5. Layout e Responsividade
* A aplicação utiliza um sistema de espaçamento baseado em uma grade de 8px, mantendo a interface leve e organizada.

* Espaçamento base: 8px
* Margem do container: 20px
* Espaçamento entre elementos: 16px
* Espaçamento entre seções: 40px

*O desenvolvimento segue o conceito de Mobile First, garantindo praticidade para o usuário que consulta receitas pelo celular enquanto está na cozinha.*
* Mobile: Organização em coluna única, barra de pesquisa de fácil acesso e botões com área de toque de no mínimo 44px.
* Desktop: Distribuição das receitas em grid de 3 a 4 colunas, com painel de filtros lateral e formulários centralizados.

### 6. Formas e Elevação
* A interface utiliza cantos suavemente arredondados para transmitir acolhimento, criando hierarquia visual por meio de camadas e bordas sutis.

Border Radius padrão: 8px (Inputs, botões e campos de texto)
Border Radius médio: 12px (Cards de receitas e containers de filtros)
Border Radius grande: 16px (Modais de detalhes da receita)
Elementos especiais: Pílulas de filtro e badges utilizam bordas totalmente arredondadas (9999px).
A profundidade é alcançada pelo contraste das superfícies e sombras suaves, evitando poluição visual.

Background: #F8FAFC
Surface: #FFFFFF
Surface elevada: #F1F5F9
Bordas: #E2E8F0
Estados ativos: Recebem destaque visual na cor primária com transições suaves via CSS/jQuery.

### 7. Identidade Visual
* A identidade do DevCook busca transmitir:

Sabor: através do tom quente Chef Orange nas ações principais.
Praticidade Dev: através de um layout limpo, direto ao ponto e otimizado para rotinas corridas.
Precisão: através da fonte JetBrains Mono na exibição de dados nutricionais, horários e formulários.
Tecnologia: através da integração fluida de APIs em tempo real, validações dinâmicas e persistência de dados no navegador.
Agilidade: através de filtros sem recarregamento de página, garantindo foco no que interessa: preparar a refeição.
