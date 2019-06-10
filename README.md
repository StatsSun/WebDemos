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



三、在导航菜单栏添加搜索框（纯CSS实现）

[点击查看在线效果](http://www.statssun.com/SearchBox3/)

1. 页面构成
   - 导航菜单
   - 搜索框

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>带导航连接带搜索框</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <nav>
        <!--插入导航连接菜单-->
        <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">Gallery</a></li>
            <li><a href="#">Event</a></li>
            <li><a href="#">Feedback</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
        <!--插入搜索框和搜索按钮-->
        <form>
            <input type="text" name="" placeholder="Type....">
            <input type="submit" name="" value="Search">
        </form>
    </nav>
</body>
</html>
```



2. 页面CSS格式

```css
body{
    padding: 0;
    margin: 0;
    background: skyblue;
    font-family: sans-serif;
}
/*定义导航连接部分*/
nav{
    width: 100%;
    background: #112038;
    overflow: auto;
}
ul{
    margin: 0;
    padding: 0;
    list-style: none;
    line-height: 60px;
}
ul li{
    float: left;
}
ul li a{
    background: #112038;
    text-decoration: none;
    width: 130px;
    display:inline-block;
    text-align: center;
    color: #f2f2f2;
    font-size: 18px;
    letter-spacing: 0.5px;
}
/*通过透明度和字体大小变化设置动态效果*/
li a:hover{
    color: #ffffff;
    opacity: 0.5;
    font-size: 19px;
}
form{
    margin-top: 15px;
    float: right;
    margin-right: 100px;
}
input[type="text"]{
    padding: 7px;
    border: none;
    font-size: 16px;
    border-radius: 5px 0 0 5px;
}
input[type="submit"]{
    float: right;
    background: orange;
    color: white;
    border-radius:0 5px 5px 0;
    cursor: pointer;
    position: relative;
    padding: 7px;
    border: none;
    font-size: 16px;
}
input[type="submit"]:hover{
    background: red;
}
/*选择优化项：导航菜单和搜索框设置为响应式布局，避免出现页面窗口过小时出现错位情况*/
```



### 登陆表单系列

一、万圣节主题登录界面

[点击查看在线效果](http://www.statssun.com/LoginForm3/)

1. 页面结构
   - 图标
   - form表单

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>LoginForm</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="login-box">
        <img src="../../images/018.png" alt="">
        <h1>Login Here</h1>
        <form>
            <p>Username</p>
            <input type="text" name="" placeholder="Enter Your Name">
            <p>Password</p>
            <input type="password" name="" placeholder="Enter Password"><br>
            <input type="submit" name="" value="Login"><br>
            <a href="#">Lost your password?</a><br>
            <a href="#">Don't here an account?</a>
        </form>
    </div>
</body>
</html>
```



2. CSS样式


```css
body{
    padding: 0;
    margin: 0;
    font-family: sans-serif;
    background: url("../../images/029.jpg") no-repeat scroll;
    background-size:cover;
}
.login-box{
    position: absolute;
    top: 50%;
    left: 50%;
    transform:translate(-50%,-50%);
    width: 240px;
    height: 340px;
    background: rgba(0,0,0,0.5);
    border-radius:10px;
}
img{
    width: 60px;
    height: 60px;
    border-radius: 50%;
    position:relative;
    left: 90px;
    top: -30px;
}
h1{
    margin: 0;
    padding: 0;
    text-align: center;
    position: relative;
    top: -15px;
    font-size: 24px;
    color: #ffffff;
}
form{
    margin:0 25px;
    color: #ffffff;
}
p{
    margin: 0;
    font-size: 16px;
}
input[type="text"],input[type="password"]{
    background: transparent;
    border:none;
    border-bottom: 1px solid #ffffff;
    padding: 5px 0;
    margin-top: 5px;
    margin-bottom: 10px;
    width: 100%;
    color: #ffffff;
}
input[type="submit"]{
    width: 100%;
    height: 30px;
    font-size: 16px;
    margin: 10px 0;
    border: none;
    outline: none;
    border-radius:20px;
    background: darkorange;
    color: #ffffff;
}
a{
    font-size: 12px;
    color: #ffffff;
    text-decoration: none;
}
input[type="submit"]:hover{
    cursor: pointer;
    background: orange;
}
a:hover,h1:hover{
    color: orange;
}
input[type="text"]:hover,input[type="password"]:hover{
    border-bottom:1.5px solid darkorange;
}
```



四、并列双登陆界面

[点击查看在线效果](http://www.statssun.com/LoginForm4/)

1. 页面布局


```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>LoginForm</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="login-box">
        <div class="left-box">
            <h1>Sign Up</h1>
            <input type="text" name="" placeholder="Username">
            <input type="text" name="" placeholder="Email">
            <input type="password" name="" placeholder="Password">
            <input type="password" name="" placeholder="Retype password">
            <input type="submit" name="" value="Sign Up">
        </div>
        <div class="right-box">
            <span class="sign-with">Sign in with<br/>Social Network</span>
            <button class="social facebook">Log in with Facebook</button>
            <button class="social twitter">Log in with Twitter</button>
            <button class="social google">Log in with Google</button>
        </div>
        <div class="or">OR</div>
    </div>
</body>
</html>
```



2. CSS格式


```css
body{
    margin: 0;
    padding: 0;
    background: #efefef;
    font-size: 16px;
    color: #777;
    font-family: sans-serif;
    font-weight: 300;
}
/*整体布局格式*/
.login-box{
    position: relative;
    margin: 10% auto;
    width: 600px;
    height: 400px;
    background: #ffffff;
    box-shadow:0 2px 4px rgba(0,0,0,0.6);
}

/*左布局格式*/
.left-box{
    position: absolute;
    top: 0;
    left: 0;
    box-sizing:border-box;
    padding:40px;
    width: 300px;
    height: 400px;
}
h1{
    margin: 0 0 20px 0;
    font-weight: 400;
    font-size: 28px;
}
input[type="text"],input[type="password"]{
    display: block;
    box-sizing:border-box;
    margin-bottom: 20px;
    padding: 4px;
    width: 220px;
    height: 32px;
    border: none;
    outline: none;
    border-bottom: 1px solid #aaa;
    font-family: sans-serif;
    font-weight: 400;
    font-size: 15px;
    transition: 0.2s ease;
}
input[type="submit"]{
    margin-bottom: 28px;
    width: 120px;
    height: 32px;
    border: none;
    outline: none;
    background: #f44336;
    border-radius:2px;
    color: #fff;
    font-family: sans-serif;
    font-weight: 500;
    text-transform: uppercase;
    transition: 0.2s ease;
    cursor: pointer;
}
input[type="text"]:hover,input[type="password"]:hover{
    border-bottom: 1.3px solid darkolivegreen;
}
input[type="submit"]:hover{
    transition:0.2s ease;
    background: crimson;
}

/*右布局格式*/
.right-box{
    position: absolute;
    top: 0;
    right: 0;
    box-sizing:border-box;
    padding: 40px;
    width: 300px;
    height: 400px;
    background-image: url("../../images/008.jpg");
    background-size:cover;
}
.right-box .sign-with{
    display: block;
    margin-bottom: 20px;
    font-size: 28px;
    color: #ffffff;
    text-align: center;
    text-shadow: 0 2px 4px rgba(0,0,0,0.6);
}
button.social{
    margin-bottom: 20px;
    width: 220px;
    height: 36px;
    border: none;
    border-radius: 2px;
    color: #fff;
    font-family: sans-serif;
    font-weight: 500;
    transition:0.2s ease;
    cursor: pointer;
}
.facebook{
    background: #32508e;
}
.twitter{
    background: #55acee;
}
.google{
    background: #dd4b39;
}
.or{
    position: absolute;
    top: 180px;
    left: 280px;
    width: 40px;
    height: 40px;
    background: #efefef;
    opacity: 0.9;
    border-radius:50%;
    box-shadow:0 2px 4px rgba(0,0,0,0.6);
    line-height: 40px;
    text-align: center;
}
button.social:hover{
    transition:0.2s ease;
    opacity: 0.8;
}
```





五、JS贷款计算器

1. 页面布局

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>JS贷款计算器</title>
    <style>
        .output{
        font-weight:bold;}
        #graph{
            border: 1px solid black;
        }
        #payment{
            text-decoration: underline;
        }
        th,td{
            vertical-align: top;
        }
    </style>
</head>
<body>
    <table>
        <tr>
            <th>Enter Loan Data</th>
            <td></td>
            <th>Loan Balance,Cumulative Equity,and Interest Payments</th>
        </tr>
        <tr>
            <td>Amount of the loan($):</td>
            <td><input id="amount" onchange="calculate();"></td>
            <td rowspan="8"><canvas id="graph" width="400" height="250"></canvas></td>
        </tr>
        <tr>
            <td>Annual interest(%):</td>
            <td><input id="apr" onchange="calculate();"></td>
        </tr>
        <tr>
            <td>Repayment period (years):</td>
            <td><input id="years" onchange="calculate();"></td>
        </tr>
        <tr>
            <td>Zipcode (to find lenders):</td>
            <td><input id="zipcode" onchange="calculate();"></td>
        </tr>
        <tr>
            <td>Approximate Payments:</td>
            <td><button onchange="calculate();">Calculate</button></td>
        </tr>
        <tr>
            <td>Monthly payment:</td>
            <td>$<span class="output" id="payment"></span></td>
        </tr>
        <tr>
            <td>Total payment:</td>
            <td>$<span class="output" id="total"></span></td>
        </tr>
        <tr>
            <td>Total interest:</td>
            <td>$<span class="output" id="totalinterest"></span></td>
        </tr>
        <tr>
            <th>Sponsors:</th>
            <td colspan="2">
                Apply for your loan with one of these fine lenders:
                <div id="lenders"></div>
            </td>
        </tr>
    </table>
</body>
</html>
```



2. JS代码


```javascript
function calculate() {
    var amount = document.getElementById("amount"),
        apr = document.getElementById("apr"),
        years = document.getElementById("years"),
        zipcode = document.getElementById("zipcode"),
        payment = document.getElementById("payment"),
        total = document.getElementById("total"),
        totalinterest = document.getElementById("totalinterest");

    var principal = parseFloat(amount.value);
    var interest = parseFloat(apr.value)/100/12;
    var payments = parseFloat(years.value)*12;

    var x = Math.pow(1 + interest,payment);
    var monthly = (principal * x * interest)/(x-1);

    if(isFinite(monthly)){
        payment.innerHTML = monthly.toFixed(2);
        total.innerHTML = (monthly * payment).toFixed(2);
        totalinterest.innerHTML = ((monthly*payments)-principal).toFixed(2);

        save(amount.value,apr.value,years.value,zipcode.value);

        try {
            getlenders(amount.value,apr.value,years.value,zipcode.value);
        }
        catch(e){}
            chart(principal,interest,monthly,payments);
    }

    else{
            payment.innerHTML = "";
            total.innerHTML = "";
            totalinterest.innerHTML = "";
            chart();
        }
}

function save(amount,apr,years,zipcode) {
    if(window.localStorage){
        localStorage.loan_amount = amount;
        localStorage.loan_apr = apr;
        localStorage.loan_years = years;
        localStorage.loan_zipcode = zipcode;
    }
}

window.onload = function () {
    if(window.localStorage && localStorage.loan_amount){
        document.getElementById("amount").value = localStorage.loan_amount;
        document.getElementById("apr").value = localStorage.loan_apr;
        document.getElementById("years").value = localStorage.loan_years;
        document.getElementById("zipcode").value = localStorage.loan_zipcode;
    }
};

function getlenders(amount,apr,years,zipcode) {
    if(!window.XMLHttpRequest) return;
    var ad = document.getElementById("lenders");
    if(!ad) return;
    var url = "getlenders.php" +
        "?amt=" + encodeURIComponent(amount) +
        "?apr=" + encodeURIComponent(apr) +
        "?yrs=" + encodeURIComponent(years) +
        "?zip=" + encodeURIComponent(zipcode);

    var req = new XMLHttpRequest();
    req.open("GET",url);
    req.send(null);
    req.onreadystatechange = function () {
        if(req.readyState === 4 && req.status === 200){
            var response = req.responseText;
            var lenders = JSON.parse(response);
            var list = "";
            for(var i = 0;i<lenders.length;i++){
                list +="<li><a href = '"+lenders[i].url+"'>" +
                    lenders[i].name + "</a>>";
            }
            ad.innerHTML = "<ul>" + list + "</ul>";
        }
    }
}
```



3. js知识点

   我今天没有什么要更新的
