## Setup do projeto
    mkdir menu-api
    cd menu-api

    npm init -y

    npm i express dotenv cors helmet

    npm i -D typescript

    npm i -D @types/node @types/express @types/dotenv @types/cors @types/helmet

    npx tsc --init

    echo PORT=7000 > .env

    mkdir src

    touch src/index.ts

    npm i -D ts-node-dev
#
## Configurações no package.json
    --respawn: Keep watching for changes after the script has exited.

    --pretty: Use pretty diagnostic formatter (TS_NODE_PRETTY).

    --transpile-only: Use TypeScript's faster transpileModule (TS_NODE_TRANSPILE_ONLY).

    src/index.ts: This is the application's entry file.
#
## Executando o projeto
    npm run dev
#
## Recursos da aplicação
Abaixo a chamado de alguns endpoints via curl.

### Recuperar todos os items
    curl http://localhost:7000/api/menu/items -i

### Recuperar um item com id 2
    curl http://localhost:7000/api/menu/items/2 -i

### Incluindo um item
    curl -X POST -H 'Content-Type: application/json' -d '{
        "name": "Salad",
        "price": 499,
        "description": "Fresh",
        "image": "https://cdn.auth0.com/blog/whatabyte/salad-sm.png"
    }' http://localhost:7000/api/menu/items -i

### Atualizando um item
    curl -X PUT -H 'Content-Type: application/json' -d '{
        "name": "Spicy Pizza",
        "price": 599,
        "description": "Blazing Good",
        "image": "https://cdn.auth0.com/blog/whatabyte/pizza-sm.png"
    }' http://localhost:7000/api/menu/items/2 -i

### Deletando um item
    curl -X DELETE http://localhost:7000/api/menu/items/2 -i

## Configurando regras de segurança 
    https://auth0.com/blog/node-js-and-typescript-tutorial-build-a-crud-api/