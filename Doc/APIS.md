## Cloud_Sign文档

### Auth - 协议版本检查

🎉🎉🎉 目前最新版本：1.0

API -> ```Url/Auth?version=xxx```

返回格式
```json
{"code":0}
```
|  code   | 含义  |
|  ----  | ----  |
| 0  | 协议版本正常 |
| 1  | 协议版本不匹配 |
|400 | 参数不全 |

##### ✅ 本接口主要用于检查数据传输协议版本

### Login - 玩家登录

API -> ```Url/Login?xuid=xxxx&password=xxxx```

返回格式
```json
{"code":0}
```
|  code   | 含义  |
|  ----  | ----  |
| 0  | 登录成功 |
| 1  | 登录失败 |
|400 | 参数不全 |

##### ✅ 本接口主要用于检查玩家password是否正确

### Register - 注册

API -> ```Url/Register?xuid=xxxxx&password=xxxxx?name=xxxxx```

返回格式
```json
{"code":0}
```

|  code   | 含义  |
|  ----  | ----  |
| 0  | 注册成功 |
| 1  | 此用户已注册 |
|400 | 参数不全 |

⛔ 请务必提供玩家名```name```，因为需要根据xuid反查玩家姓名

##### ✅ 本接口主要用于玩家注册

### Sign - 签到！

返回格式
```json
{
	"total":1,
	"code":1,
	"items":[
	{"itemname":"Clock","count":2}
	]
}
```

|  json项  | 含义  |
|  ----  | ----  |
| code | 状态码 |
| total  | 今日签到总人数 |
| items | 签到奖励 |

⛔ 只要code不为0均为签到失败


### Xuidquery - 根据name进行xuid查询

API -> ```Url/Xuidquery?name=xxx```

返回格式
```json
{"code":0}
```

|  code   | 含义  |
|  ----  | ----  |
| 16位整数  | 根据name查询到的xuid |
| 1  | 无记录 |
|400 | 参数不全 |

##### ✅ 本接口主要用于检查注册和反查XUID之用
