install nestjs
---
```
$ npm i -g @nestjs/cli
$ nest

```

create project
---
```
$ nest new

? What name would you like to use for the new project? hi-nest
> npm
```
open vscode
---
```
cd hi-nest
code .
```

github
---
https://github.com/new

1. Repository name : hi-nest
2. Description : Learning NestJS by making an enterprise ready API
3. Create repository


```
$ git remote add origin https://github.com/kangtae49/hi-nest.git
```

package.json
``` json
{
    
    ...
    
    "scripts": {
    
    ...
    
    "start": "nest start",
    "start:dev": "nest start --watch",
    "start:debug": "nest start --debug --watch",
    "start:prod": "node dist/main",
    
    ...
    
    }

    ...

}
```

run
---
```
$ npm run start:dev
```

http://localhost:3000/

app.controller.ts
``` ts
  @Get("/hello")
  sayHello(): string {
    return this.appService.getHi();
  }
``` 
app.service.ts
``` ts
getHi(): string {
  return "Hi Nest";
}
```


http://localhost:3000/hello

generate controller
---
```
$ nest
$ nest g co
? What name would you like to use for the controller? movies
```

movies/movies.controller.ts
``` ts
@Controller('movies')
export class MoviesController {
  @Get()
  getAll() {
      return 'This will return all movies';
  }
}
```
http://localhost:3000/movies

``` ts
getOne(@Param('id') movieId: string) {
    return `This will return one movie with the id: ${movieId}`;
}
```

http://localhost:3000/movies/1

http://localhost:3000/movies/search?year=2000

generate service
---
```
$ nest g s
? What name would you like to use for the service? movies
```

install validator
---
```
$ npm i class-validator class-transformer
```

install mapped-types
---
```
$ npm i @nestjs/mapped-types
```

generate module
---
```
nest g mo
? What name would you like to use for the module? movies
```

test
---
```
$ npm run test:cov

$ npm run test: watch

$ npm run test:e2e

```

