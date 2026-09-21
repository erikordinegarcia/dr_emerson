# Site — Dr Emerson Advocacia

Site institucional em HTML, CSS e JavaScript puro (sem frameworks). Basta abrir `index.html` no navegador para visualizar.

## Estrutura

```
/
├── index.html
├── css/style.css
├── js/script.js
└── assets/
    ├── images/   → fotos do site
    ├── icons/    → ícones adicionais, se necessário
    └── logo/     → logo e favicon
```

## O que precisa ser substituído antes de publicar

Como os dados reais do escritório ainda não foram enviados, o site usa **placeholders claramente identificados** — que precisam ser trocados antes de ir ao ar:

1. **Nome, áreas de atuação e OAB**
   - As áreas de atuação (Trabalho, Civil, Previdenciário, Tributário, Empresarial, Família) são de **exemplo**. Ajuste na seção `#areas` do `index.html` para refletir as áreas reais.
   - O número da OAB no rodapé está com o texto `(inserir número real)` — substitua antes de publicar.

2. **Imagem de fundo do Hero** — atualmente a seção usa um fundo escuro decorativo com um ícone de balança da justiça em SVG. Para usar a foto que você já tem:
   - Coloque o arquivo em `assets/images/hero-advocacia.jpg`
   - No `css/style.css`, dentro da regra `.hero`, adicione:
     ```css
     background-image: linear-gradient(180deg, rgba(11,15,20,.55), rgba(11,15,20,.85)), url('../assets/images/hero-advocacia.jpg');
     background-size: cover;
     background-position: center;
     ```
   - Depois disso, pode remover ou deixar o `.hero__decor` (o ícone de balança) como um detalhe visual adicional — funciona bem sobreposto a fotos escuras.

3. **Foto "Sobre"** (`assets/images/dr-emerson.jpg`) — troque o placeholder da seção "Sobre" por uma foto real do advogado/escritório. Há um comentário no HTML indicando exatamente onde.

4. **Depoimentos** — os 3 depoimentos são **fictícios**, marcados com comentário no HTML. Substitua por depoimentos reais e autorizados de clientes.

5. **Dados de contato** — telefone, WhatsApp, e-mail e endereço são placeholders de exemplo. Atualize em:
   - Seção "Fale com o escritório" (`#contato`)
   - Botão flutuante do WhatsApp
   - Rodapé (redes sociais)

6. **Texto institucional ("Sobre")** — genérico, sem inventar formação, OAB ou histórico. Substitua pelo texto real do escritório.

7. **Formulário de contato** — valida os campos no navegador mas não envia dados de verdade. Para receber mensagens, integre com backend, e-mail (ex.: Formspree, EmailJS) ou similar.

## Paleta de cores (definida em `css/style.css`, no `:root`)

| Variável | Cor | Uso |
|---|---|---|
| `--gold` | `#C9A46B` | Dourado principal |
| `--gold-dark` | `#A67C3D` | Botões e destaques |
| `--ink` | `#0B0F14` | Fundo escuro (hero, rodapé, seção "processo") |
| `--paper` | `#F7F5F1` | Fundo claro das demais seções |

## Testado

- Responsivo de 360px a 1440px+, sem scroll horizontal
- Menu hamburger no mobile com fechamento automático ao clicar em um link, e `inert`/`aria-hidden` corretos para acessibilidade quando fechado
- Header flutuante com sombra ao rolar
- Animações de entrada discretas via `IntersectionObserver`
- Validação de formulário (nome, e-mail, telefone, mensagem) com mensagens de erro/sucesso
- Botão flutuante do WhatsApp com tooltip
- Carrossel de depoimentos com setas e indicadores
- HTML validado (html-validate), CSS com chaves balanceadas, JS sem erros de sintaxe
