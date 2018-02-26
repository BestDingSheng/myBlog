---
title: webpack 常用插件
date: 2018-02-26 09:30:29
tags: webpack
---





```js
// 提取js里面的css
const ExtractTextPlugin = require("extract-text-webpack-plugin");
// 注入html
const HtmlWebpackPlugin = require('html-webpack-plugin')
// 删除文件夹
const CleanWebpackPlugin = require('clean-webpack-plugin')
// 压缩js
new webpack.optimize.UglifyJsPlugin
// 提取公用模块
new webpack.optimize.CommonsChunkPlugin
//  去掉打包后里面 没用的闭包
new webpack.optimize.ModuleConcatenationPlugin(),
```

webpack 基础配置

<!-- more -->


```js
const path = require('path');
const webpack = require("webpack");
const extractPlugin = require('extract-text-webpack-plugin');
const HtmlWebpackPlugin = require('html-webpack-plugin')
const CleanWebpackPlugin = require('clean-webpack-plugin')
const OptimizeCssAssetsPlugin = require('optimize-css-assets-webpack-plugin');

module.exports = {
    entry: {
        "index": "./assets/scripts/index.es"
    },
    output: {
        path: path.join(__dirname, './assets/'),
        publicPath: './',
        filename: 'build/[name][hash:5].bundle.js'
    },
    module: {
        rules: [{
                test: /\.es$/,
                use: 'babel-loader',
                //  把babel 提取到.babelrc 文件中
                // use: [{
                //     loader: "babel-loader",
                //     options: {
                //         "presets": [
                //             ["es2015", {
                //                 "modules": false
                //             }], "stage-0"
                //         ]
                //     }
                // }]
            },
            {
                test: /\.less$/i,
                use: extractPlugin.extract({
                    fallback: "style-loader",
                    use: [{
                        loader: "css-loader",
                        //  压缩css
                        options:{
                            minimize:true
                        }
                    }, {
                        loader: "less-loader"
                    }]
                })
            }

        ]
    },
    plugins: [
        //  css提取插件
        new CleanWebpackPlugin('./assets/build'),
        new extractPlugin("build/[name][hash:5].css"),
        new webpack.optimize.CommonsChunkPlugin({
            name: "common",
            filename: 'build/[name][hash:5].js',
            minChunks: 2
        }),
        //    html 自动生成插件
        new HtmlWebpackPlugin({
            filename: 'index.html',
            template: './index.html',
            inject: true
        }),
        //  代码压缩插件
        new webpack.optimize.UglifyJsPlugin({
            compress: {
                warnings: true
            },
            output: {
                comments: false
            },
            sourceMap: false
        }),
        //  去掉打包后里面 没用的闭包
        new webpack.optimize.ModuleConcatenationPlugin(),



    ]

}
```



