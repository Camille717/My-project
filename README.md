登录页面代码
<html> 
<head> 
    <meta charset="utf-8">
    <title>登录页面</title>    
</head> 

<body> 
    <form action="./wait.html"> 
        用户名:<input type="text" id="uname"/><br> 
        密码:<input type="password" id="pwd"/><br> 
        <input type="submit" value="登录" onclick="return checkuser()"/> 
    </form> 
</body> 
<script type="text/javascript"> 
    function getValue(id) { 
        return document.getElementById(id).value; 
    } 
    function checkuser() { 
        if(getValue('uname') == "magicliu" && getValue('pwd') == "123") { 
            return true; 
        }else { 
            alert("登录名或密码错误！")
            return false; 
        } 
    } 
</script> 
</html> 

等待页面代码
<html> 
<head> 
  <meta charset="utf-8">
  <title>等待页面</title> 
</head> 

<body> 
  登录成功，<span id="myspan">5</span>秒后自动跳转到管理页面 
</body> 

  <script type="text/javascript"> 
    function getLabel(id) { 
      return document.getElementById(id); 
    } 
    function changeSec() { 
      //得到myspan值，每秒减一，会进行隐士转换
      getLabel('myspan').innerText=getLabel('myspan').innerText-1; 
    }
    var mytime = setInterval("changeSec()",1000); 
    //五秒后跳转
    function tiao() { 
      clearInterval(mytime); 
      //window.open("./welcome.html","_self"); 
      window.location.href = "./welcome.html";
    } 

    setTimeout("tiao()",5000); 
  </script> 
</html>

登录成功
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title></title>
</head>
<body>
    <h1>登录成功，欢迎来到主页！</h1>
</body>
</html>
