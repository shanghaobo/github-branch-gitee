# github-branch-gitee
GithubAction同步Github指定分支到Gitee

## 示例

```
name: Demo
on: [push]
jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
    - name: checkout
      uses: actions/checkout@master

    - name: Async Github Branch To Gitee
      uses: shanghaobo/github-branch-gitee@master
      with:
        github_repo: shanghaobo/test-async
        github_branch: test
        gitee_repo: shanghaobo/test-async2
        gitee_branch: master
        username: ${{ secrets.GITEE_USERNAME }}
        password: ${{ secrets.GITEE_PASSWORD }}
```

- `github_repo`：Github 仓库名
- `github_branch`：Github 分支名
- `gitee_repo`：Gitee 仓库名
- `gitee_branch`：Gitee 分支名
- `username`：Gitee 账号，用于登录
- `password`：Gitee 密码，用于登录
- 注意：密码需要以 [Secrets](https://docs.github.com/cn/actions/reference/encrypted-secrets) 方式给出，以保证密码不被泄露


