# Spaolonzi · Precificação Ouro 18K

Calculadora de precificação de peças exclusivas de ouro 18K. Aplicação web estática — roda diretamente no navegador, sem servidor.

## Como usar

### Localmente
```
Abra o arquivo index.html no navegador.
```
Sem instalação, sem Node.js, sem dependências.

### GitHub Pages
1. Faça upload da pasta (ou do repositório) no GitHub
2. Vá em **Settings → Pages → Source: main / root**
3. Acesse o link gerado (ex: `https://seunome.github.io/spaolonzi-ouro/`)

### Netlify / Vercel (arraste e solte)
- Arraste a pasta `spaolonzi-ouro/` para [netlify.com/drop](https://app.netlify.com/drop)
- Deploy em segundos, URL pública gerada automaticamente

---

## Funcionalidades

| Módulo | Descrição |
|---|---|
| **Base de Preço** | Custo × Markup multiplicador → PVF automático |
| **Cliente / Produto** | Identificação da cotação (opcional) |
| **Calculadora Trade-in** | Peso (g) × Cotação ouro 24K × Fração → crédito automático |
| **Descontos** | PIX · À vista · Parcelado · Pag. direto fornecedor |
| **4 Cenários** | Preço ao cliente + Margem bruta % + Margem líquida % + Lucro R$ |
| **Fórmula Trade-in** | Imposto sobre PVF total · Taxa máquina só sobre cash recebido |
| **Histórico** | Últimas 20 cotações · localStorage · Editar cliente/produto |
| **Dark mode** | Toggle persistido |
| **Atalhos** | `Ctrl+S` salva · `Esc` fecha modal |

## Fórmulas principais

```
PVF = Custo × Markup

Cenário PIX:
  Preço = PVF × (1 − dPix%)
  MB = Preço − Custo
  ML = Preço × (1 − Imposto%) − Custo

Cenário Parcelado 12×:
  Preço = PVF × (1 − dParcela%)
  ML = Preço × (1 − Imposto% − TaxaCartão%) − Custo

Cenário Trade-in + PIX:
  Preço PIX = PVF × (1 − dPix%)
  Cash cliente = Preço PIX − Crédito trade-in
  MB = Preço PIX − Custo
  ML = MB − (Preço PIX × Imposto%) − (Cash cliente × TaxaMáquina%)
```

## Estrutura

```
spaolonzi-ouro/
└── index.html   ← app completo (HTML + CSS + JS inline)
```

Arquivo único · zero dependências · ~1.4 KB de código útil por seção.

---

*Desenvolvido para uso interno Spaolonzi · v1.0*
