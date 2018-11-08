---
description: '向 PBX 提交主叫/被叫号码, PBX 先拨打主叫号码再拨打被叫号码。'
---

# 点击拨号

{% api-method method="post" host="https://api.zycoo.net" path="/coocenter-api/extensions/click-number" %}
{% api-method-summary %}
Click Call
{% endapi-method-summary %}

{% api-method-description %}

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
被叫号码
{% endapi-method-parameter %}

{% api-method-parameter name="src" type="string" required=true %}
主叫号码
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
    "name": "Cake's name",
    "recipe": "Cake's recipe name",
    "cake": "Binary cake"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```javascript
{
    "message": "Ain't no cake like that."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```bash
curl -X POST "https://192.168.12.185:8080/coocenter-api/extensions/click-number" -H "accept: application/json" -H "Content-Type: application/x-www-form-urlencoded" -d "src=808&dst=809"
```

