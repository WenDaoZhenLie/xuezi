## Markdown(轻量级标记语言，文件后缀名".md")
### **标题**
```
# h1
## h2
### h3
#### h4
##### h5
###### h6
```
> # h1
>
> ## h2
>
> ### h3
>
> #### h4
>
> #### h5
>
> ##### h6

### **段落**
```
用空白行将一行或多行文本进行分隔
```

### **换行**
```
在一行的末尾添加两个或多个空格，然后按回车键
```

### **字体**
* 加粗
  ```
  **文本**
  ```
  > **文本**

* 斜体
  ```
  *文本*
  ```
  > *文本*

* 加粗&斜体
  ```
  ***文本***
  ```
  > ***文本***

### **引用**
* 块引用
  ```
  > 文本
  ```
  > 文本

* 多个段落的块引用(段落之间的空白行添加一个 > 符号)
  ```
  > 段落1
  >
  > 段落2
  ```
  > 文本1
  >
  > 文本2

* 嵌套块引用
  ```
  > 段落1
  >
  >> 段落2
  ```
  > 段落1
  >
  >> 段落2

### **列表**
* 有序列表
  ```
  1. 元素1
  2. 元素2
  3. 元素3
  ```
  > 1. 元素1
  >
  > 2. 元素2
  >
  > 3. 元素3

* 无序列表
  ```
  * 元素1
  * 元素2
  * 元素3
  ```
  > * 元素1
  >
  > * 元素2
  >
  > * 元素3

### **代码**
````
```java
public class HelloWorld { 
	public static void main(String[] args) { 
		System.out.print("Hello world!");
	}
}

`print("Hello world!")`
```
````
```java
public class HelloWorld { 
	public static void main(String[] args) { 
		System.out.print("Hello world!");
	}
}
```
`print("Hello world!")`

### **分隔线**
```
---
```
> ---

### **链接**
```
[Markdown教程](https://markdown.com.cn/)
```
> [`Markdown教程`](https://markdown.com.cn/)

### **图片**
```
![图片alt](图片链接 "图片title")
```