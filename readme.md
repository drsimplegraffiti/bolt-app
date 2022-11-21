[source](https://codevoweb.com/node-typescript-mongodb-jwt-authentication/)


#### Install typescript
> yarn init -y
> yarn
> yarn add -D typescript

#### Initialize a typescript project
> npx tsc --init

#### Add tsconfig configuration
```json
{
  "compilerOptions": {
    "target": "es2016",
    "experimentalDecorators": true,
    "emitDecoratorMetadata": true,
    "module": "commonjs",
    "esModuleInterop": true,
    "forceConsistentCasingInFileNames": true,
    "strict": true,
    "strictPropertyInitialization": false,
    "skipLibCheck": true
  }
}

```

#### Install libraries
> yarn add @typegoose/typegoose bcryptjs config cookie-parser dotenv express jsonwebtoken lodash mongoose redis ts-node-dev zod cors

#### Explanation: 
> dotenv – loads environment variables from a .env file into process.env

> @typegoose/typegoose – writing Mongoose models with TypeScript class
bcryptjs – to hash the password data

> config – allow us to provide TypeScript types for the environment variables we import from the .env file

>cookie-parser – to parse the cookies in the request headers and attach them to req.cookies

> jsonwebtoken – to sign and verify JWTs

> lodash – contains utilities for simplifying common programming tasks.

> ts-node-dev – allow us run the server. An alternative solution is nodemon and ts-node.


#### Install dev dependencies
> yarn add -D morgan typescript

#### Install type definitions
> yarn add -D @types/bcryptjs @types/config @types/cookie-parser @types/express @types/jsonwebtoken @types/lodash @types/morgan @types/node @types/cors


##### start the docker containers
> docker-compose up -d

#### Stop all running containers
> docker rm -f $(docker ps -aq)

#### stop and remove all compose
> docker-compose down -v


#### Endpoints
##### Register
> POST  "url": "http://localhost:8000/api/auth/register"
{
    "name":"jude",
    "email":"jude@gmail.com",
    "password":"judeokoye",
    "passwordConfirm":"judeokoye"
}


##### Login
> POST  "url": "http://localhost:8000/api/auth/login"

### User profile
> GET "url": "http://localhost:8000/api/users/me" 
headers: {
      "authorization": "Bearer token"
}



### All users
> GET "url": "http://localhost:8000/api/users" 
headers:{
      "authorization": "Bearer token"
}




