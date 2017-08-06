## Dashboard


### 信息接口:

```
Method:GET 
URL: /api/v1/info
```
返回参数说明:

| 参数 | 说明 |
| --- | --- |
| update_info | 更新信息 |
| license | 授权信息 |
| major_version | 主要版本号 |
| minor_version | 小版本号 |
| build_number | 创建时间 |

### 账户信息:

```
Method:GET 
URL: /api/v1/me
```

返回参数说明:

| 参数 | 说明 |
| --- | --- |
| first_name | 当前账户名 |
| user_id | 当前用户id |
| email | Email地址 |
| enabled |  当前账户是否启用 |
| child_account |  是否子账户 |
| su | 是否最高权限 |



### Dashboard信息:

```
Method:GET 
URL: /api/v1/me/stats
```

返回参数说明:

| 参数 | 说明 |
| --- | --- |
| most_vulnerable_targets | 最脆弱的目标 |
| scans_waiting_count | 等待扫描个数|
| targets_count | 目标数 |
| scans_running_count |  正在扫描的个数 |
| scans_conducted_count |  总进行扫描个数 |
| vuln_count | 发现漏洞等级的分布个数 |
| vuln_count_by_criticality | 通过危险程度进行漏洞等级个数分布 |
| critical |  / |
| low |  / |
| top_vulnerabilities | 排名靠前漏洞分布 |
| vulnerabilities_open_count | 共发现漏洞总数 |

