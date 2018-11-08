---
description: 'PBX 向指定 HTTP 服务器通过 POST 推送通话日志, 分机状态等事件。'
---

# 主动推送

### 呼叫开始

```javascript
{
  event:"dialbegein",
  timestamp:"1534993059.785012",           //时间戳
  channel:"DAHDI/i1/18782985586-51",       //主叫通道
  channelstate:"6",
  calleridnum:"18782985586",               //主叫号码
  destchannel:"SIP/886-00000065",          //被叫通道
  destchannelstate:"0",
  destcalleridnum:"886",                   //被叫号码  
  destexten:"",
  destuniqueid:"1534993059.630",
  dialstring:"SIP/886",
  uniqueid:"1534993030.626",               //呼叫唯一标识
  mac:"68:69:2e:05:0f:9a",                 //设备MAC地址
}
```

### 呼叫结束

```javascript
{
  event:"dialend",
  timestamp: "1534993059.785012",      //时间戳
  channel: "DAHDI/i1/18782985586-51",  //主叫通道
  channelstate: "",
  calleridnum: "18782985586",	       //主叫号码
  destchannel:"SIP/886-00000065",      //被叫通道
  destchannelstate: "",
  destcalleridnum: "886",	           //被叫号码
  destexten: "",
  destuniqueid: "",
  uniqueid: "1534993030.626",	       //呼叫唯一标识
  dialstatus:"hangup"
}
```

### 挂机

```javascript
{
  event: "hangup"
  calleridnum: "808",                  // 主叫号码
  calleridname: "808",                 // 主叫名称
  connectedlinenum: "809",             // 被叫号码
  connectedlinename: "809",            // 被叫名称
  uniqueid: "1325747409.260",
}
```

### 分机状态

```javascript
{
  event: "extensionstatus",
  exten: "808",
  statustext: "Idle",
}
```

### IVR 事件

```javascript
{
  event: 'ivr',
  uuid: '1541643689.15',              //唯一标识
  caller: '810',			          //主叫号码
  called: '',
  callType: 'IN',
  queueCode: '630',			          //下一级队列
  startTime: '2018-11-08 10:21:29',	  //当前IVR的开始时间
  endTime: '2018-11-08 10:21:32',	  //当前IVR的结束时间
  duration: '3',			          //当前IVR的持续时间
  ivrId: '610',				          //当前IVR中的IVR的ID
  ivrName: 'working time',		      //当前IVR中的IVR的名称
  ivrDtmf: '0',				          //当前IVR中的DTMF按键
  trunkNumber: 's',			          //DID号码
  mac: '68:69:2e:03:8b:3e' 
}
```

### 通话日志

```javascript
{ 
  event: 'cc_cdr',
  uuid: '1541415929.807',		      //唯一标识
  caller: '85322361',			      //主叫号码
  called: '100',			          //被叫号码
  queueCode: '630',			          //队列号码
  agentCode: '100',			          //坐席分机
  callType: 'incoming',			      //呼叫类型
  cdrState: 'queue',			      //结束时所在位置:bridged接通;feedback评价;queue队列;ivr自动话务员
  hangupCause: 'ANALOG ANALOG_EVENT_ONHOOK',
  startTime: '2018-11-05 19:05:31',	  //通话开始时间
  endTime: '2018-11-05 19:05:39',	  //通话结束时间
  duration: '8',			          //通话持续时长	
  queueTime: '7',			          //队列中等待时间
  feedbackTime: '0',			      //满意度评价使用的时间
  ivrTime: '',				          //IVR中经历的时间
  ringTime: '7',			          //振铃时长
  holdTime: 0,				          //保持时长
  pauseTime: 0,				          //后处理时长
  talkingTime: '0',			          //通话时长
  voicemailState: '0',			      //是否有语音留言
  ivrId: '',				          //呼入经过的IVR的ID
  ivrName: '',				          //呼入经过的IVR的名称
  ivrDtmf: '0',				          //呼入经过的DTMF按键
  fwType: '',
  score: '0',				          //满意度评价数字
  trunkNumber: '',			          //DID号码
  forwardNumber: '',
  filePath: '',				          //录音文件
  missCause: 'MEMBER_CANCEL',		  //来电丢失原因;NO_ASSIGN客服人数不够;NO_AGENT_ANSWER电话不接听;NO_AGENT_LOGIN无人登陆;MEMBER_CANCEL排队10秒内挂机
  mac: '68:69:2e:0b:00:01' 
  }
```

​



