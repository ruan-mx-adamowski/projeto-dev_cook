# 🍳 DevCook — Catálogo Inteligente de Receitas

O **DevCook** é uma aplicação web responsiva projetada para facilitar a busca inteligente de receitas com base em ingredientes disponíveis na despensa do usuário, com suporte a filtros por restrições alimentares e categorias culinárias. Além do catálogo global, o sistema permite o cadastro de receitas autorais da comunidade e planejamento nutricional.

**Autor:** Ruan Matheus Adamowski Linhares

---

## 🚀 Tecnologias, Frameworks e APIs

Para o desenvolvimento da aplicação, foram selecionadas as seguintes tecnologias principais:

* **HTML5 & CSS3** — Estrutura semântica e estilização customizada.
* **Bootstrap (v5.3.3)** — Framework CSS para layout responsivo e componentes de interface.
* **JavaScript (ES6+) & jQuery (v3.7.1)** — Lógica de aplicação, manipulação do DOM e requisições assíncronas (AJAX/Fetch).
* **Spoonacular API (v1)** — API pública para busca inteligente de receitas e dados nutricionais.
* **JSON Server (v0.17.4)** — API REST local para simulação de persistência das receitas e usuários autorais.
* **ViaCEP API** — Preenchimento automático do endereço no cadastro do usuário.

---

## 💡 Justificativa das Escolhas de Engenharia e Design

### 1. Framework Frontend: Bootstrap 5.3
* **Justificativa Visual:** Fornece um sistema de *Grid System* (Flexbox/Grid) fluido e componentes pré-estilizados de alta qualidade (como Cards para exibição de pratos, Modais para detalhes da receita e Badges para tags dietéticas). Garante uma experiência consistente entre dispositivos *Mobile* e *Desktop*.
* **Justificativa Comercial/Técnica:** Reduz drasticamente o tempo de desenvolvimento (*Time-to-Market*) na prototipagem de telas, permitindo foco nas regras de negócio e integração com APIs sem a necessidade de construir um Design System do zero.

### 2. API Externa de Receitas: Spoonacular API
* **Justificativa Comercial:** É a solução mais completa do mercado para plataformas gastronômicas. Oferece suporte nativo a buscas refinadas por múltiplos ingredientes, filtros por intolerâncias (ex.: sem glúten, vegano) e traz dados nutricionais estruturados por porção.
* **Justificativa de Escalabilidade (Visão de Futuro):** A escolha da Spoonacular viabiliza a futura implementação da **Calculadora Nutricional** do DevCook sem a necessidade de alterar a arquitetura ou integrar fornecedores secundários de dados.

---

## 📚 Documentação Técnica

Para mais detalhes sobre as regras de negócio, endpoints e a modelagem do banco de dados:

* [Product Requirements Document (PRD)](./docs/prd.md) — Personas, requisitos e histórias de usuário.
* [Software Design Document (Architecture)](./docs/architecture.md) — Diagrama de banco de dados (DER em Mermaid), dependências e fluxo de dados.
* [Design System do Projeto](./docs/designsystem.md) — Guia de estilos e prototipagem.
* [Checklist de Indicadores de Desempenho](./docs/checklist.md) — Acompanhamento dos requisitos.

---

## 🎨 Protótipo e Design

* **Protótipo Interativo:** [Projeto no Stitch](https://stitch.withgoogle.com/projects/13453382550039179519)

---

## 📷Telas da Aplicação

## 🎨Paleta de Cores
<img width="333" height="185" alt="Cores" src="https://github.com/user-attachments/assets/38c38106-c8fc-44db-b272-75ee2898a71e" />

## 📱Mobile
### Cadastro
<img width="390" height="830" alt="screen" src="https://github.com/user-attachments/assets/e2cb268d-8fe7-4aaa-87d1-6e64dbd30bb4" />

### Login
<img width="390" height="648" alt="screen" src="https://github.com/user-attachments/assets/8fc3b0c4-0286-498c-ba76-6fa09d9c860d" />

### Explorar
<img width="390" height="1445" alt="screen" src="https://github.com/user-attachments/assets/4843b266-f726-4f99-b6b6-244d8badf577" />

## 💻Versão Desktop
<img width="1038" height="1600" alt="image" src="https://github.com/user-attachments/assets/906a5c7c-4386-470e-bdc8-25976ce298d2" />

<img width="1600" height="1280" alt="image" src="https://github.com/user-attachments/assets/60522f48-ff88-473f-8e7f-8f5417f2a91b" />

<img width="1600" height="1425" alt="image" src="https://github.com/user-attachments/assets/9337d9ba-8482-4b0c-b1b6-67608223666d" />
