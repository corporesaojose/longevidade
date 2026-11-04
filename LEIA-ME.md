# 2º Workshop de Saúde Corpore — Landing Page
## Seu Futuro Começa Agora · 15/11/2026 (domingo) · 9h30 às 12h

Duplicado do site do Workshop de Sono (sono.corporetraininggym.com.br), mesma base visual e técnica.
Convidada: Dra. Paloma Ratto, médica geriatra. 40 vagas. Investimento: R$ 60 por pessoa.

---

## Como rodar localmente

```bash
npm install
npm run dev
# → Abra http://localhost:4321
```

## Como gerar o site para Hostinger

```bash
npm run build
```

Depois do build, **faça upload da pasta `dist/`** para o subdomínio do novo evento na Hostinger
(File Manager ou FTP). Não sobrescreva o site do sono.

---

## Pendências antes de publicar

1. ~~**Foto da Dra. Paloma**~~ — feito: `public/foto-dra-paloma.webp` (704×880, 25 KB) e `foto-dra-paloma-480.webp` (480×600, 16 KB) para celular.
   Para trocar, substitua os dois arquivos mantendo o formato 4:5 (vertical).
2. ~~**Webhook do formulário no n8n**~~ — feito: workflow "Workshop Saúde 40+ → Planilha + ChatGuru"
   (n8n, ID YpRHeav6BPUfMVoz), ativo em `/webhook/workshop-saude-inscricao`. Grava na planilha
   "2º Workshop de Saúde - Inscrições" (Google Drive da corpore.saojose) e manda a mensagem de
   boas-vindas pelo ChatGuru (chat_add para contato novo; message_send se o contato já existir).
3. ~~**Investimento**~~ — feito: R$ 60 (objeto `EVENTO`, detalhes, FAQ, formulário, CTAs e `offers` no schema).

---

## O que foi mantido igual

- Formulário: nome, e-mail, WhatsApp (com máscara) e bairro (com autocomplete de SJC)
- Meta Pixel + CAPI via n8n (`health-map-lead`), mesmos eventos: PageView, ViewContent, Lead, Contact
- Redirecionamento para o WhatsApp da Corpore (`wa.me/551239094444`) após o envio
- Campo `origem` agora vai como `workshop-saude-40`

## Estrutura

```
landing-page/
├── public/
│   ├── logo-branco.png
│   ├── logo-amarelo-icone.png
│   ├── foto-dra-paloma.webp
│   └── foto-dra-paloma-480.webp
├── src/
│   ├── layouts/Layout.astro     ← meta tags, Pixel, schema do evento
│   ├── pages/index.astro        ← página (12 seções) + script do formulário
│   └── styles/global.css        ← design system
├── astro.config.mjs
└── package.json
```

## Ordem das seções

1. Abertura · 2. O futuro que você deseja · 3. O workshop · 4. O que você vai aprender ·
5. Para quem ainda não começou · 6. A convidada · 7. Seu plano pessoal · 8. Inscrição ·
9. A Corpore · 10. Informações · 11. Perguntas frequentes · 12. CTA final

---

*Corpore — 2º Workshop de Saúde · 15/11/2026*
