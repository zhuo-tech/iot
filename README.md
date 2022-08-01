# 数据平台接入规范
# 接口清单
# 网关地址 https://iot.gateway.smtbs.cn
## 查询指令执行记录
- 请求地址: https://api.zhuo-zhuo.com/api/cmd
- 调用方式：`HTTP GET`
- 接口描述: 更新地理位置指令｜召唤设备拍视频指令 
                   `cmd: call `则表示是召唤拍视频
                   `cmd: location` 则表示上报地理位置信息
- 请求参数: `无`
- 请求返回结果:
```json
{
    "code": 0,
    "msg": "success",
    "data": {
        "cmd": [
            {
                "id": "1",
                "sn": "202206210001",
                "cmd": "call",
                "createTime": "2022-06-22 10:07:13",
                "updateTime": "2022-06-22 10:07:13"
            },
            {
                "id": "2",
                "sn": "202206210001",
                "cmd": "location",
                "createTime": "2022-06-22 10:07:13",
                "updateTime": "2022-06-22 10:07:13"
            }
        ],
        "notifyUrl": "https://api.zhuo-zhuo.com/api/cmd/notify"
    }
}
```

## 位置上报
- 请求地址: https://api.zhuo-zhuo.com/api/location
- 调用方式：`HTTP POST`
- 接口描述: 召唤设备；拍照回传视频信息
- 请求参数:
```json
{
    "sn":"202206210001",
    "longitude": "116.397128",
    "latitude": "39.916527"
}
```
- 请求返回结果:
```json
{
    "code":"0",
    "msg":"success",
    "data": true
}
```

## 监控上报
- 请求地址: https://api.zhuo-zhuo.com/api/monitor
- 调用方式：`HTTP POST`
- 接口描述: 召唤设备,拍照回传视频信息
- 请求参数:
``` json
{
    "sn":"202206210001",
    "vodUrl":"https://1.mp4/",
    "fileId":"20200201"
}
```

- 请求返回结果:
```json
{
    "code":"0",
    "msg":"success",
    "data": true
}
```
