---
description: api.conf 中若设置了 WEBKEY 将对请求头中的 Authorization  进行验证。
---

# 认证

## 认证方式

YYYY-MM-DD 为当日的 年-月-日 格式日期

```bash
$ md5sum(WEBKEY + 'YYYY-MM-DD')
```

{% hint style="info" %}
 若不需要要认证直接注释 api.conf 中的 WEBKEY
{% endhint %}



