# study-meituan

> 学习《Vue 全家桶 + SSR + Koa2 全栈开发美团网》

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).

## 环境参数

1. Node v14.4.0
2. npm 6.14.5
3. Nuxt 2.0.0
4. Koa 2.6.2
5. Element 2.4.11

```json
{
  "name": "study-meituan",
  "version": "1.0.0",
  "description": "学习《Vue 全家桶 + SSR + Koa2 全栈开发美团网》",
  "author": "negrochn",
  "private": true,
  "scripts": {
    "dev": "cross-env NODE_ENV=development nodemon server/index.js --watch server --exec babel-node",
    "build": "nuxt build",
    "start": "cross-env NODE_ENV=production node server/index.js --exec babel-node",
    "generate": "nuxt generate",
    "lint": "eslint --ext .js,.vue --ignore-path .gitignore ."
  },
  "dependencies": {
    "@nuxtjs/axios": "^5.3.6",
    "babel-preset-es2015": "^6.24.1",
    "cross-env": "^5.2.0",
    "element-ui": "^2.4.11",
    "koa": "^2.6.2",
    "node-sass": "^4.14.1",
    "nuxt": "^2.0.0",
    "sass-loader": "^8.0.2"
  },
  "devDependencies": {
    "nodemon": "^1.18.9",
    "@nuxtjs/eslint-config": "^2.0.0",
    "@nuxtjs/eslint-module": "^1.0.0",
    "babel-eslint": "^10.0.1",
    "eslint": "^6.1.0",
    "eslint-plugin-nuxt": ">=0.4.2"
  }
}
```



