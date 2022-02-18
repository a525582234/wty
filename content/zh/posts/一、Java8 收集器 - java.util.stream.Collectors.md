---
title:  一、Java8 收集器 - java.util.stream.Collectors
date: 2022-02-18T16:32:06+09:00
description:  一、Java8 收集器 - java.util.stream.Collectors
draft: false
hideToc: false
enableToc: true ##侧边栏目录
enableTocContent: false ##文章内部的目录
author: wty                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                
authorEmoji: 😀
tags:
- java8
categories:
- Java ##series:-Themes Guide
image: /images/feature1/img.png
---

## Java

Java 8 流的新类 java.util.stream.Collectors 实现了 java.util.stream.Collector 接口，同时又提供了大量的方法对流 ( stream ) 的元素执行 map and reduce 操作，或者统计操作。

## Collectors.averagingDouble()

Collectors.averagingDouble() 方法将流中的所有元素视为 double 类型并计算他们的平均值。该方法返回的是同一个 Collectors 实例，因此可以进行链式操作。

Collectors.averagingDouble() 接受一个参数，这个参数是一个 lambda 表达式，用于对所有的元素执行一个 map 操作。

Java 所有集合的 stream().collect() 可以接受一个收集器实例作为其参数并返回该收集器的计算结果

例如下面的代码，collect() 方法会把所有的元素收集起来然后传递给 Collectors.averagingDouble(d->d*2) 收集器，对每个元素执行 *2 操作后计算平均值。

```java
package com.souyunku.tech.util.stream;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;
public class AveragingDoubleExample {
    public static void main(String[] args) {
        List<Integer> list = Arrays.asList(1,2,3,4);
        Double result = list.stream().collect(Collectors.averagingDouble(d->d*2));
        System.out.println(result);
    }
}
输出结果为 5.0
```

## Collectors.averagingInt()

Collectors.averagingInt() 方法和 Collectors.averagingDouble() 一样，不同的是它把流中的所有元素看成是 int类型，并返回一个浮点类型的平均值

```java
package com.souyunku.tech.util.stream;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;
public class AveragingIntExample {
    public static void main(String[] args) {
        List<Integer> list = Arrays.asList(1,2,3,4);
        Double result = list.stream().collect(Collectors.averagingInt(v->v*2));
        System.out.println(result);
    }
}
输出结果为 5.0
```

## Collectors.averagingLong()

Collectors.averagingLong() 方法也和 Collectors.averagingDouble() 类似，不同的是它把流中的所有元素看成是 long类型，并返回一个 double类型的平均值

```java
package com.souyunku.tech..util.stream;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;
public class AveragingLongExample {
    public static void main(String[] args) {
        List<Integer> list = Arrays.asList(1,2,3,4);
        Double result = list.stream().collect(Collectors.averagingLong(v->v*2));
        System.out.println(result);
    }
}
输出结果为 5.0	
```

## Collectors.collectingAndThen()

`Collectors.collectingAndThen()` 函数应该最像 `map and reduce` 了，它可接受两个参数，第一个参数用于 `reduce`操作，而第二参数用于 `map`操作。

也就是，先把流中的所有元素传递给第二个参数，然后把生成的集合传递给第一个参数来处理。

例如下面的代码，先把 `[1,2,3,4]` 这个集合传递给 `s-> s*s lambda` 表达式，计算得出结果为`[1,4,9,16]` ，然后再把 `[1,4,9,16]`传递给 `v->v*2` 表达式，计算得出 `[2,8,18,32]` ，然后传递给 `Collectors.averagingLong()` 计算得到结果为 `25.0`

```java
package com.souyunku.tech..util.stream;

import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;
public class CollectingAndThenExample {
    public static void main(String[] args) {
        List<Integer> list = Arrays.asList(1,2,3,4);
        Double result = list.stream().collect(Collectors.collectingAndThen(Collectors.averagingLong(v->v*2),
                s-> s*s));
        System.out.println(result);
    }
} 
```

## Collectors.counting()

Collectors.counting() 用于统计流中元素的个数。

```java
package com.souyunku.tech.util.stream;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;
public class CountingExample {
    public static void main(String[] args) {
        List<Integer> list = Arrays.asList(1,2,3,4);
       long result=  list.stream().collect(Collectors.counting());
       System.out.println(result);
    }
}
输出结果为 4
```

## Collectors.joining()

Collectors.joining() 方法用某个指定的拼接字符串把所有元素拼接成一个字符串，并添加可选的前缀和后缀

```java
package com.souyunku.tech.util.stream;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;
public class JoiningExample {
    public static void main(String[] args) {
       List<String> list = Arrays.asList("A","B","C","D");
       String result=  list.stream().collect(Collectors.joining(",","(",")"));
       System.out.println(result);
    }
}
输出结果为 (A,B,C,D)
```

Collectors.maxBy() 和 Collectors.minBy()
Collectors.maxBy() 和Collectors.minBy() 两个方法分别用于计算流中所有元素的最大值和最小值。

两个方法都可以接受一个比较器作为参数，用于如何计算最大值或最小值

```java
package com.souyunku.tech.util.stream;
import java.util.Arrays;
import java.util.Comparator;
import java.util.List;
import java.util.stream.Collectors;
public class MaxByMinByExample {
    public static void main(String[] args) {
       List<Integer> list = Arrays.asList(30,10,20,35);
       //Get Max       
       list.stream().collect(Collectors.maxBy(new MaxByMinByExample().new IntegerComp()))
               .ifPresent(i->System.out.println(i));
       //Get Min
       list.stream().collect(Collectors.minBy(new MaxByMinByExample().new IntegerComp()))
               .ifPresent(i->System.out.println(i));
    }
    class IntegerComp implements Comparator<Integer> {
        @Override
        public int compare(Integer i1, Integer i2) {
          if(i1 >=i2 ){
              return 1;
          }else{
              return -1;
          }
        }
    }
}
输出结果如下

35
10
```

## Collectors.summingInt()

Collectors.summingInt() 方法将流中的所有元素视为 int类型，并计算所有元素的总和 ( sum )

```java
package com.souyunku.tech.util.stream;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;
public class SummingIntExample {
    public static void main(String[] args) {
       List<Integer> list = Arrays.asList(30,10,20,35);
       int result = list.stream().collect(Collectors.summingInt(i->i));
       System.out.println(result);
    }
}
输出结果我为 95
```

## Collectors.summingLong()

Collectors.summingLong() 将流中的所有元素视为 long类型，并计算所有元素的总和

```java
package com.souyunku.tech.util.stream;
import java.util.ArrayList;
import java.util.List;
import java.util.stream.Collectors;
public class SummingLongExample {
    public static void main(String[] args) {
       List<Long> list = new ArrayList<>();
       list.add((long)340);
       list.add((long)240);
       list.add((long)360);
       long result = list.stream().collect(Collectors.summingLong(l->l));
       System.out.println(result);
    }
}
```

## Collectors.summingDouble()

Collectors.summingDouble() 将流中的所有元素视为 double类型，并计算所有元素的总和

```java
package cn.util.stream;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;
public class SummingDoubleExample {
    public static void main(String[] args) {
       List<Double> list = Arrays.asList(340.5,234.56,672.76);
       Double result = list.stream().collect(Collectors.summingDouble(d->d));
       System.out.println(result);
    }
}
输出结果为 1247.82
```

也许你也注意到了，这三个函数的结果的类型，就是它们如何看待元素的类型。

## Collectors.toList()

Collectors.toList() 将流中的所有元素导出到一个列表( List )中

```java
package com.souyunku.tech.util.stream;
import java.util.List;
import java.util.stream.Collectors;
import java.util.stream.Stream;
public class ToListExample {
    public static void main(String[] args) {
       List<String> list = Stream.of("AA","BB","CC").collect(Collectors.toList());
       list.forEach(s->System.out.println(s));
    }
}
输出结果如下

AA
BB
CC
```

## Collectors.toSet()

Collectors.toSet()把流中的所有元素导出到一个集合 ( Set )中，并排除重复的元素 ( Set 的特性 )

```java
package com.souyunku.tech.util.stream;
import java.util.Set;
import java.util.stream.Collectors;
import java.util.stream.Stream;
public class ToSetExample {
    public static void main(String[] args) {
       Set<String> set = Stream.of("AA","AA","BB").collect(Collectors.toSet());
       set.forEach(s->System.out.println(s));
    }
}
输出结果为

AA
BB
```

## Collectors.toMap()

Collectors.toMap() 将流中的所有元素导出到一个哈希表 ( Map ) 中。该方法接受两个参数，第一个参数用于生成键 ( key ) ，第二个参数用于生成值 ( value )。两个参数都是 Lambda 表达式。

```java
package com.souyunku.tech.util.stream;
import java.util.Map;
import java.util.stream.Collectors;
import java.util.stream.Stream;
public class ToMapExample {
    public static void main(String[] args) {
       Map<String,String> map = Stream.of("AA","BB","CC").collect(Collectors.toMap(k->k, v->v+v));
       map.forEach((k,v)->System.out.println("key:"+k +"  value:"+v));
    }
输出结果为

key:CC  value:CCCC
key:BB  value:BBBB
key:AA  value:AAAA
```

## Collectors.mapping()

Collectors.mapping() 一般用于多重 map and reduce 中。 Java 文档中描述的原型如下

mapping(Function<? super T,? extends U> mapper, Collector<? super U,A,R> downstream)
第一个参数用于 map ，第二个参数用于 reduce

```java
package com.souyunku.tech.util.stream;
import java.util.ArrayList;
import java.util.List;
import java.util.Map;
import java.util.stream.Collectors;
public class MappingDemo {
    public static void main(String[] args) {
        List<Person> list = Person.getList();
        Map<Integer, String> nameByAge
           = list.stream().collect(Collectors.groupingBy(Person::getAge, 
                   Collectors.mapping(Person::getName, Collectors.joining(","))));
        nameByAge.forEach((k,v)->System.out.println("Age:"+k +"  Persons: "+v));
    }   
}
class Person {
    private String name;
    private int age;
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public String getName() {
        return name;
    }
    public int getAge() {
        return age;
    }
    public static List<Person> getList() {
        List<Person> list = new ArrayList<>();
        list.add(new Person("Ram", 30));
        list.add(new Person("Shyam", 20));
        list.add(new Person("Shiv", 20));
        list.add(new Person("Mahesh", 30));
        return list;
    }
} 
输出结果如下

Age:20  Persons: Shyam,Shiv
Age:30  Persons: Ram,Mahesh
```

