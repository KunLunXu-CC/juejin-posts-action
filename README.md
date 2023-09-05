# 在 README 中追加掘金文章列表


## 使用方法

1. 在 `README` 中任意位置添加标志位

```markdown
<!-- posts start -->
这里会插入生成的文章列表
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