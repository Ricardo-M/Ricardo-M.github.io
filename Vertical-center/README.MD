1、通过给内容元素一个（包含元素总宽度减去内容元素总宽度）的一半的margin-left和通过给内容元素一个（包含元素总高度减去图片总高度）的一半的margin-top的方式去居中。
2、通过给父元素一个上下相同的padding值，但是缺点是父元素不能固定高度。
3、jQuery或者js方法
4、水平居中：margin:0 auto;但是，如果你的Web页面没有明确声明"!DOCTYPE"，那么在IE也会以怪异模式解析你的Web页面，此时上面这种办法将无法让你的页面实现水平居中，但你可以使用下面这种方法解决这个bug。
body {
text-align: center;/*实现IE在怪异模式下页面水平居中*/
}
.container {
text-align: left;/*让文本恢复到左对齐*/
width: 960px;/*设置页面总宽度*/
margin: 0 auto;/*使页面水平居中对
}
5、使用负数一般元素宽度margin配合绝对定位left：50%实现水平居中
6、使用负数一般元素高度margin配合绝对定位top：50%实现垂直居中






还有一种方法使用CSS3与flex，所以兼容存在问题，只考虑移动端使用

<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Document</title>
<style type="text/css">
body {
margin: 0;
}

.m-demo-2 {
margin: 50px 0 50px 0;
width: 100%;
height: 48px;
outline: 1px solid #000000;
}

.m-demo-2 .w div {
padding: 20px;
background-color: #FF0000;
margin-left: 5px;
font-size: 18px;
}

.g-horCtrCSS3fitCotent {/*指定了width为fit-content的元素的width会随着子元素的实际宽度的扩展而扩展，配合margin-left:auto,margin-right：auto就能实现想要的效果*/
width: -moz-fit-content;
width: -webkit-fit-content;
width: fit-content;
margin-left: auto;
margin-right: auto;
font-size: 0;
letter-spacing: -0.307em;
}

.g-horCtrCSS3fitCotent .g-item {
display: inline-block;
letter-spacing: normal;
}
</style>
</head>
<body>

<div class="m-demo-2 g-hriCtr-1">
<div class="w g-horCtrCSS3fitCotent">
<div class="g-item" style="margin-left:0;">CSS居中样式</div>
<div class="g-item">CSS居中样式</div>
<div class="g-item">CSS居中样式</div>
<div class="g-item">CSS居中样式</div>
<div class="g-item">CSS居中样式CSS居中样式CSS居中样式CSS居中样式</div>
</div>
</div>

</body>
</html>