## **JDK-Java开发环境**
---
* SE(J2SE)：标准版本，通用版本
* EE(J2EE)：企业版，用于开发j2ee应用程序
* ME(J2ME)：用于嵌入式开发

### **一、jdk目录**
---
#### **bin**：jdk开发工具可执行文件目录
1. javac.exe：编译器，将.java源码转换成.class字节码
2. java.exe：解释器，执行.class
3. javadoc.exe：文档生成工具，根据Java源码中的注释生成类说明文档
4. jar.exe：打包工具，将相关类打包成一个文件
5. javap.exe：反汇编器，反汇编一个.class字节码文件，返回有关可变部分和成员函数的信息
6. javah.exe：头文件生成器，创建C头文件和存根文件
7. jdb.exe：调试器，debugger
8. ...

#### **include**：引入的C语言的头文件
JDK是通过C和C++实现的，在启动时需要引入一些C语言的头文件，include目录里面是一些供C语言使用的标题文件，其中C语言的头文件支持Java本地接口和Java虚拟机调试程序接口的本地编程技术。

#### **jre(专用jre)**：jdk开发工具所使用的Java运行时环境
Java运行时环境，包含jvm，运行时类包。(专用jre：开发环境下运行的jre，可以使用jdk的开发工具）
1. bin
2. lib：开发环境中，jvm使用的类库目录，导入外部驱动

#### **lib**：开发工具使用的类库目录
> 主要包括tools.jar和dt.jar

#### **src.zip**
java源代码：
1. com
2. java
3. javax
4. launcher
5. org

#### **javafx-src.zip**
javafx脚本：
1. com
2. javafx
3. netscape

### **二、jre目录(公共jre)**
---
运行已有的Java程序，不能使用jdk的开发工具
1. bin
2. lib

### **系统环境变量配置**
---
#### **JAVA_HOME环境变量：Java目录**
C:\Program Files\Java\jdk1.8.0_221

#### **PATH环境变量：开发工具目录**
C:\Program Files\Java\jdk1.8.0_221\bin

#### **CLASSPATH环境变量**
C:\Program Files\Java\jdk1.8.0_221\lib\dt.jar
C:\Program Files\Java\jdk1.8.0_221\lib\tools.jar


