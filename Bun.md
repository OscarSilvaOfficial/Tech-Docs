# Bun

## Package Manager

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

- É possível ter uma tabela com pacotes instalados, versão atual, e última versão rodando o comando `bun outdated`

![Captura de tela de 2024-12-14 01-09-32](https://github.com/user-attachments/assets/5b3cdcae-dfc9-486e-9e46-59ac2a7ec24e)


## CI/CD

- Usa o [oven-sh/setup-bun](https://github.com/oven-sh/setup-bun) como pacote oficial para realizar CI/CD pelo Github Actions
