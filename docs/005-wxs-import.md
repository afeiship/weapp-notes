# wxs-import:
> 使用 relative-file-loader，是因为在目前微信小程序的 wxml 语法中，暂不支持使用绝对路径引用 wxs 文件。

```js
{
    test: /\.(wxs)$/,
    include: /src/,
    use: {
    loader: 'file-loader',
    options: {
        useRelativePath: true,
        name: '[name].[ext]',
        context: srcDir,
        publicPath: '../../components/filters'
    }
    }
},
```