## 命名
| 命名分类 | 描述 |
| ------ | ------ |
| 文件夹 | 默认为小写，若为英文缩写，可使用大写英文字母，多个单词件使用中划线 - 间隔，尽可能采用有意义的英文命名方式 |
| HTML文件 | 小写英文字母，多个单词使用中划线 - 间隔，如 list-details.html |
| CSS文件 | 小写英文字母，多个单词使用点 . 间隔，如 main.min.css |
| JavaScript文件 | 小写英文字母，多个单词使用点 . 间隔，如 dateformat.min.js |
| .vue文件 | 使用帕斯卡命名，如 App.vue |
| .jsx文件 | 使用帕斯卡命名，如 App.jsx |
| 图片文件 | 小写英文字母，以类型前缀加自定义名命名，多个单词使用下划线 _ 间隔，如 bg_main.png |

## 项目结构
    [jq-example]            /* 系统根目录 */
    |--README.md            /* 项目说明markdown */
    |--src                  /* 项目源码文件夹 */
        |--css              /* css文件夹 */
        |--favicon.ico      /* 系统icon */
        |--fonts            /* 字体文件夹 */
        |--img              /* 存放固定图片文件，如网站icon */
        |--images           /* 存放不固定图片文件，如banner图 */
        |--index.html       /* 包括其他页面，必要时归类放入不同文件夹 */
        |--js               /* js封装函数文件夹 */
        |--json             /* 本地数据文件夹 */
        |--plugins          /* 插件文件夹 */
    |--test                 /* 测试文件夹 */

---

    [spa-example]           /* 系统根目录 */
    |--dist                 /* 打包文件夹 */
    |--node_modules         /* 包文件夹 */
    |--package.json         /* 包管理文件 */
    |--README.md            /* 项目说明markdown */
    |--src                  /* 项目源码文件夹 */
        |--App.vue          /* vue项目主组件，非vue项目忽略 */
        |--assets           /* 资源文件夹 */
        |--components       /* 组件文件夹 */
        |--css              /* css文件夹 */
        |--favicon.ico      /* *系统icon*v */
        |--index.html       /* html模板 */
        |--js               /* js封装函数文件夹 */
        |--main.js          /* 项目入口文件 */
        |--pages            /* 页面文件夹 */
        |--router           /* 路由文件夹 */
        |--store            /* store文件夹 */
    |--test                 /* 测试文件夹 */
    |--webpack.config.js    /* webpack配置文件 */