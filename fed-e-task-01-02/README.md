# 刘浪|Part2|模块二
### 第一题
引用计数
+ 核心思想：设置引用数，判断当前引用数是否为0
+ 引用计数器
+ 引用关系改变时修改应用数字
+ 引用数字为0时立即回收
> 简单来说 就是当变量没有被引用的时候就会被回收
引用计数算法优点
+ 发现垃圾时立即回收
+ 最大限度减少程序暂停
引用计数算法缺点
+ 无法回收循环引用的对象
+ 时间开销大

### 第二题
标记清除
+ 核心思想：分标记和清除二个阶段完成
+ 遍历所有对象找标记活动对象  
+ 遍历所有对象清除没有标记对象
+ 回收相应的空间

### 第三题
新生代对象回收实现
+ 回收过程采用复制算法+标记整理
+ 新生代内存区分为二个等大小空间
+ 使用空间为From，空闲空间为To
+ 活动对象存储于From空间
+ 标记整理后将活动对象拷贝至T0
+ From与To交换空间完成释放

### 第四题
增量式垃圾回收是主线程间歇性的去做少量的垃圾回收的方式。我们不会在增量式垃圾回收的时候执行整个垃圾回收的过程，只是整个垃圾回收过程中的一小部分工作。 为了降低全堆垃圾回收带来的停顿时间,V8先从标记阶段入手,将原本要一口气停顿完成的动作改为增量标记(incremental marking),也就是拆分为许多小“步进”,每做完一“步进” 就让 JavaScript 应用逻辑执行一小会儿,垃圾回收与应用逻辑交替执行直到标记阶段完成


### 练习题在 code/functional-programming/代码题2.js