# Volar

> ⚡ Explore high-performance tooling for Vue

- [Vue Language Features](https://github.com/johnsoncodehk/volar/tree/master/extensions/vscode-vue-language-features) (👈 The Main VSCode Extension)\
*Vue language support extension for VSCode*
- [TypeScript Vue Plugin](https://github.com/johnsoncodehk/volar/tree/master/extensions/vscode-typescript-vue-plugin) \
*VSCode extension to support Vue in TS server*
- [vue-tsc](https://github.com/johnsoncodehk/volar/tree/master/packages/vue-tsc) \
*Type-check and dts build command line tool*

Discord: https://discord.gg/5bnSSSSBbK

## IDE Supports by Community

[yaegassy/coc-volar](https://github.com/yaegassy/coc-volar) ⚡ 🤝 \
*Vue language client for coc.nvim*

[neovim/nvim-lspconfig](https://github.com/neovim/nvim-lspconfig) ⚡ 🤝 \
*Vue language server configuration for Neovim* \
[[Multiple servers set up tutorial](https://github.com/johnsoncodehk/volar/discussions/606)]

[mattn/vim-lsp-settings](https://github.com/mattn/vim-lsp-settings) ⚡ \
*Vue language server auto configuration for vim-lsp*

[sublimelsp/LSP-volar](https://github.com/sublimelsp/LSP-volar) 🤝 \
*Vue language client for Sublime*

[kabiaa/atom-ide-volar](https://github.com/kabiaa/atom-ide-volar) \
*Vue language client for Atom*

[jadestrong/lsp-volar](https://github.com/jadestrong/lsp-volar) ⚡ 🤝 \
*Vue language client for Emacs*

\* ⚡ support [multiple servers](https://github.com/johnsoncodehk/volar/discussions/393#discussioncomment-1213736) \
\* 🤝 support [take over mode](https://github.com/johnsoncodehk/volar/discussions/471)

## High Level System Overview

```mermaid
flowchart LR
    %% IDEs
    VSC[VSCode]
    COC[coc.nvim]
    NEO[Neovim]
    VIM[vim-lsp]
    SUBLIME[Sublime]
    ATOM[Atom]
    EMACS[Emacs]

    %% Language Clients
    COC_VUE[yaegassy/coc-volar]
    NEO_VUE[neovim/nvim-lspconfig]
    VIM_VUE[mattn/vim-lsp-settings]
    SUBLIME_VUE[sublimelsp/LSP-volar]
    ATOM_VUE[kabiaa/atom-ide-volar]
    EMACS_VUE[jadestrong/lsp-volar]
    VSC_TS[vscode.typescript-language-features]

    %% Volar - Extensions
    VSC_VUE[vscode-vue-language-features]
    VSC_TSVP[vscode-typescript-vue-plugin]

    %% Volar - Packages
    VUE_SERVER["@volar/vue-language-server"]
    VTS["@volar/vue-typescript"]
    VUE_CG["@volar/vue-code-gen"]
    VUE_SERVICE["@volar/vue-language-service"]
    PUG_SERVICE["@volar/pug-language-service"]
    TS_SERVICE["@volar/typescript-language-service"]
    VTSC[vue-tsc]
    TSVP[typescript-vue-plugin]

    %% Language Services
    HTML_SERVICE[vscode-html-languageservice]
    CSS_SERVICE[vscode-css-languageservice]
    JSON_SERVICE[vscode-json-languageservice]
    TS[typescript]

    subgraph VUE_CLIENTS[Language Clients]
      direction LR
      VUE_CLIENT_API[api]
      VUE_CLIENT_DOC[doc]
      VUE_CLIENT_HTML[html]
    end

    subgraph Embedded Language Services
      direction LR
      TS_SERVICE
      PUG_SERVICE
      HTML_SERVICE
      CSS_SERVICE
      JSON_SERVICE
    end

    VSC --> VSC_VUE
    COC --> COC_VUE
    NEO --> NEO_VUE
    SUBLIME --> SUBLIME_VUE
    ATOM --> ATOM_VUE
    EMACS --> EMACS_VUE
    VIM --> VIM_VUE

    VSC_VUE --> VUE_CLIENTS
    COC_VUE --> VUE_CLIENTS
    NEO_VUE --> VUE_CLIENTS
    SUBLIME_VUE --> VUE_CLIENTS
    ATOM_VUE --> VUE_CLIENTS
    EMACS_VUE --> VUE_CLIENTS
    VIM_VUE --> VUE_CLIENTS

    VUE_CLIENTS -- Language Server Protocol --> VUE_SERVER

    VSC --> VSC_TS
    VSC_TS --> VSC_TSVP
    VSC_TSVP --> TSVP
    VUE_SERVER --> VUE_SERVICE
    VTSC --> VTS
    TSVP --> VTS

    VUE_SERVICE --> VTS
    VUE_SERVICE --> TS_SERVICE
    VUE_SERVICE --> PUG_SERVICE
    VUE_SERVICE --> HTML_SERVICE
    VUE_SERVICE --> CSS_SERVICE
    VUE_SERVICE --> JSON_SERVICE

    VTS --> TS
    VTS --> VUE_CG
```

## Sponsors

<p align="center">
  <a href="https://cdn.jsdelivr.net/gh/johnsoncodehk/sponsors/sponsors.svg">
    <img src='https://cdn.jsdelivr.net/gh/johnsoncodehk/sponsors/sponsors.svg'/>
  </a>
</p>
