```python
def quick_sort(arr, left, right):
    # 시작과 끝점을 기준으로 작업하는데, 시작점이 끝점 보다 작을 때만 실행
    if left < right:
        pivot = hoare_partition(arr, left, right)
        # 피벗을 기준으로 큰값과, 작은값으로 정렬(partition)
        # 왼쪽 부분집합 정렬 실행
        quick_sort(arr, left, pivot-1)
        # 오른쪽 부분집합 정렬 실행
        quick_sort(arr, pivot+1, right)
    pass


def hoare_partition(arr, left, right):
    i = left
    j = right
    pivot = arr[left]

    # i가 j 보다 작거나 같을 때 까지 계속 반복(left와 right가 역전되면 수행 X)
    while i <= j:
        # i 는 증가하면서, pivot 보다 큰 값을 찾음
        while arr[i] <= pivot:
            i += 1
        # j 는 감소하면서, pivot 보다 작은값을 찾음.
        while arr[j] > pivot:
            j -= 1

        if i < j:
            arr[i], arr[j] = arr[j], arr[i]
    # 피벗보다 작은값중 제일 뒤에 위치한 arr[j]와 pivot의 위치를 바꿔줌
    arr[j], arr[left] = arr[left], arr[j]
    return j

    pass


arr = [4, 3, 2, 1, 7, 6, 6, 2]
quick_sort(arr, 0, len(arr)-1)
print(arr)

```

