---
layout:     post
title:      SpringBoot配置虚拟路径解决Not allowed to load local resource错误
date:       2019-05-06
author:     Jericho
header-img: img/article-pic/342160.jpg
catalog: false
categories: Technology
tags:
    - Java
    - SpringBoot
---

#### 新增配置文件

    @Configuration
    public class MyWebAppConfiguration extends WebMvcConfigurerAdapter {
        /**
         * 添加一些虚拟路径的映射
         * 静态资源路径和上传文件的路径
         *
         * @param registry
         */
        @Override
        public void addResourceHandlers(ResourceHandlerRegistry registry) {
            /**
             * @Description: 对文件的路径进行配置, 创建一个虚拟路径/path/** ，即只要在< img src="/Path/picName.jpg" />便可以直接引用图片
             *这是图片的物理路径  "file:/+本地图片的地址"
             */
            registry.addResourceHandler("/path/**").addResourceLocations("file:/D:/files/");
            super.addResourceHandlers(registry);
        }
    }

其中addResourceHandler指的是对外暴露的路径，而addResourceLocations是文件真正放的位置。
