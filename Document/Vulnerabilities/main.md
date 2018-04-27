##  Vulnerabilities



### 获取所有漏洞信息

```
Method:GET 
URL: /api/v1/vulnerabilities?q=status:{status}
```

status: 默认为open 

| 值 | 说明 |
| --- | --- |
| open | 公开  |
| fixed | 已修复 |
| ignored | 已忽略 |
| false_positive | 误报 |
| !open | 不公开 |


返回参数说明:

| 参数 | 说明 |
| --- | --- |
| pagination | 页码信息 |
| vulnerabilities | 漏洞信息 |

### 条件筛选漏洞信息

```
Method:GET 
URL: /api/v1/vulnerabilities?q=severity:{int};criticality:{int};status:{string};cvss_score:{logic expression
};cvss_score:{logic expression
};target_id:{target_id};group_id:{group_id}
```

### 获取单个漏洞信息

说明: 此处的vuln_id 应是根据本模块中获取全部漏洞信息中得到的vuln_id, 不能将scans模块得到的vuln_id传入,否则无法获取到漏洞信息.

```
Method:GET 
URL: api/v1/vulnerabilities/{vuln_id}
```




