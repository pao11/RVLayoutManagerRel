[![](https://jitpack.io/v/pao11/RVLayoutManagerRel.svg)](https://jitpack.io/#pao11/RVLayoutManagerRel)
[![Travis](https://img.shields.io/badge/Gradle-2.3.1-brightgreen.svg)]()

#概述
自定义RecyclerView的LayoutManager。

####注意!!!
在定义样式item样式的时候请确保每个子view的大小相同，暂不支持不同大小的子view

##Gradle 增加引用
```
compile 'com.github.pao11:RVLayoutManagerRel:v1.0.0'
```
##Usage 使用
```
   1、如果想自定义layoutManager，继承ViewPagerLayoutManager，
        重写protected float setInterval()方法，返回一个item的大小。
        重写protected void setItemViewProperty(View itemView, float targetOffset)方法，用于实现各种特效。
        
   2、内置几个自定义的LayoutManager，使用效果如下：
        circleLayoutManager = new CircleLayoutManager();//环形滚动，不带放大效果
        circleScaleLayoutManager = new CircleScaleLayoutManager();//环形滚动，带放大效果
        scaleLayoutManager = new ScaleLayoutManager(Dp2px(10));//横向滚动，带放大效果
        galleryLayoutManager = new GalleryLayoutManager(Dp2px(10));//横向滚动，gallery效果
        elevateScaleLayoutManager = new ElevateScaleLayoutManager(Dp2px(-100));//横向滚动，带放大效果
        rotateLayoutManager = new RotateLayoutManager(Dp2px(50), 180);//横向滚动，带旋转效果
        recyclerView.addOnScrollListener(new CenterScrollListener());//启动回弹
        recyclerView.setAdapter(new Adapter());
        circleLayoutManager.setEnableEndlessScroll(true);//无限滚动
        elevateScaleLayoutManager.setEnableEndlessScroll(true);//无限滚动
        //滚动监听
        elevateScaleLayoutManager.setOnPageChangeListener(new ViewPagerLayoutManager.OnPageChangeListener() {
            @Override
            public void onPageSelected(int position) {
                Toast.makeText(MainActivity.this, "pageSelected===" + position, Toast.LENGTH_SHORT).show();
            }

            @Override
            public void onPageScrollStateChanged(int state) {

            }
        });
```
##更新记录

 **v1.0.0**　`2017.10.20`　发布第一个版本--SDK VERSION 23.2.0

## License

```
Copyright 2017 pao11

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
