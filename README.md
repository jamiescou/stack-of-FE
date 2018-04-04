# stack-of-FE
# 2018年前端技术栈

如果项目要求支持低版本的 IE 的话（比如 IE7，8），就用较传统的jQuery，Bootstrap，jQuery插件/组件以及类似 Knockout.js 能够提供数据绑定的 JS 库，再加上 require.js + gulp 或者 fis3 做模块化和自动化构建。

如果不需要支持低版本 IE 的话，我们主要使用 React：

React – 编写页面组件

Redux – 数据流和状态管理，一般结合 redux-saga 使用

React-router v4 – 前端路由管理（Note：dva 整合了 redux, redux-router 以及 redux-saga。在熟悉了基本的 Redux, Redux-saga, Redux-router 的使用之后，可以尝试用 dva 替代）

Webpack – 前端构建工具

前端开发我在用到的其他类库，技术选择和工具还包括：

SCSS – CSS 预处理，提供 Variables, Mix-in 等功能

ESLint – JavaScript 代码质量工具，之前使用 airbnb 配置方案，现在使用 standard 配合方案

StyleLint – CSS/SCSS/Less 代码质量工具

EditorConfig – 统一编辑器配置

git – 版本控制工具，结合 git-flow 做分支管理

oh-my-zsh – 提高终端操作效率

Ant Design – React 组件库，适合中后台应用开发，极大提高开发效率。另外一个可以参考的是 Material UI，是 Google Material Design 的 React 实现。

Ant Design Pro – 基于 Ant Design 的中后台项目脚手架，提供了更高层的常用业务组件和最佳实践，大大减少重复性工作

Animate.css – 流行的动画样式库，实现了包括 Attention（吸睛？），Bouncing（弹跳），Fading（淡入/淡出），Flippers（翻转），Lightspeed（光速？），Rotating（旋转），Sliding（滑动），Zoom（缩放）等各种动效。

Alloy Touch – 丝般顺滑的触摸运动方案（官方原文），支持缓动效果，使用了 matrix-3D（transformjs），requestAnimationFrame 以及针对 touchmov 事件的优化（{ passive: false, …}），体验与原生非常接近。同时支持各种触控场景：2D/3D 旋转，翻页，步进。我还用它实现了无限滑动的效果。还有一个非常流行的 swiper（ nolimits4web/swiper ），但是我没有用过。不知道跟 Alloy touch 的区别。

AutoPrefixer – PostCSS 插件，构建时根据 caniuse-lite 数据库以及你设置的或者默认的浏览器列表（browserslist）给 CSS 属性自动增加浏览器厂商前缀。一般结合 gulp 或者 webpack 等 Task runner 使用。这样我们写 CSS 样式的时候只需要写纯 CSS 而不需要考虑厂商前缀的问题。

Async Flow Control – JavaScript 的异步流程控制，大概经历了 callback -> Async.js -> Promise(bluebird -> 原生 Promise 支持) -> yield/generator -> async/await(ES7) 这样一个过程。推荐 async/await + promise 的解决方案，Node.js 现在(8+)也可以用 Util.promisify() 对原先的 callback API 进行封装成 Promise。

Axios – 基于 Promise 的 HTTP 客户端，可以运行于浏览器和 Node.js 环境。我主要是在 Node.js 中使用 Axios，替代了 request；浏览器中还是使用 Fetch API，还没有在浏览器中尝试使用 Axios。

Babel + ES6/6+ – 现代 JavaScript 语法和编译器，Babel 可以让你使用目前主流浏览器尚未全面支持的新的 JavaScript 语法来编写代码，同时帮你编译成现代浏览器都支持的 ES5 语法，还提供了一些 polyfill （通过 core.js）实现了浏览器不支持的 feature。

Ava, Chai.js, Jest, Enzyme, Headless Chrome – 测试框架，runner，断言库，单元测试，组件测试，端对端测试的一些工具。我用 Ava 替代了 Mocha 用来做测试框架和 Runner，Headless Chrome 替代了 PhantomJS 做端对端测试，断言主要用 Chai 里面的 expect 以及 jsonschema 等 Chaijs插件。

CSS Modules – CSS 模块化方案，避免全局作用域/冲突，实现显式依赖。暂时没有使用 css-in-js 方案。

Data Visualization – 数据可视化和一些图表工具，使用最多的还是 ECharts，支持各种图表，交互和渲染模式，PC 端移动端通吃，文档很全，最近还成为了 Apache 孵化项目。另外还用过 g2，感觉也不错，现在也能看到源码了。g2 是 grammer of graphic 的缩写，算是 g2 的理论基础。自己从基础做起的话，可以使用 d3.js，提供了可视化的很多基础模块，基于 SVG。

Docker – 嗯，前端应用部署也可以使用 docker，基于 Nginx image 或者 Node.js image。我以前写过一个构建 docker 的 shell 脚本： 分享一个自动构建 docker 并导出 image 的 shell 脚本

esprima, espree, acorn, babel-parser – 进行 JS/JSX 语法解析和句法分析的 JS 库。espree 是 ESLint 使用的 parser，最初 fork 自 Esprima，后来基于 Acorn。Esprima 是最老牌的 js parser，现在使用 TypeScript 实现；Acorn 使用 ES6，特点是模块化，但是 Esprima 的文档比 Acorn 相对要全一些。babel-parser 的解析器 fork 自 Acorn。

Express.js/Koa2/Egg.js/Strongloop – Express 和 Koa 都是 Node.js 的 Web 框架，主要用来实现 API 网关，也可以 serve 一些静态内容。我用过时间最长的是 Express, koa2 也在几个项目中用过，也了解过 loopback, hapi, kraken 等。推荐直接使用 Egg 或者 Strongloop 这种封装了最佳实践的企业级 Node.js 框架，而不是自己基于 express 或者 koa 攒一堆组件。

Functional Programming – 函数式编程，这个真的是前端流行… 还有纯函数，pure render, pure component，immutable 等概念。参考：lodash 中的 FP 实现。嫌 immutable.js 太重可以试试 immer。

GraphQL/thrift/RESTful API/OpenAPI – 各种接口方案。REST 有一种明日黄花的感觉，虽然还在用，但是感觉早晚被 GraphQL 等取代，毕竟我们真的越来越不关心数据是如何获取的，而应该关注在 store 如何设计上，专注在领域分析上面。Thrif 支持跨语言 RPC 调用，比如跨 Node.js 和 Java 等。嗯，Thrif 支持自动生成桩代码，什么定接口、JSON、MOCK 就都是浮云了，不需要纠结是否符合 RESTful 规范了。NOTE：Github 提供的 API 之前是 RESTful 的，现在都是 GraphQL 了。

Homebrew – MAC 软件包管理工具，brew 相当于 Ubuntu 的 apt，RedHat/CentOS 的 yum。

lodash/moment.js – 最常用的两个 JS 库了，lodash 是一个现代、高效、模块化的 JS 功能包，moment.js 主要用来处理日期时间相关的操作。都是即可运行在浏览器环境，也可以运行在 Node.js 环境。

MongoDb/MySQL/Nginx/Redis – 这些都是常用的服务器应用。MongoDB 使用 mongoose，MySQL 使用 sequelizer（都是非常优秀的 Node.js 的 ORM 实现），Nginx 会配置反向代理，URL 重写，缓存设置等即可。

npm/yarn – 包管理工具。我倾向于还是使用 npm，搞清楚 npm 的常用 script；搞清楚npm install 时候依赖安装的流程，以及 package-lock 的作用；能维护和发布自己的 npm 包；知道 npx 是干什么的就可以了。

Performance – 前端性能，善用 Chrome Devtool 中的各种功能，包括 lighthouse。

PostCSS – 本身是一个 CSS 的 parser，最早是从 AutoPrefixer 中抽取出来的，现在已经是 CSS 的瑞士军刀了。可以结合 gulp, Webpack 等 task runner 使用，能够解析 CSS/SCSS/Less 等各种语法，提供了 AutoPrefixer（加浏览器前缀）, cssnano（各种严压缩，各种配置）, cssnext（用未来的 CSS 语法规范写当前浏览器支持的代码）, css moudles（模块化）,variables, mix-in（类 SCSS 的预处理支持）等各种丰富插件…没有你还可以自己写（提供插件 boilplate）！

React Native/Flutter – 跨端方案。最近关于 RN 是否凉了？如何评价 Flutter？的问答挺多的，我更关注的可能还是了解他们是如何实现的，以及解决了什么问题吧

source maps – 了解 js、css 的 source maps 是如何生成的，相应的规范，在浏览器、生产环境调试、以及异常追踪系统里面的使用。

TypeScript – 用 TS 实现的项目越来越多了，特别是一些大型项目，流行程度也是越来越高

WebSocket – 需要长连接、实时通信的场景

WebStorm/VS Code – IDE/编辑器，使用最多的就是用这两种了

另外，我觉得大家关注讨论比较多的但是我自己还没有实践过的前端技术还包括：

rx.js

mobx

小程序 – 包括 wepy, mpvue 等

rollup（侧重 JS library 的打包构建）

parcel（约定式的打包构建工具）

服务端渲染（SSR）

前后端同构

createReactApp – React 项目脚手架工具
