---
description: 'PBX 向指定 HTTP 服务器通过 POST 推送通话日志, 分机状态等事件。'
---

# 主动推送

### 呼叫开始

```javascript
{
  event:"dialbegein",
  timestamp:"1534993059.785012",			//主叫通道唯一标识
  channel:"DAHDI/i1/18782985586-51",		//主叫通道
  calleridnum:"18782985586", 				//主叫号码
  destchannel:"SIP/886-00000065",		    //被叫通道
  destcalleridnum:"886",					//被叫号码  
  destuniqueid:"1534993059.630",			//被叫通道唯一标识
  dialstring:"SIP/886",
  uniqueid:"1534993030.626",				//呼叫唯一标识
  mac:"68:69:2e:05:0f:9a",				    //设备MAC地址
}
```

### 呼叫结束

```javascript
{
  event:"dialend",
  timestamp: "1534993059.785012", 				//时间戳
  channel: "DAHDI/i1/18782985586-51", 			//主叫通道
  calleridnum: "18782985586",   				//主叫号码
  destchannel:"SIP/886-00000065", 				//被叫通道
  destcalleridnum: "886",   					//被叫号码
  uniqueid: "1534993030.626",   				//呼叫唯一标识
  dialstatus:"hangup"
}
```

### 挂机

```javascript
{
  event: "hangup"
  calleridnum: "808",     					//主叫号码
  calleridname: "808",      				//主叫名称
  connectedlinenum: "809",    				//被叫号码
  connectedlinename: "809",   				//被叫名称
  uniqueid: "1325747409.260",				//呼叫唯一标识
}
```

### 分机状态

```javascript
{
  event: "extensionstatus",
  exten: "808",       			          //分机号码
  status: "0",        			          //状态码: 0:待机，1:通话中，2:忙线，4:离线，8:振铃中，16:保持
  statustext: "Idle",
}
```

### IVR 事件

```javascript
{
  event: 'ivr',
  uuid: '1541643689.15',					//唯一标识
  caller: '810',      						//主叫号码
  called: '',
  callType: 'IN',
  queueCode: '630',     					//下一级队列
  startTime: '2018-11-08 10:21:29', 		//当前IVR的开始时间
  endTime: '2018-11-08 10:21:32', 		    //当前IVR的结束时间
  duration: '3',      						//当前IVR的持续时间
  ivrId: '610',       						//当前IVR中的IVR的ID
  ivrName: 'working time',    			    //当前IVR中的IVR的名称
  ivrDtmf: '0',       						//当前IVR中的DTMF按键
  trunkNumber: '123456',     				//DID号码
  mac: '68:69:2e:03:8b:3e ' 				//设备MAC地址
}
```

### 通话日志1

```javascript
{
  event: 'cc_cdr',
  uuid: '1541415929.807',   				//唯一标识
  caller: '85322361',     				    //主叫号码
  called: '100',      						//被叫号码
  queueCode: '630',     					//队列号码
  agentCode: '100',     					//坐席分机
  callType: 'incoming',     				//呼叫类型
  cdrState: 'queue',      				    //结束时所在位置:bridged接通;feedback评价;queue队列;ivr自动话务员
  hangupSide: 'caller',					    //结束挂断方
  hangupCause: 'ANALOG ANALOG_EVENT_ONHOOK',
  startTime: '2018-11-05 19:05:31', 		//通话开始时间
  endTime: '2018-11-05 19:05:39', 		    //通话结束时间
  duration: '8',      						//通话持续时长  
  queueTime: '7',     						//队列中等待时间
  feedbackTime: '0',      				    //满意度评价使用的时间
  ivrTime: '',        						//IVR中经历的时间
  ringTime: '7',      						//振铃时长
  holdTime: 0,        						//保持时长
  pauseTime: 0,       						//后处理时长
  talkingTime: '0',     					//通话时长
  voicemailState: '0',      				//是否有语音留言
  ivrId: '',        						//呼入经过的IVR的ID
  ivrName: '',        						//呼入经过的IVR的名称
  ivrDtmf: '0',       						//呼入经过的DTMF按键
  fwType: '',
  score: '0',       						//满意度评价数字
  trunkNumber: '',      					//DID号码
  forwardNumber: '',
  filePath: '',       						//录音文件
  missCause: 'MEMBER_CANCEL',   			//来电丢失原因;NO_ASSIGN客服人数不够; NO_AGENT_ANSWER 电话不接听; NO_AGENT_LOGIN无人登陆;MEMBER_CANCEL排队10秒内挂机
  mac: '68:69:2e:03:8b:3e' 				    //设备MAC地址
}
```

### ​通话日志2

```javascript
{
  event: "cdr",
  callerid: "\"808\" <808>",    			//名称 <号码>
  source: "808",      						//主叫号码
  destination: "809",     				    //被叫号码
  starttime: "2012-01-05 15:10:09",		    //呼叫开始时间
  answertime: "2012-01-05 15:10:10",		//呼叫应答时间
  endtime: "2012-01-05 15:10:11",		    //呼叫结束时间
  disposition: "ANSWERED",    			    //通话状态
  duration: "2",      						//呼叫时长
  billableseconds: "1",     				//通话时长
  calltype: "",       						//呼叫类型（outbound:呼出，inbound：呼入，空为内部呼叫）
  recordfile: "",     						//录音文件
  uniqueid: "1325747409.260"				//唯一标识
}
```



