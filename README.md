# Restaurant-page-
mkdir webpack-demo 
cd webpack-demo 
npm init -y 
npm install webpack webpack-cli --save-dev
npm install --save-dev html-webpack-plugin
npm install toml yamljs json5 --save-dev
 npm uninstall css-loader csv-loader json5 style-loader toml xml-loader yamljs
npm install --save-dev express webpack-dev-middleware


  webpack-demo
|- package.json
|- package-lock.json
|- webpack.config.js
|- server.js
|- /dist
   |- bundle.js
   |- index.html
|- /src
   |- index.js
   |- print.js
|- /node_modules


const express = require('express');
const webpack = require('webpack');
const webpackDevMiddleware = require('webpack-dev-middleware');

const app = express();
const config = require('./webpack.config.js');
const compiler = webpack(config);

// Tell express to use the webpack-dev-middleware and use the webpack.config.js
// configuration file as a base.
app.use(
  webpackDevMiddleware(compiler, {
    publicPath: config.output.publicPath,
  })
);

// Serve the files on port 3000.
app.listen(3000, function () {
  console.log('Example app listening on port 3000!\n');
  });
  
export default function printMe() {
    console.log('I get called from print.js!');
  }
...
[webpack-cli] Compilation finished
asset index.bundle.js 1.38 MiB [emitted] (name: index)
asset print.bundle.js 6.25 KiB [emitted] (name: print)
asset index.html 272 bytes [emitted]
runtime modules 1.9 KiB 9 modules
cacheable modules 530 KiB
  ./src/index.js 406 bytes [built] [code generated]
  ./src/print.js 83 bytes [built] [code generated]
  ./node_modules/lodash/lodash.js 530 KiB [built] [code generated]
webpack 5.4.0 compiled successfully in 706 ms


<?xml version="1.0" encoding="UTF-8"?>
<note>
  <to>Mary</to>
  <from>John</from>
  <heading>Reminder</heading>
  <body>Call Cindy on Tuesday</body>
</note>

to,from,heading,body
Mary,John,Reminder,Call Cindy on Tuesday
Zoe,Bill,Reminder,Buy orange juice
Autumn,Lindsey,Letter,I miss you


 

 
   const path = require('path');
   const HtmlWebpackPlugin = require('html-webpack-plugin');
  
module.exports = {
 mode: 'development',
 entry: {
  './src/index.js',
  print: './src/print.js',
},
devtool: 'inline-source-map',
devServer: {
    static: './dist',
  },
 plugins: [
  new HtmlWebpackPlugin({
       
       title: 'Development',
     }),
   ],
   output: {
 filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist'),
    clean: true,
    publicPath: '/',
  },
};
 
 
 ...
[webpack-cli] Compilation finished
asset index.bundle.js 69.5 KiB [compared for emit] [minimized] (name: index) 1 related asset
asset print.bundle.js 316 bytes [compared for emit] [minimized] (name: print)
asset index.html 253 bytes [emitted]
runtime modules 1.36 KiB 7 modules
cacheable modules 530 KiB
  ./src/index.js 406 bytes [built] [code generated]
  ./src/print.js 83 bytes [built] [code generated]
  ./node_modules/lodash/lodash.js 530 KiB [built] [code generated]
webpack 5.4.0 compiled successfully in 2189 ms

  
  
   npx webpack --watch
 
 import _ from 'lodash';
 import printMe from './print.js';

 
function component() {
  const element = document.createElement('div');
  const btn = document.createElement('button');
  
 
  element.innerHTML = _.join(['Hello', 'webpack'], ' ');
  
  btn.innerHTML = 'Click me and check the console!';
  btn.onclick = printMe;

  element.appendChild(btn);

  return element;
}

document.body.appendChild(component());

// No warning
import data from './data.json';

// Warning shown, this is not allowed by the spec.
import { foo } from './data.json';





title = "TOML Example"

[owner]
name = "Tom Preston-Werner"
organization = "GitHub"
bio = "GitHub Cofounder & CEO\nLikes tater tots and beer."
dob = 1979-05-27T07:32:00Z


title: YAML Example
owner:
  name: Tom Preston-Werner
  organization: GitHub
  bio: |-
    GitHub Cofounder & CEO
    Likes tater tots and beer.
  dob: 1979-05-27T07:32:00.000Z
  
  
  {
  // comment
  title: 'JSON5 Example',
  owner: {
    name: 'Tom Preston-Werner',
    organization: 'GitHub',
    bio: 'GitHub Cofounder & CEO\n\
Likes tater tots and beer.',
    dob: '1979-05-27T07:32:00.000Z',
  },
  
 


$ npm run build

...
[webpack-cli] Compilation finished
asset bundle.js 72.6 KiB [emitted] [minimized] (name: main) 1 related asset
runtime modules 1000 bytes 5 modules
orphan modules 326 bytes [orphan] 1 module
cacheable modules 539 KiB
  modules by path ./node_modules/ 538 KiB
    ./node_modules/lodash/lodash.js 530 KiB [built] [code generated]
    ./node_modules/style-loader/dist/runtime/injectStylesIntoStyleTag.js 6.67 KiB [built] [code generated]
    ./node_modules/css-loader/dist/runtime/api.js 1.57 KiB [built] [code generated]
  modules by path ./src/ 965 bytes
    ./src/index.js + 1 modules 639 bytes [built] [code generated]
    ./node_modules/css-loader/dist/cjs.js!./src/style.css 326 bytes [built] [code generated]
webpack 5.4.0 compiled successfully in 2231 ms


@font-face {
  font-family: 'MyFont';
  src: url('./my-font.woff2') format('woff2'),
    url('./my-font.woff') format('woff');
  font-weight: 600;
  font-style: normal;
}


$
.hello {
  color: blue;
  font-family: 'MyFont';
  background: url('./icon.png');
 }


$ npm run build

...
[webpack-cli] Compilation finished
assets by status 9.88 KiB [cached] 1 asset
assets by info 33.2 KiB [immutable]
  asset 55055dbfc7c6a83f60ba.woff 18.8 KiB [emitted] [immutable] [from: src/my-font.woff] (auxiliary name: main)
  asset 8f717b802eaab4d7fb94.woff2 14.5 KiB [emitted] [immutable] [from: src/my-font.woff2] (auxiliary name: main)
asset bundle.js 73.7 KiB [emitted] [minimized] (name: main) 1 related asset
runtime modules 1.82 KiB 6 modules
orphan modules 326 bytes [orphan] 1 module
cacheable modules 541 KiB (javascript) 43.1 KiB (asset)
  javascript modules 541 KiB
    modules by path ./node_modules/ 539 KiB
      modules by path ./node_modules/css-loader/dist/runtime/*.js 2.38 KiB 2 modules
      ./node_modules/lodash/lodash.js 530 KiB [built] [code generated]
      ./node_modules/style-loader/dist/runtime/injectStylesIntoStyleTag.js 6.67 KiB [built] [code generated]
    modules by path ./src/ 1.98 KiB
      ./src/index.js + 1 modules 794 bytes [built] [code generated]
      ./node_modules/css-loader/dist/cjs.js!./src/style.css 1.21 KiB [built] [code generated]
  asset modules 126 bytes (javascript) 43.1 KiB (asset)
    ./src/icon.png 42 bytes (javascript) 9.88 KiB (asset) [built] [code generated]
    ./src/my-font.woff2 42 bytes (javascript) 14.5 KiB (asset) [built] [code generated]
    ./src/my-font.woff 42 bytes (javascript) 18.8 KiB (asset) [built] [code generated]
webpack 5.4.0 compiled successfully in 2142 ms


<!DOCTYPE html>
<html>
  <head>
  <meta charset="utf-8" />
  <title>Output Management</title>
<script src="./print.bundle.js"></script>
  </head>  
  </body> 
  
      <script src="./index.bundle.js"></script>
    </body>
 </html>
 
 
 $ npx webpack
[webpack-cli] Compilation finished
asset main.js 69.3 KiB [emitted] [minimized] (name: main) 1 related asset
runtime modules 1000 bytes 5 modules
cacheable modules 530 KiB
  ./src/index.js 257 bytes [built] [code generated]
  ./node_modules/lodash/lodash.js 530 KiB [built] [code generated]
webpack 5.4.0 compiled successfully in 1851 ms

<meta name="viewport" content="width=device-width,initial-scale=1">
<link rel="stylesheet" href="">
<div#content>
</div#content>
<script src=""></script>
<body>



     <img src=""
alt:""> 
  
  

}
<div class="">
 <h1>Welcome back to... THE ICE AGE!</h1>
 <p>Travel back to prehistoric times with us with our lovable friends from the adorable and hilarious fanatic film series: The Ice Age!</p>
 <p>As you travel back in time wih us, please make sure to try all our freshly prepared mediteranian entres along side with our crunchy beatle salad! And for all you party aniamls out there, ask your waitor what our exotic drink of the day is. Taste so good it'll make your taste buds dance with flavors! Remember though DO NOT FEED THE DINOS AND MAMMOTHS!</p>
</div>

</body>
</html>




{
   "name": "webpack-demo",
   "version": "1.0.0",
   "description": "",
    "private": true,
   "scripts": {
      "test": "echo \"Error: no test specified\" && exit 1",
       "watch": "webpack --watch",
       "start": "webpack serve --open",
   "server": "node server.js",
   build: "webpack"
   },
   "keywords": [],
   "author": "",
   "license": "ISC",
   "devDependencies": {
     "webpack": "^5.4.0",
     "webpack-cli": "^4.2.0"
   },
   "dependencies": {
     "lodash": "^4.17.20"
   }
 }
     

Example app listening on port 3000!
...
<i> [webpack-dev-middleware] asset index.bundle.js 1.38 MiB [emitted] (name: index)
<i> asset print.bundle.js 6.25 KiB [emitted] (name: print)
<i> asset index.html 274 bytes [emitted]
<i> runtime modules 1.9 KiB 9 modules
<i> cacheable modules 530 KiB
<i>   ./src/index.js 406 bytes [built] [code generated]
<i>   ./src/print.js 83 bytes [built] [code generated]
<i>   ./node_modules/lodash/lodash.js 530 KiB [built] [code generated]
<i> webpack 5.4.0 compiled successfully in 709 ms
<i> [webpack-dev-middleware] Compiled successfully.
<i> [webpack-dev-middleware] Compiling...
<i> [webpack-dev-middleware] assets by status 1.38 MiB [cached] 2 assets
<i> cached modules 530 KiB (javascript) 1.9 KiB (runtime) [cached] 12 modules
<i> webpack 5.4.0 compiled successfully in 19 ms
<i> [webpack-dev-middleware] Compiled successfully.
