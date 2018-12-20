# 分机注册信息列表

{% api-method method="get" host="https://api.zycoo.net" path="/coocenter-api/extensions/extension-status" %}
{% api-method-summary %}
Get Extensions Status
{% endapi-method-summary %}

{% api-method-description %}
获取分机注册信息
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
  "message":"Peer status list will follow",
  "data":
  [
    {
      "Exten": "800",
      "Type": "SIP",
      "IPAddr": "-none-",
      "Status": "UNKNOWN"
    },
    {
      "Exten": "801",
      "Type": "SIP",
      "IPAddr": "192.168.12.4",
      "Status": "OK (45 ms)"
    },
    {
      "Exten": "802",
      "Type": "SIP",
      "IPAddr": "192.168.12.3",
      "Status": "OK (42 ms)"
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

```bash
curl -X GET "http:// 192.168.12.183:8000/coocenter-api/extensions/extension-status" -H "accept: application/json"
```

