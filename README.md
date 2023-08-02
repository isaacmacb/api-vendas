server.ts {
--import 'reflect-metadata': Isso é uma importação do pacote reflect-metadata, que é usado para habilitar a reflexão de metadados em TypeScript. Ele é frequentemente utilizado em conjunto com bibliotecas como o TypeORM, que precisa de informações adicionais sobre as classes e entidades definidas no código.

--import express, { NextFunction, Request, Response } from 'express';: Aqui, estamos importando o módulo express e algumas interfaces (NextFunction, Request, Response) do pacote express. O express é um framework para aplicativos web Node.js que simplifica o processo de criação de APIs e aplicativos web.

--import cors from 'cors';: O pacote cors é utilizado para habilitar o Cross-Origin Resource Sharing (CORS) em nossa aplicação. Isso permite que nossa API seja acessada de um domínio diferente do que a originou, tornando-a acessível a partir de aplicações front-end em diferentes domínios.

--import routes from './routes';: Aqui, estamos importando o arquivo routes.ts (ou .js, dependendo do ambiente de execução) que contém as definições das rotas da nossa API.

--const app = express();: Criamos uma instância do aplicativo Express, que será a base para configurarmos nossas rotas e middlewares.

--app.use(cors());: Habilitamos o middleware de CORS para que nossa aplicação permita solicitações de diferentes origens.

--app.use(express.json());: Habilitamos o middleware express.json(), que analisa as requisições com formato JSON e transforma o corpo da requisição em um objeto JavaScript. Isso nos permite manipular os dados enviados pelos clientes como objetos JavaScript.

--app.use(routes);: Aqui, estamos aplicando o middleware de rotas definido no arquivo routes.ts (ou .js) à nossa aplicação. Esse middleware mapeia as requisições para os respectivos manipuladores de rotas definidos na API.

--O próximo trecho do código é um middleware de tratamento de erros: (error: Error, resquest: Request, response: Response, next: NextFunction) => { ... }. Esse middleware captura erros que ocorrem em rotas anteriores e trata de forma apropriada. Se o erro for uma instância de AppError (um erro personalizado definido em outro lugar), ele retorna uma resposta com o status e a mensagem de erro específicos. Caso contrário, retorna um erro 500 (Internal Server Error) com uma mensagem padrão.

--app.listen(3333, () => { ... }): Finalmente, a aplicação é iniciada e começa a ouvir por requisições na porta 3333. Quando a aplicação está pronta para receber solicitações, a mensagem "Server está on port 3333" é exibida no console.
}
