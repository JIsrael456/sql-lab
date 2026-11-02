# SQL Lab Academy

Laboratório interativo para praticar consultas SQL diretamente no navegador, com **30 desafios** distribuídos em três níveis: **Iniciante, Intermediário e Avançado** (10 exercícios por nível).

**[Abrir a aplicação](https://jisrael456.github.io/sql-lab/)** · **[Estudo de caso no portfólio](https://jisrael456.github.io/projetos/sql-lab.html)**

## Objetivo

Oferecer um ambiente de prática com dados fictícios, editor de consultas, execução real de SQL e feedback sobre os resultados, sem exigir instalação local de um banco de dados.

## Tecnologias

- **HTML e CSS:** interface responsiva com tema escuro.
- **JavaScript:** navegação entre desafios, controle do editor, feedback e progresso.
- **SQLite via sql.js / WebAssembly:** execução das consultas no navegador.
- **localStorage:** armazenamento de rascunhos e exercícios concluídos neste navegador.
- **GitHub Pages:** publicação estática.

> O carregamento inicial do mecanismo SQLite depende de arquivos hospedados em CDN e requer conexão com a internet. O progresso salvo é local ao navegador/dispositivo e não é sincronizado com uma conta.

## Funcionalidades implementadas

- 30 desafios, com 10 em cada nível.
- Editor SQL e botão **Executar SQL**.
- Botão **Verificar resposta** com comparação do resultado da consulta com o resultado de referência.
- Dicas e soluções que podem ser exibidas durante o exercício.
- Visualização tabular dos resultados.
- Consulta à estrutura das tabelas disponíveis.
- Indicador de progresso total e por nível.
- Salvamento local de rascunhos e desafios concluídos.
- Atalho **Ctrl+Enter** (ou **Cmd+Enter**) para executar a consulta.
- Opção de limpar o progresso local.

## Como a validação funciona

A aplicação executa a consulta enviada e a consulta de referência em bancos SQLite inicializados com o mesmo conjunto de dados. A verificação compara:

1. Os nomes das colunas, desconsiderando diferenças entre maiúsculas e minúsculas.
2. Os valores retornados, com arredondamento numérico interno para a comparação.
3. O conjunto de linhas, sem exigir a mesma ordem.

Isso significa que **consultas SQL diferentes podem ser aceitas** quando produzem o resultado esperado. A validação não demonstra equivalência lógica para todos os conjuntos de dados possíveis: ela confere os resultados na base de exercícios fornecida.

## Banco de dados de prática

O aplicativo disponibiliza tabelas fictícias de **setores, colaboradores, projetos, participações, clientes e chamados**. Os desafios trabalham progressivamente com seleção, filtros, ordenação, agregações, junções, subconsultas e funções analíticas.

## Como utilizar

1. Abra a [aplicação publicada](https://jisrael456.github.io/sql-lab/).
2. Selecione um nível e um dos dez desafios.
3. Leia o enunciado e consulte a estrutura das tabelas.
4. Escreva a consulta no editor e clique em **Executar SQL**.
5. Confira os resultados e use **Verificar resposta** para validar.
6. Avance para os próximos exercícios; seu progresso fica salvo no navegador.

## Como executar localmente

O projeto está concentrado em `index.html`. Você pode abrir esse arquivo em um navegador moderno ou servi-lo por um servidor estático local. Para carregar o SQLite WebAssembly a partir da CDN, é necessário acesso à internet.

## Limitações e decisões de implementação

- O editor aceita consultas iniciadas com `SELECT` ou `WITH`; comandos de alteração do banco são bloqueados pela aplicação.
- A verificação de comandos proibidos é uma restrição didática baseada em texto, **não um mecanismo de segurança para executar SQL não confiável em servidor**.
- Cada execução usa um banco de exercícios recém-inicializado, evitando que uma consulta altere o estado das próximas atividades.
- O progresso salvo em `localStorage` pode desaparecer se os dados do navegador forem apagados.
- A validação se baseia na saída esperada para a base atual e não em uma análise semântica geral da consulta.

## Próximas melhorias possíveis

- Testes automatizados para as consultas de referência.
- Recursos adicionais de acessibilidade e navegação por teclado.
- Exportação e importação do progresso.
- Mais desafios e conjuntos de dados.

## Autor

**Jacó Israel** · [Portfólio](https://jisrael456.github.io/) · [LinkedIn](https://www.linkedin.com/in/jaco-israel/)
