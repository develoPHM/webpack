# webpack
초기 설정
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