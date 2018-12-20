---
description: 监听指定分机的通话
---

# 通话监听

{% api-method method="post" host="https://api.zycoo.net" path="/coocenter-api/extensions/extenSpy" %}
{% api-method-summary %}
Extension Spy
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to get free cakes.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token to track down who is emptying our stocks.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="dst" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="src" type="string" required=true %}

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
  "message": "spy extension success"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```bash
curl -X POST "http://192.168.12.183:8000/coocenter-api/extensions/extenSpy" -H "accept: application/json" -H "Content-Type: application/x-www-form-urlencoded" -d "dst=806&src=801"
```

