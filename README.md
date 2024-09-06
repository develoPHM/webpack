# webpack

1. `npm init -y`
2. `npm i webpack webpack-cli -D`
3. `npm i lodash`
4. 폴더에 `index.html` 파일을 생성
5. 프로젝트 루트 레벨에 src 폴더 생성 후 `index.js` 파일 생성
6. 웹팩 빌드 명령어를 실행하기 위해 package.json 에 추가
   `"scripts": {
   "build": "webpack"
   }`
7. 프로젝트 루트레벨에 `webpack.config.js` 파일 생성
    ```
    var path = require('path')
   
    module.exports = {
      mode: 'none',
      entry: './src/index.js',
      output: {
        filename: 'main.js',
        path: path.resolve(__dirname, 'dist')
      }
    };
   ```
8. `npm run build` 명령어로 빌드

# webpack dev-server

1. `npm init -y`
2. `npm i webpack webpack-cli webpack-dev-server html-webpack-plugin -D`
3. `package.json` 파일에서 아래와 같이 scripts 속성에 커스텀 명령어를 추가
   ```
   {
   // ...
   "scripts": {
      "dev": "webpack-dev-server"
      },
   }
   ```
4. 프로젝트 루트레벨에 index.html 생성 후 내용추가
5. 프로젝트 루트레벨에 index.js 생성 및 아래 내용 추가
   ```
   var div = document.querySelector('.container');
   div.innerText = 'Webpack loaded!!';
   ```
6. 웹팩 설정 파일 `webpack.config.js` 생성 후 아래 내용 추가
   ```
   var path = require('path');
   var HtmlWebpackPlugin = require('html-webpack-plugin');

   module.exports = {
       mode: 'none',
       entry: './index.js',
       output: {
           filename: 'bundle.js',
           path: path.resolve(__dirname, 'dist'),
   },
   devServer: {
       port: 9000,
   },
   plugins: [
       new HtmlWebpackPlugin({
           // index.html 템플릿을 기반으로 빌드 결과물을 추가해줌
           template: 'index.html',
           }),
       ],
   };
   ```
7. 터미널에 `npm run dev` 입력 후 데브서버 실행 