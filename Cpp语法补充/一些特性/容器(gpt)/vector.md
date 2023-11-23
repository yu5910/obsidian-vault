当谈到 STL 中的容器时，另一个非常重要的容器是 `std::vector`，它是一个动态数组，允许你在运行时动态添加或删除元素。让我用更正式的语言和代码示例来介绍 `std::vector`：

**`std::vector` 容器**

`std::vector` 是 C++标准模板库（STL）中的一个容器，用于存储一组相同类型的元素。它是一个动态数组，可以在运行时自动调整大小，因此非常适用于需要灵活管理元素集合的情况。你可以将 `std::vector` 想象成一个可自动伸缩的数组，允许你按需添加或删除元素。

**示例代码：**

```cpp
#include <iostream>
#include <vector>

int main() {
    // 创建一个std::vector来存储整数
    std::vector<int> numbers;

    // 向vector中添加元素
    numbers.push_back(1);
    numbers.push_back(2);
    numbers.push_back(3);

    // 访问vector中的元素
    std::cout << "First element: " << numbers[0] << std::endl;
    std::cout << "Size of vector: " << numbers.size() << std::endl;

    // 遍历vector并打印所有元素
    for (int i = 0; i < numbers.size(); i++) {
        std::cout << numbers[i] << " ";
    }
    std::cout << std::endl;

    return 0;
}
```

在这个示例中，我们创建了一个 `std::vector` 容器来存储整数。我们使用 `push_back` 函数向 `vector` 中添加元素，然后访问 `vector` 中的元素，并遍历并打印所有元素。

`std::vector` 是一个非常常用的容器，适用于需要管理可变大小集合的情况。它提供了灵活性，允许你动态添加或删除元素，而无需手动处理内存管理。这使得它成为处理动态数据集合的有力工具。