## 步骤
a.npm init （npm最好最新版）
b.cnpm install webpack-cli -g    npm install --save lodash
c.配置package.json
设置 main scripts
{
  "name": "test",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "private": true,
  "scripts": {
    "dev": "webpack --mode development",
    "build": "webpack --mode production"
  },
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "webpack-cli": "^2.0.13"
  },
  "dependencies": {
    "lodash": "^4.17.5",
    "webpack": "^4.4.1"
  }
}
d.webpack run dev

## css打包 参考https://www.webpackjs.com/concepts/targets/##
You may need an appropriate loader to handle this file type.
a.安装 cnpm install style-loader css-loader
b.根目录添加webpack.config.js文件
const path = require('path');
module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'main.js',
    path: path.resolve(__dirname, 'dist')
  },
  module: {
   rules: [
      {
       test: /\.css$/,
        use: [
         'style-loader',
           'css-loader'
        ]
     }
    ]
  }
};
