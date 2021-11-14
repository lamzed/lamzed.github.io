---
author: "lamzed"
date: 2021-06-20
title: CPU乱序执行的证明
summary: "或许你可以理解为我在里面显摆我的CPU（假的"
categories: ["技术随笔"]
tags: ["Java"]
---

或许CPU性能会影响代码执行耗时和次数，可并不影响结果。

嗯...我的CPU：amd r9 5900HS。rog flow x13永远滴神！

## po代码

```
package demo.chaos;

public class Disorder {

    private static int a, b, x, y;
    private static long start;


    public static void main(String[] args) throws InterruptedException {
        int i = 0;
        start = System.currentTimeMillis();
        while (true) {
            i++;
            a = 0;
            b = 0;
            x = 0;
            y = 0;
            Thread X = new Thread(() -> {
                a = 1;
                x = b;
            });
            Thread Y = new Thread(() -> {
                b = 1;
                y = a;
            });
            X.start();
            Y.start();
            X.join();
            Y.join();
            String result = "takes " + i + " time when x=0 and y=0.";
            if (x == 0 && y == 0) {
                System.err.println(result);
                System.err.println("cost: " + (System.currentTimeMillis() - start) + "ms");
                break;
            }
        }
    }
}
```

## 执行结果

```
takes 15744 time when x=0 and y=0.
cost: 1976ms
```

```
takes 847 time when x=0 and y=0.
cost: 143ms
```

```
takes 708712 time when x=0 and y=0.
cost: 99281ms
```

## 乱序证明

我们假设若是不会出现乱序执行，那么x和y的组合就只有三种：

``` 
1. x = 0; y = 1;
2. x = 1; y = 0;
3. x = 1; y = 1;
```

即x=0和y=0组合永远不可能存在。(中二点说，`x和y绝对不会抵达同时为零的真实！`

也即程序死循环永远不会被终结。

可执行结果出现了第四种可能。

那么真相只有一个：假设被推翻。你品你细品。