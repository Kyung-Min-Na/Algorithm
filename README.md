# Algorithm
algorithm-Report
code by Python

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

##Heap sort
import heapq

def heapsort(array):
    h = []
    for value in array:
        heapq.heappush(h, value)
    return [heapq.heappop(h) for i in range(len(h))]

array = heapsort(array)
print("After heap sort:", array)

##Bubble sort, Insertion sort, Selection sort, Merge sort
def bubblesort(array):
    n = len(array)
    for i in range(n):
        for j in range(n-i-1):
            if array[j] > array[j+1]:
                array[j], array[j+1] = array[j+1], array[j]
    return array

def insertionsort(array):
    for i in range(1, len(array)):
        key = array[i]
        j = i - 1
        while j >= 0 and array[j] > key:
            array[j+1] = array[j]
            j -= 1
        array[j+1] = key
    return array

def selectionsort(array):
    n = len(array)
    for i in range(n):
        min_idx = i
        for j in range(i+1, n):
            if array[j] < array[min_idx]:
                min_idx = j
        array[i], array[min_idx] = array[min_idx], array[i]
    return array

def mergesort(array):
    if len(array) > 1:
        mid = len(array) // 2
        left = array[:mid]
        right = array[mid:]

        mergesort(left)
        mergesort(right)

        i = j = k = 0

        while i < len(left) and j < len(right):
            if left[i] < right[j]:
                array[k] = left[i]
                i += 1
            else:
                array[k] = right[j]
                j += 1
            k += 1

        while i < len(left):
            array[k] = left[i]
            i += 1
            k += 1

        while j < len(right):
            array[k] = right[j]
            j += 1
            k += 1

    return array

array = bubblesort(array)
print("After bubble sort:", array)

array = insertionsort

