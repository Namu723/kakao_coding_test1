#[1차] 비밀지도


def solution(n, arr1, arr2):
    array1 = []
    array2 = []
    answer = []

    for a1,a2 in zip(arr1,arr2):
        array1.append(list(map(int, format(a1,'b').zfill(n))))
        array2.append(list(map(int, format(a2,'b').zfill(n))))
    for i in range(len(array1)):
        tmp = ''
        for j in range(len(array2)):
            if array1[i][j] or array2[i][j]:
                tmp += '#'
            else:
                tmp += ' '
        answer.append(tmp)
    return answer

#print(solution(5,[9, 20, 28, 18, 11],[30, 1, 21, 17, 28]))

def solution(n, arr1, arr2):
    answer = []
    for i,j in zip(arr1,arr2):
        a12 = str(bin(i|j)[2:])
        a12=a12.rjust(n,'0')
        a12=a12.replace('1','#')
        a12=a12.replace('0',' ')
        answer.append(a12)
    return answer

