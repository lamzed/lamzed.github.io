---
author: "lamzed"
date: 2021-06-02
title: 学习之路：知识体系构建及独家笔记整理
summary: "所谓的觉悟，就是在黑暗的荒野中，开辟出一条应当前进的道路。"
categories: ["技术干货"]
tags: ["计算机网络","Java"]
---

## 前言

这里使用的语言是Java，若哪里用到其他语言，自会另行说明。

## 网络多线程

> 基础照例略过，概念相关需要各位同学面向搜索引擎自行理清。

### 网络相关概念

`IP地址` `域名和端口` `网络协议` `TCP和UDP`  `Socket`

### TCP字节流编程

虽说这部分内容比较基础也比较简单，但不经常使用就容易忘记。

- SocketServer

```
    public static void main(String[] args) throws IOException {
        ServerSocket serverSocket = new ServerSocket(8888);
        System.out.println("server-socket start listening...port 8888");

        Socket socket = serverSocket.accept();

        InputStream inputStream = socket.getInputStream();

        byte[] buf = new byte[1024];
        int len;
        while ((len = inputStream.read(buf)) != -1) {
            System.out.println(new String(buf, 0, len));
        }

        OutputStream outputStream = socket.getOutputStream();
        outputStream.write("yo,jojo".getBytes(StandardCharsets.UTF_8));
        socket.shutdownOutput(); // important

        outputStream.close();
        inputStream.close();
        socket.close();
        serverSocket.close();
    }
```

- SocketClient

```
    public static void main(String[] args) throws IOException {
        InetAddress localHost = InetAddress.getLocalHost();
        System.out.println("localhost: " + localHost);

        Socket socket = new Socket(localHost, 8888);

        OutputStream outputStream = socket.getOutputStream();
        outputStream.write("dio!!!".getBytes(StandardCharsets.UTF_8));
        socket.shutdownOutput();

        InputStream inputStream = socket.getInputStream();

        byte[] buf = new byte[1024];
        int len;

        while ((len = inputStream.read(buf)) != -1) {
            System.out.println(new String(buf, 0, len));
        }

        inputStream.close();
        outputStream.close();
        socket.close();
    }
```

### TCP字符流编程

说什么字节流字符流，其实挺绕的，直接上代码吧。

```
    public static void main(String[] args) throws IOException {
        ServerSocket serverSocket = new ServerSocket(8888);
        System.out.println("server-socket start listening...port 8888");

        Socket socket = serverSocket.accept();

        InputStream inputStream = socket.getInputStream();
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(inputStream));
        System.out.println(bufferedReader.readLine());

        OutputStream outputStream = socket.getOutputStream();
        BufferedWriter bufferedWriter = new BufferedWriter(new OutputStreamWriter(outputStream));
        bufferedWriter.write("yo,jojo");
        bufferedWriter.newLine(); // important
        bufferedWriter.flush(); // important

        bufferedWriter.close();
        bufferedReader.close();
        socket.close();
        serverSocket.close();
    }
```

- SocketServer

```
    public static void main(String[] args) throws IOException {
        InetAddress localHost = InetAddress.getLocalHost();
        System.out.println("localhost: " + localHost);

        Socket socket = new Socket(localHost, 8888);

        OutputStream outputStream = socket.getOutputStream();
        BufferedWriter bufferedWriter = new BufferedWriter(new OutputStreamWriter(outputStream));
        bufferedWriter.write("dio!!!");
        bufferedWriter.newLine(); // 插入换行符，以示写入内容结束
        bufferedWriter.flush();

        InputStream inputStream = socket.getInputStream();
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(inputStream));
        System.out.println(bufferedReader.readLine());

        bufferedReader.close();
        bufferedWriter.close();
        socket.close();
    }
```

### 网络文件传输

- SocketClient

知识体系构建、梳理的最佳选择，肯定毋庸置疑是写思维导图。

再者其次是`markdown`。

不过使用`md`进行笔记整理、心得记录却又是极好的。故才有了你现在见到的页面。

但这不是二选一的问题，想要`xmind`导图的同学，可到`github`私我。