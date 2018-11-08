---
description: 设置呼入黑名单
---

# 呼入黑名单

{% api-method method="get" host="https://api.zycoo.net" path="/coocenter-api/blacklist/index" %}
{% api-method-summary %}
List Block
{% endapi-method-summary %}

{% api-method-description %}
获取所有黑名单号码
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "success",
  "data": [
    "111"
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```bash
curl -X GET "https://192.168.12.185:8080/coocenter-api/blacklist/index" -H "accept: application/json"
```

{% api-method method="delete" host="https://api.zycoo.net" path="/coocenter-api/blacklist/delete" %}
{% api-method-summary %}
Delete Block
{% endapi-method-summary %}

{% api-method-description %}
删除指定黑名单号码
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token to track down who is emptying our stocks.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="number" type="string" required=true %}
需要删除的黑名单号码
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
  "status": "success",
  "message": "Key deleted successfully"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```bash
curl -X DELETE "http://localhost:8000/coocenter-api/blacklist/delete" -H "accept: application/json" -H "Content-Type: application/x-www-form-urlencoded" -d "number=123456"
```

{% api-method method="post" host="https://api.zycoo.net" path="/coocenter-api/blacklist/create" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}
添加指定号码到黑名单
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-form-data-parameters %}
{% api-method-parameter name="number" type="string" required=true %}
添加的黑名单号码
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "success",
  "message": "Updated database successfully"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```bash
curl -X POST "http://localhost:8000/coocenter-api/blacklist/create" -H "accept: application/json" -H "Content-Type: application/x-www-form-urlencoded" -d "number=123123"
```

