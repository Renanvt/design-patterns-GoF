# Configurando um projeto **typescript**

```bash
npm init -y
```
Inicia um projeto node, cria o package .json

# Configurando o **package.json**
```bash
npm i typescript -D
```
Instala o typescript para poder compilar o projeto

# Configurando o **tsconfig.json**, arquivo de configuração do typescript

```ts
{
  "compilerOptions": {
    "target": "ES2019",
    "module": "CommonJS",
    "lib": [
      "ESNext",
      "DOM"
    ],
    "outDir": "./dist",
    "rootDir": "./src",
    "removeComments": true,
    "noEmitOnError": true,
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true
  },
  "include": [
    "./src"
  ]
}
```

**ComilerOptions** - Configurações referente ao projeto

**Target** - Ambiente que será rodado o projeto em produção. Precisa saber qual é a versão do ECMA script que irá rodar no ambiente de produção

**Module** - Sistema de módulos

**lib** - DOM - console.log, etc

**outDir** - Quando compilar o projeto, será compilado para a pasta definida

**rootDir** - Raiz do meu projeto

**removeComments** - Remover comentários quando compilar o código

**noEmitOnError** - Se tiver algum erro no código, não omitir o código compilado

**strict** - Modo restrito

**esModuleInterop** - Habilita interoperabilidade entre commonjs e es6modules

**skipLibCheck** - Pular a checkagem de arquivos que são declaration files, esses arquivos tem a extensão .d.js, que geramente já estão checados, acelerando a compilação do projeto

**forceConsistentCasingInFileNames** - Não permitir referências incosistentes para nome de arquivos

**include** - Só checke a pasta definida

**exclude** - Não checke a pasta definida

## Configurar o **git**
```bash
git init
```
* Criar o arquivo **.gitgnore** e ignorar os seguintes arquivos:
*node_modules*
*dist*

```bash
git config user.name "Jonatan Renan"
git config user.email "jonatan_rvs@hotmail.com"
```

# Instalar o **Code Runner**
O javascript irá pareçer com o typescript, ou seja, vai pareçer que ele é uma linguagem interpretada ao invés de ser compilada

**Usando o tsnode para compilar os arquivos**

```bash
npm i -D ts-node
```
Instala o ts-node como pacote Dev

```bash
npx ts-node src/index.ts
```
Executa o projeto como se fosse uma linguagem interpretada

# Criar a pasta .vscode
> setings.json
```ts
{
  "window.zoomLevel": 0,
  "code-runner.executorMap": {
    "typescript": "clear && npx ts-node --files --transpile-only",
    "python": "clear && venv/bin/python"
  },
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true,
    "source.fixAll": true
  },
  "python.pythonPath": "venv/bin/python",
  "cSpell.enabled": true
}
```
**window.zoomLevel** - Configuração referente ao meu projeto. Aplica zoom
**typescript** - Limpa a tela, executa o projeto e faz com que o tsnode transpire muito mais rápido os arquivos

**Impedir que o visual studio altere o código ao salvar**
> settings.json
//Auto fix on save
**editor.codeActionsOnSave**...
Copia essa configuração e cola dentro de **settings.json**
```ts
"editor.codeActionsOnSave": {
    "source.fixAll.eslint": false,
    "source.fixAll": false
```

# Configura o *ESlint*
Fazer com que a linguagem siga um padrão
> .eslintrc.js
```ts
module.exports = {
  env: {
    browser: true,
    es6: true,
    node: true,
  },
  extends: [
    'eslint:recommended',
    'plugin:@typescript-eslint/eslint-recommended',
    'plugin:@typescript-eslint/recommended',
    'plugin:prettier/recommended',
  ],
  globals: {
    Atomics: 'readonly',
    SharedArrayBuffer: 'readonly',
  },
  parser: '@typescript-eslint/parser',
  parserOptions: {
    ecmaVersion: 11,
    sourceType: 'module',
  },
  plugins: ['@typescript-eslint'],
  rules: {
    '@typescript-eslint/no-empty-function': 'off',
  },
};
```
## Precisa instalar as dependências definidas em extends

```bash
npm i -D eslint @typescipt-eslint/eslint-plugin @typescript-eslint/parser prettier eslint-config-prettier eslint-plugin-prettier
```

# Configurar o *prettier*
> .prettierrc.js
```ts
module.exports = {
  semi: true,
  trailingComma: 'all',
  singleQuote: true,
  printWidth: 80,
  tabWidth: 2,
}
```
**printWidth** - Na hora que passar da linha definida, quebra a linha

Instalar a extensão **reload** para poder reiniciar o projeto com as configurações
Para trabalhar no front-end, configura-se o **webpack**