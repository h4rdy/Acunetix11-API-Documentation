## Reports



### 获取所有扫描报告

```
Method:GET 
URL: /api/v1/reports
```


返回参数说明:

| 参数 | 说明 |
| --- | --- |
| generation_date | 生成时间 |
| template_type | 模板类型 |
| report_id | 报告id |
| template_name | 模板名字 | 
| status | 状态 |
| template_id | 模板id | 
| download | 下载链接[html, pdf] |
| source | 来源 |
| description | 备注 |



### 生成扫描报告

```
Method:POST 
URL: /api/v1/reports
```

Data:

```

{"template_id":"11111111-1111-1111-1111-111111111119",
"source":{
    "list_type":"scan_result",
     "id_list":["f2985648-da9e-430a-830b-f1bf34d9c4f2"]
     }
}
```



返回参数说明:

| 参数 | 类型 | 说明 |
| --- | --- |--- |
| template_id|String| 扫描报名模板类型 |
| list_type |String | 值为: scans / targets|
| id_list | String |  值为: scan_id / target_id |

template_id:

| 类型 | 值 |
| --- | --- |
| Affected Items | 11111111-1111-1111-1111-111111111115 |
| CWE 2011 |  11111111-1111-1111-1111-111111111116 |
| Developer  | 11111111-1111-1111-1111-111111111111 |
| Executive Summary | 11111111-1111-1111-1111-111111111113|
| HIPAA | 11111111-1111-1111-1111-111111111114 |
| ISO 27001 | 11111111-1111-1111-1111-111111111117 |
| NIST SP800 53 | 11111111-1111-1111-1111-111111111118 |
| OWASP Top 10 2013 | 11111111-1111-1111-1111-111111111119 |
|PCI DSS 3.2|11111111-1111-1111-1111-111111111120|
|Quick|11111111-1111-1111-1111-111111111112|
|Sarbanes Oxley|11111111-1111-1111-1111-111111111121|
|Scan Comparison|11111111-1111-1111-1111-111111111124|
|STIG DISA|11111111-1111-1111-1111-111111111122|
|WASC Threat Classification|11111111-1111-1111-1111-111111111123|




