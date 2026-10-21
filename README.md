# Quiz da Zélia — versão reconstruída

Site educacional responsivo de Língua Portuguesa com 150 questões, categorias, modo treino, modo avaliação, revisão, resultados, tema escuro e ranking online via Supabase e histórico local.

## Abrir e usar

**Opção rápida:** extraia o ZIP e abra `index.html` no navegador. O banco de questões está incluído no JavaScript para que a página abra mesmo sem servidor.

**No VS Code:** abra a pasta do projeto e, se preferir, execute com a extensão Live Server.

## Publicar gratuitamente no GitHub Pages

1. Entre no GitHub e crie um repositório novo chamado `quiz-da-zelia`.
2. Extraia este ZIP no computador.
3. Envie para a raiz do repositório **todos os arquivos e pastas que estão junto deste README**. O `index.html` precisa ficar na raiz, não dentro de outra pasta.
4. Faça o commit na branch `main`.
5. Abra **Settings → Pages** no repositório e, em **Build and deployment → Source**, escolha **GitHub Actions**.
6. Abra a aba **Actions** e aguarde o fluxo “Publicar Quiz da Zélia no GitHub Pages” terminar com sucesso.
7. A URL pública aparecerá em **Settings → Pages**. Na primeira publicação, pode levar alguns minutos.

O workflow de publicação já está incluído em `.github/workflows/pages.yml`.

## Questões

O arquivo editável é `data/questoes.json`. O arquivo `js/questions-data.js` contém uma cópia local do banco para que o quiz funcione também quando `index.html` é aberto diretamente. Se você editar as questões, mantenha os dois arquivos sincronizados.

Quantidade validada: Morfologia 50, Sintaxe 50, Semântica 20 e Estilística 30. As perguntas, alternativas e gabaritos recebidos foram preservados. Algumas explicações do material original são genéricas; elas não foram reescritas para não alterar silenciosamente o conteúdo pedagógico fornecido.

## Funcionalidades

- Seleção por categoria ou quiz completo.
- Filtro por dificuldade, com total atualizado antes de iniciar.
- Modo avaliação (gabarito só na revisão) e modo treino (feedback ao responder).
- Navegação anterior/próxima, alteração de respostas e aviso de questões pendentes.
- Resultado com acertos, erros, pendentes, porcentagem e duração.
- Revisão filtrada por acertos, erros e questões não respondidas.
- Ranking de avaliações armazenado no navegador atual.
- Tema escuro persistente quando o navegador permite armazenamento local.
- Layout responsivo para celular, tablet e computador.

## Limitações importantes

O histórico local continua no `localStorage`. A integração Supabase acrescenta um ranking online compartilhado; consulte `SUPABASE-INTEGRACAO.md` para configurar a chave pública e conhecer as limitações de segurança.

A fotografia em `assets/img/professora-zelia.jpg` é usada na tela inicial. Para trocar, substitua o arquivo mantendo o mesmo nome.


## Organização por tema

As 150 questões estão identificadas com um tema específico. Ao escolher uma das quatro áreas (Morfologia, Sintaxe, Semântica ou Estilística), use o campo **Escolha o tema específico** para praticar apenas aquele assunto. No **Quiz completo**, também é possível escolher um tema identificado pela área correspondente. A opção **Todos os temas** mantém o quiz da área inteira.


## Supabase

O código de integração está em `js/supabase.js`. Antes de publicar, configure a chave pública `sb_publishable_` nesse arquivo. Instruções e limites de segurança: `SUPABASE-INTEGRACAO.md`.
