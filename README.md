## 자료구조와 알고리즘

### 기본 알고리즘

3값의 최대값 알고리즘 소스코드

```C
// 3 값의 최댓값
#include <stdio.h>

int main(void)
{
    int a, b, c;//정수형 변수 a, b, c를 선언
    int max;//정수형 변수 max 선언
    
    printf("입력받은 세 값중에 최대값을 구합니다.\n");
    
    printf("a의 값은 : "); scanf("%d", & a);//a 값을 입력받고 그것을 출력한다.
    printf("b의 값은 : "); scanf("%d", & b);//b 값을 입력받고 그것을 출력한다.
    printf("c의 값은 : "); scanf("%d", & c);//c 값을 입력받고 그것을 출력한다.

    max = a;//최대값을 a 라고 임의로 설정을 하고

    if(b > max) max = b;//max의 값과 b의 값을 비교하고 b가 크면 max에 b를 대입한다. 아니면 넘어간다.
    if(c > max) max = c;//max의 값과 c의 값을 비교하고 c가 크면 max에 c를 대입한다. 아니면 넘어간다.

    printf("최대값은 %d 입니다.\n", max);//최종적으로 max에 담긴 값을 출력한다.

    return 0;
}
```
