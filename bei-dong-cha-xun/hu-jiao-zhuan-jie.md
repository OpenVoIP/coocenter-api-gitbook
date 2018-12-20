---
description: 将指定分机的通话转接到另外的分机
---

# 呼叫转接

{% api-method method="post" host="https://api.zycoo.net" path="/coocenter-api/extensions/transfer" %}
{% api-method-summary %}
Transfer Call
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
  "message": "tansfer extension success"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```bash
curl -X POST "https://192.168.12.185:8080/coocenter-api/extensions/transfer" -H "accept: application/json" -H "Content-Type: application/x-www-form-urlencoded" -d "dst=801&src=802"
```

