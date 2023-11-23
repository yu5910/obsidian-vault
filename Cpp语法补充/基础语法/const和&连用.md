在 C++中，`const` 和 `&`（引用）常常一起使用是为了声明常量引用。这样的组合有一些有用的效果和用途。

1. **防止修改：** 当你声明一个使用 `const` 修饰的引用时，它表明你承诺不会通过这个引用修改引用的对象。这提供了一层保护，确保了在函数或其他上下文中，通过该引用不会意外地修改原始数据。

    ```cpp
    void foo(const int& x) {
        // x 是一个常量引用，不能通过它修改原始数据
        // ...
    }
    ```

2. **允许使用临时对象：** 常量引用允许你使用临时对象，即使它们不能被修改。这是因为在常量引用的上下文中，C++ 允许将临时对象（右值）绑定到常量引用。

    ```cpp
    void bar(const std::string& str) {
        // 可以接受字符串字面量或临时字符串对象
        // ...
    }

    int main() {
        bar("Hello, World!");  // 允许传递字符串字面量
        bar(std::string("Temporary"));  // 允许传递临时字符串对象
        return 0;
    }
    ```

3. **避免拷贝：** 使用 `const` 引用还可以避免在函数调用时进行不必要的拷贝。如果没有使用 `const` 引用，会导致在传递参数时触发拷贝构造函数。

    ```cpp
    void baz(const std::vector<int>& vec) {
        // 不会触发不必要的拷贝
        // ...
    }

    int main() {
        std::vector<int> myVector = {1, 2, 3};
        baz(myVector);
        return 0;
    }
    ```

总的来说，使用 `const` 引用通常是为了在函数参数中表示“只读”语义，同时允许对常量对象和临时对象进行有效的传递，同时避免了不必要的拷贝。
避免拷贝是为了提高程序的性能和效率。在 C++中，拷贝操作可能涉及大量数据的复制，尤其是对于容器和自定义类等情况。通过使用引用，特别是常量引用，可以有效地避免不必要的拷贝。

以下是一些关于如何避免拷贝的细节：

1. **传递大型对象：** 当你需要传递一个大型对象给函数时，通过使用常量引用可以避免拷贝整个对象。这尤其对于容器、字符串、以及其他包含大量数据的对象非常重要。

    ```cpp
    // 避免拷贝整个 vector
    void processVector(const std::vector<int>& vec) {
        // ...
    }

    int main() {
        std::vector<int> myVector = {1, 2, 3};
        processVector(myVector);
        return 0;
    }
    ```

2. **避免不必要的拷贝构造函数调用：** 在函数调用时，如果不使用引用，而是通过传值的方式传递对象，将会调用拷贝构造函数。使用常量引用可以避免这种情况。

    ```cpp
    class MyClass {
    public:
        // 拷贝构造函数
        MyClass(const MyClass& other) {
            // 复制其他对象的数据
            // ...
        }
    };

    void processObject(const MyClass& obj) {
        // ...
    }

    int main() {
        MyClass myObject;
        processObject(myObject);  // 避免拷贝构造函数调用
        return 0;
    }
    ```

3. **避免不必要的对象创建：** 使用引用可以避免创建不必要的临时对象。如果你传递的是一个右值（临时对象或表达式的结果），那么通过使用常量右值引用，可以将其绑定到引用，而不是创建新的对象。

    ```cpp
    void processString(const std::string& str) {
        // ...
    }

    int main() {
        processString("Hello");  // 避免创建不必要的临时对象
        return 0;
    }
    ```

通过使用常量引用，特别是常量引用参数，可以避免对大型对象的不必要拷贝，从而提高程序的性能和效率。在设计函数接口和类时，考虑如何使用引用来最小化拷贝是一个重要的优化策略。