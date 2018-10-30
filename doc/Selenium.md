# Selenium自动化测试

M：环境搭建需要什么东西呢？

Z：谷歌浏览器对应的测试驱动，具体对应表格自行百度。

M：自动化测试需要做什么准备？

Z：指定实例化驱动即可

```java
    private WebDriver driver = null;
    private final String URL = "http://localhost:8080/th_info_sys";

    public ThPage() {
        System.setProperty("webdriver.chrome.driver","D:\\chromedriver\\chromedriver.exe");//chromedriver服务地址
        driver = new ChromeDriver(); //新建一个WebDriver 的对象，但是new 的是FirefoxDriver的驱动
    }
```

### 测试常用脚本

#### 1.打开指定url

driver.get(url);

#### 2.最大化窗口

driver.manage().window().maximize();

#### 3.线程休息

Thread.sleep(2*1000);

#### 4.传递文本内容

driver.findElement(By.id("usertext")).sendKeys(“文本内容”);

#### 5.点击元素

driver.findElement(By.className("icon_exit")).click();

#### 6.切换iframe

driver.switchTo().frame("frmleft");

driver.switchTo().parentFrame();

提取出来的方法要切换回原来的父iframe

#### 7.鼠标控制

```java
        Actions action = new Actions(driver);
        action.moveToElement(driver.findElement(By.xpath("//*[@id=\"loginForm\"]/table/tbody/tr[7]/td/input")));
        action.click().perform();   //双击  action.doubleClick().perform();
```

注意driver当前所处的iframe位置

#### 8.执行js代码

```java
JavascriptExecutor js = (JavascriptExecutor) driver;
js.executeScript("$(\"input[name*='dealUserName']\").val(\"广东省计算机技术应用研究所\");");   //注意引号问题
js.executeScript("$(\"#psname\").val(\"广东省计算机技术应用研究所\");");
```

#### 9.退出浏览器

```java
driver.quit();//退出浏览器
```

### 定位

Z：一般情况下使用id定位：``By.id("letternum")``  

Z：定位一种实用的方式就是用Xpath，以下为XPath用的定位方式：

1. 普通属性定位：``//*[@title=\"属性内容\"]``
2. 文本内容定位：``"//span[text()='用户名']/.."``（一般配合父子定位使用）