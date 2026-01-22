# Noah Scherner - Portfolio Website

Site portfolio pessoal do artista visual brasileiro Noah Scherner.

---

## Sobre o Artista

**Noah Scherner** (n. 2005) e um artista visual brasileiro nascido em Uberlandia (MG), atualmente vivendo e trabalhando no Rio de Janeiro. Sua pratica concentra-se na pintura a oleo, articulando elementos do expressionismo, surrealismo contemporaneo e psicanalise. E representado pela Cana Galeria (RJ).

---

## Visao Geral do Site

Este e um site estatico de portfolio desenvolvido em HTML, CSS e JavaScript puro. O site apresenta:

- **Pagina Inicial** (`index.html`): Imagem de perfil do artista em destaque
- **Trabalhos Selecionados** (`obras.html`): Galeria de obras em formato carrossel interativo
- **Sobre/CV** (`cv.html`): Biografia completa, formacao academica e exposicoes
- **Contato** (`contato.html`): Informacoes de contato e representacao

### Funcionalidades Principais

- **Suporte Bilingue (PT/EN)**: Sistema de alternancia de idiomas com persistencia via localStorage
- **Carrossel Interativo**: Navegacao por setas ou teclado (esquerda/direita)
- **Design Responsivo**: Layout adaptavel para desktop, tablet e dispositivos moveis
- **Tipografia Profissional**: Fonte Inter do Google Fonts

---

## Estrutura de Arquivos

```
/
├── index.html              # Pagina inicial (hero com imagem de perfil)
├── obras.html              # Galeria de obras (carrossel interativo)
├── cv.html                 # Pagina Sobre/CV (biografia, formacao, exposicoes)
├── contato.html            # Pagina de contato
├── styles.css              # Estilos globais do site
│
├── assets/
│   ├── profile.jpg         # Foto de perfil (pagina inicial)
│   └── obras/              # Imagens das obras de arte
│       ├── posidon.jpg
│       ├── tres-irmas.jpg
│       ├── agape.jpg
│       ├── afano.jpg
│       ├── cortejo.jpg
│       ├── epopeia.jpg
│       └── obra-4.jpg
│
└── data/
    ├── content.json        # Dados textuais bilingues (bio, CV, exposicoes)
    └── artworks.json       # Catalogo das obras de arte
```

---

## Como Atualizar o Conteudo

### 1. Adicionar Nova Obra de Arte

**Passo 1:** Adicione a imagem da obra na pasta `assets/obras/`
- Formato recomendado: JPG
- Largura maxima recomendada: 2000px
- Nome do arquivo: apenas letras minusculas, numeros e hifens (ex: `nova-obra.jpg`)

**Passo 2:** Edite o arquivo `obras.html` e adicione um novo slide dentro da div `.carousel-container`:

```html
<div class="carousel-slide">
    <img src="assets/obras/nova-obra.jpg" alt="Titulo da Obra">
    <p class="carousel-caption">
        <em>Titulo da Obra</em>, 2025. <span lang="pt-br">Oleo sobre tela</span><span lang="en">Oil on canvas</span> — 100 x 80 cm
    </p>
</div>
```

**Passo 3 (Opcional):** Atualize o arquivo `data/artworks.json` para manter o catalogo sincronizado:

```json
{
    "id": "nova-obra",
    "title": "Titulo da Obra",
    "year": 2025,
    "medium": {
        "pt": "Oleo sobre tela",
        "en": "Oil on canvas"
    },
    "dimensions": "100 x 80 cm",
    "image": "assets/obras/nova-obra.jpg"
}
```

### 2. Remover uma Obra

Localize e apague todo o bloco `<div class="carousel-slide">...</div>` correspondente no arquivo `obras.html`. Opcionalmente, remova a entrada correspondente em `data/artworks.json`.

### 3. Adicionar Nova Exposicao

Edite o arquivo `cv.html` e localize a secao "Exposicoes Selecionadas". Adicione uma nova entrada em **ambos os idiomas**:

```html
<!-- Dentro da div lang="pt-br" -->
<div class="cv-item">2025, "Nome da Exposicao", Local, Cidade</div>

<!-- Dentro da div lang="en" -->
<div class="cv-item">2025, "Exhibition Name", Venue, City</div>
```

**Dica:** Mantenha a ordem cronologica (mais recente primeiro).

### 4. Atualizar Formacao Academica

No arquivo `cv.html`, localize a secao "Formacao/Education" e adicione:

```html
<!-- Portugues -->
<div class="cv-item">Periodo, Nome do Curso, Instituicao, Cidade</div>

<!-- Ingles -->
<div class="cv-item">Period, Course Name, Institution, City</div>
```

### 5. Atualizar Biografia

Edite a secao `<div class="bio-text">` no arquivo `cv.html`. Existem duas versoes:
- `<div lang="pt-br">` para Portugues
- `<div lang="en">` para Ingles

**Importante:** Atualize ambas as versoes para manter a consistencia entre idiomas.

### 6. Atualizar Imagem de Perfil

Substitua o arquivo `assets/profile.jpg` pela nova imagem, mantendo exatamente o mesmo nome de arquivo.

### 7. Atualizar Informacoes de Contato

Edite o arquivo `contato.html`:

```html
<!-- Email -->
<p><a href="mailto:novo-email@exemplo.com">novo-email@exemplo.com</a></p>

<!-- Instagram -->
<p><a href="https://instagram.com/novo_usuario" target="_blank" rel="noopener">Instagram</a></p>

<!-- Representacao -->
<h4><span lang="pt-br">Representado por</span><span lang="en">Represented by</span></h4>
<p>
    Nome da Galeria<br>
    Cidade, Pais
</p>
```

---

## Sistema de Cores

O site utiliza uma paleta de tons de cinza profissionais definidos como variaveis CSS:

| Variavel CSS   | Cor Hex   | Uso Principal                           |
|----------------|-----------|----------------------------------------|
| `--gray-900`   | #212121   | Texto principal, titulos, logo          |
| `--gray-700`   | #424242   | Texto de corpo, paragrafos              |
| `--gray-600`   | #5a5a5a   | Links, texto terciario                  |
| `--gray-500`   | #757575   | Labels, subtitulos, texto mudo          |
| `--gray-400`   | #9e9e9e   | Elementos sutis, botoes inativos        |
| `--gray-200`   | #e0e0e0   | Bordas, divisores, separadores          |
| `--gray-100`   | #f5f5f5   | Fundos alternativos                     |
| `--white`      | #ffffff   | Fundo principal                         |
| `--black`      | #1a1a1a   | Texto de alto contraste                 |

Para alterar a paleta de cores, edite as variaveis no inicio do arquivo `styles.css`:

```css
:root {
    --gray-900: #212121;
    /* ... */
}
```

---

## Sistema de Idiomas (PT/EN)

O site possui suporte completo para Portugues (padrao) e Ingles.

### Como Funciona

1. Um botao de alternancia no header permite trocar entre PT e EN
2. A preferencia e salva no `localStorage` do navegador
3. A preferencia persiste entre sessoes e paginas

### Implementacao Tecnica

O sistema utiliza:
- Atributo `lang` nos elementos HTML (`lang="pt-br"` ou `lang="en"`)
- Atributo `data-lang` no `<body>` para controlar a visibilidade
- CSS para mostrar/ocultar conteudo baseado no idioma selecionado

### Adicionar Conteudo Bilingue

**Para blocos de texto:**
```html
<div lang="pt-br">Texto em portugues</div>
<div lang="en">Text in English</div>
```

**Para texto inline (dentro de paragrafos, captions, etc.):**
```html
<span lang="pt-br">Texto em portugues</span><span lang="en">Text in English</span>
```

---

## Navegacao do Carrossel

A galeria de obras (`obras.html`) possui um carrossel interativo:

### Controles

- **Setas na tela**: Clique nas setas < > nas laterais
- **Teclado**: Use as setas esquerda/direita do teclado
- **Loop infinito**: Ao chegar na ultima obra, volta para a primeira

### Personalizar Animacao

O efeito de transicao e definido no `styles.css`:

```css
@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}
```

---

## Design Responsivo

O site e totalmente responsivo com tres breakpoints principais:

| Breakpoint     | Descricao                                        |
|----------------|--------------------------------------------------|
| > 900px        | Desktop: layout em duas colunas, navegacao fixa  |
| 600px - 900px  | Tablet: layout em coluna unica, header compacto  |
| < 600px        | Mobile: header empilhado, navegacao centralizada |

### Ajustes Responsivos Principais

- Header fixo que se adapta ao tamanho da tela
- Grid de duas colunas colapsa para coluna unica em telas menores
- Carrossel ajusta o tamanho das imagens
- Fonte e espacamento se adaptam

---

## Arquivos de Dados (data/)

Os arquivos JSON na pasta `data/` servem como fonte de dados estruturados e podem ser usados para futuras integracoes ou automacoes.

### content.json

Contem todos os dados textuais do artista:

```json
{
    "artist": {
        "name": "Noah Scherner",
        "birthYear": 2005,
        "nationality": "Brazilian",
        "currentCity": "Rio de Janeiro"
    },
    "contact": { /* email, instagram, galeria */ },
    "bio": { /* versoes pt e en */ },
    "education": [ /* lista de formacoes */ ],
    "exhibitions": [ /* lista de exposicoes */ ],
    "representation": { /* dados da galeria */ }
}
```

### artworks.json

Catalogo estruturado das obras de arte:

```json
{
    "artworks": [
        {
            "id": "posidon",
            "title": "Posidon",
            "year": 2025,
            "medium": { "pt": "...", "en": "..." },
            "dimensions": "120 x 80 cm",
            "image": "assets/obras/posidon.jpg"
        }
    ]
}
```

---

## Requisitos Tecnicos

- Navegadores modernos (Chrome, Firefox, Safari, Edge)
- JavaScript habilitado (necessario para alternancia de idiomas e carrossel)
- Conexao com internet (para carregar fonte Google Fonts)

---

## Boas Praticas para Atualizacoes

### Imagens

1. **Formato**: Use JPG para fotografias de obras
2. **Tamanho**: Largura maxima de 2000px para equilibrar qualidade e performance
3. **Nomes de arquivo**: Use apenas letras minusculas, numeros e hifens
   - Correto: `minha-nova-obra.jpg`
   - Incorreto: `Minha Nova Obra (1).JPG`

### Conteudo Bilingue

1. **Sempre** atualize ambos os idiomas simultaneamente
2. Verifique se os textos estao dentro das tags de idioma corretas
3. Teste a alternancia de idiomas apos fazer alteracoes

### Backup

- Mantenha copias de seguranca antes de fazer alteracoes significativas
- Os arquivos JSON em `data/` servem como referencia caso precise restaurar conteudo

### Testes

1. Abra os arquivos HTML diretamente no navegador
2. Teste em diferentes tamanhos de tela (desktop, tablet, mobile)
3. Verifique a alternancia de idiomas
4. Teste a navegacao do carrossel (setas e teclado)

---

## Hospedagem

Este site e hospedado na Netlify como site estatico. Alteracoes enviadas ao repositorio sao automaticamente publicadas.

---

## Suporte

Para duvidas sobre o site, alteracoes mais complexas ou questoes tecnicas, entre em contato com o desenvolvedor.
