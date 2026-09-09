# Product Requrimente Document(PRD) - DevCook

## 1. Descrição

O DevCook é uma aplicação web voltada para simplificar a rotina culinária de desenvolvedores, estudantes e entusiastas da cozinha. A proposta central é resolver o dilema comum de "não saber o que cozinhar com o que tem na geladeira", oferecendo uma busca inteligente baseada em ingredientes disponíveis, com receitas personalizadas.

## 2. Atores do Sistema
Pessoas com rotina corrida que buscam refeições práticas, usuários interessados em acompanhar a ingestão calórica/nutricional de suas refeições e entusiastas da culinária que desejam criar e organizar seu próprio livro de receitas digital.

## 3. História de usuário e escopo

### Módulo 1: Autenticação e Perfis
- **US01 - Criação de Conta:** Como um Visitante, quero preencher um formulário com meus dados (Nome, Email, Senha, CEP) para criar uma conta na plataforma.

    -*Critérios de Aceitação:* Todos os campos são obrigatórios; a senha deve ter no mínimo 6 caracteres e 1 caractere especial (validação por REGEX); o CEP deve buscar e preencher automaticamente o endereço via API do ViaCEP.

- **US02 - Acesso ao Sistema (Login):** Como um Usuário, quero inserir meu Email e Senha para acessar meu painel personalizado.

    -*Critérios de Aceitação:* O email deve estar cadastrado no sistema; em caso de credenciais incorretas, exibir mensagem clara de erro no lado cliente sem recarregar a página.

### Módulo 2: Busca e Catálogo de Receitas
- **US03 - Busca por Ingredientes:** Como um Visitante, quero digitar os ingredientes que tenho em casa na barra de pesquisa para encontrar receitas compatíveis.
  
    -*Critérios de Aceitação:* A busca deve consumir a API pública do TheMealDB em tempo real; se nenhum resultado for encontrado ou ocorrer falha de conexão, uma mensagem visual amigável deve ser exibida.

- **US04 - Filtragem por Categoria e Restrições:** Como um Usuário, quero selecionar categorias (Massas, Sobremesas) e restrições (Vegano, Low-Carb) usando seletores e botões para refinar os resultados exibidos.

    -*Critérios de Aceitação:* A filtragem deve atualizar os cards na tela sem recarregar a página, utilizando manipuladores de eventos e animações com jQuery.

### Módulo 3: Detalhes e Nutrição
- **US05 - Visualização de Detalhes da Receita:** Como um Visitante, quero clicar no card de um prato para abrir uma janela com a lista completa de ingredientes, modo de preparo e valor calórico.

   -*Critérios de Aceitação:* As informações detalhadas devem ser exibidas dentro de um Modal responsivo do Bootstrap.

### Módulo 4: Gerenciamento e Persistência
- **US06 - Favoritar Receitas:** Como um Usuário, quero clicar no ícone de estrela de qualquer receita para adicioná-la ou removê-la da minha lista de favoritos.

   -*Critérios de Aceitação:* A lista de favoritos deve ser persistida no localStorage do navegador para que o usuário não perca seus dados ao fechar a aba.

- **US07 - Cadastro de Receita Autoral:** Como um Usuário autenticado, quero preencher um formulário com título, tempo de preparo, ingredientes e foto para publicar minha própria receita.

   -*Critérios de Aceitação:* O tempo de preparo e os campos numéricos devem possuir máscara de formatação via jQuery Mask Plugin; o envio do formulário deve realizar uma requisição assíncrona POST para o JSON Server.

- **US08 - Painel "Minhas Receitas":** Como um Usuário, quero visualizar uma tela com todas as receitas que cadastrei na plataforma.

   -*Critérios de Aceitação:* As receitas devem ser recuperadas via requisição assíncrona GET ao JSON Server e renderizadas dinamicamente em uma grade de cards responsiva.
