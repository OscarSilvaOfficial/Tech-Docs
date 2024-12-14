# Bun

## Package Manager

- Para salvar as dependências, bun irá criar um arquivo binário chamado `bun.lockb`
  - O lock file é agnóstico a sistema operacional [ref](https://bun.sh/docs/install/lockfile#platform-specific-dependencies)
  - Junto com esse lock file, é gerado um package.json, para conseguir ler as dependências do projeto 
- Resolve módulos através do seu próprio gerênciador de dependências
  - O registry padrão para a publicação de pacotes é o **npm**
  - Consegue trabalhar com arquivos de gerênciamento de memória pré-existentes
    - **npm, yarn. pnpm**

- Suporta instalação de pacotes npm, github, git, tarball.
```json
{
  "dependencies": {
    "dayjs": "git+https://github.com/iamkun/dayjs.git",
    "lodash": "git+ssh://github.com/lodash/lodash.git#4.17.21",
    "moment": "git@github.com:moment/moment.git",
    "zod": "github:colinhacks/zod",
    "react": "https://registry.npmjs.org/react/-/react-18.2.0.tgz"
  }
}
```

- É possível ter uma tabela com pacotes instalados, versão atual, e última versão rodando o comando ``
```zsh
bun outdated
```

![Captura de tela de 2024-12-14 01-09-32](https://github.com/user-attachments/assets/5b3cdcae-dfc9-486e-9e46-59ac2a7ec24e)

- Quando é instalado um pacote, o gerênciador faz cache em disco da dependência no diretório `~/.bun/install/cache`

## CI/CD

- Usa o [oven-sh/setup-bun](https://github.com/oven-sh/setup-bun) como pacote oficial para realizar CI/CD pelo Github Actions
