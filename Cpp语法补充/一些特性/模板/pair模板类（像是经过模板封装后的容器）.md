`std::pair` 是 C++ 标准库中定义的一个模板类，用于表示存储两个值的有序对。它的语法形式如下：

```cpp
template <class T1, class T2>
struct pair {
    T1 first;
    T2 second;
};
```

`std::pair` 是一个模板类，它有两个模板参数 `T1` 和 `T2`，分别表示有序对中的第一个值和第二个值的类型。在实际使用时，可以根据需要指定具体的类型。

`std::pair` 的实例对象可以通过使用大括号 `{}` 或 `std::make_pair` 函数来初始化。例如：

```cpp
std::pair<int, double> p1; // 默认初始化，first 和 second 的值是未定义的

std::pair<int, double> p2(10, 3.14); // 使用值初始化，first 是 10，second 是 3.14

std::pair<int, double> p3 = {5, 2.71}; // 使用初始化列表进行初始化

std::pair<int, double> p4 = std::make_pair(7, 1.23); // 使用 make_pair 函数进行初始化
```

通过 `pair` 对象的成员变量 `first` 和 `second`，可以访问有序对中的第一个值和第二个值。例如：

```cpp
std::pair<int, double> p(10, 3.14);
std::cout << "First value: " << p.first << std::endl;  // 输出 First value: 10
std::cout << "Second value: " << p.second << std::endl; // 输出 Second value: 3.14
```

`std::pair` 可以用于在函数中返回多个值或接收多个值作为参数。例如：

```cpp
std::pair<int, double> getValues() {
    int intValue = 42;
    double doubleValue = 3.14;
    return std::make_pair(intValue, doubleValue);
}

void processValues(std::pair<int, double> values) {
    int intValue = values.first;
    double doubleValue = values.second;
    // 处理 intValue 和 doubleValue
}
```

`std::pair` 提供了一种方便的方式来存储和操作两个相关的值，尤其适用于需要返回多个值或将多个值作为参数传递的情况。