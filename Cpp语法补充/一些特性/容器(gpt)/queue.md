![[Pasted image 20231110021952.png]]

下一个容器是 `std::queue`，它是一个队列容器，遵循先进先出（FIFO）的原则。让我用更正式的语言和代码示例来介绍 `std::queue`：

**`std::queue` 容器**

`std::queue` 是 C++标准模板库（STL）中的一个容器，它表示队列数据结构。队列是一种按照先进先出原则管理元素的数据结构，类似于排队等待的行为。`std::queue` 是一个受限制的容器，只允许在队列的前端添加元素，从队列的尾部删除元素，因此适用于模拟排队或任务管理等场景。

**示例代码：**

```cpp
#include <iostream>
#include <queue>

int main() {
    // 创建一个std::queue来表示排队的人
    std::queue<std::string> peopleQueue;

    // 添加人到队列
    peopleQueue.push("Alice");
    peopleQueue.push("Bob");
    peopleQueue.push("Charlie");

    // 出队列，先进先出
    std::cout << peopleQueue.front() << " is the first to leave the queue." << std::endl;
    peopleQueue.pop();

    // 查看队列的大小
    std::cout << "Number of people left in the queue: " << peopleQueue.size() << std::endl;

    return 0;
}
```

在这个示例中，我们创建了一个 `std::queue` 容器来表示排队的人。我们使用 `push` 函数将人加入队列，然后使用 `front` 函数查看队列中的第一个人，并使用 `pop` 函数将其移出队列。

`std::queue` 是一个适用于排队和任务管理的容器，因为它遵循先进先出原则，非常适合模拟按照顺序执行任务的场景。它在 STL 中提供了一种简单而有用的数据结构。