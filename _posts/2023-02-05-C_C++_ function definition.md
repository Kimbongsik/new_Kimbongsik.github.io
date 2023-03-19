---
title: "[C언어] 함수 선언 및 정의"
last_modified_at: 2023-02-05T16:20:02-05:00
categories:
  - C_C++

tags:
  - C_C++
---


 C로 짜여진 여러 코드들을 들여다보면, 함수의 선언과 정의를 분리하고, main 함수 위에 함수의 선언을, 정의는 main 함수의 아래에 하는 경우가 상당히 많이 보인다. 왜 굳이 둘을 나누는 것일까? 답은 ‘컴파일러에게 함수의 존재를 알리기 위함’에 있다.

---

 함수를 호출하기 위해서는, 호출 이전에 함수가 정의되어 있어야 한다. 컴파일러에게 함수의 이름, 파라미터, 리턴 형식에 대해 알려준다. 아래는 예시이다.

### 예시 1

```c
#include <stdio.h>

void sum(int a, int b); //함수 선언문

int main(){
	int a = 10;
	int b = 20;
	int result;

	result = sum(a, b);
	
	return 0;
}

void sum(int a, int b){
	return a + b;
}
```

main 함수 위의 sum()과 같은 형식을 **함수 선언**이라고 한다. 코드의 길이가 길어지면 함수 관리가 어렵기 때문에, main 함수보다 아래에 함수를 정의시켜두어서 관리하는 편이 훨씬 깔끔하다. 따라서 함수 호출을 위한 선언문은 main 함수 위에, 함수 정의부는 main 함수에 위치시키는 경우가 많다. 위와 같은 이유로, 아래와 같이 작성해도 무리없이 동작한다. 

### 예시 2

```c
#include <stdio.h>

void sum(int a, int b){
	return a + b;
}

int main(){
	int a = 10;
	int b = 20;
	int result;

	result = sum(a, b);
	
	return 0;
}
```

한편, 함수 선언은 정의를 포함하고 있지 않기 때문에, 식별자의 매개변수명은 의미가 없어 생략이 가능하다. 따라서 함수 선언자에서 데이터 형식만을 지정해주어도 된다. 코드는 아래와 같다.

### 예시 3