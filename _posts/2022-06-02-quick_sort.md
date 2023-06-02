快速排序是一种常用的排序算法，它的基本思想是通过选择一个基准元素，将数组分为两部分，其中一部分的所有元素都小于基准元素，另一部分的所有元素都大于基准元素。然后递归地对这两部分进行排序，直到整个数组有序。

下面是用 Python 实现快速排序的示例代码：

def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    else:
        pivot = arr[0]  # 选择第一个元素作为基准
        less = [x for x in arr[1:] if x <= pivot]  # 比基准小的元素
        greater = [x for x in arr[1:] if x > pivot]  # 比基准大的元素
        return quick_sort(less) + [pivot] + quick_sort(greater)

# 测试
arr = [5, 3, 8, 4, 2]
sorted_arr = quick_sort(arr)
print(sorted_arr)

输出结果为：[2, 3, 4, 5, 8]

在这个示例代码中，quick_sort 函数接受一个数组作为参数，并返回排好序的数组。函数首先检查数组长度，如果长度小于等于1，则直接返回数组。否则，选择第一个元素作为基准 pivot，然后使用列表推导式将数组分为两部分，一部分是比基准小的元素 less，另一部分是比基准大的元素 greater。接着，通过递归地对 less 和 greater 进行快速排序，并将结果与基准元素连接起来，返回最终排序后的结果。

请注意，这只是快速排序的一种实现方式，还有其他不同的实现方式，如使用随机选择基准元素等。