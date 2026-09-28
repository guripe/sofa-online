# 🍿 Sofá Online

Site para compartilhar a tela e assistir séries/vídeos com os amigos, com chat e reações.
É um site estático (um único `index.html`) — a conexão de vídeo é direta entre os navegadores (WebRTC via PeerJS), então não precisa de servidor próprio.

## Publicar no Vercel

**Opção 1 — pelo site (mais fácil)**
1. Crie um repositório no GitHub e suba esta pasta (`index.html`, `vercel.json`, `README.md`).
2. Em https://vercel.com/new, clique em **Import** no repositório.
3. Framework Preset: **Other**. Não precisa de build command. Clique em **Deploy**.

**Opção 2 — pela linha de comando**
```bash
npm i -g vercel
cd sofa-online
vercel          # primeira vez: faz login e cria o projeto
vercel --prod   # publica em produção
```

## Como usar
1. Quem vai transmitir abre o site **no computador (Chrome ou Edge)**, coloca o nome e clica em **Criar sala**.
2. Clica em **Copiar convite** e manda o link pros amigos.
3. Clica em **Compartilhar tela** → escolha a **aba** onde o vídeo está e marque **"Compartilhar áudio da aba"** (sem isso, vai sem som).
4. Os amigos abrem o link, colocam o nome e entram — funciona no celular também.

## Perfil
Não tem login nem senha: cada um coloca um nome e (opcional) uma foto na tela inicial. Os dois ficam salvos no próprio navegador pra próxima vez. Sem foto, aparece a inicial do nome num círculo colorido.

## Canal de voz (estilo Discord)
- Qualquer pessoa na sala clica em **Entrar na voz** e libera o microfone.
- **Mutar** desliga seu microfone; **Ensurdecer** silencia as vozes dos outros (o áudio da transmissão continua).
- O nome de quem está falando acende em verde na lista; 🎙️ = na voz, 🔇 = mutado, 👑 = anfitrião.
- **Use fone de ouvido**, senão o som da série sai da caixa e volta pelo microfone.
- A voz é em malha (cada um conecta com cada um) — ótimo para até ~6–8 pessoas.

## Limitações a saber
- **Netflix, Prime, Disney+ etc.** bloqueiam captura de tela (DRM): quem assiste vê tela preta. Funciona bem com YouTube, arquivos de vídeo locais e players sem DRM.
- O vídeo sai do PC do anfitrião direto pra cada amigo, então quanto mais gente, mais upload o anfitrião precisa. Para 3–5 pessoas costuma ir bem.
- Em algumas redes muito restritas (4G de certas operadoras, redes corporativas) a conexão direta pode falhar. A solução é adicionar um servidor TURN (ex.: Metered.ca tem plano grátis) na lista `iceServers` do `index.html`.
- A sala existe enquanto a aba do anfitrião estiver aberta.
