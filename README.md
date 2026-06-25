# qrcode-wx
微信小程序生成二维码
基于https://github.com/davidshimjs/qrcodejs
```
new QRCode(ctx, canvas, {
    text: "https://example.com",
    width: 200,
    height: 200,
    x: 50,
    y: 50,
    colorDark: "#000000",              // 二维码颜色
    colorLight: "#ffffff",             // 二维码区域背景色
    canvasBackgroundColor: "#f0f0f0",  // 整个 Canvas 背景色（灰色）
    correctLevel: QRCode.CorrectLevel.H
})
```

logo 配置选项：

```
logo: {
    image: logo,           // 图片对象（必需，微信小程序的 Image 对象）
    width: 40,            // logo 宽度（可选）
    height: 40,           // logo 高度（可选）
    ratio: 0.2,           // logo 占二维码大小的比例（可选，默认 0.2 即 20%）
    borderColor: "#fff",  // logo 边框颜色（可选）
    borderWidth: 2        // logo 边框宽度（可选，默认 2px）
}
```
使用示例：

```
// 创建 logo 图片对象
const logo = canvas.createImage()
logo.src = '/images/logo.png'
logo.onload = () => {
  new QRCode(ctx, canvas, {
    text: "https://example.com",
    width: 200,
    height: 200,
    colorDark: "#000000",
    colorLight: "#ffffff",
    logo: {
      image: logo,           // 图片对象
      width: 40,             // 固定宽度（可选，不设置则按 ratio 计算）
      height: 40,            // 固定高度（可选）
      ratio: 0.2,            // 占二维码 20%（默认）
      borderColor: "#ffffff",// 白色边框
      borderWidth: 2         // 边框 2px
    },
    correctLevel: QRCode.CorrectLevel.H  // 建议使用 H 级别以保证容错率
  })
}
```
注意事项：

- 嵌入 logo 会破坏部分二维码数据，建议使用 H 级别纠错（QRCode.CorrectLevel.H）以保证可扫描性
- logo 尺寸建议不超过二维码的 20%（默认 ratio: 0.2）
- 微信小程序中使用 canvas.createImage() 创建图片对象
