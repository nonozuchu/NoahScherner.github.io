# Noah Scherner - Portfolio Website

Site portfolio pessoal do artista visual Noah Scherner.

---

## Estrutura de Arquivos

```
/
├── index.html          # Pagina inicial (imagem de perfil)
├── obras.html          # Galeria de obras (carrossel)
├── cv.html             # Pagina Sobre/CV (biografia e curriculo)
├── contato.html        # Pagina de contato
├── styles.css          # Estilos do site
├── assets/
│   ├── profile.jpg     # Foto de perfil (pagina inicial)
│   └── obras/          # Imagens das obras
│       ├── posidon.jpg
│       ├── tres-irmas.jpg
│       └── ...
└── data/
    ├── content.json    # Conteudo textual bilingue (bio, CV, exposicoes)
    └── artworks.json   # Dados das obras de arte
```

---

## Como Atualizar o Conteudo

### 1. Atualizar Biografia e CV (cv.html)

O conteudo bilingue esta organizado no arquivo `cv.html`. Cada secao possui duas versoes:
- `lang="pt-br"` para Portugues
- `lang="en"` para Ingles

**Para adicionar uma nova exposicao:**

Localize a secao "Exposicoes Selecionadas" e adicione uma nova linha em ambos os idiomas:

```html
<!-- Dentro da div lang="pt-br" -->
<div class="cv-item">2025, "Nome da Exposicao", Local, Cidade</div>

<!-- Dentro da div lang="en" -->
<div class="cv-item">2025, "Exhibition Name", Venue, City</div>
```

**Para atualizar a educacao:**

Localize a secao "Formacao/Education" e adicione:

```html
<!-- Portugues -->
<div class="cv-item">Ano, Nome do Curso, Instituicao, Cidade</div>

<!-- Ingles -->
<div class="cv-item">Year, Course Name, Institution, City</div>
```

### 2. Atualizar Obras (obras.html)

**Para adicionar uma nova obra:**

1. Adicione a imagem na pasta `assets/obras/`
2. No arquivo `obras.html`, adicione um novo slide:

```html
<div class="carousel-slide">
    <img src="assets/obras/nome-da-imagem.jpg" alt="Titulo da Obra">
    <p class="carousel-caption">
        <em>Titulo da Obra</em>, Ano. Oleo sobre tela — Largura x Altura cm
    </p>
</div>
```

**Para remover uma obra:**

Apague todo o bloco `<div class="carousel-slide">...</div>` correspondente.

### 3. Atualizar Imagem de Perfil (index.html)

Substitua o arquivo `assets/profile.jpg` pela nova imagem, mantendo o mesmo nome.

### 4. Atualizar Informacoes de Contato (contato.html)

Edite diretamente os valores no arquivo:

```html
<p><a href="mailto:seu-email@exemplo.com">seu-email@exemplo.com</a></p>
<p><a href="https://instagram.com/seu_usuario">Instagram</a></p>
```

---

## Estrutura dos Arquivos de Dados (data/)

Os arquivos JSON na pasta `data/` servem como referencia para o conteudo e podem ser usados no futuro para automatizar atualizacoes.

### content.json

Contem todas as informacoes textuais:
- Dados do artista (nome, ano de nascimento, cidade)
- Contato (email, Instagram, galeria)
- Biografia em PT e EN
- Formacao educacional
- Exposicoes
- Representacao

### artworks.json

Lista de todas as obras com:
- Titulo
- Ano
- Tecnica (bilingue)
- Dimensoes
- Caminho da imagem

---

## Sistema de Cores

O site utiliza uma paleta de tons de cinza profissionais:

| Variavel | Cor | Uso |
|----------|-----|-----|
| `--gray-900` | #212121 | Texto principal, titulos |
| `--gray-700` | #424242 | Texto secundario, corpo |
| `--gray-600` | #5a5a5a | Links, texto terciario |
| `--gray-500` | #757575 | Labels, texto mais claro |
| `--gray-400` | #9e9e9e | Elementos sutis |
| `--gray-200` | #e0e0e0 | Bordas, divisores |

---

## Funcionalidade de Idiomas

A pagina "Sobre" possui um seletor de idioma (PT/EN) que alterna entre portugues e ingles.

O sistema funciona assim:
1. Elementos com `lang="pt-br"` aparecem por padrao
2. Elementos com `lang="en"` estao ocultos por padrao
3. Ao clicar em "EN", o sistema inverte a visibilidade

Para adicionar conteudo bilingue, sempre inclua as duas versoes:

```html
<div lang="pt-br">Texto em portugues</div>
<div lang="en">Text in English</div>
```

---

## Dicas Importantes

1. **Imagens**: Use JPG para fotos. Recomendado: largura maxima de 2000px para web.

2. **Nomes de arquivos**: Use apenas letras minusculas, numeros e hifens. Evite espacos e caracteres especiais.
   - Correto: `minha-obra.jpg`
   - Incorreto: `Minha Obra (1).jpg`

3. **Backup**: Sempre mantenha uma copia de seguranca antes de fazer alteracoes.

4. **Teste local**: Abra os arquivos HTML no navegador para verificar as alteracoes antes de publicar.

---

## Contato Tecnico

Para duvidas sobre o site ou necessidade de alteracoes mais complexas, entre em contato com o desenvolvedor.
