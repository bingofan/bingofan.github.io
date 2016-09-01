---
title: Java 中的类型转换
tags: Java
categories: Java
description: >-
  本文用于摘要和记录Java语言中一些类型转换相关内容.   部分内容转载自[java
  int转String所有方式的效率对比与深入解析](http://blog.csdn.net/self_study/article/details/50880110)
date: 2016-09-01 15:03:52
---


### String 和 int 转换 ###

**三种方式** 按效率排序

1.`String s = Integer.toString(i);`

2.`String s = String.valueOf(i);`

3.`String s = "" + i;`

<!-- more -->

事例程序

```java
int a = 123456789;
long start = System.currentTimeMillis();
for (int i=0; i<100000; i++){
    String m = a+"";
}
long end = System.currentTimeMillis();
Log.e("time", "a+\"\" = " + (end - start));

start = System.currentTimeMillis();
for (int i=0; i<100000; i++){
    String n = String.valueOf(a);
}
end = System.currentTimeMillis();
Log.e("time", "String.valueOf(a) = " +(end-start));

start = System.currentTimeMillis();
for (int i=0; i<100000; i++){
    String n = Integer.toString(a);
}
end = System.currentTimeMillis();
Log.e("time", "Integer.toString(a) = " +(end-start));
```

最后打印出来的执行时间：
```java
E/time: Integer.toString(a) = 159
E/time: String.valueOf(a) = 140
E/time: a+"" = 257
```

**源码调用方式**

Integer.toString(a)

`Integer.toString(a)` -> `IntegralToString.intToString(a)` -> `convertInt(null, a)`

String.valueOf(a)

`String.valueOf(a)` -> `Integer.toString(a)` -> `IntegralToString.intToString(a)` -> `convertInt(null, a)`

a+""

+运算符重载
```java
StringBuilder sb = new StringBuilder();
sb.append("");
sb.append(i);
String strI = sb.toString();
```
`append`源码

`StringBuffer.append` -> `IntegralToString.appendInt(this, a)` -> `convertInt(sb, i)`


**`convertInt`**函数
```java
private static String convertInt(AbstractStringBuilder sb, int i) {
    boolean negative = false;
    String quickResult = null;
    if (i < 0) {
        negative = true;
        i = -i;
        if (i < 100) {
            if (i < 0) {
                // If -n is still negative, n is Integer.MIN_VALUE
                quickResult = "-2147483648";
            } else {
                quickResult = SMALL_NEGATIVE_VALUES[i];
                if (quickResult == null) {
                    SMALL_NEGATIVE_VALUES[i] = quickResult =
                            i < 10 ? stringOf('-', ONES[i]) : stringOf('-', TENS[i], ONES[i]);
                }
            }
        }
    } else {
        if (i < 100) {
            quickResult = SMALL_NONNEGATIVE_VALUES[i];
            if (quickResult == null) {
                SMALL_NONNEGATIVE_VALUES[i] = quickResult =
                        i < 10 ? stringOf(ONES[i]) : stringOf(TENS[i], ONES[i]);
            }
        }
    }
    if (quickResult != null) {
        if (sb != null) {
            sb.append0(quickResult);
            return null;
        }
        return quickResult;
    }

    int bufLen = 11; // Max number of chars in result
    char[] buf = (sb != null) ? BUFFER.get() : new char[bufLen];
    int cursor = bufLen;

    // Calculate digits two-at-a-time till remaining digits fit in 16 bits
    while (i >= (1 << 16)) {
        // Compute q = n/100 and r = n % 100 as per "Hacker's Delight" 10-8
        int q = (int) ((0x51EB851FL * i) >>> 37);
        int r = i - 100*q;
        buf[--cursor] = ONES[r];
        buf[--cursor] = TENS[r];
        i = q;
    }

    // Calculate remaining digits one-at-a-time for performance
    while (i != 0) {
        // Compute q = n/10 and r = n % 10 as per "Hacker's Delight" 10-8
        int q = (0xCCCD * i) >>> 19;
        int r = i - 10*q;
        buf[--cursor] = DIGITS[r];
        i = q;
    }

    if (negative) {
        buf[--cursor] = '-';
    }

    if (sb != null) {
        sb.append0(buf, cursor, bufLen - cursor);
        return null;
    } else {
        return new String(cursor, bufLen - cursor, buf);
    }
}
```
分析一下，这个函数的工作主要可以分为这几步：

1.如果a为负数，将a变成正数，如果a还小于0，直接置为Integer.MIN_VALUE；如果a小于100，则直接使用TENS和ONES数组进行快速计算得出结果，加上’-‘号，直接返回该结果。

2.如果a为正数并且小于100，直接使用TENS和ONES数组进行快速计算得出结果返回。

3.如果上面两步没有处理完，说明a是大于100的数字，无法直接使用TENS和ONES数组进行快速计算，处理方式就是2位为一步循环处理，每次将这两位使用TENS和ONES数组进行快速计算得出这两位的结果存在数组的相应位置，直到只剩一位；最后剩下的一位使用DIGITS数组得出16进制的结果放在最后，返回结果。

{% textcolor danger %}
那么问题来了，当a>=100的时候，那两次while循环为什么会使用0x51EB851FL和0xCCCD这两个数字呢？
这个问题不要问我，我也不知道，不过源码作者注释写的很明白了： 去看《Hacker’s Delight》的10-8章。 
{% endtextcolor %}
```java
// Compute q = n/100 and r = n % 100 as per "Hacker's Delight" 10-8 
// Compute q = n/10 and r = n % 10 as per "Hacker's Delight" 10-8 
```



TENS和ONES数组，直接看代码，一目了然：
```java
/** TENS[i] contains the tens digit of the number i, 0 <= i <= 99. */
private static final char[] TENS = {
        '0', '0', '0', '0', '0', '0', '0', '0', '0', '0',
        '1', '1', '1', '1', '1', '1', '1', '1', '1', '1',
        '2', '2', '2', '2', '2', '2', '2', '2', '2', '2',
        '3', '3', '3', '3', '3', '3', '3', '3', '3', '3',
        '4', '4', '4', '4', '4', '4', '4', '4', '4', '4',
        '5', '5', '5', '5', '5', '5', '5', '5', '5', '5',
        '6', '6', '6', '6', '6', '6', '6', '6', '6', '6',
        '7', '7', '7', '7', '7', '7', '7', '7', '7', '7',
        '8', '8', '8', '8', '8', '8', '8', '8', '8', '8',
        '9', '9', '9', '9', '9', '9', '9', '9', '9', '9'
};

/** Ones [i] contains the tens digit of the number i, 0 <= i <= 99. */
private static final char[] ONES = {
        '0', '1', '2', '3', '4', '5', '6', '7', '8', '9',
        '0', '1', '2', '3', '4', '5', '6', '7', '8', '9',
        '0', '1', '2', '3', '4', '5', '6', '7', '8', '9',
        '0', '1', '2', '3', '4', '5', '6', '7', '8', '9',
        '0', '1', '2', '3', '4', '5', '6', '7', '8', '9',
        '0', '1', '2', '3', '4', '5', '6', '7', '8', '9',
        '0', '1', '2', '3', '4', '5', '6', '7', '8', '9',
        '0', '1', '2', '3', '4', '5', '6', '7', '8', '9',
        '0', '1', '2', '3', '4', '5', '6', '7', '8', '9',
        '0', '1', '2', '3', '4', '5', '6', '7', '8', '9',
};
```
每个数组都是100的长度，都是用来处理0~99这100个数字，个位和十位的处理方式也很清楚。 
从代码角度来看，这个算法在数字小于100的和大于100的处理方式是不一样的，小于100的快速计算法执行时间会远远短于大于100的方式




