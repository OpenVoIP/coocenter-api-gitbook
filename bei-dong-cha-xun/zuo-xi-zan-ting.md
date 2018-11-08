---
description: 设置坐席在队列中的忙/闲状态
---

# 坐席暂停

{% api-method method="get" host="https://api.zycoo.net" path="/coocenter-api/queues/agent-pause" %}
{% api-method-summary %}
Agent Pause
{% endapi-method-summary %}

{% api-method-description %}
设置队列中坐席状态
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token to track down who is emptying our stocks.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-form-data-parameters %}
{% api-method-parameter name="state" type="string" required=true %}
on/off on 表示开启暂停 off 表示关闭暂停
{% endapi-method-parameter %}

{% api-method-parameter name="member" type="string" required=true %}
分机号
{% endapi-method-parameter %}

{% api-method-parameter name="queue" type="string" required=true %}
队列号
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
暂停成功.
{% endapi-method-response-example-description %}

```javascript
{
  "status": "success",
  "message": "Interface paused successfully"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
暂停失败.
{% endapi-method-response-example-description %}

```javascript
{
  "status": "error",
  "message": "Interface not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```bash
curl -X POST "http://localhost:9990/coocenter-api/queues/agent-pause" -H "accept: application/json" -H "Content-Type: application/x-www-form-urlencoded" -d "queue=630&member=808&state=on"
```

```bash
curl -X POST "http://localhost:9990/coocenter-api/queues/agent-pause" -H "accept: application/json" -H "Content-Type: application/x-www-form-urlencoded" -d "queue=630&member=808&state=off"
```

