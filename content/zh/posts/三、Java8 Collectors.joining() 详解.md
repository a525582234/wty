---
title: 三、Java8 Collectors.joining() 详解
date: 2022-02-18T16:32:06+09:00
description:  三、Java8 Collectors.joining() 详解
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

本章节我们来详细讲讲 Java 8 流 ( stream ) 收集器 ( Collectors ) 中的 joining() 方法。该方法会返回一个 Collectors 实例，方便在流收集器上的链式操作。

Collectors.joining() 方法以遭遇元素的顺序拼接元素。我们可以传递可选的拼接字符串、前缀和后缀

## joinning() 方法定义

假设我们的流中有四个元素["A","B","C","D"]，那么我们就可以按照以下方式来收集它们

## joining()

joinning()无参数方法会返回一个 Collectors 实例，并且以空字符串 ( “” ) 来拼接收集到的所有元素

```java
package com.souyunku.tech.util.stream;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;
public class JoiningExample {
    public static void main(String[] args) {
       List<String> list = Arrays.asList("A","B","C","D");
       String result=  list.stream().collect(Collectors.joining());
       System.out.println(result);
    }
}
输出结果为 ABCD
```

## joining(CharSequence delimiter)

joining(CharSequence delimiter)接受一个参数字符串序列作为拼接符，并返回一个 Collectors 实例。假如我们传递的拼接符为 “-” 。那么输出结果为A-B-C-D

```java
package com.souyunku.tech.util.stream;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;
public class JoiningExample {
    public static void main(String[] args) {
       List<String> list = Arrays.asList("A","B","C","D");
       String result=  list.stream().collect(Collectors.joining("-"));
       System.out.println(result);
    }
}
运行结果为 A-B-C-D
```

## joining(CharSequence delimiter, CharSequence prefix, CharSequence suffix)

joining(CharSequence delimiter, CharSequence prefix, CharSequence suffix)方法接受一个字符串序列作为拼接符，并在拼接完成后添加传递的前缀和后缀。假如我们传递的分隔符为 "-"，前缀为 "[" ， 后缀为 "]" 。那么输出结果为[A-B-C-D]

```java
package com.souyunku.tech.util.stream;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;
public class JoiningExample {
    public static void main(String[] args) {
       List<String> list = Arrays.asList("A","B","C","D");
       String result=  list.stream().collect(Collectors.joining("-", "[", "]"));
       System.out.println(result);
    }
}
运行结果为 [A-B-C-D]
```

## 范例

### 范例 1 ： 如果流中的数据是字符串

下面的代码演示了如何使用 joinning() 的三种重载方法来拼接字符串

```java
package com.souyunku.tech.util.stream;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Collectors;
public class JoiningExampleWithListOfString {
    public static void main(String[] args) {
        List<String> list = Arrays.asList("Ram","Shyam","Shiv","Mahesh");
        String result=  list.stream().collect(Collectors.joining());
        System.out.println(result);
        result=  list.stream().collect(Collectors.joining(","));
        System.out.println(result);        
        result=  list.stream().collect(Collectors.joining("-","[","]"));
        System.out.println(result);        
    }       
} 
运行结果为

RamShyamShivMahesh
Ram,Shyam,Shiv,Mahesh
[Ram-Shyam-Shiv-Mahesh] 
```

### 范例 2: 如果流中的数据是对象

如果流中的数据是对象，下面的代码演示了如何拼接它们。

首先，我们创建一个 Person 类

```java
package com.souyunku.tech.util.stream;
import java.util.ArrayList;
import java.util.List;
public class Person {
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
        list.add(new Person("Ram", 23));
        list.add(new Person("Shyam", 20));
        list.add(new Person("Shiv", 25));
        list.add(new Person("Mahesh", 30));
        return list;
    }
} 
```

然后创建一个 Person 对象流

```java
package com.souyunku.tech.util.stream;
import java.util.List;
import java.util.stream.Collectors;
public class JoiningExampleWithListOfObject {
    public static void main(String[] args) {
        List<Person> list = Person.getList();
        System.out.println("--Join person name--");
        String result=  list.stream().map(p -> p.getName()).collect(Collectors.joining());
        System.out.println(result);
        result=  list.stream().map(p -> p.getName()).collect(Collectors.joining("|"));
        System.out.println(result);
        result=  list.stream().map(p -> p.getName()).collect(Collectors.joining("-","[","]"));
        System.out.println(result);

        System.out.println("--Join person age--");
        result=  list.stream().map(p -> String.valueOf(p.getAge())).collect(Collectors.joining());
        System.out.println(result);
        result=  list.stream().map(p -> String.valueOf(p.getAge())).collect(Collectors.joining("|"));
        System.out.println(result);
        result=  list.stream().map(p -> String.valueOf(p.getAge())).collect(Collectors.joining("-","[","]"));
        System.out.println(result);       

        System.out.println("--Join person name-age--");
        result=  list.stream().map(p -> p.getName()+"-" + p.getAge()).collect(Collectors.joining("|"));
        System.out.println(result);
        result=  list.stream().map(p -> p.getName()+"-" + p.getAge()).collect(Collectors.joining("|","[","]"));
        System.out.println(result);        
    }       
} 
运行结果为

--Join person name--
RamShyamShivMahesh
Ram|Shyam|Shiv|Mahesh
[Ram-Shyam-Shiv-Mahesh]

--Join person age--
23202530
23|20|25|30
[23-20-25-30]
--Join person name-age--
Ram-23|Shyam-20|Shiv-25|Mahesh-30
[Ram-23|Shyam-20|Shiv-25|Mahesh-30] 
```

