#  [小林coding](https://segmentfault.com/a/1190000021668990) 
## chatgpt 的解释
多态是 C++中的一个重要概念，它允许你使用统一的接口处理不同类型的对象，而不需要关心对象的具体类型。通俗来说，多态就像是使用相同的电话号码打电话给不同的人，不必关心谁会接听电话。

考虑一个通俗的比喻：

假设你有一台电话，上面只有一个按钮，你按下按钮后可以与不同的人通话。这个按钮是多态的接口，你不需要知道按钮内部是如何工作的，只需要按下它，就可以与不同的人交流。

在 C++中，多态通过虚函数和基类派生类结构来实现。你可以定义一个基类，并在其内部声明虚函数。然后，派生类可以继承这个虚函数，并提供自己的实现。当你通过基类指针或引用调用虚函数时，实际执行的是派生类的实现。

这意味着你可以使用基类指针或引用来操作不同派生类的对象，而无需了解它们的具体类型。这就是多态的力量，使你的代码更灵活和可扩展。

## 例如，考虑一个动物的例子：
^the-example-of-dog
```cpp
class Animal {
public:
    virtual void makeSound() {
        std::cout << "Some generic sound" << std::endl;
    }
};

class Dog : public Animal {
public:
    void makeSound() override {
        std::cout << "Woof woof!" << std::endl;
    }
};

class Cat : public Animal {
public:
    void makeSound() override {
        std::cout << "Meow meow!" << std::endl;
    }
};

int main() {
    Animal* myPet = new Dog();
    myPet->makeSound();  // 输出 "Woof woof!"

    myPet = new Cat();
    myPet->makeSound();  // 输出 "Meow meow!"

    delete myPet;
    return 0;
}
```

在这个示例中，`Animal` 是基类，`Dog` 和 `Cat` 是派生类。它们都有一个虚函数 `makeSound`，但派生类提供了不同的实现。通过使用基类指针 `myPet`，你可以轻松地在不知道具体类型的情况下调用 `makeSound`，这就是多态的体现。

## 另一端和 python 对比（包含继承）
### C++
![[Pasted image 20231031143307.png|500]]

### Python (主打一个简洁和变态)
![[Pasted image 20231031143135.png|475]]


- 相当于 [[#^the-example-of-dog]]，前面是一个对象，后面继承后不断改写从而形成多态
- 但是后面的那个 C++, 它是在类外创建一个狗叫函数，函数的参数为类或子类的引用
- 