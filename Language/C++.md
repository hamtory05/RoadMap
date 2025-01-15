<h1 align = "center"> C++ </h1>

## iostream
* C++ 표준 입출력 클래스
* cout : 출력, cin : 입력

<br>

### cout 객체
``` C++
std::cout << 출력할 데이터;
```
``` C++
std::cout << "Hello World";   // 출력 값 : Hello World!
```

<br>

### sin 객체
``` C++
std::cin >> 저장할 변수;
```
``` C++
int age;

std::cout << "나이를 입력해주세요";
std::cin >> age;

std::cout << "나이는" << age << "살 입니다." << std::endl;

// 나이는 { } 살 입니다
```

<br>

### endl 객체
* 줄바꿈 + 출력 버퍼를 비우는 역할
* 간단한 출력을 할 때에는 "\n"
* 즉각적인 출력이 필요할 때 std::endl

<br>

### using namespace std
* std::를 생략할 수 있게 해줌

``` C++
#include <iostream>

using namespace std;

int main(void) {

    cout << "Hello World!" << endl;

    return 0;
}
```
