# GSI P2 — Exemplos de JavaScript para a Web

Colecção de exemplos práticos de JavaScript e DHTML desenvolvidos no âmbito da unidade curricular de **Gestão de Sistemas de Informação**, organizados por tema.

---

## Índice

- [GSI P2 — Exemplos de JavaScript para a Web](#gsi-p2--exemplos-de-javascript-para-a-web)
  - [Índice](#índice)
  - [Estrutura do Projecto](#estrutura-do-projecto)
  - [JS.1 — HTML DOM](#js1--html-dom)
  - [JS.2 — DHTML](#js2--dhtml)
  - [JS.3 — Imagens Animadas (DHTML)](#js3--imagens-animadas-dhtml)
  - [JS.4 — Menus PopUp (DHTML)](#js4--menus-popup-dhtml)
  - [JS.5 — Formulários](#js5--formulários)
  - [JS.6 — Handling Forms](#js6--handling-forms)
  - [JS.7 — Dados Locais](#js7--dados-locais)
  - [JS.8 — Cookies](#js8--cookies)
  - [JS.9 — Array de Cookies](#js9--array-de-cookies)
  - [Configuração de Debug — launch.json](#configuração-de-debug--launchjson)
    - [Configurações disponíveis](#configurações-disponíveis)
    - [Como utilizar](#como-utilizar)
    - [Estrutura do ficheiro](#estrutura-do-ficheiro)
  - [Tecnologias Utilizadas](#tecnologias-utilizadas)
  - [Como Executar](#como-executar)

---

## Estrutura do Projecto

```
GSI_P2/
├── index.html
├── images/
├── script/
├── style/
│   ├── basic.css
│   └── noticias.css
├── JS.1_HTML_DOM/
│   ├── JSBrowser.htm          ← Objecto Navigator (informação do browser)
│   ├── JSredirect.htm         ← Redireccionamento com window.location
│   └── JSschekjs.htm          ← Verificação de JavaScript activo
├── JS.2_DHTML/
│   ├── Dhtml.htm              ← Alteração de estilos CSS via eventos
│   └── jsPosicao.htm          ← document.write em diferentes posições
├── JS.3_ImagensAnimadas[DHTML]/
│   ├── animacao_v1.htm        ← Troca de imagem ao passar o rato
│   ├── animacao_v2.htm        ← Slideshow manual com array
│   ├── animacao_v3.htm        ← Slideshow automático com setTimeout
│   └── imageroll.htm          ← Slideshow automático com navegação por botões
├── JS.4_MenusPopUp[DHTML]/
│   ├── JSMenus_frame.htm      ← Menu de navegação com CSS e JS
│   ├── menus.js               ← Lógica dos menus popup
│   └── blank_green.htm        ← Página de destino dos menus
├── JS.5_Formularios/
│   └── Formulario.htm         ← Leitura e apresentação de elementos de formulário
├── JS.6_HandlingForms/
│   ├── JSValidForm.htm        ← Validação básica de formulário
│   ├── JSValidForm_wValues.htm← Validação com apresentação de valores
│   ├── JSValid_ext.htm        ← Validação com ficheiro externo
│   ├── JSValidMail.htm        ← Validação de endereço de e-mail
│   ├── JSPassingValues_tabela.htm ← Recepção de valores via URL (query string)
│   ├── mailValido.htm         ← Página de confirmação de endereço válido
│   ├── scripts/
│   │   └── valida.js          ← Funções de validação externas
│   └── style/
│       └── estilo.css
├── JS.7_LocalData/
│   ├── biblioteca_v1.htm      ← CRUD de livros em memória (array)
│   ├── biblioteca_v2.htm      ← CRUD de livros com localStorage
│   ├── script/
│   │   ├── datahandle.js
│   │   └── valida.js
│   └── style/
│       └── datahandle.css
├── JS.8_Cookies/
│   ├── 1.JSSetCookie.htm      ← Criação de cookie
│   └── 2.JSReadCookie.htm     ← Leitura de cookie
└── JS.9_CookieArr/
    └── alunos.htm             ← Gestão de alunos com cookies
```

---

## JS.1 — HTML DOM

**Pasta:** [`JS.1_HTML_DOM/`](JS.1_HTML_DOM/)

Introdução ao modelo de objectos do documento (DOM) e aos objectos de sistema disponíveis no browser.

| Ficheiro | Descrição |
|----------|-----------|
| [`JSBrowser.htm`](JS.1_HTML_DOM/JSBrowser.htm) | Utiliza o objecto `navigator` para ler e apresentar informações do browser: nome, versão, plataforma, língua, estado online e suporte a cookies. |
| [`JSredirect.htm`](JS.1_HTML_DOM/JSredirect.htm) | Demonstra o redireccionamento de páginas usando `window.location`. Se o JavaScript estiver activo, o utilizador é automaticamente enviado para outra página; caso contrário, é apresentada uma mensagem de aviso. |
| [`JSschekjs.htm`](JS.1_HTML_DOM/JSschekjs.htm) | Página de destino do redireccionamento. Confirma que o JavaScript está activo e desactiva o menu de contexto do botão direito do rato via `document.oncontextmenu`. |

---

## JS.2 — DHTML

**Pasta:** [`JS.2_DHTML/`](JS.2_DHTML/)

Exemplos de DHTML (Dynamic HTML): manipulação de estilos e conteúdo de elementos HTML em tempo de execução.

| Ficheiro | Descrição |
|----------|-----------|
| [`Dhtml.htm`](JS.2_DHTML/Dhtml.htm) | Ao passar o rato sobre um texto, as propriedades CSS do elemento são alteradas dinamicamente (`backgroundColor`, `color`, `textDecoration`, `innerHTML`) através de `getElementById`. Ao retirar o rato, os valores originais são restaurados. |
| [`jsPosicao.htm`](JS.2_DHTML/jsPosicao.htm) | Demonstra o efeito da posição do bloco `<script>` na página: código no `<head>`, a meio do `<body>` e em resposta ao evento `onLoad`, produzem resultados diferentes com `document.write` e `innerHTML`. |

---

## JS.3 — Imagens Animadas (DHTML)

**Pasta:** [`JS.3_ImagensAnimadas[DHTML]/`](JS.3_ImagensAnimadas[DHTML]/)

Técnicas progressivas de animação de imagens com JavaScript, desde a troca simples ao slideshow automático com navegação.

| Ficheiro | Descrição |
|----------|-----------|
| [`animacao_v1.htm`](JS.3_ImagensAnimadas[DHTML]/animacao_v1.htm) | Versão inicial: ao passar o rato sobre a imagem, a fonte da imagem (`src`) é alterada ciclicamente usando um `switch` com contador. |
| [`animacao_v2.htm`](JS.3_ImagensAnimadas[DHTML]/animacao_v2.htm) | Evolução com array de imagens (`imgArray`). A imagem é seleccionada por índice, separando a lógica de navegação da lógica de apresentação. |
| [`animacao_v3.htm`](JS.3_ImagensAnimadas[DHTML]/animacao_v3.htm) | Introduz o slideshow automático usando `setTimeout` para chamar a função de mudança de imagem a cada intervalo de tempo. |
| [`imageroll.htm`](JS.3_ImagensAnimadas[DHTML]/imageroll.htm) | Slideshow completo: transição automática com `setTimeout` e navegação manual por botões numerados. Permite ao utilizador seleccionar directamente qualquer imagem. |

---

## JS.4 — Menus PopUp (DHTML)

**Pasta:** [`JS.4_MenusPopUp[DHTML]/`](JS.4_MenusPopUp[DHTML]/)

Construção de um menu de navegação interactivo usando exclusivamente CSS e JavaScript, sem recorrer a frames ou tabelas.

| Ficheiro | Descrição |
|----------|-----------|
| [`JSMenus_frame.htm`](JS.4_MenusPopUp[DHTML]/JSMenus_frame.htm) | Página principal com o menu lateral. Utiliza posicionamento absoluto CSS (`position`, `z-index`, `display`) para criar submenus popup que aparecem ao passar o rato. A área de conteúdo é gerida por uma `<iframe>`. |
| [`menus.js`](JS.4_MenusPopUp[DHTML]/menus.js) | Contém as funções JavaScript de mostrar e esconder os submenus (`showMenu`, `hideMenu`), bem como a lógica da barra de estado. |
| [`blank_green.htm`](JS.4_MenusPopUp[DHTML]/blank_green.htm) | Página de destino simples carregada na área de conteúdo ao clicar nos itens do menu. |

---

## JS.5 — Formulários

**Pasta:** [`JS.5_Formularios/`](JS.5_Formularios/)

Apresentação dos principais elementos de um formulário HTML e demonstração da sua leitura via JavaScript.

| Ficheiro | Descrição |
|----------|-----------|
| [`Formulario.htm`](JS.5_Formularios/Formulario.htm) | Formulário completo com: caixa de texto, campo de data, selector de ficheiro, checkboxes, botões de rádio e lista drop-down. Ao submeter, a função `apresentaValores` lê e apresenta os valores seleccionados na mesma página. O evento `onreset` limpa os resultados apresentados. |

---

## JS.6 — Handling Forms

**Pasta:** [`JS.6_HandlingForms/`](JS.6_HandlingForms/)

Validação de formulários e passagem de valores entre páginas.

| Ficheiro | Descrição |
|----------|-----------|
| [`JSValidForm.htm`](JS.6_HandlingForms/JSValidForm.htm) | Validação básica: verifica se os campos obrigatórios (nome, e-mail) estão preenchidos antes de submeter. O evento `onsubmit` usa `return` para bloquear a submissão caso a validação falhe. |
| [`JSValidForm_wValues.htm`](JS.6_HandlingForms/JSValidForm_wValues.htm) | Extensão do exemplo anterior: apresenta os valores validados directamente na página após validação bem-sucedida. |
| [`JSValid_ext.htm`](JS.6_HandlingForms/JSValid_ext.htm) | Demonstra a separação de responsabilidades: as funções de validação são movidas para o ficheiro externo [`scripts/valida.js`](JS.6_HandlingForms/scripts/valida.js). |
| [`JSValidMail.htm`](JS.6_HandlingForms/JSValidMail.htm) | Validação específica de endereços de e-mail com expressão regular, verificando o formato `utilizador@dominio.extensão`. |
| [`JSPassingValues_tabela.htm`](JS.6_HandlingForms/JSPassingValues_tabela.htm) | Recebe valores passados via query string no URL (`?nome=...&email=...`), analisa a string com `split` e apresenta os dados numa tabela. |
| [`mailValido.htm`](JS.6_HandlingForms/mailValido.htm) | Página de confirmação que indica que o endereço de e-mail foi validado com sucesso. |

---

## JS.7 — Dados Locais

**Pasta:** [`JS.7_LocalData/`](JS.7_LocalData/)

Gestão de dados no lado do cliente (CRUD) com persistência progressiva, desde arrays em memória até `localStorage`.

| Ficheiro | Descrição |
|----------|-----------|
| [`biblioteca_v1.htm`](JS.7_LocalData/biblioteca_v1.htm) | Aplicação de biblioteca com interface completa (registo, listagem, filtro e ordenação). Os livros são guardados num **array JavaScript em memória** — os dados perdem-se ao fechar a página. Inclui campos: título, autor, data de publicação e idioma. |
| [`biblioteca_v2.htm`](JS.7_LocalData/biblioteca_v2.htm) | Evolução da versão anterior com persistência real usando **`localStorage`** do browser. Os dados sobrevivem ao fecho da página e são recuperados automaticamente ao reabrir. |

---

## JS.8 — Cookies

**Pasta:** [`JS.8_Cookies/`](JS.8_Cookies/)

Introdução ao mecanismo de cookies para persistência de dados no browser entre sessões.

| Ficheiro | Descrição |
|----------|-----------|
| [`1.JSSetCookie.htm`](JS.8_Cookies/1.JSSetCookie.htm) | Formulário para criar um cookie com nome, valor e data de expiração definida. Demonstra a sintaxe de `document.cookie` para escrita. |
| [`2.JSReadCookie.htm`](JS.8_Cookies/2.JSReadCookie.htm) | Leitura e apresentação dos cookies existentes. Demonstra como percorrer a string `document.cookie` para extrair pares nome/valor. |

---

## JS.9 — Array de Cookies

**Pasta:** [`JS.9_CookieArr/`](JS.9_CookieArr/)

Utilização avançada de cookies para armazenar e gerir colecções de dados (registos de alunos).

| Ficheiro | Descrição |
|----------|-----------|
| [`alunos.htm`](JS.9_CookieArr/alunos.htm) | Aplicação de gestão de alunos que persiste os dados usando **múltiplos cookies** (um por aluno). Permite registar, listar e remover alunos, demonstrando como simular um array de objectos com o mecanismo de cookies. |

---

## Configuração de Debug — launch.json

**Ficheiro:** [`.vscode/launch.json`](.vscode/launch.json)

O projecto inclui uma configuração de depuração do VS Code que permite abrir o ficheiro HTML activo directamente num browser, sem necessidade de configuração adicional.

### Configurações disponíveis

| Nome | Browser | Modo de abertura |
|------|---------|------------------|
| `Launch Edge` | Microsoft Edge | Ficheiro local activo (`${relativeFile}`) |
| `Launch chrome` | Google Chrome | Ficheiro local activo (`${relativeFile}`) |
| `Launch firefox` | Mozilla Firefox | Ficheiro local activo (`${workspaceFolder}/${relativeFile}`) |

### Como utilizar

1. Abrir o ficheiro `.htm` que se pretende testar no editor.
2. Ir ao painel **Run and Debug** (`Ctrl+Shift+D`).
3. Seleccionar a configuração pretendida no menu dropdown (Edge, Chrome ou Firefox).
4. Premir **F5** para iniciar a depuração.

O browser abre automaticamente o ficheiro activo e activa as ferramentas de depuração do VS Code (breakpoints, consola, inspeção de variáveis).

> **Nota:** Para usar com um servidor local (ex: Live Server), substituir `"file"` por `"url"` em cada configuração e indicar o URL correspondente, por exemplo `"url": "http://localhost:5500/${relativeFile}"`.

### Estrutura do ficheiro

```jsonc
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Launch Edge",
            "request": "launch",
            "type": "msedge",
            "file": "${relativeFile}",
            "trace": true
        },
        {
            "name": "Launch chrome",
            "request": "launch",
            "type": "chrome",
            "file": "${relativeFile}",
            "trace": true
        },
        {
            "name": "Launch firefox",
            "request": "launch",
            "type": "firefox",
            "file": "${workspaceFolder}/${relativeFile}"
        }
    ]
}
```

---

## Tecnologias Utilizadas

- HTML4 / HTML5
- CSS2 / CSS3
- JavaScript (ES5/ES6)
- DOM API (`document`, `window`, `navigator`)
- Web Storage API (`localStorage`)
- Cookie API (`document.cookie`)

---

## Como Executar

Abrir os ficheiros `.htm` directamente num browser moderno (Chrome, Firefox, Edge).  
Não é necessário servidor web para a maioria dos exemplos, com excepção dos que utilizam `localStorage` ou cookies, que requerem que os ficheiros sejam servidos por um servidor HTTP local (ex: extensão **Live Server** do VS Code  ver indicações na secção [Configuração de Debug — launch.json](#configuração-de-debug--launchjson)).
