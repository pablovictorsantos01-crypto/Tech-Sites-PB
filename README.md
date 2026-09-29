# TECH SITES · Pablo Borges — techsitespb.online

Site institucional one-page (preto profundo + dourado metálico).

## Índice
1. [Estrutura](#estrutura)
2. [Rodar localmente](#rodar-localmente)
3. [Publicar (Vercel)](#publicar-vercel)
4. [Editar](#editar)
5. [Seções do site](#seções-do-site)
6. [Pendências antes do lançamento](#pendências-antes-do-lançamento)

## Estrutura
```
index.html            Página principal (abre direto no navegador)
support.js            Runtime do componente (obrigatório, mesma pasta do index)
image-slot.js         Componente de imagem
vercel.json           Headers de segurança e cache
assets/
  logo-emblema.png    Emblema do header / preloader
  logo.jpg
  works/site-0X.mp4   Vídeos do portfólio (6)
```

## Rodar localmente
Vídeos e scripts precisam de servidor HTTP (não abrir via `file://`):
```
npx serve .
# ou
python3 -m http.server 8080
```
Acesse http://localhost:8080

## Publicar (Vercel)
1. `npm i -g vercel`
2. Na pasta do site: `vercel --prod`
3. Em Settings → Domains, adicione `techsitespb.online` e aponte o DNS (A `76.76.21.21` / CNAME `cname.vercel-dns.com`).

Também funciona em Netlify, Hostinger ou qualquer hospedagem estática — basta subir a pasta inteira.

## Editar
- **WhatsApp:** buscar o número no `index.html` e trocar em todos os links `wa.me`.
- **Promoção:** data final do countdown (28/10/2026 23:59:59, Brasília) no bloco de lógica do `index.html`.
- **Portfólio:** trocar os MP4 em `assets/works/` mantendo os nomes (ideal: H.264, até ~3 MB cada, sem áudio).

## Seções do site
1. Preloader (logo animado + contador 0–100%)
2. Banner da promoção com contagem regressiva (até 28/10/2026 23:59:59)
3. Hero com relógio de São Paulo e CTAs
4. Portfólio — 6 trabalhos em vídeo
5. Planos: Essencial, Profissional e Completo (botão "Pedir prévia via WhatsApp")
6. Suporte (3 níveis)
7. Tráfego pago — simulador de anúncios
8. Contato final + WhatsApp flutuante

## Privacidade (LGPD) — já incluso
- Banner de cookies (Aceitar / Rejeitar / Personalizar) após o preloader.
- Central de preferências: Necessários, Análise, Marketing, Preferências. Escolha salva por 12 meses.
- Políticas de Privacidade, de Cookies e Termos de Uso: rodapé ou `#privacidade`, `#politica-cookies`, `#termos`, `#gerenciar-cookies`.
- Google Consent Mode v2 começa negado por padrão.
- **GA4 / Meta Pixel:** no `index.html`, preencha `GA_ID = ''` e `PIXEL_ID = ''`. Eles só carregam depois do consentimento.

## Pendências antes do lançamento
- Revisar os textos legais com um advogado.
- Preencher os IDs do GA4 e do Meta Pixel, se for usar.
