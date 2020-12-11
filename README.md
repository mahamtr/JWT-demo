# JWT-demo Maai Ham


## Generate App todo example LB4


`lb4 example todo`

## Add authentication-jwt package


`npm i --save @loopback/authentication @loopback/authentication-jwt`


## Add JWT component to App in src/application.ts


```
    this.component(AuthenticationComponent);
    // Mount jwt component
    this.component(JWTAuthenticationComponent);
    // Bind datasource
    this.dataSource(DbDataSource, UserServiceBindings.DATASOURCE_NAME);
```

add inside ctor


## Add user controller


`lb4 controller`

add snippet from https://github.com/strongloop/loopback-next/blob/master/examples/todo-jwt/src/controllers/user.controller.ts

## Add decorator to any controller


`@authenticate('jwt') // <---- Apply the @authenticate decorator at the class level`

add decorator for authentication to any controller

## deploy heroku

--add "heroku-postbuild": "npm run build"
--update  "start": "node .",
--delete  "prestart": "npm run rebuild",

from package.json

## testing in live App

Do a signup first and then login to obtain token.

http://{URL}/signup
http://{URL}/login



