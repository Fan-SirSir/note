

- 盒子的尺寸（css3）

  - 默认情况下，盒子可见框的大小由内容区，内边距和边框共同决定
    - `box-sizing`用来设置盒子尺寸的计算方式，（设置width和height的作用）
      - 可选值
        - content-box 默认值，宽度和高度用来设置内容区的大小
        - border-box 宽度和高度用来设置整个盒子的可见框的大小，width和height指的是内容区 和 内边距 和 边框的大小

- 轮廓阴影和圆角（css3）

  - （轮廓）`outline`：用来设置元素的轮廓线，用法和border一样

    - 不同点：轮廓不会影响可见框的大小

  - （阴影）`box-shadow`

    - ```css
      /* 
         box-shadow用来设置元素的阴影效果，阴影不会影响页面布局
             第一个值 水平偏移量 设置阴影的水平位置 正值向右移动 负值向左移动
             第二个值 垂直偏移量 设置阴影的垂直位置 正值向下移动 负值向上移动
             第三个值 阴影的模糊半径
             第四个值 阴影的颜色
      */
      ```

  - 圆角

    - ```css
      /*border用来设置圆角 圆角设置的圆的半径大小*/
      
      /*
      	border-top-left-radios
      	border-top-right-radios
      	border-bottom-right-radio
      	border-top-left-radios
      */
      
      /*将元素设置为一个圆形 */
      border-radios：50%px；
      ```




- 字体

  - `vertical-align`

    - ```css
      /*用来设置元素垂直对齐的方式
      	可选值：
      		baseline 默认值 基线对齐
      		top 顶部对齐
      		bottom 底部对齐
      		middle 居中对齐
      */
      ```

- 过渡

  ~~~css
  - ```css
     /* 
                    过渡（transition）
                        -通过过渡可以指定一个属性发生变化时的切换方式
                        通过过渡可以创建一些非常好的效果，提升用户的体验
  						
     */
    
     /* 
                    transition-property：指定要执行过渡的属性
                    多个属性间使用逗号隔开
                    如果所有属性都需要过渡。则使用all关键字
                    大部分属性都支持过渡效果，注意过渡时必须是从一个有效数值向另外一个有效数值进行过渡
                */
    
     /*transition-duration：指定过渡效果的持续时间*/
    
     /*
                 transition-timing-function：过渡的时序函数
                    指定过渡的执行方式
                    可选值，
                        ease 默认值，慢速开始，先加速，再减速
                        linear 匀速运动
                        ease-in 加速运动
                        ease-out 减速运动
                        ease-in-out 先加速 后减速
                        cubic-bezier() 来制定时序函数
                        steps() 分布执行过渡效果
                            可以设置一个第二个值
                                end，在时间结束时执行过渡（默认追）
                                start，在时间开始时执行过渡
     */
    
    /* transition-delay：过渡效果的延迟。等待一段时间后在执行过渡*/
    
                /* transition 可以同时设置过渡相关的所有属性，只有一个要求。如果要写延迟则两个时间中第一个显示持续时间，第二个是延迟 */
    
    ```
  ~~~

  



- 动画

  - ```css
     /* 
            动画
                动画和过渡类似，都是可以实现一些动态的效果
                    不同的是过渡需要在某个属性发生变化时才会触发
                    动画可以自动触发动态效果
                设置动画效果，必须先要设置一个关键帧，
           */
      			/* from表示动画开始的位置 也可以使用 0% */
                /* to动画的结束位置  也可以使用100%*/
     			/*百分号表示的是在某个时间段*/
      
                /* animation-name:要对当前元素生效的关键帧的名字 */
                /* animation-name: test; */
      
                /* animation-duration:动画的执行时间 */
                /* animation-duration: 4s; */
      
                /* 动画的延时 */
                /* animation-delay: 2s; */
      			
       			/**动画先加速后减速**/
             /* animation-timing-function: ease-in-out; */
         
                /* 
                animation-iteration-count 动画执行的效果
                    可选值:
                        次数
                        infinite 无限执行
                */
             /* animation-iteration-count: （次数）; */
         
                /* 
                animation-direction
                    指定动画运行的方向
                        可选值：
                        normal 默认值 从 from 向 to运行 每次都是这样 
                        reverse 从 to 向 from 运行 每次都是这样
                        alternate-reverse 从 to 向 from运行 重复执行动画时反向执行
                */
      
                /*
                 animation-play-state: 设置动画的执行状态
                 可选值:
                 running 默认值 动画执行  
                 paused 动画暂停
                 */
         
              /*
                 animation-fill-mode: 动画的填充模式
                    可选值:
                        none 默认值 动画执行完毕
                        forwards 停到执行完毕元素会停止在动画结束的位置
                        backwards 动画延时等待时，元素就会处于开始位置
                        both 结合了forwards 和 backwards
                 */
     
     			animation（简写属性）: 动画名字 ......;(若要写动画持续时间和动画延时，先持续后延时)
     ```

  - 补充 

     - ![image-20220607131511897](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20220607131511897.png)
     - ![image-20220607132112319](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20220607132112319.png)

- 变形平移

  - ![image-20220716164534101](C:\Users\ASUS\AppData\Roaming\Typora\typora-user-images\image-20220716164534101.png)

    - x轴： 水平向右 注意： x 右边是正值，左边是负值
    - y轴： 垂直向下 注意： y 下面是正值，上面是负值
    - z轴： 垂直屏幕 注意： 往外面是正值，往里面是负值 （前提必须设置透视 ）

  - ```css
    /* 
    变形就是指通过CSS来改变元素的形状或位置
        -    变形不会影响到页面的布局
        -transform 用来设置元素的变形效果
        - 平移：
            translateX() 沿着x轴方向平移
            translateY() 沿着Y轴方向平移
            translateZ() 沿着Z轴方向平移
        - 平移元素时，百分比时相对于自身计算的
     */
        
    							
    ```

- 透视`perspective`

  - **透视：** 在2D平面产生近大远小视觉立体，但是只是效果二维的

  ```css
  /* 设置当前网页的视距为800px，人眼距离网页的距离 */
  /* 
                z轴平移，调整元素在z轴的位置，正常情况就是调整元素和人眼之间的距离
                     距离越大，元素离人越近
                z轴平移属于立体效果（近大远小），默认情况下网页是不支持透视
                     必须要设置网页的视距
  */						
  ```

- 旋转

  - ```css
    
                /* 
                    通过旋转可以使元素沿着x y 或 z旋转指定的角度
                        rotateX()
                        rotateY()
                        rotateZ()
                */
                  
     /*
      	backface-visibility:是否显示元素的背面
      		可选值：
      			hidden：隐藏
      			visible	：默认
    */
    ```

  - ==使用注意事项：==y轴是向下的

  - 使用方法：

    轻握左手，大拇指指向旋转轴正方向，四指指向的方向就是旋转方向。

- 3D呈现`transform-style`

  - 控制子元素是否开启三维立体环境
  - `transform-style: flat` 子元素不开启3d立体空间（默认）
  - `transform-style: preserve-3d` 子元素开启立体空间
  - 代码写给父级，但是影响的是子盒子

- 缩放

  ```css
  /*
  	对元素进行缩放的函数
  	scaleX() 水平方向缩放
  	scaleY() 垂直方向缩放
  	scale() 双方向缩放
  */
  
  /*变形的原点 默认值 center*/
  /*transform-origin:第一个值 第二个值*/
  ```



- ==flex（弹性盒、伸缩盒）==

  ```css
  /*
  	- 是css中的又一种布局手段，它主要用来代替浮动来完成页面的布局
  	- flex可以使元素具有弹性，让元素可以跟随页面的大小的改而改变
  	- 弹性容器
  		- 要使用弹性盒，必须先将一个元素设置为弹性容器
  		- 我们通过 display 来设置弹性容器
  			display：flex 设置为块级弹性容器
  			display：inline-flex 设置为行内的弹性容器
  
  	- 弹性元素
  		- 弹性容器的子元素是弹性元素（弹性项）
  		- 一个元素可以同时是弹性容器和弹性元素
  */
  
  ```

  - 弹性容器的样式

    ```css
    /*
    	flex-direction 指定容器中弹性元素的排列方式
    	可选值：
    		row默认值，弹性元素在容器中水平排列（左向右）
    			- 主轴 自左向右
    		row-reverse 弹性元素在容器中反向水平排列（右向左）
    			- 主轴 自右向左
    		column 弹性元素纵向排列（自上向下）
    		column-reverse 弹性元素方向纵向排列（自下向上）
    		
    	主轴
    		弹性元素的排列方向称为主轴
    	侧轴（辅轴）
    		与主轴垂直方向的称为侧轴
    */
    
    /*
    	flex-wrap:
    		设置弹性元素是否在弹性容器中自动换行
    		可选值：
    			nowrap 默认值，元素不会自动换行
    			wrap 元素沿着辅轴方向自动换行
    			wrap-reverse 元素沿着主轴反方向换行
    */
    
    /*flex-flow: wrap和direction的简写属性*/
    /*flex-flow:row wrap;*/
    
    /*
    	justify-content
    		- 如何分配主轴上的空白空间（主轴上的元素如何排列）
    		- 可选值：
    			flex-start 元素沿着主轴起边排列
    			flex-end 元素沿着主轴终边排列
    			center 元素居中排列
    			space-around 空白分布到元素两侧
    			space-between 空白均匀分不到元素间
    			space-evenly 空白分布到元素的单侧
    */
    
    /*
    	align-items:
    	- 元素在辅轴上如何对齐
    	- 元素间的关系
    		- 可选值：
    			stretch 默认值，将元素的长度设置为相同的值
    			flex-start 元素不会拉伸，沿着辅轴起边对齐
    			flex-end 沿着辅轴的终边对齐
    			center 居中对齐
    			baseline 基线对齐
    */
    
    /*让容器内元素水平垂直居中的方式：*/
    align-items:center;
    justify-content: center;
    
    /*align-content:space-between:辅轴空白空间的分布*/
    align-content:（与aligin-itens值一致）;
    
    /*align-self:用来覆盖当前弹性元素上的align-items*/
    align-self:str
    ```

  - 弹性元素的样式

    ```css
    /*
    		flex-grow 指定弹性元素的伸展的系数
                - 当父元素有多余空间时，子元素如何伸展
                - 当父元素的剩余空间，会按照比例进行分配
    */
    
    /*
    		flex-shrink 指定弹性元素的收缩系数
                - 当父元素中的空间不足以容纳所有的子元素时，如何对子元素进行收缩
    */
    
    /*align-self:用来覆盖当前弹性元素上的align-items*/
    align-self:(例：stretch);
    
    /*
    	元素基础长度
    	flex-basis 指定的是元素在主轴上的基础长度
    		如果主轴是 横向 则 该值指定的就是元素的宽度
    		如果主轴是 纵向 则 该值指定的就是元素的高度
    		- 默认值是 auto，表示参考元素自身的高度或宽度
    		- 如果传递了一个具体的数值，则以该值为准
    */
    
    /*
    	flex 可以设置弹性元素所有的三个样式
    		flex 增长 缩减 基础；
    		默认值: 0 1 auto
    */
    
    /*
    	order 决定弹性元素的排列顺序，用数字指定
    */
    ```
    



- 像素

  ```css
  - 屏幕是由一个一个发光的点构成，这一个个小点就是像素
  - 分辨率：1920*1080说的就是屏幕中小点的数量
  - 在前端开发中像素要分成两种情况讨论：CSS像素 和 物理像素
  - 物理像素，上述所说的小点就属于物理像素
  -CSS像素，编写网页时，我们所用像素都是CSS像素
  	- 浏览器在显示网页时，需要将CSS像素转换为物理像素然后再呈现
  	- 一个css像素最终由几个物理像素显示，由浏览器决定
  		默认情况下在pc端，一个css像素 = 一个物理像素
  
  视口（viewport）
  	- 视口就是屏幕中用来显示网页的区域
  	- 可以通过查看视口的大小，来观察CSS像素和物理像素的比值
  	- 默认情况下：
  		视口宽度 1920px（CSS像素）
  				1920px（物理像素）
  				- 此时，css像素和物理像素的比是1:1
  
  	- 我们可以通过改变视口的大小，来改变CSS像素和物理像素的比值
  
  ```




- 完美视口

  ```css
  <meta name="viewprot" content="width=device-width,initial-scale=1.0">
  /*写移动端页面时，要加上这条代码*/
  ```




- vw单位

```css
vw表示的是视口的宽度（viewport width）
	- 100vw = 一个视口的宽度
	- 1vw = 1%视口宽度

	/*vw这个单位永远相对于视口宽度进行计算*/


	100vw = 750px（设计图的像素） 0.13333... = 1vw
```

- `rem`

  ```css
  /*
  	rem 它的全称是 font size of the root element （根元素的字体大小）
  	作用：
  		用来做web app的屏幕适配，因为不同手机型号的屏幕大小都不同，所以这时候我们就不能用px来做单位，rem是适配不同手机屏幕的一种方案
  */
  	例子：
  :root{
        font-size:20px;
       }
  .box{
        width:1rem;
        height:1rem;
        background-color:purple;
      }
  /*将根元素html的font-size设置为20px，此时box的宽高都为20px，也就是1rem = 20px,成乘积关系*/
  
  /*
  	网页中字体大小最小是12px，不能设置一个比12像素还小的字体
  		如果我们设置了一个小12px的字体，则字体自动设置为12
  */
  
  /*
  	rem
  		- 1 rem = 1 html的字体大小
  */
  ```
  
  

- 媒体查询

  ```css
  /*
  使用媒体查询
  	语法：@media 查询规则()
  		媒体类型：
  			all 所有设备
  			print 打印设备
  			screen 带屏幕的设备
  			speech 屏幕阅读器
  			- 可以使用，连接多个媒体类型
  
  		可在媒体类型前加only，兼容老版本浏览器
  */
  
  
  ```

  ```html
  <!-- 
  	响应式布局
  		- 网页可以根据不同的设备或窗口大小呈现出不同的效果
  		- 使用响应式布局，可以使一个网页适用于所有设备
  		- 响应式布局的关键： 媒体查询
  		- 通过媒体查询，可以为不同的设备，或设备不同状态分别设置样式
  -->
  ```

  - 媒体特性

    ```css
    /*
    	width 视口的宽度
    	height 视口高度
    	
    	min-width 视口的最小宽度（视口大于指定宽度时生效）
    	max-width 视口的最大宽度（视口小于指定宽度时生效）
    */
    
    /*
    样式切换的分界点，我们称其为断点
    	（常用断点）
    	<768 超小屏幕
    	>768 小
    	大于992 中型
    	大于1200 大屏幕
    
    ```

    
