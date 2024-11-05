# Configuração do Biome no Projeto

Este guia fornece instruções para configurar o **Biome** no projeto, permitindo melhorar a formatação de código, análise estática e a padronização de estilos.

---

## Pré-requisitos

- **Node.js**: Certifique-se de que o Node.js está instalado em seu sistema. Você pode baixá-lo [aqui](https://nodejs.org/).
- **NPM** ou **Yarn**: Utilize um dos gerenciadores de pacotes para instalar o Biome.

## Passo a Passo

### 1. Instalação do Biome

Para instalar o Biome localmente no projeto, execute um dos seguintes comandos na raiz do projeto:

```bash
npm install biome --save-dev
# ou
yarn add biome --dev
```

### 2. Configuração do Biome

Após a instalação, você pode configurar o Biome usando o comando automático ou criando o arquivo manualmente:

#### Configuração automática

Execute o comando abaixo para iniciar uma configuração básica:

```bash
npx @biomejs/biome init
```

#### Configuração manual

Crie um arquivo `biome.config.json` na raiz do projeto com o seguinte conteúdo para personalizar as regras e o estilo:

```json
{
  "formatter": {
    "enabled": true,
    "formatWithErrors": false,
    "ignore": [],
    "attributePosition": "auto",
    "indentStyle": "tab",
    "indentWidth": 1,
    "lineWidth": 80,
    "lineEnding": "lf"
  },
  "javascript": {
    "formatter": {
      "arrowParentheses": "always",
      "bracketSameLine": false,
      "bracketSpacing": true,
      "jsxQuoteStyle": "double",
      "quoteProperties": "asNeeded",
      "semicolons": "always",
      "trailingCommas": "all"
    }
  },
  "typescript": {
    "formatter": {
      "arrowParentheses": "always",
      "bracketSameLine": false,
      "bracketSpacing": true,
      "jsxQuoteStyle": "double",
      "quoteProperties": "asNeeded",
      "semicolons": "always",
      "trailingCommas": "all"
    }
  },
  "json": {
    "formatter": {
      "trailingCommas": "none"
    }
  }
}
```

Aqui estão algumas das configurações básicas para o Biome:
- `formatter`: Define opções de formatação, como uso de tabulação e comprimento de linha.
- `javascript` e `typescript`: Configurações específicas para JavaScript e TypeScript, como estilo de aspas e uso de ponto e vírgula.

### 3. Executando o Biome

Você pode rodar o Biome para verificar e corrigir problemas de formatação no projeto:

#### Verificando problemas

```bash
npx biome check .
```

#### Corrigindo problemas automaticamente

```bash
npx biome fix .
```

### 4. Integrando o Biome com o VS Code

Para facilitar o uso do Biome no VS Code, instale a extensão **Biome** na loja de extensões do editor.

### 5. Configurando o Ambiente de Desenvolvimento

Para que o código seja automaticamente formatado ao salvar no VS Code, siga os passos abaixo:

1. Crie uma pasta `.vscode` na raiz do projeto.
2. Dentro dessa pasta, crie um arquivo `settings.json` com o seguinte conteúdo:

    ```json
    {
      "editor.formatOnSave": true,
      "editor.defaultFormatter": "biomejs.biome",
      "[typescript]": {
        "editor.defaultFormatter": "vscode.typescript-language-features"
      }
    }
    ```

Essas configurações garantem que o Biome seja usado como formatador padrão e que o editor formate o código ao salvar.

---

### Referências

- [Documentação oficial do Biome](https://biomejs.dev/docs)
- [Biome no GitHub](https://github.com/biomejs/biome)

---

Este guia deve ajudar você a configurar e utilizar o Biome em seu projeto com eficiência.
