## 1. 接口描述

功能： 直拨 PSTN 虚拟中间号话单推送接口  
接口地址：在直拨 PSTN 获取虚拟中间号的接口参数`hangupUrl`带上对应的回调地址或者线下配置默认地址
请求方式：POST  

## 2. 参数说明 
| 参数名 | 要求 | 备注 | 
|---------|---------|------------|
| appId | 必选 | xxx | 
| callId | 必选 | 通话唯一标识 callId | 
| requestId | 可选 | App 操作 session buffer 原样返回 | 
| bindId | 必选 | 双方号码 + 中间号绑定 ID，该 ID 全局唯一 | 
| src | 必选 | 主叫号码 | 
| dst | 必选 | 被叫号码 | 
| dstVirtualNum | 必选 | 主叫通讯录直拨虚拟保护号码 | 
| callCenterAcceptTime | 必选 | 虚拟保护号码平台收到呼叫时间 | 
| startDstCallTime | 必选 | 被叫呼叫开始时间 | 
| startDstRingTime | 必选 | 被叫响铃开始时间 | 
| dstAcceptTime | 必选 | 被叫接听时间 | 
| endCallTime | 必选 | 用户挂机通话结束时间 | 
| callEndStatus | 必选 | 通话最后状态： 0：未知状态  1：正常通话  2：查询呼叫转移被叫号异常  3：未接通 4：未接听 5：拒接挂断 6：关机 7：空号 8：通话中 9：欠费 10：运营商线路或平台异常 | 
| srcDuration | 必选 | 主叫接通虚拟保护号码到通话结束通话时间 | 
| dstDuration | 必选 | 呼叫转接被叫接通到通话结束通话时间 | 

**确认响应包必填字段**  
```
HTTP/1.1 200 OK
Content-Type: text/plain;charset=utf-8
Content-Length: 0
```
