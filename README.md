# nest-angular-monorepo
![Nest-Angular-Monorepo-banner](https://github.com/gajanannarwade1412/nest-angular-monorepo/assets/150010996/6f56eb18-4026-40cd-8180-3d36f4375f4c)

This document is a guide for configuring API and UI in one repository to create a unified endpoint for NestJS and Angular.
![image](https://github.com/gajanannarwade1412/nest-angular-monorepo/assets/150010996/b2ab7759-f8bb-415f-89da-fdc881aaff0d)

# Benefits:
•	Benefits of this implementation is to reduce the server budget to half.
•	

# 1.	Consolidate UI and API code into a single repository, as shown in the image below:
![Nest-Angular-Monorepo](https://github.com/gajanannarwade1412/nest-angular-monorepo/assets/150010996/803c33da-b23f-440d-b67b-58abfb6d9447)


# 2.	Update the Angular.JSON file 'frontend\angular.json' for changes related to 'dist':
 "outputPath": "../www",
...

# 3.	Install the 'serve-static' npm package in the API terminal:
$ npm install --save @nestjs/serve-static
Reference: https://docs.nestjs.com/recipes/serve-static

# 4.	Include the following code in the root module of the API application inside import, @Module({imports: [...]}):
 ServeStaticModule.forRoot({
 	rootPath: join(__dirname, '../../', 'www'),
 	serveRoot: '/'
 })
 ...

# 5.	API app.controller.ts: 
 @Controller('api')
 ...

# 6.	Commands: 
$ cd frontend 
$ npm run build 
$ cd .. 
$ npm run build 
$ npm run start

# Application is live 🎉: (Wait up to 4min to start server)
UI: https://nest-angular-monorepo.onrender.com
API: https://nest-angular-monorepo.onrender.com/api
Swagger: https://nest-angular-monorepo.onrender.com/swagger

# Git Repository for reference:
https://github.com/gajanannarwade1412/nest-angular-monorepo

# Versions: 
$ ng v 
Angular CLI: 16.2.3

$ ionic -v 
Ionic CLI 7.1.1

$ nest -v 
10.1.18

$ node -v 
v20.6.1

$ npm -v 
9.8.1
