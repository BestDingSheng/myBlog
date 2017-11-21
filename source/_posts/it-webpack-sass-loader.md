---
title: webpack sass-loader安装使用
date: 2017-06-24 21:51:28
tags: [webpack,mac]
---

elementUI 默认webpack配置是没有sass-loader的
sass-loader 依赖 node-sass 这个插件所以我们需要安装两个插件
```
npm install --save-dev node-sass  (注：sass-loader依赖于node-sass)
npm install --save-dev sass-loader
```
把css全部提取出来还有个插件
```
npm install extract-text-webpack-plugin --save-dev
```
如何使用sass-loader和extract-text-webpack-plugin 请看下面配置

<!--more-->

```js
const resolve = require('path').resolve
const webpack = require('webpack')
const HtmlWebpackPlugin = require('html-webpack-plugin')
const ExtractTextPlugin = require('extract-text-webpack-plugin')  // 把分离css插件加载进来
const url = require('url')
const publicPath = ''

module.exports = (options = {}) => ({
  entry: {
    vendor: './src/vendor',
    index: './src/main.js'
  },
  output: {
    path: resolve(__dirname, 'dist'),
    filename: options.dev ? '[name].js' : '[name].js?[chunkhash]',
    chunkFilename: '[id].js?[chunkhash]',
    publicPath: options.dev ? '/assets/' : publicPath
  },
  module: {
    rules: [{
        test: /\.vue$/,
        use: ['vue-loader']
      },
      {
        test: /\.js$/,
        use: ['babel-loader'],
        exclude: /node_modules/
      },
      {
        test: /\.css$/,
        use: ExtractTextPlugin.extract({
          fallback: 'style-loader',
          use: ['css-loader', 'sass-loader', 'postcss-loader']
        }) // 通过use来使用插件
      },
      {
      // 匹配scss文件
        test: /\.scss$/,
        /*
        先使用sass-loader处理, 返回的结果交给css-loader处理
        */
        use: ExtractTextPlugin.extract({
          fallback: 'style-loader',
          use: ['css-loader', 'sass-loader', 'postcss-loader']
        })
      },
      {
        test: /\.(png|jpg|jpeg|gif|eot|ttf|woff|woff2|svg|svgz)(\?.+)?$/,
        use: [{
          loader: 'url-loader',
          options: {
            limit: 10000
          }
        }]
      }
    ]
  },
  plugins: [
    new webpack.optimize.CommonsChunkPlugin({
      names: ['vendor', 'manifest']
    }),
    new ExtractTextPlugin("style.css"), //提取出来的样式放在style.css文件中

    new HtmlWebpackPlugin({
      template: 'src/index.html'
    })
  ],
  resolve: {
    alias: {
      '~': resolve(__dirname, 'src')
    }
  },
  devServer: {
    host: '127.0.0.1',
    port: 8010,
    proxy: {
      '/api/': {
        target: 'http://127.0.0.1:8080',
        changeOrigin: true,
        pathRewrite: {
          '^/api': ''
        }
      }
    },
    historyApiFallback: {
      index: url.parse(options.dev ? '/assets/' : publicPath).pathname
    }
  },
  devtool: options.dev ? '#eval-source-map' : '#source-map'
})

```


