## Pontos positivos
- O event loop do Deno é feito em Rust, tornando o processo de delegar as tarefas para as threads muito mais rápido.
- O gerenciamento de dependências é muito mais eficaz do que o atual que usamos (npm).
- Podemos usar todos os pacotes do NPM dentro do Deno,
  -  Exemplo de importação feito no NodeJS:
      ```typescript 
      import express from 'express'
      ```
   -  Exemplo de importação feito no Deno:
      ```typescript 
      import express from 'npm:express@4'
      ```
- Roda nativamente Typescript e ES Modules.
- Não será necessário ter uma curva de aprendizado de uma novam linguagem.
- A construção do build é muito simplificado. Pelo fato do Deno rodar nativamente com Typescript, não será necessário, realizar o processo de transpilação para o Javascript como é feito no Node.
- Temos todos os pacotes do Deno Land + NPM
- A importação dos pacotes é feita via URL dentro do deno.json e importado no código através de alias, isso nos livra da pasta `node_modules` <3
  ```json
   {
     "imports": {
       "std/": "https://deno.land/std@0.223.0/"
     },
     "tasks": {
       "dev": "deno run --watch main.ts"
     }
   }
  ```
- O Deno por padrão limita as permissões em arquivos, uso de rede, variáveis de ambiente e etc. Isso permite uma segurança a mais no controle de permissões de cada aplicação, pois o permissionamento torna-se mais granular.
- Existem alguns casos onde precisamos usar uma biblioteca, porem, em duas versões diferentes, isso pode ocorrer em migrações principalmente. Com o modelo de importação de libs do Deno conseguimos configurar isso facilmente,

  `deno.json`
  ```json
  {
    "imports": {
      "old-firebase": "npm:firebase@8",
      "firebase": "npm:firebase@9"
    }
  }
  ```
  
  `index.ts`
  ```ts
  import firebase from 'firebase'
  import oldFirebase from 'old-firebase'
  ```

## Pontos negativos
- Nova runtime, novos problemas. Podemos acabar adquirindo problemas não habituais, ou problemas que facilmente resolveríamos no Node demorar mais para resolver com o Deno.
- Existem os riscos de quebras enormes no funcionamento de uma major para outra, pois atualmente o Deno está na versão 1. Então realizar updates de major no ponto em que ele está hoje, pode ser bem arriscado.
- Hoje, é simples realizarmos a publicação de pacotes internos no NPM, e usando o Github. Não tenho certeza se teremos a mesma facilidade em fazer isso com o Deno Land

## Node x Deno
No artigo [escolhendo o runtime certo para o seu projeto](https://medium.com/@parthp4018/deciding-between-deno-js-and-node-js-choosing-the-right-runtime-for-your-project-ca5c47c771c9), temos uma imagem bem legal, para conseguirmos visualizar as principais diferenças entre Node e Deno

![image](https://github.com/somostera/RFC/assets/49827992/1438515f-ff0f-48b9-89a9-25c2d66d240c)


## Referências
- [Artigo auxiliar](https://medium.com/@parthp4018/deciding-between-deno-js-and-node-js-choosing-the-right-runtime-for-your-project-ca5c47c771c9)
- [Repositório Deno](https://github.com/denoland/deno)
- [Criação de libs privadas](https://docs.deno.com/runtime/manual/basics/modules/private)
- [Deno Docs](https://deno.com/)
- [Deno Land](https://deno.land/x)
