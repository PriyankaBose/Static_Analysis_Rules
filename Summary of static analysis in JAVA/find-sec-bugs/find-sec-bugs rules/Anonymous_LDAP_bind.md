### Anonymous LDAP bind

LDAP匿名绑定

**Bug Pattern：**LDAP_ANONYMOUS
####描述：
如果没有适当的访问控制，执行包含用户控制值的LDAP语句可能允许攻击者滥用配置不良的LDAP环境。 所有针对ctx执行的LDAP查询都将在没有身份验证和访问控制的情况下执行。 攻击者可能能够以一种意想不到的方式操纵这些查询中的一个，以获得对目录的访问控制机制可能受到保护的记录的访问。

- [x] 安全相关

####漏洞代码：
```
...

env.put(Context.SECURITY_AUTHENTICATION, "none");

DirContext ctx = new InitialDirContext(env);

...

```
####解决方案：
Consider other modes of authentication to LDAP and ensure proper access control mechanism.

#### Check级别：AST

####相关信息：
1. [Ldap Authentication Mechanisms](https://docs.oracle.com/javase/tutorial/jndi/ldap/auth_mechs.html )



