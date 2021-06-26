# OrbitControls



## Constructor

### OrbitControls( object : Camera, domElement : HTMLDOMElement )

object: （必须）将要被控制的相机。

domElement: 用于事件监听的HTML元素。

## Events

### change

Fires when the camera has been transformed by the controls.



### start



Fires when an interaction was initiated.



### end

Fires when an interaction has finished.



## 属性

### .autoRotate : Boolean

.autoRotate = true; // 自动围绕目标旋转（依赖：update()）

control.update();



### .autoRotateSpeed : Float

.autoRotateSpeed = 2.0 // 相当于在60fps时每旋转一周需要30秒。



.autoRotate = true;

control.updata()



### .enableDamping : Boolean

.enableDamping = true  //默认：false启用阻尼：会给控制器带来重量感

control.updata()



### .dampingFactor : Float

.dampingFactor = 1.0 // 阻尼惯性大小



.enableDamping = true

control.updata()



### .domElement : HTMLDOMElement

该 HTMLDOMElement 用于监听鼠标/触摸事件，该属性必须在构造函数中传入。在此处改变它将不会设置新的事件监听。



### .enabled : Boolean

enabled = true;  // 开启control（默认）

enabled = false // 关闭control



### .enablePan : Boolean

.enablePan = true // 默认，允许相机平移

.enablePan = false // 禁止许相机平移



### .screenSpacePanning : Boolean

定义当平移的时候摄像机的位置将如何移动。如果为true，摄像机将在屏幕空间内平移。 否则，摄像机将在与摄像机向上方向垂直的平面中平移。当使用 OrbitControls 时， 默认值为true；当使用 MapControls 时，默认值为false。



### .panSpeed : Float

位移的速度，其默认值为1。



### .keyPanSpeed : Float

.keyPanSpeed = 7.0 // 每次按下按键时平移7像素。（需要开启键盘按键）



### .enableRotate : Boolean

.enableRotate = true // 默认，允许相机水平or垂直旋转

.enableRotate = false // 禁止相机水平or垂直旋转


请注意，可以通过将polar angle或者azimuth angle 的min和max设置为相同的值来禁用单个轴， 这将使得水平旋转或垂直旋转固定为所设置的值。



### .enableZoom : Boolean

.enableRotate = true  // 启用或禁用摄像机的缩放。



### .keys : Object

这一对象包含了用于控制相机平移的按键代码的引用。默认值为4个箭头（方向）键。

`controls.keys = { `

`	LEFT: 'ArrowLeft', //left arrow `	

`UP: 'ArrowUp', // up arrow `

`RIGHT: 'ArrowRight', // right arrow `

`BOTTOM: 'ArrowDown' // down arrow `

`}`

请参阅[KeyboardEvent.code](https://developer.mozilla.org/zh-CN/docs/Web/API/KeyboardEvent/code)来查看所有按键的代码列表。



### .maxAzimuthAngle : Float

你能够水平旋转的角度上限。

如果设置，其有效值范围为[-2 * Math.PI，2 * Math.PI]，

且旋转角度的上限和下限差值小于2 * Math.PI。

默认值为无穷大。



### .maxPolarAngle : Float

你能够垂直旋转的角度的上限，范围是0到Math.PI，其默认值为Math.PI。



### .maxDistance : Float

你能够将相机向外移动多少（仅适用于PerspectiveCamera），其默认值为Infinity。



### .maxZoom : Float

你能够将相机缩小多少（仅适用于OrthographicCamera），其默认值为Infinity。



### .minAzimuthAngle : Float

你能够水平旋转的角度下限。如果设置，其有效值范围为[-2 * Math.PI，2 * Math.PI]，且旋转角度的上限和下限差值小于2 * Math.PI。默认值为无穷大。



### .minDistance : Float

你能够将相机向内移动多少（仅适用于PerspectiveCamera），其默认值为0。



### .minPolarAngle : Float

你能够垂直旋转的角度的下限，范围是0到Math.PI，其默认值为0。



### .minZoom : Float

你能够将相机放大多少（仅适用于OrthographicCamera），其默认值为0。



### .mouseButtons : Object

该对象包含由控件所使用的鼠标操作的引用。`controls.mouseButtons = { LEFT: THREE.MOUSE.ROTATE, MIDDLE: THREE.MOUSE.DOLLY, RIGHT: THREE.MOUSE.PAN }`



### .object : Camera

正被控制的摄像机。



### .position0 : Vector3

由 .saveState : saveState和 .reset : reset方法在内部使用。



### .rotateSpeed : Float

旋转的速度，其默认值为1。



### .target0 : Vector3

由 .saveState : saveState和 .reset : reset方法在内部使用。



### .target : Vector3

控制器的焦点，.object的轨道围绕它运行。 它可以在任何时候被手动更新，以更改控制器的焦点。



### .touches : Object

该对象包含由控件所使用的触摸操作的引用。`controls.touches = { ONE: THREE.TOUCH.ROTATE, TWO: THREE.TOUCH.DOLLY_PAN }`



### .zoom0 : Float

由 .saveState : saveState和 .reset : reset方法在内部使用。



### .zoomSpeed : Float

摄像机缩放的速度，其默认值为1。



## Methods

### .dispose () : null

移除所有的事件监听。



### .getAzimuthalAngle () : radians

获得当前的水平旋转，单位为弧度。



### .getPolarAngle () : radians

获得当前的垂直旋转，单位为弧度。



### .listenToKeyEvents ( domElement : HTMLDOMElement ) : void

为指定的DOM元素添加按键监听。推荐将window作为指定的DOM元素。



### .reset () : null

将控制器重置为上次调用.saveState时的状态，或者初始状态。



### .saveState () : null

保存当前控制器的状态。这一状态可在之后由.reset所恢复。



### .update () : Boolean

更新控制器。必须在摄像机的变换发生任何手动改变后调用， 或如果.autoRotate或.enableDamping被设置时，在update循环里调用。

