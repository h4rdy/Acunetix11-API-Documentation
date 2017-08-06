## 扫描设置

### General设置:
#### criticality设置:

```
Method:PATCH 
URL: /api/v1/targets/{target_id}
```

Data:

```
{"description":"xxxx","criticality":20}
```

发送参数说明:

| 参数 | 类型 |说明 |
| --- | --- |--- |
| description | String | 备注 |
| criticality | Int | 危险程度;范围:[30,20,10,0]|


#### 连续扫描(Continuous Scanning):

```
Method:POST 
URL: /api/v1/targets/{target_id}/continuous_scan
```

Data:

```
{"enabled":false}
```

发送参数说明:

| 参数 | 类型 |说明 |
| --- | --- |--- |
| enabled | bool | 关闭:false;开启:true |


#### 扫描速度(Scan Speed):

```
Method:PATCH 
URL: /api/v1/targets/{target_id}/configuration
```

Data:

```
{"scan_speed":"sequential"}
```

发送参数说明:

| 参数 | 类型 |说明 |
| --- | --- |--- |
| scan_speed | string | 由慢到快:sequential/slow/moderate/fast |

#### 登录设置(Site Login)
***网站登录设置***

```
Method: PATCH 
URL: /api/v1/targets/{target_id}/configuration
```
Data:

```
{
    login:
        {kind: "automatic",
         credentials: 
            {enabled: true, 
             username: "h4rdy", 
             password: "123"}
        }
}
```
OR:

```
{
    login:
        {kind: "none/sequence"}
}
```

发送参数说明:

| 参数 | 类型 |说明 |
| --- | --- |--- |
| kind | string | 启用:automatic;不启用:none(默认);使用登录序列:sequence |
| credentials | dict | 登录凭证 |
|enabled|bool| false/true |
| username | string | 用户名 |
| password | string | 密码 |


***上传登录序列***

```
Method: POST/DELETE
URL: /api/v1/targets/{target_id}/configuration/login_sequence
```
Data:

```
{name: "wiki.h4rdy.me.lsr", size: 2068}
```
发送参数说明:

| 参数 | 类型 |说明 |
| --- | --- |--- |
| name | string | 登录序列文件位置 |
| size | int | 文件大小:计算单位为Byte |

返回参数说明:
Data:

```
{"upload_url": "/uploads/73998157-2cc5-4569-92eb-5ea0bd35946e"}
```

| 参数 | 说明 |
| --- | --- |
| upload_url |文件名 |

注: 删除操作不带任何参数直接以DELETE方法请求接口

```
Method: POST 
URL: {upload_url}
Content-Type: application/octet-stream
```

发送参数说明:

| 说明 |
| --- | --- |--- |
| 直接将登录序列文件内容POST到接口 |


#### AcuSensor:

```
Method:PATCH 
URL: /api/v1/targets/{target_id}/configuration
```
Data:  

```
{sensor: false}
```
| 参数 | 类型 |说明 |
| --- | --- |--- |
| sensor | bool | false/true  |

### 爬虫(Crawl):
#### 爬虫设置(Crawling / Navigation):

```
Method:PATCH 
URL: /api/v1/targets/{target_id}/configuration
```
Data:  

```
{"limit_crawler_scope":true,
"case_sensitive":"no",
"excluded_paths":["xxx"],
"user_agent":"Opera/9.80 (Windows NT 6.0; U; en) Presto/2.8.99 Version/11.10"
}
```

发送参数说明:

| 参数 | 类型 |说明 |
| --- | --- |--- |
| limit_crawler_scope | bool | Limit crawling to address and sub-directories only;值:true/false|
| case_sensitive | string | 路径大小写敏感设置;值: auto(默认)/no/yes |
| excluded_paths | list | 排除路径;  |
| user_agent | string | UA设置 |

### HTTP设置(HTTP):

#### HTTP身份验证(HTTP Authentication):

```
Method:PATCH 
URL: /api/v1/targets/{target_id}/configuration
```
Data: 

```
{"authentication":{"enabled":true,"username":"h4rdy","password":"123"}}
```

发送参数说明:

| 参数 | 类型 |说明 |
| --- | --- |--- |
| enabled | bool | false/true  |
| username | string | 用户名 |
| password | string | 密码  |

#### 客户端证书(Client Certificate):
***上传证书***

```
Method: POST/DELETE 
URL: /api/v1/targets/{target_id}/client_certificate
```
Data: 

```
{"name":"123.crt","size":712}
```

发送参数说明:

| 参数 | 类型 |说明 |
| --- | --- |--- |
| name | string | 文件名 |
| size | int | 文件大小:计算单位为Byte |


返回参数说明:
Data:

```
{"upload_url": "/uploads/73998157-2cc5-4569-92eb-5ea0bd35946e"}
```
| 参数 | 说明 |
| --- | --- |
| upload_url | 文件路径名 |

注: 删除操作不带任何参数直接以DELETE方法请求接口

```
Method: POST 
URL: {upload_url}
Content-Type: application/octet-stream
```

发送参数说明:

| 说明 |
| --- | --- |--- |
| 直接将文件内容POST到接口 |

***客户端证书密码设置***

```
Method:PATCH 
URL: /api/v1/targets/{target_id}/configuration
```
Data: 

```
{"client_certificate_password":"123"}
```
发送参数说明:

| 参数 | 类型|说明 |
| --- | --- | --- |
| client_certificate_password |string| 密码 |


#### 代理设置(Proxy Server):

```
Method:PATCH 
URL: /api/v1/targets/{target_id}/configuration
```
Data:

```

{"proxy": 
    {"enabled":true,
    "address":"127.0.0.1",
    "protocol":"http",
    "port":8080,
    "username":"aaa",
    "password":"bbb"}
}
```

发送参数说明:

| 参数 | 类型 |说明 |
| --- | --- |--- |
| enabled | bool | false/true  |
| address | string | 地址 |
| protocol | string | http  |
| port | int | 端口  |
| username | string | 用户名 |
| password | string | 密码 |

### Advanced设置:

```
Method:PATCH 
URL: /api/v1/targets/{target_id}/configuration
```
Data:

```
{"issue_tracker_id":"",
"technologies":["ASP","ASP.NET"],
"custom_headers":["h4rdy:xxx"],
"custom_cookies":[{"url":"http://baidu.com","cookie":"mycookie=test"}],
"debug":false,
"excluded_hours_id":""}
```


发送参数说明:

| 参数 | 类型 |说明 |
| --- | --- |--- |
| issue_tracker_id | string | issue tracker id  |
| technologies | list | Technologies设置 |
| custom_headers | list | 自定义header |
| custom_cookies | list | 自定义cookie  |
| debug | bool | false/true  |
| excluded_hours_id | string | excluded hours id |

