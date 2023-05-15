# Algorithm
algorithm-Report

##20개의 난수 생성
import random

array = []
for i in range(20):
    arr.append(random.randint(1, 100))

print("Before sorting:", arr)

##Quick sort 
def quicksort(array):
    if len(array) <= 1:
        return array

    pivot = array[len(array) // 2]
    less, equal, greater = [], [], []
    for num in array:
        if num < pivot:
            less.append(num)
        elif num == pivot:
            equal.append(num)
        else:
            greater.append(num)

    return quicksort(less) + equal + quicksort(greater)

array = quicksort(array)
print("After quick sort:", array)
