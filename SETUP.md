# Configuração do perfil — passos que dependem de você

O README já está pronto e os widgets de stats agora usam fontes confiáveis
(`github-profile-summary-cards` e `streak-stats.demolab.com`) — **não precisa
self-host de nada.** Sobraram poucas ações, todas suas:

## 1. Skyline 3D — secret `PAT_TOKEN`

O workflow `3d-contrib.yml` roda diariamente, mas precisa de um Personal Access Token.

1. GitHub → **Settings (conta) → Developer settings → Personal access tokens → Tokens (classic)** → Generate.
   - Escopos: `repo` e `read:user`.
2. Repo `diego-caldeira-12` → **Settings → Secrets and variables → Actions** → secret `PAT_TOKEN` com esse token.
3. Aba **Actions → GitHub-Profile-3D-Contrib → Run workflow** pra gerar na hora.

> Os SVGs já existem na pasta `profile-3d-contrib/`, então a skyline já aparece. O secret só garante a atualização automática.

## 2. Snake — já funciona

O workflow `snake.yml` gera a animação na branch `output` a cada 12h. Já está no ar. Atualizar na hora: **Actions → Generate Snake Animation → Run workflow**.

## 3. Links de projeto que faltam (opcional)

Dois cards do destaque estão sem link no ar (código privado):

- **Comparador de Preços**
- **Contempla Já**

Se tiverem URL pública (Vercel/domínio), me passe que eu transformo o card em link clicável. Senão ficam marcados como "Código privado".

## 4. WakaTime — opcional (desativado por padrão)

O card **productive-time** já mostra "tempo/horário de código" com dados reais do GitHub, sem plugin. Por isso o WakaTime saiu do README e o workflow `waka.yml` ficou como *manual only* (não fica mais falhando sozinho).

Se um dia quiser o WakaTime de verdade:
1. Conta em https://wakatime.com → copie a **API Key**.
2. Extensão **WakaTime** no VS Code (cole a key).
3. Secret `WAKATIME_API_KEY` no repo (Settings → Secrets → Actions).
4. Readicione os marcadores no README onde quer o bloco:
   ```
   <!--START_SECTION:waka-->
   <!--END_SECTION:waka-->
   ```
5. **Actions → WakaTime → Run workflow**.

## 5. Bilíngue

- `README.md` = Português (o que aparece no seu perfil).
- `README.en.md` = Inglês (um clique no topo).
- Ao editar um, reflita no outro pra não divergirem.
