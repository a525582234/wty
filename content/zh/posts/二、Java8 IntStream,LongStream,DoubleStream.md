---
title:  二、Java8 IntStream,LongStream,DoubleStream
date: 2022-02-18T16:32:06+09:00
description:  二、Java8 IntStream,LongStream,DoubleStream
draft: false
hideToc: false
enableToc: true ##侧边栏目录
enableTocContent: false ##文章内部的目录
author: wty                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                
authorEmoji: 😊
tags:
- java8
categories:
- Java ##series:-Themes Guide
image: /images/feature1/img.png
---

## 引言

本章节我们提供一些 Java 8 中的 IntStream、LongStream 和 DoubleStream 使用范例。IntStream、LongStream 和 DoubleStream 分别表示原始 int 流、 原始 long 流 和 原始 double 流。

这三个原始流类提供了大量的方法用于操作流中的数据，同时提供了相应的静态方法来初始化它们自己。

这三个原始流类都在 java.util.stream 命名空间下。

## java.util.stream.IntStream

java.util.stream.IntStream 是一个原始整数值序列 ( sequence ) 。该流提供了许多方法可以对该流中的元素顺序执行或并行执行一些聚合操作，比如 max() 或 average()

## 聚合方法

| 方法             | 说明                                       |
| ---------------- | ------------------------------------------ |
| rangeClosed(a,b) | 返回子序列 [a,b]，包含起始值，增长步值为 1 |
| range(a,b)       | 返回子序列 [a,b)，左闭右开，意味着不包括 b |
| sum              | 计算所有元素的总和                         |
| sorted           | 排序元素                                   |

这些方法使用示例如下

```java
IntStreamDemo.java
package com.souyunku.tech.util.stream;
import java.util.stream.IntStream;
public class IntStreamDemo {
    public static void main(String[] args) {
        System.out.println("--Using IntStream.rangeClosed--");
        IntStream.rangeClosed(13, 15).map(n->n*n).forEach(s->System.out.print(s +" "));
        System.out.println("\n--Using IntStream.range--");
        IntStream.range(13,15).map(n->n*n).forEach(s->System.out.print(s +" "));
        System.out.println("\n--Sum of range 1 to 10--");
        System.out.print(IntStream.rangeClosed(1,10).sum());
        System.out.println("\n--Sorted number--");
        IntStream.of(13,4,15,2,8).sorted().forEach(s->System.out.print(s +" "));
    }
}
运行结果如下

--Using IntStream.rangeClosed--
169 196 225 
--Using IntStream.range--
169 196 
--Sum of range 1 to 10--
55
--Sorted number--
2 4 8 13 15 
```

## LongStream

java.util.stream.LongStream是一个原始长整型值序列 ( sequence ) 。该流提供了许多方法可以对该流中的元素顺序执行或并行执行一些聚合操作。其实，它的使用方式和 IntStream 一样，因为提供的方法也一样，我们就不做展开了，直接看范例

```java
package com.souyunku.tech.util.stream;
import java.util.stream.LongStream;
public class LongStreamDemo {
    public static void main(String[] args) {
        System.out.println("--Using LongStream.rangeClosed--");
        LongStream.rangeClosed(13, 15).map(n->n*n).forEach(s->System.out.print(s +" "));
        System.out.println("\n--Using LongStream.range--");
        LongStream.range(13,15).map(n->n*n).forEach(s->System.out.print(s +" "));
        System.out.println("\n--Sum of range 1 to 10--");
        System.out.print(LongStream.rangeClosed(1,10).sum());
        System.out.println("\n--Sorted number--");
        LongStream.of(13,4,15,2,8).sorted().forEach(s->System.out.print(s +" "));
    }
} 
输出结果如下

--Using LongStream.rangeClosed--
169 196 225 
--Using LongStream.range--
169 196 
--Sum of range 1 to 10--
55
--Sorted number--
2 4 8 13 15 
DoubleStream
```

java.util.stream.LongStream 是一个原始双精度浮点型序列 ( sequence ) 。该流提供了许多方法可以对该流中的元素顺序执行或并行执行一些聚合操作。它的使用方式和 IntStream 一样，提供的方法也一样，除此之外，还额外提供了几个聚合方法

| 方法    | 说明       |
| ------- | ---------- |
| average | 计算平均值 |
| max     | 查找最大值 |

下面的代码是 DoubleStream 类的一些简单的使用示例

```java
package com.souyunku.tech.util.stream;
import java.util.function.DoublePredicate;
import java.util.stream.DoubleStream;
public class DoubleStreamDemo {
    public static void main(String[] args) {
        System.out.println("--Using DoubleStream.of--");
        DoubleStream.of(5.33,2.34,5.32,2.31,3.51).map(d->d*1.5).forEach(s->System.out.print(s +" "));
        System.out.println("\n--Using DoubleStream.average--");
        double val = DoubleStream.of(12.1,11.2,13.3).average().getAsDouble();
        System.out.println(val);
        System.out.println("--Using DoubleStream.max--");
        val = DoubleStream.of(12.1,11.2,13.3).max().getAsDouble();
        System.out.println(val);
        System.out.println("--Using DoubleStream.filter--");
        DoublePredicate range = d -> d > 12.11 && d < 12.99;        
        DoubleStream.of(12.1,11.2,12.3).filter(range).forEach(d->System.out.print(d));
    }
}
输出结果如下

--Using DoubleStream.of--
7、995 3.51 7.98 3.465 5.265 
--Using DoubleStream.average--
12、200000000000001
--Using DoubleStream.max--
13、3
--Using DoubleStream.filter--
12、3 
```

