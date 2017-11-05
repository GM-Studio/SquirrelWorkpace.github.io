---
title: Java学习－网络编程(一)
date: 2017-11-01 18:48:29
tags: [Java,网络编程]
categories: Java学习
---

# 序
大家都会发现,在工作当中,网络编程是基础的,也是很必要的.比如我们经常会用```socket```通信,```HTTP协议```,```UDP协议```之类的.那么今天我们将会学习到如何用```HttpURLConnection```这个类进行网络编程.
# API解释
首先我们在官网查下```HttpURLConnetcion```的API，官网解释如下：

```
A URLConnection with support for HTTP-specific features. See the spec for details.
Each HttpURLConnection instance is used to make a single request but the underlying network connection to the HTTP server may be transparently shared by other instances. Calling the close() methods on the InputStream or OutputStream of an HttpURLConnection after a request may free network resources associated with this instance but has no effect on any shared persistent connection. Calling the disconnect() method may close the underlying socket if a persistent connection is otherwise idle at that time.
The HTTP protocol handler has a few settings that can be accessed through System Properties. This covers Proxy settings as well as >various other settings.
```

大概的意思则是与```HTTP```特定功能的支持一个```URLConnection```.详情请参阅规范.每个```HttpURLConnection```实例是用来制造单个请求,但基础网络连接到```HTTP```服务器可以通过其他实例可以透明共用,呼吁一个```HttpURLConnection```类的的```InputStream```和```OutputStream```的密切方法的请求后,可能释放与此实例关联的网络资源,但对任何共享的持久连接没有任何影响.如果一个持久连接就是在那个时候闲置的调用```disconnect()```方法可以关闭基础套接字.```HTTP```协议处理程序,可以通过系统属性来访问一些设置.这包括代理设置,以及其他各种设置.而在上述叙述中,我们发现```HttpURLConnection```是有一个父类的```URLConnetcion```API文档描述如下:

```
The abstract class URLConnection is the superclass of all classes that represent a communications link between the application and a URL. Instances of this class can be used both to read from and to write to the resource referenced by the URL. In general, creating a connection to a URL is a multistep process
```

翻译如下就是

```
抽象类URLConnection是代表应用程序和URL之间的通信链路的所有类的超类.这个类的实例既可以用来读取和写入由URL引用的资源.一般况下,创建一个URL连接是一个多步骤的过程.
```

# 举个栗子
那么现在废话少说，查看例子是怎么使用的吧：

```java
package com.baoquan.upload;
import java.io.DataOutputStream;
import java.io.OutputStream;
import java.net.HttpURLConnection;
import java.net.URL;
public class DataUpload implements Upload {
        @Override
       public boolean fileupload(String filename, String url) {
                // TODO Auto-generated method stub
              return false;
   }
       @Override
       public boolean dataupload(String url, String data) {
            // TODO Auto-generated method stub 
                try{
            //创建URL连接
            URL uploadurl=new URL(url);
                     //打开端口通信
                HttpURLConnection con=(HttpURLConnection)uploadurl.openConnection();
                    //设置相关属性设置 输入输出流打开 
                con.setDoInput(true);
                con.setDoOutput(true);
                  //设置请求方式 包括POST GET
                 con.setRequestMethod("POST");
                   //设置请求头属性
                 con.setRequestProperty("Connection","keep-Alive");
                 con.setRequestProperty("User-Agent", "Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Ubuntu Chromium/51.0.2704.79 Chrome/51.0.2704.79 Safari/537.36");
                 con.setRequestProperty("Charset", "UTF-8");
                     //打开输出流
                 OutputStream out=new DataOutputStream(con.getOutputStream());   
                        //写入数据
                 out.write(data.getBytes());
                     //清空缓冲区
                 out.flush();
                    //关闭输出流
                 out.close();
                 System.out.println(con.getResponseCode());
                 return true;
            }
               catch(Exception e)
              {
                 System.out.println("POST请求异常");
                 e.printStackTrace();
            }
               return false;
           
        }
        public static void main(String[] args)
  {
                 DataUpload dataup=new DataUpload();
                 dataup.dataupload("http://localhost:8080/Server/servlet/UploadServlet", "你好世界");
        }
      
}

```

由以上代码 可以看出

```
1. 创建URL对象
2. URL打开URL地址连接也就是openConnection()
3. 设置请求的相关方式POST/GET
4. 设置请求的头的相关属性
5. 获取输入/输出流
6. 读取/写入数据
7. 清空缓冲区
8. 关闭连接
```

# 结束
大概就是这么的一个过程,大家都明白了吧.其实```HttpURLConnection```也是采用```socket```通信的.它内部封装了关于```socket```的相关信息.因此熟悉```socket```的通信相关编程知识的,也就能发现其实```HttpURLConnection```也是类似的编程步骤.好了.暂时写到这儿.有什么不对或者问题,请务必告知本人.谢谢.

