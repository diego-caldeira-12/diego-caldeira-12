# Configuração do perfil — passos que dependem de você

O README já está pronto. Alguns widgets precisam de segredos/ações que só você pode fazer (envolvem suas contas). Lista curta:

## 1. WakaTime — Tempo de Código (a seção fica vazia até isso)

1. Crie conta em https://wakatime.com e copie sua **API Key** (Settings → API Key).
2. Instale a extensão **WakaTime** no VS Code e cole a API Key quando pedir.
3. No GitHub: repo `diego-caldeira-12` → **Settings → Secrets and variables → Actions → New repository secret**:
   - Nome: `WAKATIME_API_KEY`
   - Valor: sua API Key
4. Rode o workflow uma vez: aba **Actions → WakaTime → Run workflow**.

> Começa vazio e enche conforme você programa. É normal levar alguns dias pra ficar bonito.

## 2. Skyline 3D — secret `PAT_TOKEN`

O workflow `3d-contrib.yml` já roda diariamente, mas precisa de um Personal Access Token.

1. GitHub → **Settings (conta) → Developer settings → Personal access tokens → Tokens (classic)** → Generate.
   - Escopos: `repo` e `read:user`.
2. Repo → **Settings → Secrets → Actions** → secret `PAT_TOKEN` com esse token.
3. Aba **Actions → GitHub-Profile-3D-Contrib → Run workflow** pra gerar na hora.

## 3. Snake — já funciona

O workflow `snake.yml` gera a animação na branch `output` a cada 12h. Já existe. Se quiser atualizar na hora: **Actions → Generate Snake Animation → Run workflow**.

## 4. (Opcional, recomendado) Stats à prova de bala — self-host do github-readme-stats

As instâncias públicas do `github-readme-stats` vivem caindo (erro 503 / "Maximum retries exceeded"). Como você usa Vercel, self-hospede a sua:

1. Faça fork de https://github.com/anuraghazra/github-readme-stats
2. Importe no Vercel (New Project → seu fork).
3. Em **Environment Variables**, crie `PAT_1` = um GitHub token (escopo `repo`).
4. Deploy. Vai gerar algo como `https://SEU-PROJETO.vercel.app`.
5. No README (PT e EN), troque **todas** as ocorrências de
   `https://github-readme-stats.vercel.app` por `https://SEU-PROJETO.vercel.app`.
   (São os cards de **GitHub Stats** e **Top Languages**.)

Isso mata o 503 de vez e deixa o **Top Languages** confiável (já configurado com `hide=jupyter notebook,html,css` pra sua linguagem principal não cair em "Others").

## 5. Links de projeto que faltam (opcional)

Dois projetos do destaque estão sem link no ar (código privado):

- **Comparador de Preços**
- **Contempla Já**

Se eles tiverem URL pública (Vercel/domínio), me passe que eu transformo o card em link clicável. Senão ficam como "código privado" mesmo.

## 6. Bilíngue

- `README.md` = Português (o que aparece no seu perfil).
- `README.en.md` = Inglês (um clique no topo).
- Ao editar um, lembre de refletir no outro pra não divergirem.
