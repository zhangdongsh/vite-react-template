参考文章：https://juejin.cn/post/7101596844181962788#heading-20

## vscode

配置推荐的 vscode 插件，配置 vscode 的基础设置。保存自动修复 js、css 等
新增 .vscode 配置

## editorconfig

规范本项目中文件的缩进风格，和缩进空格数等，会覆盖 vscode 的配置，来达到不同编辑器中代码默认行为一致的作用
vscode 插件：EditorConfig for VS Code
新增.editorconfig 配置文件

## Prettier

vscode 插件：Prettier - Code formatter
新增 .prettierrc.js 配置文件

## Eslint

## Stylelint

## lint-staged

只检测 git 暂存区文件

```
"lint-staged": {
  "src/**/*.{ts,tsx}": [
    "npm run eslint"
  ]
},
```

## tsc

ts 类型检测
"build": "tsc && vite build",

## husk

1、npx husky install 生成 .husky 配置文件夹

2、npx husky add .husky/pre-commit 'npm run xxx'，会在 .husky 目录下生成 pre-commit 文件，每次 commit 执行对的 script 脚本

3、husky 生效需要手动执行 husky install，可以借助 package.json 里面的 postintall 钩子实现这个功能，该钩子会在依赖安装完成后执行，在 package.json 里面添加

```
"scripts": {
    "postinstall": "husky install"
}
```

## commitlint

git 提交信息规范
npx husky add .husky/commit-msg 'npx --no-install commitlint --edit "$1"' 在 .husky 目录下生成 commit-msg 文件，并且配置 commitlint 命令对提交信息进行验证配置

## commitizen

git cz 替代 git commit
命令行配置提交信息
package.json

```
"config": {
    "commitizen": {
        "path": "./node_modules/cz-customizable"
    }
}
```
