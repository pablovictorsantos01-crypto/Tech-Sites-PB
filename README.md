# Tech.SitesPB — Site institucional

Site de uma página da **Tech.SitesPB** (Pablo Victor Santos Borges) — sites, e-commerce e sistemas sob medida com padrão de segurança corporativa.

Sem build, sem npm, sem framework para instalar: é HTML + JS estático. Basta subir a pasta.

---

## Como abrir localmente

Abrir `index.html` direto no navegador funciona, mas o vídeo do hero e as imagens carregam melhor por HTTP. Rode um servidor local na raiz do projeto:

```bash
# Python 3
python3 -m http.server 8080

# ou Node
npx serve .
```

Depois acesse `http://localhost:8080`.

---

## Estrutura

```
.
├── index.html              # a página publicada (cópia de Tech.SitesPB.dc.html)
├── Tech.SitesPB.dc.html    # arquivo de trabalho / edição
├── support.js              # runtime que renderiza a página (obrigatório)
├── README.md
└── assets/
    ├── logo.png            # logotipo </> dourado (favicon, header, rodapé, contato)
    ├── hero.mp4            # vídeo de fundo do hero
    ├── hero-poster.png     # imagem exibida antes do vídeo carregar
    ├── pablo.jpg           # retrato frontal
    ├── pablo-side.jpg      # retrato de perfil (seção "Quem constrói")
    └── proj-artemdoces.png # mockup do projeto Art em Doces
```

`index.html` e `Tech.SitesPB.dc.html` têm o mesmo conteúdo. Edite o `.dc.html` e copie sobre o `index.html` antes de publicar (ou publique o `.dc.html` renomeado).

**Todos os arquivos acima são necessários.** O `support.js` precisa ficar na mesma pasta do HTML.

---

## Publicar

### Vercel
```bash
npm i -g vercel
vercel
```
Sem framework, sem build command, output directory = raiz (`.`).

### Netlify / Cloudflare Pages
Arraste a pasta inteira. Publish directory = raiz, build command = vazio.

### Hospedagem tradicional (cPanel, FTP)
Envie todos os arquivos para `public_html/` mantendo a pasta `assets/`.

Depois de publicar, aponte o domínio e habilite SSL + Cloudflare na frente, como descrito na própria seção de processo do site.

---

## Seções da página

| # | Seção | Conteúdo |
|---|-------|----------|
| — | Preloader | contador 000→100 e abertura de cortina |
| — | Hero | vídeo de fundo, headline, status de disponibilidade, relógio de São Paulo |
| — | Marquee | stack de tecnologias em rolagem contínua |
| 01 | Quem constrói | retrato, texto de autoridade, 5 métricas animadas, formação |
| 02 | Serviços | acordeão com 6 serviços e suas tecnologias |
| 03 | Projetos | Art em Doces by Jessica com mockup e link ao vivo |
| 04 | Prova técnica | terminal com boot automático e comandos reais |
| 05 | Processo | 4 etapas com linha de progresso ligada ao scroll |
| 06 | Clientes | carrossel de depoimentos |
| 07 | Contato | CTA de WhatsApp, e-mail copiável, LinkedIn |
| — | Rodapé | navegação, contatos, fuso horário, marca em outline |

---

## Onde editar o conteúdo

Todo o texto está em `Tech.SitesPB.dc.html`. Os blocos de dados ficam no `<script data-dc-script>`, no fim do arquivo:

| O que mudar | Onde |
|---|---|
| Serviços | array `services` |
| Projetos | array `projects` |
| Etapas do processo | array `steps` |
| Depoimentos | array `quotes` |
| Métricas | método `baseCounters()` |
| Stack do marquee | array `stack` |
| Formação e idiomas | array `badges` |
| Itens do menu | array `navSpec` |
| Terminal (boot) | array `boot` |
| Terminal (comandos) | objeto `routes`, em `onTermSubmit` |

### Pendências de conteúdo

1. **Depoimentos** — os 2 itens de `quotes` são espaços reservados. Peça 2–3 frases à Jessica (resultado concreto: mais pedidos diretos, tempo economizado) e substitua `text`, `who` e `role`.
2. **Novos projetos** — ao adicionar um segundo item em `projects`, a seção volta automaticamente ao modo de rolagem horizontal fixada. Cada item aceita `img` (mockup) ou, sem imagem, mostra um placeholder com o texto de `shot`.
3. **Domínio** — trocar `www.artemdoce.com.br` e os links de GitHub caso mudem.

---

## Ajustes rápidos (props)

No `data-props` do arquivo:

- `motion` — `completa` (padrão), `auto` (respeita o "reduzir movimento" do sistema) ou `reduzida`. Recomendado deixar em **auto** em produção.
- `preloader` — liga/desliga a tela de carregamento.
- `customCursor` — liga/desliga o cursor dourado personalizado (desktop apenas).
- `available` — alterna entre "Disponível para projetos" e "Agenda fechada — lista de espera".

---

## Identidade

| Uso | Valor |
|---|---|
| Fundo | `#0A0A0A` |
| Superfície | `#121212` / `#1A1A1A` |
| Dourado | `#C9A24B` — claro `#E0BE72`, escuro `#8A6F2E` |
| Texto | `#F5F5F5` / secundário `#8A8A8A` |
| Sucesso (terminal) | `#4ADE80` |
| Títulos | Satoshi |
| Corpo | Inter |
| Mono / dados | JetBrains Mono |

Fontes carregadas por CDN (Fontshare + Google Fonts) e rolagem suave via Lenis por CDN — é preciso conexão na primeira carga.

---

## Contato

- WhatsApp: +55 11 99858-7409
- E-mail: pablovictorsantos01@gmail.com
- LinkedIn: linkedin.com/in/pvszzz
- GitHub: github.com/pablovictorsantos01-crypto
- Instagram: @tech.sitespb

© 2026 Tech.SitesPB — Pablo Victor Santos Borges
