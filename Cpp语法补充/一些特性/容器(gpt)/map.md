下一个容器是 `std::map`，它是一个关联式容器，用于存储键-值对，并根据键来快速查找值。让我用更正式的语言和代码示例来介绍 `std::map`：

**`std::map` 容器**

`std::map` 是 C++标准模板库（STL）中的一个关联式容器，用于存储一组键值对，其中每个键都是唯一的。它按键的升序进行排序，这使得查找和插入操作非常高效。你可以将 `std::map` 想象成一个字典或映射，其中每个键都与一个值相关联。

**示例代码：**

```cpp
#include <iostream>
#include <map>

int main() {
    // 创建一个std::map，用于存储名字和对应的电话号码
    std::map<std::string, int> phoneBook;

    // 向map中插入键值对
    phoneBook["Alice"] = 12345;
    phoneBook["Bob"] = 67890;
    phoneBook["Charlie"] = 54321;

    // 查找和打印电话号码
    std::string name = "Bob";
    if (phoneBook.find(name) != phoneBook.end()) {
        std::cout << "Phone number for " << name << ": " << phoneBook[name] << std::endl;
    } else {
        std::cout << "Name not found in the phone book." << std::endl;
    }

    return 0;
}
```

在这个示例中，我们创建了一个 `std::map` 容器，用于存储名字和对应的电话号码。我们插入了几个键值对，然后查找并打印了特定名字对应的电话号码。

`std::map` 是一个非常有用的容器，特别适用于需要高效查找和按键排序的情况。你可以将其用于构建字典、索引和其他需要将键和值相关联的数据结构。