# Restaurant-page-
mkdir webpack-demo 
cd webpack-demo 
npm init -y 
npm install webpack webpack-cli --save-dev


  webpack-demo
|- package.json
|- package-lock.json
|- webpack.config.js
|- /dist
   |- bundle.js
   |- index.html
|- /src
  |-icon.png
  |- style.css
  |- index.js
|- /node_modules


  npm install --save-dev style-loader css-loader
 
 
   const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist'),
  },
module: {
    rules: [
      {
        test: /\.css$/i,
        use: ['style-loader', 'css-loader'],
      },
       {
        test: /\.(png|svg|jpg|jpeg|gif)$/i,
        type: 'asset/resource',
      },
    ],
  },
 };
  
  
 
  npx webpack --watch
 
 import _ from 'lodash';
 import './style.css';
 import Icon from './icon.png';
 
   function component() {
  const element = document.createElement('div');
alert("Welcome to the Ice Age!");
  
  // Lodash, now imported by this script
  element.innerHTML = _.join(['Hello', 'webpack'], ' ');
  element.classList.add('hello");
  
// Add the image to our existing div.
  const myIcon = new Image();
  myIcon.src = Icon;

  element.appendChild(myIcon); 
  
  return element;
}

document.body.appendChild(component());


.hello {
   color: red;
  background: url('./icon.png');
 }


<!DOCTYPE html>
<html>
  <head>
<meta charset="utf-8" />

  <title>Asset Management</title>
  </head>  
  </body> 
  
      <script src="bundle.js"></script>
    </body>
 </html>
<meta name="viewport" content="width=device-width,initial-scale=1">
<link rel="stylesheet" href="">
<div#content>
</div#content>
<script src=""></script>
<body>


<img class="img-ice"
     src="img/iceage.jpg"
alt:"large wall of ice">
  
{
  margin: 0;
  pending: 0;
}
  
.wrapper {
  margin: 0 auto:;
  width: 1000px;
}
  
.img-ice {
  width: 300 px;
}
<div class="">
 <h1>Welcome back to... THE ICE AGE!</h1>
 <p>Travel back to prehistoric times with us with our lovable friends from the adorable and hilarious fanatic film series: The Ice Age!</p>
 <p>As you travel back in time wih us, please make sure to try all our freshly prepared mediteranian entres along side with our crunchy beatle salad! And for all you party aniamls out there, ask your waitor what our exotic drink of the day is. Taste so good it'll make your taste buds dance with flavors! Remember though DO NOT FEED THE DINOS AND MAMMOTHS!</p>
</div>

</body>
</html>


$ npm run build

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
     
