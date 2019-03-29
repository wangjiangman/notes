1. **什么是SSR**  
  SSR(服务器端渲染), 是指将与*客户端相同的组件*渲染为*服务器端的HTML字符串*，直接发送到浏览器，然后将这些静态标记"**Hydrate(激活)**"为客户端上完全可以交互的应用程序。
    > Vue SSR 主要指的是Nodejs服务端渲染。

2. **如何将服务器端相同的Vue应用程序提供给客户端**
  ![](https://cloud.githubusercontent.com/assets/499550/17607895/786a415a-5fee-11e6-9c11-45a2cfdf085c.png)
    >如何理解Hydrate过程？在此处可解释为：混合静态标记。更深层的意义是，Hydration发生在模板与视图的转换过程中，用于DOM与应用其它部分(如绑定事件等)的结合。

3. **实现服务器端渲染的要点**   
    1. 数据预取（pre-fetching data）
    2. 使用通用的组件生命钩子(beforeCreated created)
    3. 不使用特定平台的API(如只适用于web客户端的window和document)
