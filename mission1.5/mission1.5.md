# 代码规范

使用 [ESLint](https://eslint.org/) 来规范代码，推荐风格如下：

1. 字符串使用单引号
1. 分号只在必要的地方加，如果一个语句或表达式的结尾可加可不加，则不加分号
   - 不是每条语句都必须加分号，自行了解 ESI(Automatic semicolon insertion)
1. 提交到 git 的代码统一换行符为 \n，不是 \r\n，也不是\r
   - 注意编辑器也要同步设置
   - 也可以配置 git，让其自动转换

接下来动手操作一下，在工作目录下打开命令行，输入以下命令：

```
$ npm i eslint eslint-plugin-import eslint-config-airbnb-base  -D
$ npx eslint --init
```

不出意外会与命令行进行交互式：

```
? How would you like to use ESLint? To check syntax, find problems, and enforce code style
? What type of modules does your project use? JavaScript modules (import/export)
? Which framework does your project use? None of these
? Where does your code run? Browser, Node
? How would you like to define a style for your project? Answer questions about your style
? What format do you want your config file to be in? JavaScript
? What style of indentation do you use? Tabs
? What quotes do you use for strings? Single
? What line endings do you use? Unix
? Do you require semicolons? No
? What format do you want your config file to be in? JavaScript
```

命令执行后会生成一个规则配置文件，咱们再稍微修改一下

- 将 extends 改为 airbnb-base，比起 eslint:recommended，这个 preset 更加严格
- 在 rules 里加上 'no-tabs': 0 和 'no-console': 'off'

最后的文件如下

```js
module.exports = {
  env: {
    browser: true,
    es6: true,
    node: true,
  },
  extends: 'airbnb-base',
  globals: {
    Atomics: 'readonly',
    SharedArrayBuffer: 'readonly',
  },
  parserOptions: {
    ecmaVersion: 2018,
    sourceType: 'module',
  },
  rules: {
    'no-tabs': 0,
    indent: ['error', 'tab'],
    'linebreak-style': ['error', 'unix'],
    quotes: ['error', 'single'],
    semi: ['error', 'never'],
    'no-console': 'off',
  },
};
```

记得在编辑器上安装相应的 ESLint 插件，不然你会发现编辑器中刚刚设置的 ESLint 没有生效

如果发现某些语句违反了规范，但是开发者确认没有问题的，可以将相应的规则 disable 掉：[具体做法](https://eslint.org/docs/user-guide/configuring#disabling-rules-with-inline-comments)
