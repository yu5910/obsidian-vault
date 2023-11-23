![[Pasted image 20231110021518.png]]

当使用 C++的 STL（标准模板库）时，算法是非常重要的一部分。STL 提供了许多通用算法，它们可以用于各种容器，如 vector、list、set 等，以便执行各种操作，如查找、排序、转换等。下面是一些常用 STL 算法的入门示例：

**1. `std::sort`：** 用于对容器中的元素进行排序。

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> myVector = {5, 2, 8, 1, 3};
    
    std::sort(myVector.begin(), myVector.end());
    
    for (int num : myVector) {
        std::cout << num << " ";
    }

    return 0;
}
```

**2. `std::find`：** 用于在容器中查找特定元素。

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

int main() {
    std::vector<int> myVector = {5, 2, 8, 1, 3};
    
    int target = 8;
    auto it = std::find(myVector.begin(), myVector.end(), target);
    
    if (it != myVector.end()) {
        std::cout << "Found " << target << " at index " << std::distance(myVector.begin(), it);
    } else {
        std::cout << target << " not found";
    }

    return 0;
}
```

**3. `std::for_each`：** 用于对容器中的每个元素执行指定的操作。

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

void printDouble(int num) {
    std::cout << num * 2 << " ";
}

int main() {
    std::vector<int> myVector = {5, 2, 8, 1, 3};
    
    std::for_each(myVector.begin(), myVector.end(), printDouble);

    return 0;
}
```

这些只是一些 STL 算法的简单示例。STL 还提供了许多其他强大的算法，如 `std::copy`、`std::transform`、`std::remove` 等。你可以根据具体需求选择合适的算法来操作你的数据。入门 STL 算法后，你将能够更高效地处理容器中的数据。