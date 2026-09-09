# 🎨 DevCook — Design System

> **Versão:** Beta  
> **Status:** Em Produção  
> **Projeto:** DevCook

---

## 📄 Visão Geral & Princípios

O **DevCook Design System** foi criado para harmonizar a eficiência do universo de desenvolvimento com a energia da gastronomia. Ele serve de guia para garantir consistência visual, acessibilidade e fluidez na aplicação.

> [!TIP]
> **Tech & Taste (Sabor + Código):** Cores quentes ativam o apetite, enquanto a estrutura limpa e a tipografia técnica garantem agilidade na leitura de dados nutricionais e de preparo.

- **Scan-First:** Métricas como *tempo de preparo*, *calorias* e *restrições* são identificadas em milissegundos via badges e tipografia monospaced.
- **Componentização Responsiva:** Fluidez entre navegação touch (mobile chips/filtros) e layouts expansivos em grid (desktop).

---

## 🎨 Paleta de Cores (Design Tokens)

### CSS Variables (`variables.css`)

```css
:root {
  /* Brand / Primary - Laranja Chef */
  --color-primary: #FF6B35;
  --color-primary-hover: #E85D04;
  --color-primary-light: #FFE8DF;

  /* Secondary / Dev Slate */
  --color-secondary: #1E293B;
  --color-secondary-hover: #0F172A;
  --color-secondary-light: #334155;

  /* Highlights & Ações */
  --color-accent-star: #FFB703;
  --color-accent-amber: #F4A261;

  /* Neutros & Superfícies */
  --color-bg-main: #F8FAFC;
  --color-bg-card: #FFFFFF;
  --color-border: #E2E8F0;
  --color-text-main: #0F172A;
  --color-text-muted: #64748B;

  /* Badges de Restrição & Categoria */
  --badge-vegano-bg: #DCFCE7;
  --badge-vegano-text: #15803D;

  --badge-lowcarb-bg: #E0F2FE;
  --badge-lowcarb-text: #0369A1;

  --badge-massa-bg: #FEF3C7;
  --badge-massa-text: #B45309;

  /* Status & Feedback */
  --status-success: #10B981;
  --status-error: #EF4444;
  --status-warning: #F59E0B;
}

Leitores de Tela: Ícones de estado (como a estrela de favorito) devem possuir o atributo aria-label="Adicionar aos favoritos" ou aria-label="Remover dos favoritos" atualizado dinamicamente via JS.
