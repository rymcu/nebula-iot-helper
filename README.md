# nebula-iot-helper

> 使用 Vue + Electron 实现的物联网设备调试助手  
> A debugging assistant for IoT devices using Vue + Electron  

## 实现流程
> [最新实现流程地址](https://www.processon.com/view/link/5f3e8a635653bb06f2dd9fb8)

```mermaid
graph TB
    subgraph "设备端"
    d1-->d2[自建WiFi/循环发送消息]
    d3-->d4{成功连接}
    d4--N-->d2
    end
    subgraph "服务端"
    d4--Y: 10008-->s1[绑定用户/设备关系]
    end
    subgraph "用户端"
    u1[添加设备]-->u2[选择需要添加的产品]
    u2-->d1[根据产品绑定教程操作设备]
    d2--10006-->u3[连接WiFi]
    u3-->u4[填写WiFi信息]
    u4--10007-->d3[连接WiFi]
    s1-->u5[更新绑定设备列表]
    end
```

## 指令代码

```json
{
  "10001": "请求 Token",
  "10002": "返回 Token",
  "10003": "开机",
  "10004": "重启",
  "10005": "关机",
  "10006": "请求 WiFi 信息/接收到请求返回",
  "10007": "返回 WiFi 信息",
  "10008": "绑定设备"
}
```

