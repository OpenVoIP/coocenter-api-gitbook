---
description: 挂断指定分机
---

# 通话挂断

{% api-method method="post" host="https://api.zycoo.net" path="/coocenter-api/extensions/hangup" %}
{% api-method-summary %}
Hangup Call
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
{% api-method-parameter name="extension" type="string" required=true %}

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
  "message": "hangup extension success"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```bash
curl -X POST "https://192.168.12.185:8080/coocenter-api/extensions/hangup" -H "accept: application/json" -H "Content-Type: application/x-www-form-urlencoded" -d "extension=801"
```

