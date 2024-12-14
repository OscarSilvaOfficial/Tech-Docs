# Bun

- Resolve módulos através do seu próprio gerênciador de dependências
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
