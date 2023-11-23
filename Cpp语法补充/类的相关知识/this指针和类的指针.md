# this 指针
## 基本形式
>this 代指当前的对象
>
```c++
#include <iostream>
 
class MyClass {
private:
    int value;
 
public:
    void setValue(int value) {
        this->value = value;
    }
 
    void printValue() {
        std::cout << "Value: " << this->value << std::endl;
    }
};
 
int main() {
    MyClass obj;
    obj.setValue(42);
    obj.printValue();
 
    return 0;
}
```
## 一个例子
```c++
#include <iostream>
using namespace std;

class Box{
    public:
        Box(){;}
        ~Box(){;}
        Box* get_address()   //得到this的地址
        {
            return this;
        }
};

int main(){
    
    Box box1;
    Box box2;
    // Box* 定义指针p接受对象box的get_address()成员函数的返回值，并打印
    
    Box* p = box1.get_address();  
    cout << p << endl;
    
    p = box2.get_address();
    cout << p << endl; 

    return 0;
}
```
# 类的指针
>类的指针与指向结构的指针类似，需要使用成员访问运算符 **->**，。与所有的指针一样，您必须在使用指针之前，对指针进行初始化
```c++
#include <iostream>
 
using namespace std;

class Box
{
   public:
      // 构造函数定义
      Box(double l=2.0, double b=2.0, double h=2.0)
      {
         cout <<"Constructor called." << endl;
         length = l;
         breadth = b;
         height = h;
      }
      double Volume()
      {
         return length * breadth * height;
      }
   private:
      double length;     // Length of a box
      double breadth;    // Breadth of a box
      double height;     // Height of a box
};

int main(void)
{
   Box Box1(3.3, 1.2, 1.5);    // Declare box1,刚一创建对象，就立刻执行构造函数
   Box Box2(8.5, 6.0, 2.0);    // Declare box2
   Box *ptrBox;                // Declare pointer to a class.

   // 保存第一个对象的地址
   ptrBox = &Box1;

   // 现在尝试使用成员访问运算符来访问成员
   cout << "Volume of Box1: " << ptrBox->Volume() << endl;

   // 保存第二个对象的地址
   ptrBox = &Box2;

   // 现在尝试使用成员访问运算符来访问成员
   cout << "Volume of Box2: " << ptrBox->Volume() << endl;
  
   return 0;
}

```