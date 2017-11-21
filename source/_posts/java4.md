---
title: Java学习笔记(四)Java文件操作(读文件)
date: 2017.11.15
tags: [Java]
categories: Java
---

# 序
文件操作对于编程来说都是很基础很基础的知识,可是我很久没用写有关文件操作的程序.今天心血来潮的突然写一个.一来巩固下基础.二来学习了性能分析和内存优化等等的知识.

## 内容

### 按字节流读取文件

```java
static void readFileByByte(String filename) {
       System.out.println("按照字节读取");
       File file = new File(filename);
       byte[] buffer = new byte[1024];

       if (file.exists()) {
           if (file.isDirectory()) {
               System.out.println("This is directory ");
           } else {
               int read = 0;

               try {
                   FileInputStream input = new FileInputStream(file);
                   read = input.read(buffer, 0, 1024);
                   System.out.println("This is file content ");
                   while (read != -1) {
                       for (int i = 0; i < 1024; i++) {
                           System.out.print(buffer[i]);
                       }

                       System.out.print(new String(buffer, "UTF-8"));
                       read = input.read(buffer, 0, 1024);
                   }

                   System.out.println("按字节读取完毕");
               } catch (Exception e) {
                   e.printStackTrace();
               }
           }
       }
   }
```

存在的问题:
１. 打印```buffer```缓冲区的时候,请不要直接打印```buffer```，因为直接打印出来的是一个对象值,并不是所含数组的值.
２. 编码问题,因为是按照字节读取的.byte字节没有编码格式.读取的是默认的```ASCII```码.那么当读取中文的时候,就会出现乱码.因此为了解决这个问题.可以使```byte```转```String```,然后设置```UTF-8```格式.这样就能正常的读取中文并输出.(其实质是输出的时候转码了,并不是读的就是```UTF-8```)

### 按字符流读取文件

```java

    static void readFileByCharacter(String filename) {

        System.out.println("按照字符读取");
        File file = new File(filename);
        char[] buffer = new char[1024];
        int read = 0;
        if (file.exists()) {
            if (file.isDirectory()) {
                System.out.println("This is directory ");
            } else {
                try {
                    FileReader input = new FileReader(file);
                    read = input.read(buffer, 0, 1024);
                    System.out.println("This is file content");
                    while (read != -1) {
                        System.out.println(buffer);
                        read = input.read(buffer, 0, 1024);
                    }

                    System.out.println("按字符读取完毕");
                } catch (Exception e) {
                    e.printStackTrace();
                }
            }
        }
    }
```

存在问题:尚未发现

### 按行读取文件

```java
static void readFileByLine(String filename) {

      System.out.println("按行读取");

      File file = new File(filename);
      String str = new String();
      FileReader fileReader = null;
      if (file.exists()) {
          if (file.isDirectory()) {
              System.out.println("This is directory ");
          } else {
              try {

                  fileReader = new FileReader(file);
                  BufferedReader bufferedReader = new BufferedReader(fileReader);
                  System.out.println("This is file content ");
                  while ((str = bufferedReader.readLine()) != null) {
                      System.out.println(str);
                  }

                  System.out.println("按行读取完毕");
                  fileReader.close();
              } catch (Exception e) {
                  e.printStackTrace();
              }

          }
      }
  }
```

存在问题:尚未发现


### 性能分析工具　
VisualVM的使用




## 未完待续
Java学习笔记系列还没完结,老司机的车会一直开下去哦.下次再见..........
