# GO-WEB

## 项目规范

### API规范 
[Restful](http://kaelzhang81.github.io/2019/05/24/Restful-API%E8%AE%BE%E8%AE%A1%E6%9C%80%E4%BD%B3%E5%AE%9E%E8%B7%B5/)
- URL
```
一类资源两个URL

# 资源集合：
/epics
# 资源元素：
/epics/5

定制有效载荷大小
GET /stories?include=subTasks
``` 
- HTTP Method
```
增（POST：非幂等性）: 使用POST方法创建新的资源。
删（DELETE：幂等性）: 使用DELETE方法删除存在的资源。
改（PUT：幂等性）: 使用PUT或PATCH方法来更新已存在的资源。
查: 使用GET方法读取资源。（GET：幂等性）
```
- HTTP 状态码
``` 
200: Success 成功
304: Not Modified 未修改
400: Bad Request 客户端请求语法错误
401: Unauthorized 未授权
403: Forbidden 禁止访问
404: Not Found 资源无法找到
429: Too Many Requests 客户端的请求次数超过限额
500: Internal Server Error 服务器错误
503: Service Unavailable 系统维护
```

- 返回值结构
错误示例:
```json
{
  "code": 1001,
  "msg": "数据更新失败",
}
```
成功示例：
```json
{
  "code": 0,
  "msg": "ok",
  "data": {

  }
}
```

### Git提交规范
- feat：新功能（feature）
- fix：修补bug
 -docs：文档（documentation）
- style： 格式（不影响代码运行的变动）
- refactor：重构（即不是新增功能，也不是修改bug的代码变动）
- test：增加测试
- chore：构建过程或辅助工具的变动

## 目录结构

```
.
├── web
│   ├──conf: 配置
│   ├──dao: 数据访问层
│   ├──library: 公共库
│   ├──models: 数据模型
│   ├──server
│   │   └── http: 提供Restful api
│   └───service: 提供服务
│
└── vendor: 项目所需外部包
```

### License
© Jiangyang, 2020~time.Now

Released under the Apache [License](https://github.com/comeonjy/go-web/blob/master/LICENSE)