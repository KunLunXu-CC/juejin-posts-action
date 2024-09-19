# 在 README 中追加掘金文章列表


## 使用方法

1. 在 `README` 中任意位置添加标志位

```markdown
<!-- posts start -->
<ul>
<li>[3年前] <a href="https://juejin.cn/post/6939698161116479496">仿 Mac 个人网站开发 ｜项目复盘</a></li>
<li>[11月前] <a href="https://juejin.cn/post/7282953307530887179">Markdown 转微信公众号, 又何必借助于其他工具？？</a></li>
<li>[11月前] <a href="https://juejin.cn/post/7291598231954948152">Sharp: 压缩图片用啥 TinyPNG, 我也可以, 而且还免费呢?</a></li>
<li>[10月前] <a href="https://juejin.cn/post/7297790121724641331">什么不支持 transition ? 那是你不知道 @property 好不好？</a></li>
<li>[8小时前] <a href="https://juejin.cn/post/7415914052457349132">OpenWrt 与 Samba：家庭网络文件共享指南</a></li>
<li>[10天前] <a href="https://juejin.cn/post/7411812014047412235">树莓派变身无线路由器 - 终结篇</a></li>
<li>[17天前] <a href="https://juejin.cn/post/7409238250043097100">再战 OpenWrt - 树莓派 SSD 启动</a></li>
<li>[1月前] <a href="https://juejin.cn/post/7401735715782590527">树莓派 - SSD 启动 🛫🛫🛫</a></li>
<li>[1月前] <a href="https://juejin.cn/post/7401773397313077311">Graphql Codegen - 自动生成 TS 类型</a></li>
<li>[3月前] <a href="https://juejin.cn/post/7380694342744735782">NextJS 国际化 - 原生实现</a></li>
</ul>
<!-- posts end -->
```

2. 设置工作流

```yaml
jobs:
  juejin-posts:
    runs-on: ubuntu-latest
    steps:
      # 使用 actions/checkout 拉取仓库, see: https://github.com/actions/checkout
      - name: Checkout
        uses: actions/checkout@v3
        
      # 使用 KunLunXu-CC/juejin-posts-action 生成文章列表, 
      # see: https://github.com/KunLunXu-CC/juejin-posts-action
      - name: Append Juejin Posts List🔧
        uses: KunLunXu-CC/juejin-posts-action@main
        with: 
          user_id: "4459274891717223"
  
      # 使用 EndBug/add-and-commit 提交代码, see: https://github.com/EndBug/add-and-commit
      - name: Push to GitHub
        uses: EndBug/add-and-commit@v9
        with:
          branch: main
          default_author: github_actions
          message: 'juejin-posts'
```

## 本地开发

1. 安装依赖

```sh
npm i
```

2. 执行 test 脚本

```sh
npm run test
```

3. 执行结果: 执行 `npm run test` 后将在上文注入目录

4. 编译

```sh
npm run build
```

5. 修改版本号

6. 提交代码