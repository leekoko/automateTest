

1. 执行js代码

   ```java
   JavascriptExecutor js = (JavascriptExecutor) driver;
   js.executeScript("$(\"input[name*='dealUserName']\").val(\"广东省计算机技术应用研究所\");");   //注意引号问题
   js.executeScript("$(\"#psname\").val(\"广东省计算机技术应用研究所\");");
   ```

2. 退出浏览器

   ```java
   driver.quit();//退出浏览器
   ```







广东省计算机技术应用研究所(评审)



区科工信局监理