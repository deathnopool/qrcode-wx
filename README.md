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
