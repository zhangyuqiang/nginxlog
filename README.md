## nginxlog
Golang解析nginx日志，存入elasticsearch

## usage
- 进入conf目录下将conf.toml.example重命名为conf.toml并完成配置信息

```
[app]
port = ":8090"
pprof = "8091"
debug = true

[elastic]
elastic_url = "elasticsearch地址"
elastic_index = "elasticsearch index"
elastic_type = "elasticsearch type"
elastic_log_path = "./logs"
elastic_log_max_files = 5

[log]
target_path = "日志目录"
tartet_file_prefix = "默认日志文件前缀名称"
```
- 编译为可执行文件: go build -o agent agent.go，然后加入path目录，执行agent即可

## router
```
//状态码查询
api/analysis/status?status=[status]&per_page=[per_page]&page=[page]
//请求方法查询
api/analysis/method?method=[method]&per_page=[per_page]&page=[page]
//top ip访问查询
api/analysis/topIp
```

## script
- division_log.py
日志文件5分钟分割一次