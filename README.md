# Monorepo application example using Lerna

##### Steps to create monorepo app

```sh
$ npm i -g lerna
$ mkdir react-qstart-lerna
$ cd react-qstart-lerna
$ lerna init
$ git submodule add -b master git@github.com:sagarpanda/react-qstart.git packages/react-qstart
$ git submodule add -b master git@github.com:sagarpanda/reactjs-basics.git packages/reactjs-basics
```
To run app
```sh
$ lerna bootstrap
$ lerna run build --scope react-qstart
$ lerna run start --scope reactjs-basics
```
