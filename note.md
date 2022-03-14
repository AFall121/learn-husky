# make some notes

### Steps

### initial repo

    mkdir learn-husky && cd learn-husky
    npm/yarn init --yes
    git init
    #touch .gitignore
    #config .gitignore
    echo {}> .prettierrc.json
    #touch & config .prettierignore
    #touch .eslintrc.json with eslint command
    npx eslint --init
    #or below code npm init @eslint/config
    #or use yarn yarn create @eslint/config

### Install

    npm/yarn -D prettier eslint husky lint-sta

### RUN SOME COMMANDS

    npx prettier --check .
    npx prettier --write .
    npx eslint --fix .

### about husky && lint-staged

    在package.json中配置如下，当git提交到仓库经过钩子函数pre-commit时，会调用lint-staged脚本，lint-staged会检查相关的格式，并用prettier修复，当然你也可以传入eslint等去修复

<!-- 旧的没什么用 -->

```json
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged"
    }
  },
  "lint-staged": {
    "src/**/*.{js,jsx,ts,tsx,json,css,scss,md}": [
      "prettier --write"
    ]
  }
```

<!-- 新的直接用命令 -->

npx mrm@2 lint-staged
参考 prettier 官网https://prettier.io/docs/en/precommit.html
执行命令后会生成一个.husky 和其下面的一些子文件

```json
  "lint-staged": {
    "*.js": "eslint --cache --fix",
    "*.{js,jsx,ts,tsx,json,css,scss,md,html}": "prettier --write"
  },
```

本项目 package.json 这里我把 eslint 一行去掉了

### prettier && eslint

    由于eslint和prettier有时会发生冲突（rules可能设置不一样，所以最好用eslint-plugin-prettier去取代prettier
