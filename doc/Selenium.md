# Selenium

## 1.工具准备

安装firebug，安装selenium IDE

## 2.基本录制   

### 1.校验内容    

#### 1.校验内容  

1. 校验标题

```
assertTitle
selenium_百度搜索
```

2. 校验内容

```
verifyText
css=div.nums
*百度为您找到相关结果约*
```

​	*标识内容为通配    

也可以右键添加   

3. 等待加载

```
waitForTitle
selenium_百度搜索
```

​	防止加载没完执行错误验证    

4. 添加注释

   右键 Insert New Comment，在Source模式下也可以对标题等内容进行修改    

5. 保存测试文件

   右键save Test case，使用.html后缀    

6. 添加断点    

   右键Toggle Breakpoint，通过断点来调试自动化测试。    







怎么移动内容？？

怎么切换frame后进行选择元素？？   



