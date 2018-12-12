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
##### With yarn workspace
Add `{ "private": true, "workspaces": ["packages/*"] }` in package.json
```javascript
{
  "name": "root",
  "private": true,
  "devDependencies": {
    "lerna": "^3.5.1"
  },
  "workspaces": [
    "packages/*"
  ]
}
```
Add `{ "npmClient": "yarn", "useWorkspaces": true }` in lerna.json
```javascript
{
  "packages": [
    "packages/*"
  ],
  "version": "0.0.0",
  "npmClient": "yarn",
  "useWorkspaces": true
}
```
To run app
```sh
$ git clone git@github.com:sagarpanda/react-qstart-lerna.git
$ cd react-qstart-lerna
$ git submodule update --init --recursive
$ lerna bootstrap
$ lerna run build --scope react-qstart
$ lerna run start --scope reactjs-basics
```
