###Potential template injection with Freemarker

使用Freemarker进行潜在模板注入

**Bug Pattern：**TEMPLATE_INJECTION_FREEMARKER
####描述：
Freemarker模板引擎功能强大。 可以添加逻辑，包括条件语句，循环和外部调用。 这不是设计成模板操作的沙箱。 控制模板的恶意用户可以在服务器端运行恶意代码。 Freemarker模板应该被视为脚本。

- [x] 安全相关

####漏洞代码：
```
Template template = cfg.getTemplate(inputTemplate);

[...]

template.process(data, swOut);

```
####解决方案：
Avoid letting end users manipulate templates with Freemarker. If you need to expose template editing to your users, prefer logic-less template engines such as Handlebars or Moustache (See references).

#### Check级别：AST

####相关信息：
1. [PortSwigger: Server-Side Template Injection](http://blog.portswigger.net/2015/08/server-side-template-injection.html )
1. [Handlebars.java ](https://jknack.github.io/handlebars.java/ )





