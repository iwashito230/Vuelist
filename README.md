# Vuelist

> Vue-cliを使ってtodoappliを作る

GithubPagesで見れるようにする

> https://iwashito230.github.io/Vuelist/

> [参考先1](https://qiita.com/tackeyy/items/3b180b3a835dbcb39820)
> [参考先2](https://qiita.com/msrks/items/67dbfba84bc635d7337c)

### 使用したもの
- [node.js](https://nodejs.org/ja/)(v10.13.0)
- [vue-cli](https://jp.vuejs.org/2015/12/28/vue-cli/)
- [SweetAlert](https://sweetalert.js.org/)(v2.1.2)


### localでの立ち上げ
`$ npm run dev`

### docsファイルにbuild
todolistの位置で
`$ mkdir docs`
`$ vim config/index.js`

ファイル名とpathの変更(全部で3つ)
``` 
build: {
    // Template for index.html
    index: path.resolve(__dirname, '../docs/index.html'), ⇦ ここ

    // Paths
    assetsRoot: path.resolve(__dirname, '../docs'), ⇦ ここ
    assetsSubDirectory: 'static',
    assetsPublicPath: '', ⇦ ここ
   (以下省略)
```
※ 上記の変更は初回の時のみ

`$ npm run build `
