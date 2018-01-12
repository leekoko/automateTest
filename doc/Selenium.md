# Selenium IDE

该Selenium IDE主要应用于firefox浏览器  

## 1.工具准备

安装firebug，安装selenium IDE

## 2.基本录制   

### 1.校验内容    

1. 添加命令

   等待加载

```
waitForTitle
selenium_百度搜索
```

​	防止加载没完执行错误验证    

2. 添加注释

   右键 Insert New Comment，在Source模式下也可以对标题等内容进行修改    

3. 保存测试文件

   右键save Test case，使用.html后缀    

4. 添加断点    

   右键Toggle Breakpoint，通过断点来调试自动化测试。    

[基础结构](../SourceCode/Hello.html)  

### 2.源码修改   

``<link rel="selenium.base" href="http://oa.minstone.com.cn/" />``

添加baseUrl，下面的操作路径就变得简短：

```
<td>/Login/enter.jsp;jsessionid=QTrhhMTJ3lnh1yyp8L9H5K9xnQ4GcT6d15zzKFZ5dKLb2t2KBTcw!1604708425</td>
```

## 3.命令   

#### 1.highlight   

changes the backgroundColor of the specified element yellow.  Useful for debugging.

#### 2.clickAndWait

If the click action causes a new page to load.

#### 3.verifyTitle   

验证标题：错误继续 （一般在进入一个页面的时候使用）     

#### 4.assertTitle  

断言验证标题：错误停止

#### 5.verifyElementPresent   

验证元素存在与否     

#### 6.goBackAndWait   

回退  

## 4.变量   

#### 1.声明变量&打印变量   

![](../img/p01.png)   

点击的时候，可以把变量通过Value填进去。

[变量应用](../SourceCode/Variable.html)   

#### 2.变量获取属性值   

```
C: storeText
T: css = span.red
V: len
```

命令 - 定位 - 变量名   

#### 3.变量调用属性值  

```
C: stroeEval
T: Number(storedVars["totalLen"] + Number(storedVars["len"]))
V: totalLen
```

计算总值：相当于 +=

#### 4.使用js运算   

```
C: echo
T: javascript["平均数："+ storedVars["totalLen"]/27]  
```

## 5.定位元素   

### 1.XPath定位（备用）  

1. 绝对路径（不推荐）   

   ``xpath=/html/body/form[1]``   （不可省略）

2. 相对路径

   ``xpath=//form[input/@name='username']/input[3]``  （``xpath=``可以省略）      

   指定下标的位置：

   1. 那个的form标签，哪个form标签，带有input标签。哪个input标签，name为username的input标签。  

      （做为参数的，前面要添加@标识``xpath=//form[@id='loginName']``,那个form，哪个form？id为loginName的那个）      

   2. 选中form中的第3个input        

3. 模糊匹配

   ``/Root//Person[contains(Blog,'cn')]``:查找带cn的Blog标签   

### 2.Dom定位器（备用）     

1. 根据id定位   

   ``dom=document.getElementById['loginForm']``   (``dom=``可以省略)   

   ``dom=document.forms['loginForm']``      

2. 脚标定位   

   ``dom=document.form[0]``     

   泛指元素   

   ``dom=document.forms['loginForm'].elements[0]``      

3. name定位   

   ``dom=document.forms['loginForm'].username``   

   泛指元素    

   ``dom=document.forms['loginForm'].elements['username']``   

### 3.其他定位（优先使用）

#### 1.id定位

#### 2.name定位

#### 3.css样式

组合css：``css=input.className[name='userName']``           

#### 4.identifier

``identifier = loginFrom``   ,identifier可以指定id、name。  (``identifier =``可以省略)    

#### 5.link定位

``link=sample页面``    

### 4.增加过滤器  

``name=continue value=Clear``   

## 6.验证  

### 1.assertTitle

```
C: assertTitle
T: 百度一下，你就知道
```

验证标题   

### 2.verifyText   

```
C: verifyText
T: xpath=/html/body/form[1]/p
V: 显示的内容*   
```

严格：验证文字是否存在，位置是否正确   

*标识内容为通配   

### 3.verifyElementPresent

```
C: verifyText
T: xpath=/html/body/form[1]/p
```

宽松：验证元素位置是否存在

## 7.调试   

### 1.设置起点  

右键 - set start point   






























怎么移动内容？？

学习难的部分

feiman内容，发直接可用的博客    

