---
description: 坐席嵌入/签出队列
---

# 坐席签入/签出

{% api-method method="post" host="https://api.zycoo.net" path="/coocenter-api/queues/agent-login" %}
{% api-method-summary %}
Agent Login
{% endapi-method-summary %}

{% api-method-description %}
 签入坐席
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token to track down who is emptying our stocks.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="queue" type="string" required=true %}

{% endapi-method-parameter %}

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
  "message": "login extension success"
}

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```bash
curl -X POST "https://192.168.12.185:8080/coocenter-api/queues/agent-login" -H "accept: application/json" -H "Content-Type: application/x-www-form-urlencoded" -d "extension=800&queue=630"
```

{% api-method method="post" host="https://api.zycoo.net" path="/coocenter-api/queues/agent-logout" %}
{% api-method-summary %}
Agent Logout
{% endapi-method-summary %}

{% api-method-description %}
签出
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-form-data-parameters %}
{% api-method-parameter name="queue" type="string" required=false %}

{% endapi-method-parameter %}

{% api-method-parameter name="extension" type="string" required=false %}

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
  "message": "logout extension success"
}

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```bash
curl -X POST "https://192.168.12.185:8080/coocenter-api/queues/agent-logout" -H "accept: application/json" -H "Content-Type: application/x-www-form-urlencoded" -d "extension=800&queue=630"
```

