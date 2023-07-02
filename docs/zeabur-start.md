<img width="678" alt="image" src="https://github.com/xxouu/midjourney-proxy/assets/13233172/ae0c6b7e-7b11-4f09-9b5b-41d8f4079cb5">## Zeabur 部署教程

### Zeabur 优势
1. 新注册的 `Github` 账号可能无法使用 `Railway`，但是能用 `Zeabur`
2. 通过 `Railway` 部署的项目会自动生成一个域名，然而因为某些原因，形如 `*.up.railway.app` 的域名在国内无法访问
3. `Zeabur` 服务器运行在国外，但是其生成的域名 `*.zeabur.app` 没有被污染,国内可直接访问

### 开始部署

1. 打开网址 https://zeabur.com/zh-CN 
2. 点击现在开始
3. 点击 `Sign in with GitHub`
4. 登陆你的 `Github` 账号
5. 点击 `Authorize zeabur` 授权
7. <img width="678" alt="image" src="https://github.com/xxouu/midjourney-proxy/assets/13233172/882aa4eb-a2a1-43ef-8c1e-2b9164e5c468">
6. 
7. 点击 `创建项目` 并输入一个项目名称，点击 `创建`
<img width="677" alt="image" src="https://github.com/xxouu/midjourney-proxy/assets/13233172/d65e7f87-f7d5-4d3f-8846-4d9956e7fde9">
<img width="875" alt="image" src="https://github.com/xxouu/midjourney-proxy/assets/13233172/42b6c9fc-3d6a-4f16-8fdc-62f1caab697a">
<img width="634" alt="image" src="https://github.com/xxouu/midjourney-proxy/assets/13233172/1c1a74b3-d566-41e0-a919-b723e36ec9b6">
<img width="675" alt="image" src="https://github.com/xxouu/midjourney-proxy/assets/13233172/9a1e6c58-a2d2-4552-9abf-f8fd3309dfb8">

8. 点击 `+` 添加服务，选择 `Git-Deploy service from source code in GitHub repository.`
9. 点击 `Configure GitHub` 根据需要选择 `All repositories` 或者 `Only select repositories`
10. 点击 `install`，之后自动跳转，最好再刷新一下页面
11. 点击 你 fork 的 `midjourney-proxy` 项目
12. <img width="1247" alt="image" src="https://github.com/xxouu/midjourney-proxy/assets/13233172/6a6f7d7c-a216-47c4-8398-625473d9d0d5">

13. 点击环境变量，点击编辑原始环境变量，添加你需要的环境变量
14. 关于环境变量，与 `Railway` 稍有不同，需要把 `.` 和 `-` 全部换成 `_`，例如如下格式
    ```properties
    PORT=8080
    mj_discord_guild_id=xxx
    mj_discord_channel_id=xxx
    mj_discord_user_token=xxx
    mj_api_secret=***
    ```
    此处配置项参考 [Wiki / 配置项](https://github.com/novicezk/midjourney-proxy/wiki/%E9%85%8D%E7%BD%AE%E9%A1%B9) ，建议配置api密钥启用鉴权，接口调用时需添加请求头 `mj-api-secret`
15. 然后取消 `Building`，点击 `Redeploy` (此做法是为了让环境变量生效)
16. 部署 `midjourney-proxy` 大概需要 `2` 分钟，此时你可以做的是：配置域名
17. 点击下方的域名，点击生成域名，输入前缀，例如 `midjourney-proxy-demo`，点击保存；或者添加自定义域名，之后加上 `CNAME` 解析
18. 等待部署成功，访问 `https://midjourney-proxy-demo.zeabur.app/mj`
