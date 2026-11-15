# Explorador SIGTAP (GitHub + Vercel)

Página estática para pesquisa de procedimentos, descrições e atributos da Tabela SIGTAP (CBOs exigidos, Serviço/Classificação, Instrumento de Registro, CID-10, valores e compatibilidades).

## Estrutura do projeto

- `index.html` — Aplicação web autossuficiente (lê arquivos `*_layout.txt` e `.txt` em `ISO-8859-1` direto no navegador).
- `vercel.json` — Desativa o cache da pasta `dados/` para garantir que a atualização mensal apareça imediatamente para todas as unidades.
- `dados/sigtap_atual.zip` — *(você adiciona aqui)* Pacote mensal oficial baixado no portal do SIGTAP/DATASUS, renomeado para `sigtap_atual.zip`.

## Como publicar na Vercel

1. Crie um repositório no **GitHub** (público ou privado) e envie todos os arquivos desta pasta.
2. Coloque o `.zip` da competência vigente dentro de `dados/` com o nome exato **`sigtap_atual.zip`**.
3. Acesse a **Vercel**, faça login com o GitHub e clique em **Add New → Project**.
4. Selecione o repositório:
   - **Framework Preset:** `Other`
   - **Build Command:** *(deixe vazio)*
   - **Output Directory:** *(deixe vazio)*
5. Clique em **Deploy**.

Ao abrir a URL gerada, a página carregará automaticamente o arquivo `dados/sigtap_atual.zip`. Caso o arquivo ainda não tenha sido adicionado, ela iniciará em modo de demonstração e permitirá o carregamento manual pelos botões no topo.

## Atualização mensal

1. Baixe o novo pacote de estruturação no portal do SIGTAP.
2. Substitua o arquivo `dados/sigtap_atual.zip` no repositório do GitHub.
3. A Vercel atualizará o site automaticamente em cerca de 30 segundos.
