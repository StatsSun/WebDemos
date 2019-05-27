# WebDemos

###搜索框系列

一、搜索框自动隐现效果(纯CSS实现)

[点击查看在线效果](http://www.statssun.com/searchbox/)

1. 页面构成元素
   - 内容输入框
   - 搜索按钮

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>SearchBox</title>
        <link href="style.css" rel="stylesheet" type="text/css">
        <script defer src="https://use.fontawesome.com/releases/v5.0.6/js/all.js"></script>
    </head>
    <body>
        <div class="search-box">
            <!--插入内容输入框-->
            <input class="search-txt" type="text" name="" placeholder="Type to search">
            <!--插入搜索按钮-->
            <a class="search-btn" href="#"><i class="fas fa-search"></i></a>
        </div>
    </body>
</html>  
```



2. 页面CSS格式



   ```css
   body{
       margin:0;
       padding:0;
       background:#e84118;
   }
   .search-box{
       /*输入框垂直居中*/
       position:absolute;
       top:50%;
       left:50%;
       transform:translate(-50%,-50%);
       background:#2f3640;
       height:40px;
       border-radius:40px;
       padding:10px;
   }
   /*输入框淡出*/
   .search-box:hover > .search-txt{
       width: 120px;
       padding: 0 6px;
        /*宽度设置过大时图标会下移*/
    }
   /*搜索按钮*/
   .search-box:hover > .search-btn{
       background: white;
        color: #e84118;
    }
   /*输入文本显示格式设置*/
   .search-txt{
       border:none;
       background: none;
       outline: none;
       float: left;
       padding: 0;
       color: white;
       font-size: 16px;
       transition: 0.4s;
       line-height: 40px;
       width: 0;
       font-weight: bold;
   }
   /*搜索按钮格式设置*/
   .search-btn{
       position:relative;
       color:#e84118;
       float:right;
       width:40px;
       height:40px;
       border-radius:50px;
       background:#2f3640;
       display:flex;
       justify-content:center;
       align-items:center;
       transition:0.4s;
       cursor:pointer;
   }
   /**/
   .search-btn > i{
       font-size: 30px;
   }
   ```



二、搜索框点击边框圆角过渡变换（纯CSS实现）

[点击查看在线效果](http://www.statssun.com/SearchBox2/)

1. 页面构成
   - 标题(可有可无)
   - 表单：输入框和提交按钮


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>SearchBox</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="box">
        <h1>Search</h1>
        <form >
            <!--插入表单-->
            <input type="text" name="" placeholder="Type to Search">
            <input type="submit" name="" value="Search">
        </form>
    </div>
</body>
</html>
```

2. 页面CSS格式

```css
body{
    margin: 0;
    padding: 0;
    background: #000;
    font-family: sans-serif;
}
h1{
    margin: 0 0 10px;
    padding: 0;
    color: #ffffff;
    font-size: 24px;
}
.box{
    position: absolute;
    top: 50%;
    left: 50%;
    transform:translate(-50%,-50%);
}

input{
    position: relative;
    /*设置行内块元素，效果同float，IE6、IE7不支持*/
    display: inline-block;
    font-size: 20px;
    height: 50px;
    /*定义总宽度和总高度的计算方式，这里总宽高=content+padding+border*/
    box-sizing:border-box;
    /*单独设置边框弧度变化效果*/
    transition: border-radius .5s;
}
input[type="text"]{
    background: #ffffff;
    width: 340px;
    border: none;
    outline: none;
    padding: 0 25px;
    border-radius:25px 0 0 25px;
}
input[type="submit"]{
    position: relative;
    width: 150px;
    left: -5px;
    border-radius:0 25px 25px 0;
    border: none;
    outline: none;
    cursor: pointer;
    background: #ffc107;
    color: #ffffff;
}
input[type="submit"]:hover{
    background: #ff5722;
}
/*选择优化项：输入框和提交按钮设置为响应式布局，避免出现错位情况*/
```











