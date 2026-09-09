# Design System

1. Visão Geral & Princípios de Design
Sabor + Código (Tech & Taste): A interface deve transmitir calor e apetite (tons quentes e vibrantes) mantendo a estrutura limpa, objetiva e legível típica de ferramentas para desenvolvedores.

Agilidade no Fluxo (Scan-first): Informações como tempo de preparo, valor calórico e restrições alimentares devem ser lidas em segundos através de badges, tipografia mono-espaçada para métricas e hierarquia clara.

Componentização Responsiva: Fluidez entre a navegação mobile (orientada a toque e navegação inferior/chips) e desktop (grades expansivas e menus estruturados).

2. Paleta de Cores (Design Tokens)
As cores foram divididas para garantir alto contraste (Acessibilidade WCAG AA), destaque para as refeições e identificação de ações.

CSS
:root {
  /* Brand / Primary - Laranja Chef (Energia, Culinária) */
  --color-primary: #FF6B35;
  --color-primary-hover: #E85D04;
  --color-primary-light: #FFE8DF;

  /* Secondary / Dev Slate (Estrutura, Código, Contraste) */
  --color-secondary: #1E293B;
  --color-secondary-hover: #0F172A;
  --color-secondary-light: #334155;

  /* Accent / Highlights */
  --color-accent-star: #FFB703; /* Ícone de Favorito / Estrela */
  --color-accent-amber: #F4A261;

  /* Neutros & Superfícies */
  --color-bg-main: #F8FAFC;     /* Fundo da aplicação */
  --color-bg-card: #FFFFFF;     /* Fundo de cards e modais */
  --color-border: #E2E8F0;      /* Divisores e bordas de inputs */
  --color-text-main: #0F172A;   /* Títulos e textos principais */
  --color-text-muted: #64748B;  /* Subtítulos e labels secundárias */

  /* Categorias & Restrições Alimentares (Badges) */
  --badge-vegano-bg: #DCFCE7;
  --badge-vegano-text: #15803D;

  --badge-lowcarb-bg: #E0F2FE;
  --badge-lowcarb-text: #0369A1;

  --badge-massa-bg: #FEF3C7;
  --badge-massa-text: #B45309;

  /* Status / Feedback */
  --status-success: #10B981;
  --status-error: #EF4444;
  --status-warning: #F59E0B;
}
3. Tipografia
O sistema utiliza Plus Jakarta Sans (ou Inter) para a interface geral devido à excelente legibilidade em telas, e JetBrains Mono (ou Fira Code) para métricas e dados técnicos, reforçando a identidade "Dev".

Fonte Primária (UI & Textos): 'Plus Jakarta Sans', 'Inter', sans-serif

Fonte Secundária / Código (Métricas, Tempo, Calorias): 'JetBrains Mono', monospace

Escala Tipográfica
Nível	Tamanho	Peso	Line-Height	Aplicação
Display / H1	28px (Mob) / 36px (Desk)	Bold (700)	1.2	Títulos principais das telas
H2	20px (Mob) / 24px (Desk)	SemiBold (600)	1.3	Títulos de Seção e Modal
H3 / Card Title	16px (Mob) / 18px (Desk)	SemiBold (600)	1.4	Nome da Receita nos Cards
Body	14px / 16px	Regular (400)	1.5	Textos, formulários, descrições
Caption / Badge	12px	Medium (500)	1.2	Categorias, etiquetas, CEP
Mono Metrics	13px	SemiBold (600)	1.0	Tempo de preparo, Kcal, Ingredientes
4. Espaçamento, Grid e Breakpoints
Baseado no sistema de grid de 8px para manter simetria e alinhamento visual.

Espaçamentos padrão: 4px (xs), 8px (sm), 16px (md), 24px (lg), 32px (xl), 48px (2xl).

Border Radius:

Inputs, Chips & Badges: 8px ou 999px (Pill format para filtros)

Cards e Modais: 16px

Botões: 10px

Breakpoints (Compatíveis com Bootstrap 5)
Mobile (portrait): < 576px (Layout em coluna única, barra de busca fixa ou navegação simplificada)

Tablet: ≥ 768px (Grid de 2 colunas para cards)

Desktop: ≥ 992px a 1200px+ (Grid de 3 a 4 colunas de receitas, barra lateral para filtros e criação de receita em container centralizado)

5. Biblioteca de Componentes
5.1 Botões
HTML
<!-- Botão Primário (Ação Principal / Salvar / Cadastrar) -->
<button class="btn btn-primary-devcook">
  Cadastrar Receita
</button>

<!-- Botão Secundário / Outlined -->
<button class="btn btn-outline-devcook">
  Limpar Filtros
</button>

<!-- Botão de Favorito (Icon Button) -->
<button class="btn-favorite" aria-label="Favoritar receita">
  <svg class="star-icon active" ...></svg> <!-- Amarelo (#FFB703) quando ativo -->
</button>
Estilos do Botão Primário:

Background: --color-primary (#FF6B35)

Text: #FFFFFF (Font-weight: 600)

Hover: --color-primary-hover com transição CSS de 0.2s ease

Active/Focus: Shadow suave 0 0 0 3px rgba(255, 107, 53, 0.3)

5.2 Formulários, Inputs & Validações
Alinhados aos requisitos do PRD (US01 - ViaCEP / Senha REGEX e US07 - Máscaras via jQuery Mask Plugin).

Input Padrão: Altura 48px, Borda 1px solid --color-border, Padding 12px 16px, Raio 8px.

Estado de Erro (Senha / Credencial Incorreta): Borda --status-error, texto auxiliar abaixo do campo em 12px vermelho.

Feedback Assíncrono (ViaCEP): Indicador visual de carregamento dentro do campo de CEP enquanto busca os dados do endereço.

HTML
<!-- Exemplo de Estrutura de Campo -->
<div class="form-group mb-3">
  <label for="cep" class="form-label">CEP</label>
  <input type="text" id="cep" class="form-control cep-mask" placeholder="00000-000" required>
  <small class="form-text text-muted" id="cep-feedback">Buscando endereço automaticamente...</small>
</div>
5.3 Cards de Receita (Catalogo / Minhas Receitas)
O card é a peça central do DevCook. Ele exibe informações essenciais sem poluição visual.

HTML
<div class="recipe-card">
  <div class="recipe-card-header">
    <img src="foto-receita.jpg" alt="Título da Receita" class="recipe-img">
    <span class="badge badge-vegano">Vegano</span>
    <button class="btn-favorite active" title="Remover dos Favoritos">
      ★
    </button>
  </div>
  <div class="recipe-card-body">
    <h3 class="recipe-title">Macarrão ao Pesto de Manjericão</h3>
    <div class="recipe-metrics">
      <span class="metric-item">⏱️ <font face="JetBrains Mono">25 min</font></span>
      <span class="metric-item">🔥 <font face="JetBrains Mono">450 kcal</font></span>
    </div>
  </div>
</div>
Estilo do Card:

Fundo: --color-bg-card (#FFFFFF)

Borda: 1px solid --color-border

Sombra: 0 4px 6px -1px rgba(0, 0, 0, 0.05)

Hover Effect: Elevação com transform: translateY(-4px) e sombra 0 10px 15px -3px rgba(0, 0, 0, 0.1).

5.4 Filtros & Chips (Categorias e Restrições - US04)
Pills selecionáveis que interagem dinamicamente via jQuery sem recarregar a página.

Estado Inativo: Fundo --color-bg-main, Texto --color-text-muted, Borda 1px solid --color-border.

Estado Ativo (Selecionado): Fundo --color-secondary (#1E293B), Texto #FFFFFF, Borda --color-secondary.

5.5 Modal de Detalhes da Receita (Bootstrap - US05)
Abertura responsiva contendo:

Header com Imagem de Capa: Altura fixa (200px mobile, 300px desktop) com efeito overlay.

Barra de Destaques Nutricionais: Grid com calorias, tempo de preparo e porções.

Lista de Ingredientes: Checkbox simples para ajudar o usuário a checar o que já tem enquanto cozinha.

Modo de Preparo: Passos numerados em fonte limpa e espaçada.

6. Guias de Animação e Microinterações
Para garantir a melhor experiência do usuário (especialmente usando jQuery e interações em tempo real):

Favoritar (US06): Animação de scale(1.3) rápida no ícone de estrela quando clicado, transicionando de transparente para --color-accent-star.

Filtragem de Receitas (US04): Ao aplicar um filtro de categoria ou buscar por ingredientes, utilizar .fadeIn() e .fadeOut() do jQuery suavemente (duração 200ms) nos cards de receitas.

Modal de Detalhes (US05): Transição padrão de fade suave no backdrop e slide de baixo para cima (slideUp) em dispositivos móveis.

Mensagens de Erro/Sucesso: Alertas e toasts flutuantes no canto inferior da tela (Mobile) ou superior direito (Desktop), sumindo automaticamente em 3 segundos.

7. Diretrizes de Acessibilidade (a11y)
Navegação por Teclado: Todos os cards, botões de favoritos e campos de busca devem conter estados :focus-visible visíveis (outline de 2px na cor --color-primary).

Contraste de Texto: Textos sobre a cor primária laranja (#FF6B35) utilizam obrigatoriamente a cor branca (#FFFFFF), atingindo a razão de contraste WCAG AA.

Leitores de Tela: Ícones de estado (como a estrela de favorito) devem possuir o atributo aria-label="Adicionar aos favoritos" ou aria-label="Remover dos favoritos" atualizado dinamicamente via JS.
