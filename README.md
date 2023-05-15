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
def bubblesort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr

def insertionsort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and arr[j] > key:
            arr[j+1] = arr[j]
            j -= 1
        arr[j+1] = key
    return arr

def selectionsort(arr):
    n = len(arr)
    for i in range(n):
        min_idx = i
        for j in range(i+1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
    return arr

def mergesort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        left = arr[:mid]
        right = arr[mid:]

        mergesort(left)
        mergesort(right)

        i = j = k = 0

        while i < len(left) and j < len(right):
            if left[i] < right[j]:
                arr[k] = left[i]
                i += 1
            else:
                arr[k] = right[j]
                j += 1
            k += 1

        while i < len(left):
            arr[k] = left[i]
            i += 1
            k += 1

        while j < len(right):
            arr[k] = right[j]
            j += 1
            k += 1

    return arr

arr = bubblesort(arr)
print("After bubble sort:", arr)

arr = insertionsort

