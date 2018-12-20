---
description: 获取所有坐席分机当前状态
---

# 分机状态列表

{% api-method method="get" host="https://api.zycoo.net" path="/coocenter-api/extensions/extension-hints-status" %}
{% api-method-summary %}
Get all agent extensions status
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
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```javascript
[
  {
    "agentName": "800",                    //坐席名称
    "extension": "800",                    //分机号码
    "extenType": "analogCallCenter",       //坐席类型：web坐席，SIP坐席，模拟分机坐席
    "status": "0"                          //状态码: 0:待机，1:通话中，2:忙线，4:离线，8:振铃中，16:保持
  },
  {
    "agentName": "801",
    "extension": "801",
    "extenType": "analogCallCenter",
    "status": "0"
  }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```bash
curl -X GET "http://192.168.12.183:8000/coocenter-api/extensions/extension-hints-status" -H "accept: application/json"
```



