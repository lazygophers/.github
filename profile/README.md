# lazygophers

> 这是一个非常懒惰的 Gopher，他不想写任何关于自己的东西。
>
> 如果你对这个项目感兴趣，这里有一些工具可以帮助你
>

这个项目是一个基于代码生成帮助快速开发 CURD 类的项目，你可以使用它来快速生成代码。

当前阶段，这个项目还在开发中，所以还有很多功能没有实现，如果你有兴趣，可以一起来完善这个项目。

在前期阶段，我们需要一些基本共识：
- 相关工具类将会优先使用本 Orgaization 下的工具
- 代码风格将会优先使用本 Orgaization 下的代码风格
- 生成是基于 protobuf 的，所以你需要了解 protobuf 的基本使用，并且在在你的项目中使用 protobuf 进行接口、接口类型、接口文档的定义
- 为了简化实现，不区分空值（默认值）与未传入的区别，所以在使用时需要注意对空值的处理
- 所有的数据表的类型名都需要以 `Model` 为开头，例如 `ModelUser`，`ModelOrder` 等
- 所有接口的请求、返回类型都需要为 `Req`、`Resp` 结尾，例如 `UserListReq`、`UserListResp` 等
- 常用CURD的命名规则为
    - List: `ListUserReq`、`ListUserResp`
      - List的分页方式先才用offset、limit，后续再考虑更多的分页方式例如cursor、page或者token等方式
        - List的筛选、排序方式优先采用fliter(key:value)的方式，后续再考虑更多的筛选、排序方式
    - Get（依据Id或唯一标识字段进行获取数据）: `GetUserReq`、`GetUserResp`
    - GetBy（依据非唯一标识字段进行获取数据或根据非唯一字符按照一定规则获取）: `GetUserByUsernameReq`、`GetUserByUsernameResp`
    - Create: `AddUserReq`、`AddUserResp`
    - Update: `UpdateUserReq`、`UpdateUserResp`
    - Delete: `DelUserReq`、`DelUserResp`
    - Set: `SetUserReq`、`SetUserResp`

## 使用方式

代码生成工具位于 https://github.com/lazygophers/codegen 下，你可以参考其使用方式。
