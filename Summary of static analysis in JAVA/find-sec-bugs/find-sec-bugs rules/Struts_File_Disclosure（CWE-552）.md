###Struts File Disclosure
文件泄露
**Bug Pattern：** STRUTS_FILE_DISCLOSURE
####描述：
允许用户输入控制格式参数可能使攻击者能够引发异常或者泄漏信息。

攻击者可能能够修改格式字符串参数，从而引发异常。 如果此异常未被捕获，可能会导致应用程序崩溃。 或者，如果在未使用的参数中使用敏感信息，攻击者可能会更改格式字符串以显示此信息。

- [x] 安全相关

####漏洞代码：
```
String returnURL = request.getParameter("returnURL");

return new ModelAndView(returnURL); 
```
####解决方案：
Avoid constructing server-side redirects using user controlled input.

#### Check级别：AST

####相关信息：
1. [CWE-552: Files or Directories Accessible to External Parties](https://cwe.mitre.org/data/definitions/552.html)


