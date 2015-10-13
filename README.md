# svg
svg应用
# SVG用法

##SVG简介
   xml描述的矢量文件，矢量图基于数学的描述，位图基于颜色的描述
   

    <svg xmlns="http://www.w3.org/2000/svg" 
    width="200" height="200">
    <!--Face-->
    <circle cx="100" cy="100" r="90" fill="#39F" />
    <!--Eyes-->
    <circle cx="70" cy="80" r="20" fill="white" />
    <circle cx="130" cy="80" r="20" fill="white" />
    <circle cx="65" cy="75" r="10" fill="black" />
    <circle cx="125" cy="75" r="10" fill="black"/>
    <!--Smile-->
    <path d="M 50 140 A 60 60 0 0 0 150 140" 
        stroke="white" stroke-width="3" fill="none" />
     </svg>
浏览器打开
img插入svg图片

     <h1>Hello SVG with &lt;img&gt;</h1>
        <p><img src="simple.svg" />原始大小</p>
        <p><img src="simple.svg" 
            width="50" height="50" />50 x 50</p>
        <p><img src="simple.svg" 
            width="400" height="400" />400 x 400</p>
html插入svg

      <h1>Hello Nested SVG</h1>
        <p>
            <svg xmlns="http://www.w3.org/2000/svg" 
                width="200" height="200">
                <!--Face-->
                <circle cx="100" cy="100" r="90" fill="#39F" />
                <!--Eyes-->
                <circle cx="70" cy="80" r="20" fill="white" />
                <circle cx="130" cy="80" r="20" fill="white" />
                <circle cx="65" cy="75" r="10" fill="black" />
                <circle cx="125" cy="75" r="10" fill="black"/>
                <!--Smile-->
                <path d="M 50 140 A 60 60 0 0 0 150 140" 
                    stroke="white" stroke-width="3" fill="none" />
            </svg>
        </p>
css 
 

    <!DOCTYPE html><html>
    <head>
        <title>在网页中直接使用 SVG 标签</title>
        <style>
            body {
                background: #EFEFEF;
            }
            #bg {
                width: 400px;
                height: 400px;
                background: white url(simple.svg) repeat;
                box-shadow: rgba(0,0,0,.5) 2px 3px 10px;
                border-radius: 10px;
            }
        </style>
    </head>
    <body>
        <h1>Hello SVG with CSS</h1>
        <div id="bg">
            
        </div>
    </body>
</html>

### 定义的基本图形和属性
基本图形

    <rect>,<circle》，<ellipse>,<line>,<polyline>,<polygon>

基本属性
>file,stroke,stroke-width,transform

path 绘制高级的图形

#### <rect>
x,y,（原点）width,height,rx,ry(距形的圆角)，只给一个两个默认是相同的
#### <circle>
cx,cy(圆心的位置) r 半径

#### ellipse
cx,cy,(原点)rx,ry（圆角）
####  line
x1,y1, x2,y2

#### polyline
points 格式(xi,yi)+

points="x1 y1......x4 y4"

### 填充，描边和变换
fill,填充颜色 
stroke  描边颜色 
stroke-width描边粗细
transform  与父坐标变形

    <svg xmlns="http://www.w3.org/2000/svg">
    <rect 
        x="10" 
        y="10" 
        rx="5" 
        ry="5" 
        width="150" 
        height="100" 
        stroke="red" 
        fill="none">
    </rect>

    <circle 
        cx="250" 
        cy="60" 
        r="50" 
        stroke="red" 
        fill="none">
    </circle>

    <ellipse 
        cx="400" 
        cy="60" 
        rx="70" 
        ry="50" 
        stroke="red" 
        fill="none">
    </ellipse>

    <line 
        x1="10" 
        y1="120" 
        x2="160" 
        y2="220" 
        stroke="red">
    </line>

    <polyline 
        points="250 120 
                300 220
                200 220"
        stroke="red"
        fill="none">
    </polyline>

    <polygon 
        points="250 120 
                300 220
                200 220"
        stroke="red"
        stroke-width="5"
        fill="yellow"
        transform="translate(150 0)">
    </polygon>
</svg>


## jsapi
创建图形

    document.createElementNs(ns,tabName);
    
 
   可以作为单独的文件存在

添加图形

    element.appendChild(childElement);



设置、获取属性：

    element.setAttribute(name,value);
    element.getAttribute(name);

### svg坐标系统与坐标变换

#### 视界视野视窗概念
世界是无穷大的
视野是观察世界的一个矩形区域  viewbox
width,height,控制视窗，浏览器开辟的区域，根据样式发生改变
svg代码 定义世界
viewbox,preserveAspectRatio 控制视野，以多大的视野观察，
视野与视窗不一致preserveAspectRatio 来控制

看代码对应教程代码
#### svg中的图形分组
SVG 中的图形分组
•<g>标签来创建分组
• 属性继承
• transform 属性定义坐标变换
• 可以嵌套使用
<g> 标签就可以作为一个整体进行操
#### 坐标系统概述
#### 自身坐标系统 和参照坐标系
#### 坐标变换
   
