# 행렬 연산

## 행렬 연산의 조건
A행렬의 크기가 (M x K), B의 행렬의 크기 (N x K) 일 때, A의 행(K)와 B의 열(K)가 같아야 행렬 곱셈이 가능하다.

![IMG_C26996677E4D-1](https://github.com/user-attachments/assets/d053a749-4292-4279-864a-b4e94c290fe0)

## 예시

![IMG_67133B776251-1](https://github.com/user-attachments/assets/e30c6444-a8a7-4f7f-a574-338b0ce48d52)

```cpp
#include <vector>
#include <iostream>

using namespace std;

void print(vector<vector<int>> &a){
    for (int i=0; i<a.size(); i++){
        for (int j=0; j < a[i].size(); j++){
            cout << a[i][j] << " ";
        }
    	cout << endl;
    }
    
}

int main(){
    
    vector<vector<int>> matric1 = {{1,2}, 
                                   {3,4}};
    
    vector<vector<int>> matric2 = {{5,6}, 
                                   {7,8}};
    
    vector<vector<int>> answer;
    
    answer.assign(matric1.size(), vector<int>(matric2[0].size(), 0)); // matric1의 행 * matric2의 열 크기의 공간 할당
    
    for (int i=0; i< matric1.size(); i++){
        for (int j=0; j< matric2[0].size(); j++){
            for (int k=0; k < matric2.size(); k++){
                answer[i][j] += matric1[i][k] * matric2[k][j];
            }
        }
    }
    
    print(answer);
    
    return 0;
}
```

<img width="644" alt="스크린샷 2024-09-10 오후 3 53 09" src="https://github.com/user-attachments/assets/d59e910d-041b-450f-8989-4c9ff8b6ea89">

