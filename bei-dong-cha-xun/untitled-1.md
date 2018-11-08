---
description: 'PBX 作为web 服务器接受外部请求, 查询当前通话'
---

# 当前通话

{% api-method method="get" host="https://api.zycoo.net" path="/coocenter-api/extensions/current-calls" %}
{% api-method-summary %}
Get Current Calls
{% endapi-method-summary %}

{% api-method-description %}
获取当前所有通话.
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
  "message":"Channels will follow",
  "data":[
    {
      "calleridname":"896",         //主叫名称
      "calleridnum":"896",          //主叫号码
      "channel":"SIP/896-0000000b",	//主叫通道
      "channelstate":"6",
      "channelstatedesc":"Up",
      "connectedlinename":"897",    //被叫名称
      "connectedlinenum":"897",	    //被叫号码
      "context":"macro-stdexten-withoutvm",
      "duration":"00:02:58",        //通话时长
      "exten":"s"
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```bash
curl -X POST "http://localhost:9990/coocenter-api/extensions/current-calls" -H "accept: application/json"
```

