# Markdown-
1、编辑README文件

大标题（一级标题）：在文本下面加等于号，那么上方的文字就变成了大标题，等于号的个数无限制，但一定要大于0

大标题
====
 

中标题（二级标题）：在文本下面加下划线，那么上方的文本就变成了中标题，下划线个数无限制，中标题比大标题低一级

中标题
-------
 

 1~6级标题：文本大小依次减小，以#号开头，多少个#号就是多少级标题，#号和标题名称要并排写

#一级标题
##二级标题
###三级标题
####四级标题
#####五级标题
######六级标题
插入圆点符号：编辑的时候使用的是星号 *，星号后面要有一个空格，否则为普通星号

* 列表一
* 列表二
* 列表三
 

二级圆点、三级圆点：多加一个Tab，即第二行一个Tab，第三行两个Tab

* 列表一
    * 列表二
        *列表三
 

缩进：

>缩进一
>>缩进二
>>>缩进三
>>>>缩进四
>>>>>缩进五
 

插入链接

[百度](http://baidu.com)
 

插入网络图片：![](网络图片链接地址)，即叹号!+方括号[]+括号()，如果不加叹号!就会变成普通文本，方括号里可以加入一些 标识性的信息

![baidu](http://www.baidu.com/img/bdlogo.gif "百度logo")  
 

插入GITHub仓库里的图片：![](图片链接地址)，即叹号!+方括号[]+括号()，URL写法：http://github.com/自己的用户名/项目名/raw/分支名/存放图片的文件夹/文件夹里的图片名字

给图片加上超链接：即点击一个图片进入指定网页，方括号里写自己起的标识名称，上下两行标识要一致。

[![baidu]](http://baidu.com)  
[baidu]:http://www.baidu.com/img/bdlogo.gif "百度Logo"  
 

插入代码片段：在代码上下行用```标记，注意`符号是tab键上面那个，要实现语法高亮，则在```后面加上编程语言的名称

复制代码
```Java
public static void main(String[] args){}
```

```javascript
document.getElementById("ts").innerHTML="Hello"
```
复制代码
换行：使用标签<br>

单行文本：前面使用两个Tab

多行文本:每行行首加两个Tab

部分文字高亮：使用``包围，这个符号不是单引号，而是Tab上方，数字1左边那个按键的符号

文字超链接格式：[百度网址](https://www.baidu.com)，在URL之后用双引号括起来一个字符串，即鼠标悬停显示的文本，可不写


<table><tbody>
    <tr>
        <th>方法说明</th><th>颜色名称</th><th>颜色</th>
    </tr>
    <tr>
        <td><font color="red">此处实现方法利用 CSDN-markdown 内嵌 html 语言的优势</font></td>
        <td><font color="red">Hotpink</font></td>
        <td bgcolor="red">rgb(240, 248, 255)</td>
    </tr>
    <tr>
        <td><font color="Pink">借助 table, tr, td 等表格标签的 bgcolor 属性实现背景色设置</font></td>
        <td><font color="pink">AntiqueWhite</font></td>
        <td bgcolor="Pink">rgb(255, 192, 203)</td>
    </tr>
</table>

<font face="黑体">我是黑体字</font>
<font face="微软雅黑">我是微软雅黑</font>
<font face="STCAIYUN">我是华文彩云</font>
<font color=#0099ff size=7 face="黑体">color=#0099ff size=72 face="黑体"</font>
<font color=#00ffff size=72>color=#00ffff</font>
<font color=gray size=72>color=gray</font>

统计磁盘空间：SpaceSniffer

LINQ dynamic query
Row transition column

1，安装Microsoft.AspNetCore.Mvc.Versioning
NET Core Mvc中，微软官方提供了一个可用的Api版本控制库Microsoft.AspNetCore.Mvc.Versioning。


2，修改Startup类
这里我们需要在Startup类的ConfigureService方法中添加以下代码。

        // This method gets called by the runtime. Use this method to add services to the container.
        public void ConfigureServices(IServiceCollection services)
        {
            services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);
            services.AddApiVersioning(o =>
            {
                o.ReportApiVersions = true;
                o.AssumeDefaultVersionWhenUnspecified = true;
                o.DefaultApiVersion = new ApiVersion(1, 0);
                //o.ApiVersionReader = new HeaderApiVersionReader("x-api-version");
            });
        }
3，代码
    //版本1控制器
    [ApiVersion("1.0", Deprecated = true)]
    [Route("api/values")]
    [ApiController]
    public class ValuesV1Controller : ControllerBase
    {
        [HttpGet]
        public IEnumerable<string> Get()
        {
            return new string[] { "这是版本1.0返回的——数据1", "这是版本1.0返回的——数据2" };
        }
    }
    //版本2控制器
    [ApiVersion("2.0")]
    [Route("api/values")]
    [ApiController]
    public class ValuesV2Controller : ControllerBase
    {
        [HttpGet]
        public IEnumerable<string> Get()
        {
            return new string[] { "这是版本2.0返回的——数据1", "这是版本2.0返回的——数据2" };
        }
    }
4，访问
https://localhost:44319/api/values

https://localhost:44319/api/values?api-version=1.0

https://localhost:44319/api/values?api-version=2.0

http://www.tuicool.com/articles/IRZvEzb
vs2019发布




