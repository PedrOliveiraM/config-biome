# Configuração do Biome no Projeto

## Este guia explica como configurar o **Biome** no seu projeto para melhorar a formatação de código, análise estática e padronização de estilos.

## Pré-requisitos

- **Node.js**: Certifique-se de que o Node.js está instalado. [Baixar Node.js](https://nodejs.org/).
- **NPM** ou **Yarn**: Necessário para instalar dependências.

---

## Passo a Passo

### 1. Instale o Biome

Na raiz do projeto, execute um dos comandos abaixo para instalar o Biome como dependência de desenvolvimento:

```bash
npm install biome --save-dev
# ou
yarn add biome --dev
```

---

### 2. Configure o Biome

Você pode configurar o Biome de duas formas: automaticamente ou manualmente.

#### Configuração automática

Execute o comando abaixo para gerar uma configuração padrão:

```bash
npx @biomejs/biome init
```

#### Configuração manual

Crie um arquivo `biome.json` na raiz do projeto com o seguinte conteúdo para personalizar as regras:

```json
{
  "$schema": "https://biomejs.dev/schemas/1.9.4/schema.json",
  "organizeImports": {
    "enabled": true
  },
  "formatter": {
    "indentStyle": "space",
    "indentWidth": 2,
    "lineWidth": 90
  },
  "javascript": {
    "formatter": {
      "arrowParentheses": "asNeeded",
      "jsxQuoteStyle": "double",
      "quoteStyle": "single",
      "semicolons": "asNeeded",
      "trailingCommas": "es5"
    }
  },
  "linter": {
    "enabled": true,
    "rules": {
      "recommended": true,
      "style": {
        "noNonNullAssertion": "off",
        "useImportType": "off"
      }
    }
  },
  "files": {
    "ignore": ["node_modules", ".history"]
  }
}
```

> ⚠️ **Nota:** Se você estiver usando Prettier ou ESLint no projeto, conflitos podem ocorrer. A extensão do Biome no VS Code pode ajudar na migração dessas configurações.

---

### 3. Execute o Biome

Após a configuração, você pode verificar e corrigir problemas de formatação no projeto:

- **Verificar problemas**:

  ```bash
  npx biome check .
  ```

- **Corrigir automaticamente**:
  ```bash
  npx biome fix .
  ```

---

### 4. Integração com o VS Code

Para utilizar o Biome diretamente no VS Code:

1. Instale a extensão **Biome** na loja de extensões do editor.
2. Configure o formatador padrão no VS Code:

   Crie ou edite o arquivo `.vscode/settings.json` na raiz do projeto com o seguinte conteúdo:

   ```json
   {
     "editor.formatOnSave": true,
     "editor.defaultFormatter": "biomejs.biome"
   }
   ```

Essas configurações garantem a formatação automática ao salvar arquivos.

---

<h3>Comparação com e sem Biome</h3>

<p align="center">
  <img src="Before Biome.png" alt="Antes do Biome" width="45%" />
  <img src="After Biome.png" alt="Depois do Biome" width="45%" />
</p>

---

### Referências

- [Documentação oficial do Biome](https://biomejs.dev/docs)
- [Repositório do Biome no GitHub](https://github.com/biomejs/biome)

---
