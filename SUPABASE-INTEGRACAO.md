# Integração com Supabase — Quiz da Zélia

O projeto está preparado para usar o projeto Supabase `Quiz Da Zelia` e a tabela `public.ranking`.

## 1. Configurar a chave pública

Abra `js/supabase.js` e substitua somente o valor de `PUBLISHABLE_KEY` pela chave pública que começa com `sb_publishable_`:

```js
const PUBLISHABLE_KEY = "COLE_AQUI_SUA_CHAVE_sb_publishable";
```

Use apenas a chave **Publishable** do projeto Supabase. Nunca coloque no site uma chave `sb_secret_` ou `service_role`.

## 2. O que é sincronizado

Quando uma avaliação termina, o resultado continua sendo salvo no histórico local e, se a configuração estiver preenchida, o site envia para `public.ranking` apenas:

- `nome`: nome/apelido, limitado a 20 caracteres;
- `pontuacao`: quantidade de acertos, entre 0 e 150;
- `tema`: categoria ou `Quiz completo`.

A coluna `criado_em` deve ser preenchida pelo valor padrão do banco. O site não envia respostas individuais nem gabaritos.

O ranking online lê `id`, `nome`, `pontuacao`, `tema` e `criado_em`. A interface mantém também o histórico local existente.

## 3. Publicar

Depois de salvar a chave pública no arquivo, envie os arquivos atualizados para o repositório do GitHub Pages. Não é necessário instalar SDK: a integração usa a API REST do Supabase.

## 4. Segurança

As políticas RLS da tabela precisam permitir `SELECT` e `INSERT` públicos conforme a configuração atual do projeto. Como não há autenticação de estudantes, um visitante tecnicamente experiente pode tentar enviar pontuações falsas diretamente à API. Este ranking é adequado como placar comunitário informal, não como registro inviolável de avaliação. Para pontuações confiáveis, será necessário validar resultados no servidor ou exigir autenticação e regras adicionais.
