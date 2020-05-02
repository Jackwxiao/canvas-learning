# canvas-learning

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>JS Bin</title>
</head>
<body>
  <canvas id="drawing" width="1000" height="1000" draggable="true"></canvas>
</body>
</html>
```
```
var drawing = document.getElementById('drawing')
var context = drawing.getContext('2d')
// 绘制重叠矩形
context.fillStyle ='rgba(0,255,255, 0.5)'
context.fillRect(80,80,50,50)
context.fillStyle ='lightGreen'
context.fillRect(100,100,50,50)
context.clearRect(110,110,10,10)

// 绘制时钟
context.beginPath()
context.arc(100, 100,99 ,0 ,2 * Math.PI, false)
context.moveTo(194,100)
context.arc(100, 100,94 ,0 ,2 * Math.PI, false)
context.moveTo(100,100)
context.lineTo(100,15)
context.moveTo(100,100)
context.lineTo(35,100)
context.stroke()
// 绘制文本
context.font = 'bold 14px Arial'
context.textAlign = 'center'
context.textBaseLine = 'middle'
context.fillText('12',100,20)
var gradient = context.createLinearGradient(30,30,70,70)

 // 渐变
gradient.addColorStop(0,'white')
gradient.addColorStop(1, 'black')

context.fillStyle ='red'
context.fillRect(10,10,50,50)
context.fillStyle = gradient
context.fillRect(30,30,50,50)

// 渐变封装
function createRectLinearGradient(context,x,y,width,height){
  return context.createLinearGradient(x,y,x+width,y+height)
}

var gradient= createRectLinearGradient(context,30,30,50,50)
gradient.addColorStop(0,'white')
gradient.addColorStop(1,'black')

context.fillStyle ='red'
context.fillRect(10,10,50,50)
context.fillStyle = gradient
context.fillRect(30,30,60,60)
```
