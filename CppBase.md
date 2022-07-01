## 指针
32位系统中指针都是4个字节，64位系统中指针都是8个字节。\
*p 指针p\



## 结构体
### 结构体定义
三种形式：
#### 形式一：定义结构体同时定义结构体变量
```
struct color { int res; int green; int blue;] cl;
```
#### 形式二：先定义结构体类型，再定义结构体变量
```
typedef struct { int res; int green; int blue;] COLOR;
COLOR cl;
```
#### 形式三：定义无名称的结构体类型，同时定义结构体变量
```
struct {int red; int green; int blue;} cl;
```
