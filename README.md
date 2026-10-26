# Selah ✳

Primeira versão de um leitor bíblico em português, com descoberta inspirada em streaming e um feed de reflexões editoriais.

## Executar

Node.js 22 ou 24. `npm ci --cache /tmp/selah-npm-cache`, depois `npm run dev`.

`npm run build` gera `dist/`. Publique essa pasta em Vercel, Netlify ou outro host estático. Vercel: preset Vite, build `npm run build`, output `dist`.

## Estrutura

- `src/main.js`: navegação, leitor, estudos, feed e persistência local.
- `src/styles/main.css`: sistema visual responsivo e temas.
- `public/data/`: duas Bíblias completas e registro de procedência/licença.
- `tests/`: verificações funcionais do navegador.
- `scripts/`: reservado para ferramentas de manutenção.

## Funciona nesta versão

Leitura dos 66 livros em Bíblia Livre e Bíblia Livre — Textus Receptus; troca de capítulos e tradução; busca por nome de livro; progresso e versículos salvos no navegador; exclusão de salvos; tema claro/escuro; estudo editorial de João 1; explorador piloto de “Palavra” em João 1:1; feed demonstrativo com links para passagens.

## Limites explícitos

Não há contas, sincronização, notícias em tempo real, vídeos selecionados, comentários ou alinhamento lexical geral. O piloto lexical responde ao toque/clique em “Palavra”; gesto dedicado de toque prolongado fica para próxima versão. Não apresenta as Bíblias como Almeida sem comprovação de origem editorial. Sem credenciais ou backend.

Fontes e atribuições dos textos: [public/data/SOURCES.md](public/data/SOURCES.md). Nenhuma notícia real ou fala fictícia de personagem é apresentada como fato.

## Testes

`npm test` usa Chromium do sistema quando disponível. Caso contrário, execute `PLAYWRIGHT_BROWSERS_PATH=/tmp/selah-browsers npx playwright install chromium` e `PLAYWRIGHT_BROWSERS_PATH=/tmp/selah-browsers npm test`. Os testes iniciam um servidor Vite e validam o leitor e a navegação em desktop e celular.
