# SESSION STATE — ArtesEmFerro

> Última atualização: 2026-11-28
> Branch ativa: `feature/tema-claro-visibilidade`

---

## Resumo da Sessão Atual

### Objetivo
Refatoração completa do site ArtesEmFerro para **tema claro profissional (Light Industrial)** com:
- Paleta claro/branco + tipografia escura de alto contraste
- Hero com vídeo visível + painel translúcido apenas à esquerda (texto)
- Cards de catálogo com renders 3D sobre fundo branco/neutro
- Imagem real da oficina (`assets/sobre-oficina.jpg`) na seção "Estrutura & Oficina"
- Branch: `feature/tema-claro-visibilidade` → PR para `main`

---

## Status dos Arquivos Modificados

| Arquivo | Status | Descrição |
|---|---|---|
| `css/styles.css` | ✅ MODIFICADO | Reescrito completo — Light Industrial Theme v3.0 |
| `index.html` | ✅ MODIFICADO | Meta theme-color, video attrs, cards reestruturados, sobre-oficina.jpg |
| `politica-de-uso.html` | ✅ MODIFICADO | Meta theme-color adicionado |
| `assets/hero-poster.jpg` | ✅ NOVO | Poster/fallback do vídeo hero |
| `assets/sobre-oficina.jpg` | ✅ NOVO | Foto realista de oficina de serralheria |
| `assets/catalog/suporte-estante.jpg` | ✅ SUBSTITUÍDO | Render 3D fundo branco |
| `assets/catalog/prateleira-suspensa.jpg` | ✅ SUBSTITUÍDO | Render 3D fundo branco |
| `assets/catalog/mesa-estrutura.jpg` | ✅ SUBSTITUÍDO | Render 3D fundo branco |
| `assets/catalog/grade-portao.jpg` | ✅ SUBSTITUÍDO | Render 3D fundo branco |
| `assets/catalog/escada-corrimao.jpg` | ✅ SUBSTITUÍDO | Render 3D fundo branco |
| `assets/catalog/suporte-tv-painel.jpg` | ✅ SUBSTITUÍDO | Render 3D fundo branco |

---

## Tokens de Design Aplicados (CSS Custom Properties)

```css
/* Fundo */
--color-bg-main:        #f8fafc;   /* fundo principal claro */
--color-bg-alt:         #f1f5f9;   /* seções alternadas */
--color-surface-card:   #ffffff;   /* cards */
--color-border:         #e2e8f0;   /* bordas finas */

/* Tipografia */
--color-text-primary:   #0f172a;   /* títulos H1-H3 */
--color-text-body:      #334155;   /* parágrafos */
--color-text-muted:     #64748b;   /* legendas, specs */

/* Destaque laranja/âmbar */
--color-amber-500:      #ea580c;   /* laranja — CTAs, badges */
--color-amber-700:      #b45309;   /* âmbar escuro — WCAG AA em branco */

/* WhatsApp */
--color-whatsapp:       #16a34a;   /* verde acessível */

/* Aliases de compatibilidade (para politica-de-uso.html inline) */
--color-iron:           #0f172a;
--color-copper:         #b45309;
--color-ash:            #64748b;
--color-steel-50:       #f8fafc;
--color-steel-100:      #f1f5f9;
--color-steel-200:      #e2e8f0;
--color-steel-700:      #e2e8f0;
--color-steel-850:      #ffffff;
--color-steel-900:      #0f172a;
```

---

## Overlay do Vídeo Hero

**Técnica:** Gradiente direcional horizontal, cobrindo apenas a metade esquerda.

```css
.hero-video-overlay {
  background: linear-gradient(
    90deg,
    rgba(248,250,252,0.97)  0%,
    rgba(248,250,252,0.90) 25%,
    rgba(248,250,252,0.72) 42%,
    rgba(248,250,252,0.40) 56%,
    rgba(248,250,252,0.10) 72%,
    rgba(248,250,252,0.00) 100%
  );
}
/* Vídeo: opacity: 1, filter: brightness(1.06) contrast(1.06) saturate(1.12) */
/* object-position: 70% center; transform: scale(1.11) */
```

No desktop, o texto fica sobre a área coberta pelo gradiente (esquerda), enquanto o vídeo é totalmente visível à direita.

---

## Próximos Passos

- [ ] Validação visual no navegador (abrir `index.html` localmente)
- [ ] Revisar PR aberto no GitHub: `feature/tema-claro-visibilidade` → `main`
- [ ] Merge após aprovação

---

## Restrições Permanentes

- **Nunca commitar direto em `main`** — apenas via PR
- Commits semânticos: `feat:`, `fix:`, `refactor:`, `chore:`
- Preservar toda funcionalidade: filtros, bandeja/gaveta de cotação, envio WhatsApp, busca, lixeira image switcher
- Site estático — sem build step, compatível com GitHub Pages
- Logo: `mix-blend-mode: multiply` (não `filter: invert`) no tema claro
