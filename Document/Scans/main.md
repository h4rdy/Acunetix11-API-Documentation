## Scans


### 添加扫描:

```
Method:POST
URL: /api/v1/scans
```

Data:

```
{
"target_id":"64496c9e-b340-4227-90d4-ac43e78d4a0d",
"profile_id":"11111111-1111-1111-1111-111111111112",
"schedule":    
      {"disable":false,
       "start_date":null,
       "time_sensitive":false
       }
}

```

发送参数说明:

| 参数 | 类型 |说明 |
| --- | --- |--- |
| target_id | String | 目标id |
| profile_id | String | 扫描类型 |
| schedule | Json | 扫描时间设置(默认即时) |
| report_template_id | String | 扫描报告类型(可不传) |
| ui_session_id | String | 可不传 |

附profile_id值对照表:

| 类型 | 值 |
| --- | --- |
| Full Scan | 11111111-1111-1111-1111-111111111111 | 
| High Risk Vulnerabilities | 11111111-1111-1111-1111-111111111112 |
| Cross-site Scripting Vulnerabilities | 11111111-1111-1111-1111-111111111116 | 
| SQL Injection Vulnerabilities | 11111111-1111-1111-1111-111111111113 | 
| Weak Passwords | 11111111-1111-1111-1111-111111111115 | | Crawl Only | 11111111-1111-1111-1111-111111111117 | 

### 删除扫描:

```
Method:DELETE
URL: /api/v1/scans/{scan_id}
```

### 获取所有扫描状态:

```
Method:GET 
URL: /api/v1/scans
```

返回参数说明:

| 参数 | 说明 |
| --- | --- |
| profile_id | 扫描类型id |
| target | 目标详细信息 |
| report_template_id | 扫描报告类型 |
| current_session | 当前状态 |
| criticality |  危险程度 |
| schedule | 扫描时间设置 |
| next_run | 下次扫描时间 |
| profile_name | 扫描类型 |
| scan_id | 扫描id |
| target_id | 目标id |


current_session:

| 参数 | 说明 |
| --- | --- |
| threat | 威胁等级 |
| progress | 新增 |
| scan_session_id | scan_session_id |
| status | 扫描状态 |
| severity_counts | 漏洞等级分布 |
| event_level | 事件等级 |
| start_date | 开始时间 |




### 获取单个扫描状态:

```
Method:GET 
URL: /api/v1/scans/{scan_id}

```

返回参数说明:

| 参数 | 说明 |
| --- | --- |
| profile_id | 扫描类型id |
| target | 目标详细信息 |
| report_template_id | 扫描报告类型 |
| current_session | 当前状态 |
| criticality |  危险程度 |
| schedule | 扫描时间设置 |
| next_run | 下次扫描时间 |
| profile_name | 扫描类型 |
| scan_id | 扫描id |
| target_id | 目标id |



### 单个扫描概况信息:

```
Method:GET
URL: /api/v1/scans/{scan_id}/results/{scan_session_id}/statistics

```

### 单个扫描漏洞结果:

```
Method:GET
URL: /api/v1/scans/{scan_id}/results/{scan_session_id}/vulnerabilities

```

### 获取当前扫描单个漏洞信息

```
Method: GET
URL: /api/v1/scans/{scan_id}/results/{scan_session_id}/vulnerabilities{vuln_id}
```

返回参数说明:

|参数|说明|
| --- | --- |
| affects_detail | 影响细节 |
| affects_url | 受影响链接 |
| criticality | 危险程度 |
| cvss2 | cvss2信息 |
| cvss3 | cvss3信息 |
| cvss_score | cvss 评分 |
| description | 漏洞描述 |
| details | 漏洞细节 |
| impact | 影响 |
| loc_id | loc id |
| long_description | 更多描述 |
| recommendation | 整改意见 |
| references | 来源 |
| request | 请求头信息 |
| severity | 漏洞等级(0-3) |
| source | 来源 |
| status | 漏洞状态 |
| tags | 标签 |
| target_id | 目标ID |
| vt_id | vt_id |
| vt_name | 漏洞名字 |
| vuln_id | 该次扫描中的漏洞ID |

