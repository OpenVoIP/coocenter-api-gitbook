---
description: 查询队列中坐席状态/优先级等信息
---

# 队列信息

{% api-method method="get" host="https://api.zycoo.net" path="/coocenter-api/queues/queue-info" %}
{% api-method-summary %}
Get Queue Info
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
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
{
  "status":"success",
  "message":"Queue status will follow",
  "data":
  {
    "630":        //队列号码
    [
      {"name":"sip/876","paused":"0","penalty":"0"},//队列中的坐席信息（name:坐席通道,paused:是否暂停"0为取消暂停，1为暂停",penalty:权重"队列中呼叫的优先级别"）
      {"name":"sip/805","paused":"0","penalty":"1"},
    ],
    "631":
    [
      {"name":"sip/870","paused":"0","penalty":"0"},
    ],
    "632":
    [
      {"name":"sip/897","paused":"0","penalty":"0"},
      {"name":"sip/898","paused":"0","penalty":"0"}
    ]
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```bash
curl -X POST "http://localhost:9990/coocenter-api/queues/queue-info" -H "accept: application/json"
```

