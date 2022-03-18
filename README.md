# Restaurant-page-
$ mkdir demo-app 
$ cd demo-app/
[~/demp-app]$ npm install lodash 
lodash@2.4.1 node_modules/lodash
[~/demo-app]$ ls
[~/demo-app] ls node_modules/
lodash
[~demo-app]$ clear 
npm init -y 
npm install webpack webpack-cli --save-dev
npm install --save-dev html-webpack-plugin
npm install toml yamljs json5 --save-dev
 npm uninstall css-loader csv-loader json5 style-loader toml xml-loader yamljs
npm install --save-dev express webpack-dev-middleware
npm install gitignore -g
npm install gitignore 
var gi = require(`gitignore`);


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
|-node_modules


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
 import

 npm install gitignore
 
 var gi = require(`gitignore`);
 
 <h1>Welcome back to... THE ICE AGE!</h1>
 <p>Travel back to prehistoric times with us with our lovable friends from the adorable and hilarious fanatic film series: The Ice Age!</p>
 <p>As you travel back in time wih us, please make sure to try all our freshly prepared mediteranian entres along side with our crunchy beatle salad! And for all you party aniamls out there, ask your waitor what our exotic drink of the day is. Taste so good it'll make your taste buds dance with flavors! Remember though DO NOT FEED THE DINOS AND MAMMOTHS!</p>
</div>
 
 
 <h1> Menu</h1>
 <h3>Entres</h3>
 <h4>T-rex ribs: medium rare or well done- $15.25</h4>
  <h4>The Beeschurger: merdium rare or well done. chilled letuce, swiss cheese, tomatos, pickles- $12.63</h4>
  <h4>Sids' Beatle salad: freshly prepared tossed salad with croutons with a few blackberries and beetles- $12.63</h4>
  
   
 <h3>Side dishes</h3>
 <h4>Fruit salad- $2.25</h4> 
 <h4>Mammoth nachos- $2.25</h4> 
 
 
 <h3>Fun drinks (only for 21+)</h3>
 <h4> Tigers blood: white rum, splash of vodka, crushed and frozen cherrys, red curacao syrup, lime juice, cane sugar- $12.25</h4> 
<h4> The Mammoth: tequilla, freshly squeezed OJ, lime juice with lime on the side - $12.25</h4>
 <h4> Bucks Tangy Adventure: vodka, mixed berries, scotch bonno peper, lime- $12.25</h4>
 
 
 <h4> Desserts</h4> 
 <h3> Eds'misu: tirimisu with extra chocolate and carmelized vanilla center- $6.25</h3>
 <h3> Ellies' red velvet: red velvet cake with a strawberry on top drizzled with strawberry syrup- $10.25</h3>
 <h3> ice cream: chocolate, vanilla, strawberry, black berry-$6.25</h3>
 
 
 <h1> Hours</h1>
 <h4>Monday-Thursday: 12 pm-9 pm</h4>
 <h4>Friday-Saturday: 12 Pm-10:30 PM</h4>
 <h4>Sunday 12 PM-9 PM</h4>


 <h1>Location</h1>
 <h3>1316 Iceberg Road, Nippy Nips, Alaska</h3>
 
 
 <h1>Directions</h1>
 <h4>If you get lost just walk past Ferocious Piranha Lane (they won't attack you if you do not aknowledge them) and continue until you see a dead looking tree with a cranky and confused old looking woman. Do not worry she is just Sids' granny and she's coo coo in the head. If you follow our directions carefully you should have made it to the Ice Age in one piece without any trouble.</h4>
</body>
</html>


<h1>Contact</h1>
 <h4>Sid1234@iceage.com</h4>
 <h4>Ed@iceage.com</h4>
 <h4>Eddie@iceage.com</h4>



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
