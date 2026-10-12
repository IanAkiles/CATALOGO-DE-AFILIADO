# Garimpo Tech

Página de achados e ofertas de tecnologia da **Garimpo Tech**. Reúne uma seleção de produtos (games, acessórios, áudio, casa conectada e mais) e leva o visitante para o grupo do WhatsApp, onde as ofertas são compartilhadas.

Site estático, de um único arquivo, sem build, sem dependências e sem rastreadores externos.

## Destaques

- **Um arquivo só:** todo o HTML, CSS e JavaScript está em `index.html`.
- **Catálogo editável em um lugar:** os produtos ficam em um array `products` no próprio script.
- **7 produtos em cards coloridos**, com imagem, preço, desconto, avaliação, selo e botão para a loja (Mercado Livre ou Shopee).
- **Chamadas para o grupo do WhatsApp** no menu, no hero, na seção intermediária, no fechamento e no rodapé.
- **Visual:** fundo com gradiente verde animado, ticker em movimento, barra de progresso de rolagem, cordão de luzes e assinatura "Curadoria por Ian Akiles".
- **Responsivo:** layout adaptado para desktop, tablet e celular, com menu em `<dialog>` no mobile.
- **Acessível:** link "Pular para o conteúdo", foco visível, rótulos ARIA, botão para pausar animações e respeito a `prefers-reduced-motion`.
- **Animações leves:** apenas transforms e opacity em CSS, pausadas quando a seção sai da tela ou a aba fica oculta.
- **Privacidade:** nenhum dado é enviado a terceiros. Os eventos de clique são só `CustomEvent` locais (`garimpo:interaction`), prontos para uma futura integração de analytics.

## Estrutura

```
.
├── index.html            # página completa (HTML + CSS + JS)
├── logo.png              # logo e favicon
└── NOVOS PRODUTOS/       # imagens dos produtos
    ├── SMART TV PHILCO.jpeg
    ├── FONE DE OUVIDO.jpeg
    ├── KIT SMARTWATCH.jpeg
    ├── RELOGIO INTELIGENTE.jpeg
    ├── LED LUZES.jpeg
    ├── MINI GAME.jpeg
    └── ALEXA.jpeg
```

## Como rodar localmente

Não precisa instalar nada. Abra o `index.html` no navegador.

Se preferir um servidor local:

```bash
python3 -m http.server 8000
# acesse http://localhost:8000
```

## Como publicar no GitHub Pages

1. Envie os arquivos para o repositório.
2. Vá em **Settings → Pages**.
3. Em **Build and deployment**, escolha **Deploy from a branch**, selecione a branch `main` e a pasta `/ (root)`.
4. Salve. O site ficará disponível em `https://SEU-USUARIO.github.io/NOME-DO-REPO/`.

## Como editar os produtos

No final do `index.html`, procure o array `products`. Cada item segue este formato:

```js
{
  name: "Nome do produto",
  category: "Categoria / Subcategoria",
  image: "NOVOS PRODUTOS/arquivo.jpeg",
  url: "https://link-do-anuncio",
  price: "R$ 99,90",
  oldPrice: "R$ 149,90",     // opcional
  method: "no Pix",          // opcional
  discount: "33% OFF",       // opcional
  rating: "4,8",             // opcional
  badge: "Mais vendido",     // opcional
  payment: "Ou em 10x ...",  // opcional
  detail: "Descrição curta do produto.",
  marketplace: "Mercado Livre" // ou "Shopee"
}
```

Regras da montagem atual:

- Os **3 primeiros** produtos aparecem na seção "Achados em destaque".
- Os **demais** aparecem na seção "Mais ofertas", em duas colunas.
- Campos opcionais que não forem preenchidos simplesmente não aparecem no card.

Para trocar o link do grupo, altere a constante `whatsapp` no início do mesmo script.

## Aviso sobre ofertas

Preços, descontos, avaliações e posições de venda foram informados na montagem da seleção e **não são atualizados automaticamente**. Condições, estoque, frete e disponibilidade podem mudar. Os links de compra levam ao Mercado Livre ou à Shopee e usam `rel="sponsored"`, pois podem ser links de afiliado. Confira tudo no anúncio antes de comprar.

## Tecnologias

HTML5, CSS3 e JavaScript puro (vanilla). Sem frameworks, bibliotecas ou CDNs.

## Créditos

Curadoria por **Ian Akiles**.

© Garimpo Tech. Todos os direitos reservados.
