# 从0到实现React源码，非Fiber

## 首先
视频来自Bilibili[《React源码解析》](https://www.bilibili.com/video/BV1cE411B7by)

1. 😭没有按照视频上的环境搭建，因为`Parcel`启动之后的编译有问题，难哭了
2. 🙆‍♂️我这边使用的浏览器版本的`Babel`，`babel-standalone`，支持JSX，只需要在html中的`script[type="text/babel"]`写代码就可
3. 😂写`Demo`我比较喜欢使用`CDN`(这样可以把代码直接复制到`jsbin`或者`codepen`中运行)，代码里面用的也是`CDN`的方式引入`babel-standalone`，如果网络不顺畅可以使用`lib`文件夹下的文件
4. `Babel-standalone@6.26.0`，`React@16.6.0`，`React-DOM@16.6.0`

## 其次
把必须的信息也贴出来，不需要再去[小马哥掘金](https://juejin.cn/post/6869549410875867144#comment)复制，防止自己忘记

npm依赖
```json
"devDependencies": {
  "babel-core": "^6.26.3",
  "babel-plugin-transform-react-jsx": "^6.24.1",
  "babel-preset-env": "^1.7.0",
  "parcel-bundler": "^1.12.3"
}
```

.babelrc
```json
{
  "presets": ["env"],
  "plugins": [
    ["transform-react-jsx", {
      "pragma": "React.createElement"
    }]
  ]
}
```

http://www.ayqy.net/blog/react-16/