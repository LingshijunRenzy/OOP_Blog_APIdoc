# 猫鼠小窝博客 API 文档

## 目录

1. 用户相关接口

2. 文章相关接口

3. 评论相关接口

## 用户相关接口

### 获取用户信息

- 请求方式：GET
- 请求 URL：/api/user
- 请求参数：
  - userID: 用户 ID
- 返回参数：
  - code: 状态码
  - data: 用户信息
    - nickname: 用户昵称
    - avatar: 用户头像
    - email: 用户邮箱
    - introduction: 用户个人简介
    - signature: 用户个性签名
    - createTime: 用户创建时间
    - updateTime: 用户更新时间
    - articleCount: 用户文章数
    - commentCount: 用户评论数
    - likeCount: 用户获赞数
    - followCount: 用户关注数
    - fansCount: 用户粉丝数
    - isAdmin: 是否为管理员
- 返回示例：
  ```json
  {
    "code": 200,
    "data": {
      "nickname": "猫鼠小窝",
      "avatar": "https://www.maoshuxiaowo.com/avatar.jpg",
      "email": "123456@123.com",
      "introduction": "这是一个猫鼠小窝博客的用户",
      "signature": "这是一个猫鼠小窝博客的用户",
      "createTime": "2021-01-01 00:00:00",
      "updateTime": "2021-01-01 00:00:00",
      "articleCount": 10,
      "commentCount": 20,
      "likeCount": 30,
      "followCount": 40,
      "fansCount": 50,
      "isAdmin": true
    }
  }
  ```

### 获取用户个性设置

- 请求方式：GET
- 请求 URL：/api/user/setting
- 请求参数：
  - userID: 用户 ID
- 返回参数：
  - code: 状态码
  - data: 用户个性设置
    - theme: 用户主题
    - isShowComment: 是否显示评论
    - isShowLike: 是否显示点赞
    - isShowFollow: 是否显示关注
    - isShowFans: 是否显示粉丝
    - isShowArticle: 是否显示文章

- 返回示例：
  ```json
  {
    "code": 200,
    "data": {
      "theme": "light",
      "isShowComment": true,
      "isShowLike": true,
      "isShowFollow": true,
      "isShowFans": true,
      "isShowArticle": true
    }
  }
  ```

### 获取用户文章列表
- 请求方式：GET
- 请求 URL：/api/user/article
- 请求参数：
  - userID: 用户 ID
  - page: 页码
  - pageSize: 每页数量
- 返回参数：
    - code: 状态码
    - data: 文章列表
        - articleID: 文章 ID
        - title: 文章标题
        - summary: 文章摘要
        - cover: 文章封面
        - createTime: 文章创建时间
        - updateTime: 文章更新时间
        - likeCount: 文章点赞数
        - commentCount: 文章评论数
        - viewCount: 文章浏览数
        - isTop: 是否置顶
        - isPublish: 是否发布

- 返回示例：
    ```json
    {
        "code": 200,
        "data": [
        {
            "articleID": 1,
            "title": "文章标题",
            "summary": "文章摘要",
            "cover": "https://www.maoshuxiaowo.com/cover.jpg",
            "createTime": "2021-01-01 00:00:00",
            "updateTime": "2021-01-01 00:00:00",
            "likeCount": 10,
            "commentCount": 20,
            "viewCount": 30,
            "isTop": true,
            "isPublish": true
        }
        ]
    }
    ```

### 获取用户评论列表

- 请求方式：GET
- 请求 URL：/api/user/comment
- 请求参数：
  - userID: 用户 ID
  - page: 页码
  - pageSize: 每页数量
- 返回参数：
    - code: 状态码
    - data: 评论列表
        - commentID: 评论 ID
        - articleID: 文章 ID
        - content: 评论内容
        - createTime: 评论创建时间
        - likeCount: 评论点赞数
        - isPublish: 是否发布

- 返回示例：
    ```json
    {
        "code": 200,
        "data": [
        {
            "commentID": 1,
            "articleID": 1,
            "content": "评论内容",
            "createTime": "2021-01-01 00:00:00",
            "likeCount": 10,
            "isPublish": true
        }
        ]
    }
    ```

### 获取用户点赞列表
- 请求方式：GET
- 请求 URL：/api/user/like
- 请求参数：
  - userID: 用户 ID
  - page: 页码
  - pageSize: 每页数量
- 返回参数：
    - code: 状态码
    - data: 点赞列表
        - likeID: 点赞 ID
        - articleID: 文章 ID
        - createTime: 点赞时间
