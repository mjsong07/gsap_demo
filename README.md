
# 介绍
1. 支持移动缩放渐变等常用动画
4. 支持多个动画时间线控制
2. 支持鼠标滚动控制动画
3. 支持定格 pin
官网：https://gsap.com/

# 基础应用

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>gsap</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.6.0/gsap.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.6.0/ScrollTrigger.min.js"></script> 
</head>
<style> 

.gsap .box {
  display: block;
  width: 70px;
  height: 70px;
  margin: 10px;
  border-radius: 12px;
  line-height: 70px;
  text-align: center;
  color: #fff;
  font-size: 16px
}
 

.gsap .green {
  border: 1px solid green
}

.gsap .red {
  border: 1px solid red
}

.gsap .blue {
  border: 1px solid blue
}

.gsap .purple {
  border: 1px solid purple
}

.gsap .orange {
  border: 1px solid orange
}
</style>

<body>  
  <div class="gsap">
    <div class="box green"></div> 
    <div class="box orange"></div> 
    <div class="box purple"></div> 
  </div>  
 
  <script>  

  </script>
</body>

</html>
```

![image.png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/28b9e7ac02f64b31ae76d04a0a9edc48~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735630893&x-orig-sign=ONRJFj9WOS91FGiNa9%2FAPlv8RbU%3D)

## 旋转 
```js
 gsap.to(".green", {
  rotation: 360,
  duration: 3, //动画整体 延迟
  ease: "bounce.out", // 缓冲效果
}); 
```

![Dec-30-2024 15-42-46.gif](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/881d8b79259b4c9c85d0511b1cac8f83~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735630982&x-orig-sign=htJS%2Bneue85tKnWyedF8EfQYJIk%3D)
## 移动

### to
```js
    // 移动 从那里出发
    gsap.to(".green", {
       x: 500 ,
       y: 200,
       rotation: 1360, //旋转度数
       duration:3, //动画整体 延迟
       repeat:1, // 
       yoyo:1 // 回弹
    });
```

![Dec-30-2024 15-43-32.gif](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/01b2cc547d5247d7a10b07c6b9be2249~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735631029&x-orig-sign=pqBzYf21vkc8lM8L1J78%2F0CwHnE%3D)

### from

```js

    // 从那里过来
    gsap.from(".green", {
       x: 500 ,
       y: 200,
       rotation: 1360,
       duration:3,
       repeat:1,
       yoyo:1
    }); 

```

![Dec-30-2024 15-44-02.gif](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/4e72a5a3d2044540b1ee5ace554c8b6c~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735631062&x-orig-sign=Z2oA6vWoIcXW1Ed0K7PIaX6F5vk%3D)


### fromTo
y 从 300 到 0 移动
```js

    //从那里到那里 
    gsap.fromTo(".box",{
      y : 300
    } ,{
      duration: 2, 
      y: 0,
      repeat:-1, // 一直循环
      yoyo:true,  
    });
```
![Dec-30-2024 15-44-45.gif](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/bec4912e0f05485294bfd6372e1186e8~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735631099&x-orig-sign=7vMtwSK3EEPWBQd4uGTC265bAcE%3D)

## 时间线
根据配置按顺同步执行
```js
    const t1 = gsap.timeline({defaults: {repeat:2,yoyo:true,rotation:360}});
    t1.to(".green", {
      x: 600,
      duration: 1
    }); 
    t1.to(".orange", {
      x: 600,
      duration: 1,
    } );
    t1.to(".purple", {
      x: 600,
      duration: 1,
    });
```

![Dec-30-2024 15-46-28.gif](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/bf712552834e4e53aa7763663b97e5d7~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735631202&x-orig-sign=2az5UY8z0z29zqmDdxX7174ZOn0%3D)


### 时间线 参数控制先后

```js
  // 时间参数 ，控制动画的执行顺序 相对于上一个时间。 
const t1 = gsap.timeline();
t1.to(".green", {  x: 600,   duration: 5  }); 
t1.to(".orange", {  x: 600,   duration: 1  }, '<'); // 相对于上一个green
t1.to(".purple", {  x: 600,   duration: 1  }, '-=3');    // 相对于上一个 orange 提前3秒，即2秒开发
```
![Dec-30-2024 17-32-10.gif](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/24b7439daa9745c5ae625d5020fc5160~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735637575&x-orig-sign=Wmp6eUpUn7MxXwi%2BsmwzPEN92c8%3D)



### 回调事件

```js
//时间线所有动画结束时调用
    const t1 = gsap.timeline({duration: 1 ,onComplete: tlComplete});  //这里的duration 是延迟多久后执行
    function tlComplete() {
      console.log("all is complete"); 
    }

    t1.to(".green", {
      x: 300, 
      onComplete: () => console.log("the green is complete")
    }) 

    t1.to(".orange", {
      x: 200,
      onComplete: () => console.log("the orange is complete")
    }) 
    t1.to(".purple", {
      x: 150,
      onComplete: () => console.log("the purple is complete")
    }) 
```


![Dec-30-2024 15-48-52.gif](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/f7706eda0ef749f0904408268d716a1d~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735631343&x-orig-sign=cN5xYBnXIKDrGRQOxfnUq2WQXW4%3D)


## 对象控制
可以传入对象，动态获取变化的值，相当于通过返回参数 自己实现视图的逻辑
```js
   let obj = { myNum: 10, myColor: "red" };
    gsap.to(obj, {
      myNum: 200,
      myColor: "blue",
      onUpdate: () => console.log(obj.myNum, obj.myColor)
    });
```


![Dec-30-2024 15-48-31.gif](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/5d73d01441994e52b35206cd8f390b34~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735631323&x-orig-sign=62XIwHxVG5lA11v9WP0WHEfa2jg%3D)

# 进阶

  

## 滚动库
要实现鼠标滚动配合动画，需要额外引入 `ScrollTrigger.min.js`这个库
由于要测试滚动，所以要在头尾都添加添加一个特别长的内容，才能出现滚动条来测试滚动
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.6.0/gsap.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.6.0/ScrollTrigger.min.js"></script>
</head>
<style>
 
#header {
  margin-top: 2000px;
}
#footer {
 margin-bottom: 2000px;
} 
.gsap {
  color: #000;
  position: relative;
  box-sizing: border-box;
  padding: 20px;
  display: flex;
  border: 1px solid #000;
  justify-content: center;
  flex-direction: column;
  align-items: center;
} 

.gsap .box {
  display: block;
  width: 70px;
  height: 70px;
  margin: 10px;
  border-radius: 12px;
  line-height: 70px;
  text-align: center;
  color: #fff;
  font-size: 16px
}
.gsap .green {
  border: 1px solid green
}
.gsap .red {
  border: 1px solid red
}
.gsap .blue {
  border: 1px solid blue
}
.gsap .purple {
  border: 1px solid purple
}
.gsap .orange {
  border: 1px solid orange
}
.gsap .box.active {
  background-color: red;
}
 
</style>
<body> 
  <div id="header">
  </div>
  <div class="gsap">
    <div class="box green"></div>
    <div class="box purple"></div>
     <div class="box orange"></div>
  </div>
  <div id="footer">
  </div>
  <script>
 
  </script>
</body>

</html>
```



![image.png](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/3206c6e464c94f9ea32714ceba4aea96~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735633029&x-orig-sign=6qW6YVva1uFYOmzhNR6FHpQuXPw%3D)

## ScrollTrigger.create

重要的参数：
- animation：对应的时间线
- markers：是否打开调试模式
- trigger：需要绑定滚动的元素
- scrub：只有打开才会跟鼠标滚动同步 
- start ：两个参数， 注意 start ：top center 第一个参数 top 是指traget的检测边距，第二个参数是指 浏览器的检测边距center，当两者相交后触发。
- end ： 两个参数， 对应动画结束的位置，bottom为target元素的底部，center为浏览器的中间为检查线。


![Dec-30-2024 16-58-54.gif](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/8efc852262954a8eb6da55345d290176~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735635557&x-orig-sign=pRifLoO7nfe9L%2BNE0S%2FG%2Bx0P6wE%3D)
```js 
ScrollTrigger 写法 
let tl2 = gsap.timeline()
tl2.to('.green', {scale: 2, duration: 1})
ScrollTrigger.create({
    animation: tl2,
    markers: true,
    start: "top center", // top为target元素的顶部，center为浏览器的中间位置
    end: "bottom center", //bottom为target元素的顶部，center为浏览器的中间位置
    trigger: ".gsap", // 整个 div.gsap为触发对象
    scrub: true, // 是否与鼠标同步
    pin: false, // 是否触发时，动画固定不动
});
```

我们可以看到当触发 整个div.gsap元素的top与浏览器中线相交时候，触发滚动逻辑。动画开始跟鼠标同步播放。
注意：动画变大后是不会还原，但是当鼠标回滚的时候会还原

## pin 固定

![Dec-30-2024 17-00-11.gif](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/a9b5ca1784dd44a2ae62151f824f75ef~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735635629&x-orig-sign=HEXn0b%2BbzGrnlzG8jFJ1SLZASN4%3D)
```js
let tl2 = gsap.timeline()
tl2.to('.green', {scale: 2, duration: 1})
ScrollTrigger.create({
  animation: tl2,
  markers: true,
        start: "top center",
        end: "bottom center",
        trigger: ".gsap",
        scrub: true,
        pin: true,
});
```
当我们设置pin：true后 当触发动画时，内容会一直固定在触发的位置，直到动画结束
## 特别长的滚动

![Dec-30-2024 17-00-54.gif](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/0dd86519c0b04d929505f9110417306f~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735635671&x-orig-sign=LYaBZbEimaKqZnkBwRJVFmHKeB4%3D)
可以通过start/end设置，来实现特别长的滚动效果
### start
- "top -100px" //元素顶部要超过顶部100px才出发
- "100px center" //元素顶部接触浏览器中线后100px才触发
### end
- "+=5000px" 等价于 5000px center
- "+=5000px" 等价于 top + 5000px center 就是元素顶部接触浏览器中线后 要经过5000px才触发
```js

let tl1 = gsap.timeline()
tl1.to('.purple', {scale: 2, duration: 1})
ScrollTrigger.create({
  animation: tl1,
        markers: true,
        start: "top center", 
        end: "+=5000px", // 当前的top 再加上 5000px 的距离
        trigger: ".gsap",
        scrub: true,
        pin: ".gsap",
});

```

##  gsap trigger写法 
```js
 gsap.to(".purple", {
      rotation: 360, 
      backgroundColor: "orange",
      scrollTrigger: {
        markers: true,
        start: "top center",
        end: "bottom center",
        trigger: ".purple",
        scrub: 1,
      },
    });
```

##  样式开关

![Dec-30-2024 17-01-44.gif](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/eb0013596f364d4f97e302178e466b36~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735635717&x-orig-sign=GgTjlYqwG3CIS3QnUj9GdLGEwG8%3D)
```js 
gsap.to(".green", {
    scrollTrigger: {
    trigger: ".green",
    start: "top center",
    end: "bottom center",
    markers: true,
    scrub: true,
    toggleClass: {
        targets: ".green",
        className: "active", // 激活时候背景为红色
    }
    }, 
    duration: 1000, // 这里延迟意义不大，是根据实际滚动的帧来决定时间  
});

```

## 多个动画时间线

![Dec-30-2024 17-02-18.gif](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/b5b13aeb675c4f42b81da6f07470ea83~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735635753&x-orig-sign=L1v3iCHgw%2FG%2FBqn%2BAgX2jed7EdM%3D)

```js
const tl = gsap.timeline({
    scrollTrigger: {
    trigger: ".green",
    scrub: true,
    markers: true,
    start: "top center",
    end: "bottom center",
    },
});
tl.to(".green", {
    x: 100,
    scale: 1.5,
});
tl.to(".purple", {
    scale: 2,
    x: 200,
});
tl.to(".orange", {
    scale: 2.5,
    x: 300,
});
```

# 视频控制
通过currentTime参数控制视频
```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.6.0/gsap.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.6.0/ScrollTrigger.min.js"></script>
  <link href="./gsap.css" rel="stylesheet">
</head>
<style>
  #header {
    margin-top: 2000px;
  }

  #footer {
    margin-bottom: 2000px;
  }

  .gsap {
    color: #000;
    position: relative;
    box-sizing: border-box;
    padding: 20px;
    display: flex;
    border: 1px solid #000;
    justify-content: center;
    flex-direction: column;
    align-items: center;
  } 
</style>

<body>
  <div id="header">
  </div>
  <div class="gsap">
    <video muted="" webkit-playsinline="" playsinline="" preload="auto" name="media" class="myvideo"
      poster="https://www.google.com/images/branding/googlelogo/1x/googlelogo_light_color_272x92dp.png">
      <source src="https://test-videos.co.uk/vids/bigbuckbunny/mp4/av1/360/Big_Buck_Bunny_360_10s_1MB.mp4"
        type="video/mp4">
    </video>
  </div>
  <div id="footer">
  </div>

  <script>
    var tl3 = gsap.timeline(); 
    ScrollTrigger.create({
      trigger: '.gsap',
      animation: tl3,
      start: 'top center',
      end: "bottom center",
      pin: true,
      scrub: true,
      markers: true
    })

    //移动端兼容处理 
    var video1 = document.querySelector('.myvideo');
    if (window.innerWidth < 1200) {
      video1.play().then(function () {
        video1.pause();
      })
    }
    tl3.to(video1, {
      currentTime: video1.duration || 10,
      ease: "none",
      duration: 10
    })
  </script>
</body>

</html>
```
![Dec-30-2024 17-57-17.gif](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/d8d63814e09449e8a7cd96c8c1196b6e~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735639099&x-orig-sign=8pjIYifDx%2BGe46w5NfbaWfj%2FAXw%3D)

# swiper + 滚动
通过动态创建gsap.timeline()并且根据当前显示的宽度动态设置 x的坐标
- 即： x启始位置 =  当前浏览器宽度 - 实际元素的x - 实际元素的宽度/2 
- 使用fromTo进行动画移动效果 
```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.6.0/gsap.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.6.0/ScrollTrigger.min.js"></script>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/swiper@latest/swiper-bundle.min.css">
  <script src="https://cdn.jsdelivr.net/npm/swiper@latest/swiper-bundle.min.js"></script>
  <script src="https://code.jquery.com/jquery-3.6.4.min.js"></script>

</head>
<style>
  #header {
    margin-top: 2000px;
  }

  #footer {
    margin-bottom: 2000px;
  } 

  .main-container {
      position: relative; 
      background: none no-repeat center center;
      background-size: cover;
      height: calc(100vh - 70px);
      color: #fff;
      overflow: hidden; 
  }  
  .container {
      color: #000;
      text-align: center;
      padding: 0 0 1.5em; 
      color: #fff;
  }
  .container .swiper-slide img {
      width: 100%;
      border-radius: 0.28em;
  }
  .container  .wrapper {
      max-width: 800px;
      padding: 0 20px; 
  }
  .container .swiper-container {
      padding: 0.74em 0;
  }
  .main-container .swiper-pagination {
      top: auto !important;
      bottom: 0;
      left: 50% !important;
      transform: translateX(-50%);
      max-width: 24%;
      background-color: #EFEDE9;
      height: 3px;
  }  
</style>

<body>
  <div id="header">
  </div> 
  <div class="main-container container">
    <div style="position: relative;">
        <div class="wrapper">
            <div class="swiper-container">
                <div class="swiper-wrapper">
                    <div class="swiper-slide swiper-slide1">
                        <img src="https://picsum.photos/200" alt="">
                    </div>
                    <div class="swiper-slide swiper-slide2">
                        <img src="https://picsum.photos/200" alt="">
                    </div>
                    <div class="swiper-slide swiper-slide3">
                        <img src="https://picsum.photos/200" alt="">
                    </div>
                    <div class="swiper-slide swiper-slide4">
                        <img src="https://picsum.photos/200" alt="">
                    </div>
                    <div class="swiper-slide swiper-slide5">
                        <img src="https://picsum.photos/200" alt="">
                    </div>
                    <div class="swiper-slide swiper-slide6">
                        <img src="https://picsum.photos/200" alt="">
                    </div>
                    <div class="swiper-slide swiper-slide7">
                        <img src="https://picsum.photos/200" alt="">
                    </div>
                    <div class="swiper-slide swiper-slide8">
                        <img src="https://picsum.photos/200" alt="">
                    </div>
                </div>
                <div class="swiper-pagination"></div>
            </div>
        </div>
        <span class="icon-arrow-right arrow-left"></span>
        <span class="icon-arrow-right arrow-right"></span>
    </div>
  </div>

  <div id="footer">
  </div>

  <script>
 
      var mySwiper = new Swiper('.container .swiper-container', {
          slidesPerView: 6,
          slidesPerGroup: 6,
          spaceBetween: 15,
          pagination: {
              el: '.container .swiper-pagination',
              type : 'progressbar',
          },
          breakpoints: {
              1023: {
                  slidesPerView: 4,
                  slidesPerGroup: 4,
              },
              767: {
                  slidesPerView: 3,
                  slidesPerGroup: 3,
              }
          },
          navigation: {
              nextEl: '.container .arrow-right',
              prevEl: '.container .arrow-left',
          },
      })
      var num = 6;
      // if($(window).width() < 1023) { // 可以根据当前浏览器的宽度进行判断
      //     num = 4;
      // } 

      for(i = 1;i<=num;i++){
          window['timelineItem'+ i] =  gsap.timeline()
          window['timelineItem'+ i].fromTo('.container .swiper-slide'+i, { x: $(window).width()/2 - $('.container .swiper-slide'+i).offset().left - $('.container .swiper-slide').width()/2 },
          { x: 0 })
          .to('.container .icon-arrow-right', { display: 'block' });
          ScrollTrigger.create({
              trigger: '.container',
              animation: window['timelineItem'+ i],
              start: 'top center',
              end: "bottom top",
              pin: true,
              scrub: true,
              markers :true
          })
      }
  </script>
</body>

</html>
```

![Dec-31-2024 09-49-42.gif](https://p0-xtjj-private.juejin.cn/tos-cn-i-73owjymdk6/3dc0e1deaf3b4894a313b2ca76e4f5fa~tplv-73owjymdk6-jj-mark-v1:0:0:0:0:5o6Y6YeR5oqA5pyv56S-5Yy6IEAgamFzb25feWFuZw==:q75.awebp?policy=eyJ2bSI6MywidWlkIjoiMjk3MjcwNDc5NTgwMjY1MyJ9&rk3s=e9ecf3d6&x-orig-authkey=f32326d3454f2ac7e96d3d06cdbb035152127018&x-orig-expires=1735696230&x-orig-sign=ROs%2FWD9WSzYtfll7j2tmgKXnTko%3D)

# 文章地址
https://juejin.cn/spost/7454203462836551734

# 源码地址
https://github.com/mjsong07/gsap_demo.git