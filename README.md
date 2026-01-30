# Para Nicole 💕

Site romântico de pedido de namoro, feito para celular, com céu estrelado e clima especial.

## Como usar

1. Abra o arquivo **index.html** no celular (envie por WhatsApp, e-mail ou abra pelo navegador).
2. A Nicole vê a mensagem e os botões **SIM** e **NÃO**.
3. O botão **NÃO** se move sozinho (diversão garantida).
4. Se ela clicar em **NÃO**, aparece uma tela só com o **SIM**.
5. Ao clicar em **SIM**, aparece a tela de aceite com poema, trechos das músicas e o mini-player.

---

## Tutorial: como ajustar textos, poemas, músicas e fontes

Tudo que você pode personalizar está no arquivo **index.html**. Abra-o em um editor de texto (Bloco de Notas, VS Code, Cursor etc.) e use **Ctrl+F** (ou Cmd+F no Mac) para buscar os trechos abaixo.

---

### 1. Textos das telas

#### Título da página (aba do navegador)
- **Onde:** no início do arquivo, dentro de `<head>`.
- **Busque por:** `Para Nicole` ou `<title>`.
- **O que editar:** o conteúdo entre `<title>` e `</title>`, por exemplo:  
  `<title>Para Nicole 💕</title>`  
  Troque por qualquer frase que quiser (ex.: "Para a Nicole", "Um pedido especial").

#### Tela inicial (pedido de namoro)
- **Onde:** procure por `<!-- Tela inicial -->` ou por `Nicole, você aceita`.
- **O que editar:**
  - **Título principal:** a linha com `<h1>...</h1>`. Exemplo atual:  
    `Nicole, você aceita namorar comigo? 💕`
  - **Subtítulo:** a linha logo abaixo, com `<p>...</p>`. Exemplo atual:  
    `Eu te escolhi entre todas as estrelas do céu.`  
  Você pode mudar as duas frases e os emojis (💕, ❤️, etc.).

#### Tela “só SIM” (quando ela clica em NÃO)
- **Onde:** procure por `screen-only-sim` ou `Sabia que ia voltar`.
- **O que editar:**
  - **Título:** o `<h1>...</h1>`, ex.: `Sabia que ia voltar! 😊`
  - **Texto:** o `<p>...</p>` logo abaixo, ex.: `O "não" não combina com a gente. Clica no SIM?`  
  Ajuste o tom (mais brincalhão, mais romântico, etc.).

#### Tela do SIM (sucesso) – título e dedicação
- **Onde:** procure por `heart-title` ou `Eu te amo, Nicole`.
- **O que editar:**
  - **Título grande:** o `<h2 class="heart-title">...</h2>`, ex.: `Eu te amo, Nicole! 💖`
  - **Dedicação (rodapé do texto):** procure por `success-sub` ou `Com amor, para a Nicole.`  
    É o `<p class="success-sub">...</p>`. Pode ser algo como “Com amor, [seu nome]” ou “Para a Nicole, com carinho”.

#### Nota abaixo do player
- **Onde:** procure por `player-note` ou `As músicas são reproduzidas`.
- **O que editar:** o texto dentro do `<p class="player-note">...</p>`. Exemplo atual:  
  `As músicas são reproduzidas pelo YouTube.`  
  Você pode trocar ou apagar essa frase se não quiser exibir nada.

---

### 2. Poema e trechos românticos (tela do SIM)

- **Onde:** procure por `poem-box` ou por `Em noite de estrelas`.
- **O que editar:** tudo que está dentro de `<div class="poem-box">` e `</div>`.

Cada parágrafo do poema é um `<p>...</p>`. Você pode:
- Alterar o texto de qualquer `<p>`.
- Usar `<br>` onde quiser quebra de linha no meio da frase (ex.: `primeira linha<br>segunda linha`).
- Adicionar novos parágrafos copiando uma linha como:  
  `<p>Sua nova frase aqui.</p>`

**Trechos das músicas** (as frases entre aspas com nome do artista):
- Cada trecho está em um parágrafo com classe `song-quote`, no formato:  
  `<p class="song-quote">"trecho da letra aqui."<br><small>— Nome da música, Artista</small></p>`
- Para mudar só a frase: edite o texto entre as aspas.
- Para mudar a referência (música/artista): edite o que está dentro de `<small>...</small>`.
- Para adicionar outro trecho: copie uma linha inteira `song-quote` e altere o conteúdo.

**Exemplo de estrutura:**

```html
<p>Em noite de estrelas,<br>só penso em você.</p>
<p>Seu nome é a melodia que eu quero ouvir sempre que o mundo parar.</p>
<p class="song-quote">"Cada vez que eu te vejo, me descontrogo."<br><small>— Exagerado, Cazuza</small></p>
<p class="song-quote">"Loving can hurt, but it's the only thing that I know."<br><small>— Photograph, Ed Sheeran</small></p>
<p>Obrigado por aceitar. Vamos ser felizes juntos. 💕</p>
```

Troque as frases e mantenha as tags (`<p>`, `<br>`, `<small>`) para não quebrar o layout.

---

### 3. Músicas do player (YouTube)

- **Onde:** procure por `var tracks` ou por `Exagerado – Cazuza` (no meio do arquivo, na parte de script).

Você verá algo assim:

```javascript
var tracks = [
  { name: 'Exagerado – Cazuza', youtubeId: 'RcuL-W-sJp8' },
  { name: 'Photograph – Ed Sheeran', youtubeId: 'nSDgHBxUbVQ' }
];
```

**O que editar:**

| Campo       | O que é |
|------------|---------|
| **name**   | Nome que aparece no player (ex.: “Exagerado – Cazuza”). Pode ser qualquer texto. |
| **youtubeId** | ID do vídeo do YouTube. |

**Como descobrir o ID de um vídeo do YouTube:**
1. Abra o vídeo no YouTube.
2. A URL é assim: `https://www.youtube.com/watch?v=XXXXX`  
   O **XXXXX** é o ID (só letras e números).
3. Use esse ID no lugar de `RcuL-W-sJp8` ou `nSDgHBxUbVQ`.

**Para trocar as músicas:** altere o `name` e o `youtubeId` de cada linha.  
**Para adicionar mais músicas:** copie uma linha inteira (com a vírgula) e cole antes do `];`, trocando nome e ID. Exemplo:

```javascript
var tracks = [
  { name: 'Exagerado – Cazuza', youtubeId: 'RcuL-W-sJp8' },
  { name: 'Photograph – Ed Sheeran', youtubeId: 'nSDgHBxUbVQ' },
  { name: 'Nova música – Artista', youtubeId: 'SEU_ID_AQUI' }
];
```

Não esqueça da vírgula entre as linhas.

---

### 4. Fontes (tipografia)

As fontes vêm do **Google Fonts** e são usadas em dois lugares: no link que carrega a fonte e no CSS onde ela é aplicada.

#### Carregar outra fonte do Google Fonts
- **Onde:** no início do arquivo, procure por `fonts.googleapis.com` ou `Cormorant+Garamond`.
- Você verá uma linha assim:  
  `<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:...&family=Quicksand:...&display=swap" rel="stylesheet">`
- Para usar outra fonte:
  1. Acesse [Google Fonts](https://fonts.google.com/), escolha a fonte e copie o link que o site mostrar (embed).
  2. Substitua essa linha inteira pelo novo link (ou adicione a nova família na URL, seguindo o padrão `family=Nome+da+Fonte`).

#### Onde cada fonte é usada no site
- **Onde:** procure por `font-family` no arquivo (várias ocorrências).

Resumo:

| Estilo no arquivo | Fonte atual | O que afeta |
|------------------|-------------|-------------|
| `html, body` ou `body` | **Quicksand** | Texto geral da página (botões, controles, etc.). |
| `.message-box h1` | **Cormorant Garamond** | Títulos das telas iniciais (“Nicole, você aceita...”, “Sabia que ia voltar!”). |
| `.success-content .heart-title` | **Cormorant Garamond** | Título “Eu te amo, Nicole!”. |
| `.poem-box p` | **Cormorant Garamond** | Texto do poema e dos trechos das músicas. |
| `.btn` (botões) | **Quicksand** | Botões SIM e NÃO. |

**Para trocar a fonte em um desses lugares:**
1. Adicione a nova fonte no `<link>` do Google Fonts (como acima).
2. No CSS, encontre o bloco correspondente (ex.: `.message-box h1 {`) e troque o valor de `font-family`.  
   Exemplo: de `font-family: 'Cormorant Garamond', serif;` para `font-family: 'Nome da Nova Fonte', sans-serif;`  
   Use o nome exatamente como no Google Fonts (com espaços ou não, conforme o link).

**Dica:** depois de mudar, salve o `index.html` e atualize a página no navegador (F5) para ver o resultado.

---

## Estrutura do projeto

- **index.html** – Página única: todo o conteúdo, estilos (CSS) e scripts (JavaScript) estão neste arquivo.
- **README.md** – Este arquivo (instruções e tutorial).

Basta abrir o **index.html** no navegador (de preferência com internet, para o player do YouTube funcionar).

---

Feito com carinho para a Nicole. 💖
