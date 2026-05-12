# 📋 Formulário de Cadastro com Validação

> Formulário de criação de conta com validação em tempo real, medidor de força de senha e design dark premium — tudo em HTML/CSS/JS puro, sem dependências externas.

---

## ✨ Visão Geral

Este projeto é um formulário de cadastro (`Formulariovalidacao.HTM`) construído com HTML, CSS e JavaScript vanilla. Ele oferece uma experiência de usuário refinada com feedback visual imediato, sem necessidade de frameworks ou bibliotecas JavaScript.

---

## 🖥️ Preview

O formulário apresenta um card centralizado sobre fundo escuro com os seguintes campos:

| Campo | Tipo | Validação |
|---|---|---|
| Nome completo | `text` | Obrigatório, apenas letras, nome + sobrenome |
| E-mail | `text` | Formato válido `usuario@dominio.com` |
| Senha | `password` | Mín. 8 caracteres, maiúscula, número |
| Confirmar senha | `password` | Deve coincidir com a senha |

---

## 🚀 Como Usar

Não há instalação ou build necessários. Basta abrir o arquivo no navegador:

```bash
# Opção 1 — Abrir diretamente
Clique duas vezes em Formulariovalidacao.HTM

# Opção 2 — Via terminal
open Formulariovalidacao.HTM        # macOS
start Formulariovalidacao.HTM       # Windows
xdg-open Formulariovalidacao.HTM   # Linux
```

Compatível com qualquer navegador moderno (Chrome, Firefox, Edge, Safari).

---

## ⚙️ Funcionalidades

### Validação em Tempo Real
- Erros são exibidos ao sair do campo (`onblur`) ou enquanto o usuário digita (`oninput`), após o primeiro toque no campo
- Campos marcados visualmente em vermelho (erro) ou verde (válido)
- Mensagens de erro descritivas abaixo de cada campo

### Medidor de Força de Senha
Aparece automaticamente ao digitar no campo de senha e avalia 4 critérios:

```
[ ] 8+ caracteres
[ ] Letra maiúscula
[ ] Número
[ ] Símbolo especial
```

A barra de força tem 4 níveis com cores progressivas:

```
Nível 1 → Fraca     → Vermelho   (#f05a5a)
Nível 2 → Razoável  → Laranja    (#f0a060)
Nível 3 → Boa       → Verde lima (#c8f060)
Nível 4 → Forte     → Verde      (#60f0a0)
```

### Mostrar / Ocultar Senha
Botão de olho nos campos de senha e confirmação para alternar a visibilidade.

### Envio do Formulário
- Valida todos os campos antes de aceitar o envio
- Exibe banner de sucesso verde: `✓ Conta criada com sucesso! Bem-vindo(a).`
- Limpa o formulário após sucesso
- Banner some automaticamente após **5 segundos**

---

## 🎨 Design System

### Paleta de Cores

```css
--bg:           #0d0d0f   /* Fundo da página */
--surface:      #17171a   /* Card principal */
--surface2:     #1f1f24   /* Inputs */
--text:         #f0ede8   /* Texto principal */
--muted:        #7a7a84   /* Labels e ícones */
--accent:       #c8f060   /* Verde lima — destaque */
--danger:       #f05a5a   /* Erros */
--success:      #60f0a0   /* Sucesso */
```

### Tipografia

| Fonte | Uso |
|---|---|
| **DM Serif Display** | Título do card (`h1`) |
| **DM Sans** (300/400/500) | Corpo, labels, inputs |

Ambas carregadas via Google Fonts.

---

## 🗂️ Estrutura do Arquivo

```
Formulariovalidacao.HTM
│
├── <head>
│   ├── Meta tags (charset, viewport)
│   ├── Google Fonts (DM Serif Display + DM Sans)
│   └── <style> — CSS completo (variáveis, layout, componentes, animações)
│
├── <body>
│   └── .card
│       ├── .card-header (título e subtítulo)
│       ├── #f-name     (campo Nome)
│       ├── #f-email    (campo E-mail)
│       ├── .divider
│       ├── #f-password (campo Senha + medidor de força)
│       ├── #f-confirm  (campo Confirmar senha)
│       ├── .submit-btn (botão de envio)
│       └── .success-banner (feedback de sucesso)
│
└── <script>
    ├── RULES{}         — Regras de validação por campo
    ├── validate()      — Valida campo e atualiza UI
    ├── validateBlur()  — Marca campo como "tocado" e valida
    ├── updateStrength()— Calcula e renderiza força da senha
    ├── togglePwd()     — Alterna visibilidade da senha
    └── submitForm()    — Valida tudo e processa envio
```

---

## 🔍 Detalhes de Validação

### Nome completo
- Campo obrigatório
- Aceita apenas letras (incluindo acentos), espaços, hífens e apóstrofos
- Exige ao menos duas palavras (nome + sobrenome)
- Mínimo de 4 caracteres

### E-mail
- Campo obrigatório
- Formato: `algo@algo.tld` (TLD com mínimo 2 caracteres)

### Senha
- Campo obrigatório
- Mínimo de 8 caracteres
- Ao menos uma letra maiúscula
- Ao menos um número
- *(Símbolo especial é exibido no checklist mas não bloqueia o envio)*

### Confirmar senha
- Campo obrigatório
- Deve ser idêntica ao campo de senha

---

## 🛠️ Tecnologias

- **HTML5** — Estrutura semântica
- **CSS3** — Variáveis, Flexbox, transições, animações, pseudo-elementos
- **JavaScript ES6+** — Validação, manipulação de DOM, eventos
- **Google Fonts** — DM Serif Display, DM Sans

> Zero dependências. Zero frameworks. Zero build step.

---

## 📁 Arquivos do Projeto

```
/
└── Formulariovalidacao.HTM   # Arquivo único — contém HTML, CSS e JS
```

---

## 🔮 Possíveis Melhorias Futuras

- [ ] Integração com backend / API REST para persistência de dados
- [ ] Validação de e-mail duplicado via fetch
- [ ] Campo de telefone com máscara
- [ ] Suporte a tema claro (`prefers-color-scheme: light`)
- [ ] Acessibilidade aprimorada (`aria-live`, `aria-invalid`)
- [ ] Testes unitários das funções de validação

---

## 📄 Licença

Este projeto é de uso livre para fins educacionais e de estudo.

---

## 👨‍💻 Autor

Desenvolvido por Rafael Figueiredo 💻

📫 Contato LinkedIn: https://www.linkedin.com/in/rafael-figueiredo-de-andrade/ GitHub: https://github.com/Randrade17 ⭐ Apoie o Projeto

Se você gostou do projeto:

⭐ Deixe uma estrela no repositório 🍴 Faça um fork 🛠️ Contribua com melhorias
