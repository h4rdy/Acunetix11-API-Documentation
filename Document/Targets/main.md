##  Targets

### 所有目标信息:

```
Method:GET 
URL: /api/v1/targets
```

返回参数说明:

| 参数 | 说明 |
| --- | --- |
| pagination | 分页信息 |
| targets | 目标详细信息 |

targets:

| 参数 | 说明 |
| --- | --- |
| criticality | 分页信息 |
| last_scan_session_status | 最后一次扫描状态 |
| target_id | 目标id  |
| last_scan_id | 最后一次扫描id |
| last_scan_session_id | 最后一次扫描session id |
| continuous_mode | 是否连续模式 |
| last_scan_date | 最后一次扫描时间 |
| manual_intervention | 是否手动干预 |
| threat | 威胁等级 |
| severity_counts | 漏洞等级个数分布 |
| description | 备注 |
| address | 扫描目标网址 |

### 筛选目标信息接口:

```
Method:GET 
URL: /api/v1/targets?q=threat:{list};criticality:{list};group_id:{string};text_search:*{string}
```

Demo: 

```
/api/v1/targets?q=threat:3;criticality:10,20;text_search:*h4rdy.me
```

发送参数说明:

| 参数 | 类型 |说明 |
| --- | --- |--- |
| threat | int | 威胁等级;高->低:[3,2,1,0]  |
| criticality | int | 危险程度;高->低:[30,20,10,0] |
| group_id | string | 分组id |
| last_scanned| |最后一次扫描时间(默认不传该参数) |
| text_search | string | 筛选内容 |

返回参数说明:
同 [所有目标信息]

### 添加目标接口:

```
Method:POST 
URL: /api/v1/targets
```

Data:

```
{"address":"http://wiki.h4rdy.me","description":"xxxx","criticality":"10"}
```

发送参数说明:

| 参数 | 类型 |说明 |
| --- | --- |--- |
| address | string | 目标网址:需http或https开头 |
| criticality | Int | 危险程度;范围:[30,20,10,0];默认为10|
| description | string | 备注 |

返回参数说明:

| 参数 |说明 |
| --- | --- |
| address | 目标网址 |
| criticality |  危险程度|
| description |备注 |
| target_id | 目标id |

