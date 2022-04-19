# Restaurant-page-
$ mkdir demo-app 
$ cd demo-app/
$ npm run build 
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
npm install --save-dev style-loader css-loader
npx webpack --watch



  webpack-demo
|- package.json
|- webpack.config.js
|- /dist
   |- bundle.js
 |- /src
  |- index.js
  |- print.js
|- style.css



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





 

 
   const path = require('path');
   const HtmlWebpackPlugin = require('html-webpack-plugin');
   
   module.exports = {
     entry: {
     app: './src/index.js', 
   },
   devtool: 'incline-source-map',
   devserver: {
     static: './dist',
     hot: true, 
   },
   module: { 
      rules: [
        {
         test: /\.css$/,
         use: ['style-loader', 'css-loader'],
       },
     ],
   },
   plugins: [
     new HtmlWebpackPlugin({
       title: 'Hot Module Replacement',
     }),
   ],
    output: {
   filename: '[name].bundle.js', 
   path: path.resolve(__dirname, 'dist')
    clean: true, 
  },
};
const compiler = webpack(config);

// 'hot' and 'client' option are disabled because we added them manually 
const server = new webpackDevServer({ hot: false, client: false }, compiler); 

(async () => {
  await server.start();
  console.log('dev server is running');
})();
   
 
body {
  background: red;
} 
       
 
 import _ from 'lodash';
 import printMe from './print.js';
 import './style.css';

function component() {
  const element = document.createElement('div');
  const btn = document.createElement('button');
  
   element.innerHTML = _.join(['Hello', 'webpack'], ' ');
  
  btn.innerHTML = 'Click me and check the console!';
  btn.onclick = printMe;

  element.appendChild(btn);

  return element;
}

let element = component(); // Store the element to re-render on print.js changes
 document.body.appendChild(element);

if (module.hot) {
   module.hot.accept('./print.js', function() {
      console.log('Accepting the updated printMe module!');
      document.body.removeChild(element);
      element = component(); // Re-render the "component" to update the click handler
      document.body.appendChild(element);
   })
 }
 
 
   export default function printMe() {
   console.log('Updating print.js...');

  [HMR] Waiting for update signal from WDS...
main.js:4395 [WDS] Hot Module Replacement enabled.
 2main.js:4395 [WDS] App updated. Recompiling...
 main.js:4395 [WDS] App hot update...
 main.js:4330 [HMR] Checking for updates on the server...
 main.js:10024 Accepting the updated printMe module!
 0.4b8ee77….hot-update.js:10 Updating print.js...
 main.js:4330 [HMR] Updated modules:
 main.js:4330 [HMR]  - 20


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
  
 






@font-face {
  font-family: 'MyFont';
  src: url('./my-font.woff2') format('woff2'),
    url('./my-font.woff') format('woff');
  font-weight: 600;
  font-style: normal;
}



$.hello {
  color: blue;
  font-family: 'MyFont';
 background: url('./icon.png');
 }







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




...
[webpack-cli] Compilation finished
assets by status 9.88 KiB [cached] 1 asset
asset bundle.js 73.4 KiB [emitted] [minimized] (name: main) 1 related asset
runtime modules 1.82 KiB 6 modules
orphan modules 326 bytes [orphan] 1 module
cacheable modules 540 KiB (javascript) 9.88 KiB (asset)
  modules by path ./node_modules/ 539 KiB
    modules by path ./node_modules/css-loader/dist/runtime/*.js 2.38 KiB
      ./node_modules/css-loader/dist/runtime/api.js 1.57 KiB [built] [code generated]
      ./node_modules/css-loader/dist/runtime/getUrl.js 830 bytes [built] [code generated]
    ./node_modules/lodash/lodash.js 530 KiB [built] [code generated]
    ./node_modules/style-loader/dist/runtime/injectStylesIntoStyleTag.js 6.67 KiB [built] [code generated]
  modules by path ./src/ 1.45 KiB (javascript) 9.88 KiB (asset)
    ./src/index.js + 1 modules 794 bytes [built] [code generated]
    ./src/icon.png 42 bytes (javascript) 9.88 KiB (asset) [built] [code generated]
    ./node_modules/css-loader/dist/cjs.js!./src/style.css 648 bytes [built] [code generated]
webpack 5.4.0 compiled successfully in 1972 ms

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
     

