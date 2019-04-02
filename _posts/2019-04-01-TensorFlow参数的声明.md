---
layout:     post
title:      TensorFlow参数的声明
date:       2019-04-01
author:     Jericho
header-img: img/article-pic/123125.jpg
catalog: false
categories: Technology
tags:
    - TensorFlow
    - Python
---
#### 生成0和1矩阵
    v1 = tf.Variable(tf.zeros([3, 3, 3]), name="v1")
    v2 = tf.Variable(tf.ones([2, 5]), name="v2")

###### 输出
    v1:
    [[[0. 0. 0.]
      [0. 0. 0.]
      [0. 0. 0.]]

    [[0. 0. 0.]
     [0. 0. 0.]
     [0. 0. 0.]]

    [[0. 0. 0.]
     [0. 0. 0.]
     [0. 0. 0.]]]

    v2:
    [[1. 1. 1. 1. 1.]
	 [1. 1. 1. 1. 1.]]

#### 填充单值矩阵
	v3 = tf.Variable(tf.fill([2, 3], 9))

###### 输出
	v3:
	[[9 9 9]
	 [9 9 9]]

#### 常量矩阵
	v4_1 = tf.constant([1, 2, 3, 4, 5, 6, 7])
	v4_2 = tf.constant(-1.0, shape=[2, 3])

###### 输出
    v4_1:
    [1 2 3 4 5 6 7]

    v4_2:
    [[-1. -1. -1.]
     [-1. -1. -1.]]

#### 生成等差数列
    v5 = tf.linspace(10.0, 12.0, 30, name="linspace")  # float32 or float64
    v6 = tf.range(10, 20, 3)  # just int32

###### 输出
    v5:
    [10.        10.068966  10.137931  10.206897  10.275862  10.344828
	 10.413794  10.4827585 10.551724  10.620689  10.689655  10.75862
	 10.827586  10.896552  10.965517  11.034483  11.103448  11.172414
	 11.241379  11.310345  11.379311  11.448276  11.5172415 11.586206
	 11.655172  11.724138  11.793103  11.862069  11.931034  12.       ]

	v6:
	[10 13 16 19]

#### 生成各种随机数据矩阵
	v7_1 = tf.Variable(tf.random_uniform([2, 4], minval=0.0, maxval=2.0, dtype=tf.float32, seed=1234, name="v7_1"))
	v7_2 = tf.Variable(tf.random_normal([2, 3], mean=0.0, stddev=1.0, dtype=tf.float32, seed=1234, name="v7_2"))
	v7_3 = tf.Variable(tf.truncated_normal([2, 3], mean=0.0, stddev=1.0, dtype=tf.float32, seed=1234, name="v7_3"))
	v7_4 = tf.Variable(tf.random_uniform([2, 3], minval=0.0, maxval=1.0, dtype=tf.float32, seed=1234, name="v7_4"))
	v7_5 = tf.random_shuffle([[1, 2, 3], [4, 5, 6], [6, 6, 6]], seed=134, name="v7_5")

###### 输出
	v7_1:
	[[1.696614   0.64714265 0.6134002  0.13939953]
     [1.827713   0.34095812 0.5667424  0.7125411 ]]

    v7_2
    [[ 0.51340485 -0.255814    0.6519913 ]
     [ 1.3923638   0.37256798  0.20336303]]

    v7_3
    [[ 0.51340485 -0.255814    0.6519913 ]
     [ 1.3923638   0.1662533  -0.9161797 ]]

    v7_4
    [[0.848307   0.32357132 0.3067001 ]
     [0.06969976 0.9138565  0.17047906]]

    v7_5
    [[4 5 6]
     [6 6 6]
     [1 2 3]]