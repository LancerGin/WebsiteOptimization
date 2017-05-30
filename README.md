## 网站性能优化项目

优化了 `index.html` 的关键渲染路径使这个页面尽可能快的呈现。
优化了 `pizza.html` 的 FPS，以达到至少每秒60帧的动画效果。
查看 [优化后的网站](https://lancergin.github.io/WebsiteOptimization/)


#### Part 1: 优化 index.html 的 PageSpeed Insights 得分

以下是具体的优化措施：

1.给`print.css`添加媒体查询。

2.将体积较小的 CSS 都内联到 HTML 中，减少网络请求次数。

3.给外部加载的`<script>`脚本加上`async`属性，异步加载脚本。

4.压缩了图片大小。


#### Part 2: 优化 pizza.html 的 FPS（每秒帧数）

以下是具体的优化措施：

1.将所有的 `querySelector*` 类的方法都替换为 `getElementsByClassName()` `getElementById()`这类方法。因为大多数 `querySelector*` 类的方法都非常的消耗资源，尤其是要一次性获取很多个对象的时候。

2.改变pizza元素宽度的功能。将计算pizza元素宽度的代码移出循环体，避免强制同步布局，提高效率。

3.移动背景中的披萨滑窗。将获取滚动条位置的代码移出循环体，避免强制同步布局，提高效率;滚动更新位置时调用`requestAnimationFrame`，避免掉帧；减少背景中披萨元素的数量，删除了不在可见范围内的多余元素。
