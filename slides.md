---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
image: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
---

# How to Measure Web Performance

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 p-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
  class="abs-br m-6 text-xl icon-btn opacity-50 !border-none !hover:text-white">
  <carbon-logo-github />
</a>

---
clicks: 8
---

# 分享内容

<v-clicks at='0'>
<p>
本次分享的内容主要围绕”怎么去测量 web 应用性能“主题去讲解，具体内容如下：
</p>
</v-clicks>

<ul>
<v-clicks at='1'>
<li><b>为什么要做性能优化</b> - 做一件事之前需要知道 ”Why“，那么做好性能优化给我们的项目带来什么价值？
</li>
</v-clicks>
<v-clicks at='2'>
<li><b>什么样的速度才是优秀的速度</b> - 在讨论性能的时候，我们都会关注时间的指标，那么多快算快，什么样的速度才是优秀的速度？
</li>
</v-clicks>
<v-clicks at='3'>
<li><b>6个重要 Web Vitals</b> - 对于常用的衡量页面性能的指标FCP、LCP你可能听说过，那么 TTI、SI、CLS、TTB 了？
</li>
</v-clicks>
<v-clicks at='4'>
<li><b>Lab Data VS Field Data</b> - 什么是实验数据？什么是现场数据？我们怎么去获取这些数据来评估我们应用的性能？
</li>
</v-clicks>
<v-clicks at='5'>
<li><b>RAIL 模型</b> - 什么样的应用能给用户带来极致的体验，让我们通过 RAIL 模型去窥探其中的奥秘。
</li>
</v-clicks>
<v-clicks at='6'>
<li><b>性能预算</b> - 做性能优化不能低头盲目地做，你需要给自己的项目定合理的性能预算指标。
</li>
</v-clicks>
<v-clicks at='7'>
<li><b>测量工具</b> - 我们可以通过哪些工具去测量我们应用的性能，让我们深入了解 Lighthouse 背后的原理。
</li>
</v-clicks>
<v-clicks at='8'>
<li><b>性能监控</b> - 除了开源工具能提供给我们一些数据之外，性能监控能让我们更好地获取到真实用户的数据。
</li>
</v-clicks>
</ul>  

<br>
<br>

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent; 
  -moz-text-fill-color: transparent;
}
</style>

---
clicks: 4
---

# 为什么要做性能优化

优秀的性能能给用户带来更好的体验之外，我们还要看到高性能应用背后带来的业务价值。

<ol>
<v-clicks at="1">
<li><b>性能是留住用户的关键</b>，<a href="https://www.pinterest.com/" target="_blank">pinterest</a> 减少了用户能感知到的 40% 等待时间，使他们的站点增加了15%的搜索引擎流量和注册量。</li>
</v-clicks>

<v-clicks at="2">
<li><b>性能影响用户转化率</b>，对于 <a href="https://www.crunchbase.com/organization/mobify" target="_blank">Mobify</a> 来说，首页加载速度每下降100毫秒，基于会话的转化率就会增加1.11%，从而产生近38万美元的年平均收益增长。此外，付款页面加载速度下降100毫秒，基于会话的转化率就增加了1.55%，从而带来了近53万美元的年平均收益增长。</li>
</v-clicks>

<v-clicks at="3">
<li><b>性能直接影响用户体验</b>，有一项<a href="https://www.ericsson.com/en/press-releases/2016/2/streaming-delays-mentally-taxing-for-smartphone-users-ericsson-mobility-report" target="_blank">消费研究</a>表明，用户在等待网页加载的体验类似于观看恐怖电影或者做数学题的压力，这种压力比在线下的零售店排队的压力更大。而且用户等待的时间越长，那么用户的消费意愿也可能随着时间而消逝。</li>
</v-clicks>

<v-clicks at="4">
<li><b>性能影响人的日常生活</b>，随着手机用户在全球互联网用户中所占比例的不断扩大，我们必须记住，许多手机用户是通过4G、3G甚至2G网络访问网页的。虽然手机网络数据流量费的成本正在下降，但是也让以前无法上网的地方的上网成本变得更加低廉，移动设备和互联网接入不再是奢侈品，它们是在日常生活中不可或缺的工具，我们用它来联系朋友、发邮件、逛社区、购物等等。</li>
</v-clicks>
</ol>
---

# 什么样的速度才是优秀的速度

页面“加载” 不只是一个瞬间，从访问网站到页面完成展示需要经历很多的阶段，这整个过程不是一个单独的性能指标就能说明问题的。

<br>
<br>
<img border="rounded" src="/assets/speed.png">

<br>
<br>
<uim-rocket />
<uim-rocket class="text-3xl text-red-400 mx-2" />
<uim-rocket class="text-3xl text-orange-400 animate-ping" />

---

# 四个阶段的 Web Vitals
<div class="grid">
<ul class="w-100">
<li>第一个阶段是用户收到服务器的反馈，用 <b>TTFB （Time To First Byte）</b>和<b>FP（First Painting）</b>指标衡量；
</li>
<li>第二个阶段是用户看到比较有意义的内容，用 <b>FCP （First Contentful Paint）</b> 这个指标衡量；
</li>
<li>第三个阶段是用户是否可以与网站交互，用 <b>TTI (Time to Interactive)</b> 这个指标衡量；
</li>
<li>第四个阶段是用户是否可以在与网站交互的过程中，能比较快地收到响应，这个与后面要说的 <b>RAIL</b> 模型 相关。
</li>
</ul>  

<img border="rounded" class="absolute w-120 right-5" src="/assets/vitals.png">
</div>
<br>
<br>

<style>
img {
  height: 50vh;
}
</style>
---
preload: false
---
# 6个重要 Web Vitals

<div v-motion :initial="{
      opacity: 0,
    }"
    :enter="{
      opacity: 1,
    }"><img border="rounded" src="/assets/webVitals.png"></div>
---

# First Contentful Paint

FCP度量用户导航到页面后，浏览器渲染呈现第一块 DOM 内容所花的时间。页面上的图像、非白色<code>canvas</code> 元素和 svg 被认为是 DOM 内容；iframe 内的任何内容都不包括在内。

---

# Speed Index

Speed Index 度量页面加载过程中内容可视化显示的速度。Lighthouse 首先在浏览器中捕捉页面加载的视频，并计算帧间的视觉进程。然后 Lighthouse 使用 [Speedline](https://github.com/paulirish/speedline) 模块生成速度指数分数。

---

# Largest Contentful Paint

LCP 度量视口中最大的内容元素何时呈现到屏幕上。这近似于页面的主要内容对用户可见。

---

# Time To Interactive

TTI测量的是一个页面从加载到渲染并且变成完全可交互需要多长时间。

---

# Cumulative Layout Shift

衡量视觉稳定性的一个重要的、以用户为中心的指标，因为它有助于量化用户经历意想不到的布局位移的频率，较低的 CLS 有助于确保页面视觉效果令人愉快。

--- 

# RAIL 模型

RAIL是一个以用户为中心的性能模型，该模型将用户体验分解为关键操作(例如，点击、滚动、加载)，并指导你为每个操作定义性能目标。

RAIL代表 web 应用生命周期的四个不同方面:**响应（Response）、动画（Animation）、空闲（Idle）和加载（Load）**。

<img border="rounded" src="/assets/RAIL.png">

--- 

# 响应：在50ms内处理事件

目标：在100毫秒内完成由用户输入引发的过渡，这样用户就会觉得交互的响应是瞬时的。

50 ms or 100ms？除了输入处理之外，JS 线程通常还有其他工作要做，这些工作占用了可接受的输入响应的部分可用时间。

<div class="img-container">
<img border="rounded" class="w-180" src="/assets/idle.png">
</div>

<style>
.img-container {
  display: flex;
  justify-content: center;
}
</style>
--- 

# 动画：在10毫秒内渲染一帧

目标：在10毫秒或更短的时间内完成动画中的每一帧渲染。 从技术上讲，每帧的最大预算是16毫秒（1000毫秒/每秒60帧≈16毫秒），但是浏览器需要大约6毫秒才能渲染每帧，因此指导原则是每帧10毫秒。

--- 

# 空闲时间：最大化空闲时间

目标：最大化空闲时间，以增加页面在50毫秒内响应用户输入的可能性。

---

# 加载：在5秒内交付内容并实现用户可交互

目标：

1.针对用户的设备和网络能力进行快速加载的性能优化。目前，第一次加载的目标是加载页面并在5秒或更短的时间内在3G连接较慢的中端移动设备上使得用户可交互。

2.对于正常网速的加载，目标是在2秒内加载页面。

---

# Lab Data VS Field Data

由于用户设备、网络连接和其他因素的不同，真实世界的性能变化很大。例如，如果你在办公室使用有线网络加载你的网站，并将其与在咖啡店使用 WiFi 加载进行比较，体验可能会非常不同。所以在业界内就会有很多工具为你的站点收集实验室数据（Lab Data）或现场数据（Field Data），用这两种数据来评估你的网站性能。

---

# Lab Data
实验室数据是通过预设的设备和网络设置在受控环境中收集的性能数据，实验室数据提供了可重复的结果和调试环境，但是可能不能捕获真实环境中的瓶颈，并且不能与现实世界的页面 kpi 相关联。

收集实验室数据的工具有 Lighthouse，Lighthouse 获取一个URL并对页面运行一系列审查，生成关于页面运行情况的报告。

---

# Field Data

现场数据是从用户在现实环境中体验到的真实页面加载中收集的性能数据，现场数据(也称为真实用户监控或RUM)捕捉真实的真实用户体验，并支持与业务kpi的相关性，但指标集和调试能力有限。

我们通过 [Performance API](https://developer.mozilla.org/zh-CN/docs/Web/API/Performance) 获取到用户访问站点时的性能数据，然后进行数据上报，然后分析网站性能瓶颈。目前我们的智能落地页项目就是使用 [Sentry Performance Monitoring](https://docs.sentry.io/product/performance/)。

---

# 性能预算

和大多数其他事情一样，要达到一个目标，你必须清楚地定义它。在我们做性能优化之前，我们需要设定一些性能预算。

<div class="img-container">
<img border="rounded" src="/assets/budget.png">
</div>

<style>
.img-container {
  display: flex;
  justify-content: center;
}
</style>

为此选择一个工具将在很大程度上取决于你的项目规模和用于该任务的资源。上面这些开源工具可以帮助您在构建过程中添加预算。

---

# 一些性能预算的例子

- 手机端网站页面 Javascript Bundle 体积小于170 KB；
- 在网站搜索页面的图片总体积大小小于 2 MB；
- 在 3g 网络环境中 和 Moto G4 机上用户与网站的交互时间小于 5s;
- 我们网站通过 Lighthouse 审计得分大于85分。

落地页的性能预算：

1.Google PageSpeed 评分（业界重要参考）：移动端>85，PC端>90；

2.页面加载速度 FCP：移动端<2s，PC端<1s。

--- 

# 测量工具

[Lighthouse](https://github.com/GoogleChrome/lighthouse) 是用来分析web应用和网页，收集现代性能指标和开发者最佳实践的建议的工具，也是我们平时可以用来评测我们网站性能的工具。

<div class="img-container">
<img border="rounded" class="w-120" src="/assets/lighthouse-logo.png">
</div>

<style>
.img-container {
  display: flex;
  justify-content: center;
}
</style>

---

# 通过 extension 方式使用 Lighthouse

<div class="img-container">
  <img border="rounded" class="w-120" src="/assets/lighthouse-devtools.png">
</div>

<style>
.img-container {
  display: flex;
  justify-content: center;
}
</style>

---

# 

<div class="img-container">
  <img border="rounded" class="w-90" src="/assets/lighthouse.png">
  <img border="rounded" class="w-90" src="/assets/lighthouse1.png">
</div>

<style>
.img-container {
  display: flex;
  justify-content: center;
}
</style>

---

# 通过 Node CLI 使用 Lighthouse

```bash
lighthouse https://github.com
```

or

```bash
lighthouse https://github.com --output-path=./report.json --output json
```

生成 JSON，通过在线 [Viewers](https://googlechrome.github.io/lighthouse/viewer/) 查看。

---
theme: default
---

# Lighthouse Architecture

<div class="img-container">
  <img border="rounded" class="w-150" src="/assets/lighthouse-art.png">
</div>

<style>
.img-container {
  display: flex;
  justify-content: center;
  background: #fff;
}
</style>

---

# Performance Scoring 背后的原理

性能分数是每个指标分数的加权平均值，现在影响得分的6个指标权重如下：FCP（15%）、SI（15%）、LCP（25%）、TTI（15%）、TBT（25%）、CLS（5%）。

选择这些权重是为了提供用户对性能感知的平衡表示。随着时间的推移，权重可能会发生变化，因为Lighthouse 团队会定期进行研究并收集反馈，以了解什么对用户感知性能的影响最大。

你可以通过在线的 [Scoring Calculator](https://googlechrome.github.io/lighthouse/scorecalc/) 获得你网站最后的性能分数。

---

# 那么每个指标的的得分是怎么来的了

一旦 Lighthouse 完成了性能指标数据收集，它就会将性能指标转换成0~100的分数，通过加权得到最终的评分。评分分布是一个对数正态分布，它们是从 [HTTP Archive](https://httparchive.org/reports/loading-speed#fcp) 上的真实网站性能数据的性能指标。

<div class="img-container">
  <img border="rounded" class="w-150" src="/assets/lighthouse-graph.png">
</div>

<style>
.img-container {
  display: flex;
  justify-content: center;
}
</style>

---

# 性能监控

除了使用 Lighthouse 这样的工具评估我们网站的性能之外，我们还可以通过接入 [Sentry Performance Monitoring](https://docs.sentry.io/product/performance/)，收集用户访问你站点的性能数据。

<div class="img-container">
  <img border="rounded" class="w-150" src="/assets/sentry1.png">
</div>

<style>
.img-container {
  display: flex;
  justify-content: center;
}
</style>

---
clicks: 2
---

# 接入 Sentry

<v-clicks :every='0'>

```bash
yarn add @sentry/react @sentry/tracing
```
</v-clicks>

<v-clicks :every='2'>

初始化 sentry:

 ```ts
import * as Sentry from "@sentry/react";
import { Integrations } from "@sentry/tracing";
Sentry.init({
  dsn: "https://examplePublicKey@o0.ingest.sentry.io/0",
  release: "my-project-name@" + process.env.npm_package_version,
  integrations: [new Integrations.BrowserTracing()],
  // We recommend adjusting this value in production, or using tracesSampler
  // for finer control
  // 必须添加采样率参数
  tracesSampleRate: 1.0,
});
 ```
</v-clicks> 

<v-clicks :every='3'>

监测 React 组件：

```ts
import * as Sentry from "@sentry/react";
export default Sentry.withProfiler(App);
```
</v-clicks>

---

# 查看数据

<div class="img-container">
  <img border="rounded" class="w-150" src="/assets/sentry2.png">
</div>

<style>
.img-container {
  display: flex;
  justify-content: center;
}
</style>