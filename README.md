## 자료구조와 알고리즘

### 기본 알고리즘

1. 3값의 최대값을 구하는 알고리즘 소스코드

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

2. 3값의 중간값을 구하는 알고리즘 소스코드

```C
//3 값의 중앙 값을 구합니다.
#include <stdio.h>


//입력받은 3 값의 중간값을 리턴해주는 함수입니다.
int Med3(int a, int b, int c)
{
    // 조건문으로 a, b, c 를 차례대로 돌아가며 비교 해보고 중간값을 반환한다.
    if (a >= b) 
        if (b >= c) 
            return b; 
        else if (a <= c)
            return a;
        else 
            return c;
    else if (a > c)
        return a;
    else if (b > c)
        return c;
    else
        return b;
}

int main(void)
{
    int a, b, c;

    printf("세 정수의 중앙값을 구합니다.\n");
    printf("a의 값 : "); scanf("%d", & a); //입력받은 a의 값을 출력합니다.
    printf("b의 값 : "); scanf("%d", & b); //입력받은 b의 값을 출력합니다.
    printf("c의 값 : "); scanf("%d", & c); //입력받은 c의 값을 출력합니다.

    printf("중앙값은 %d입니다.\n", Med3( a, b, c)); //Med3 함수에서 반환해준 중간값을 출력합니다.

    return 0;
}
```

*보충 : min = a < b ? a : b \
        min에 대입되는 값은 a가 b보다 작으면 a값, 그렇지 않으면 b값입니다.
        
        
3. while문을 이용한 1부터 입력받은 n까지의 합을 구하는 알고리즘 소스코드

```C
//1부터 n까지의 합을 구합니다.
#include <stdio.h>

int main(int argc, char const *argv[])
{
    int i, n;
    int sum;

    puts("1부터 n까지의 합을 구합니다.");
    printf("n의 값 : ");
    scanf("%d", &n);

    sum = 0; //현재 합은 0
    i = 1; //i는 1
    while(i <= n) // i 가 n이랑 같아질때까지 sum에 더해준다.
    {
        sum += i;
        i++;
    }
    printf("1부터 %d까지의 합은 %d입니다.\n", n, sum);//합을 출력해준다.

    return 0;
}
```

4. for문을 사용한 1부터 n 까지의 합을 구하는 알고리즘 소스코드

```C
#include <stdio.h>

int main(int argc, char const *argv[])
{
    int i, n;
    int sum;

    puts("1부터 n까지의 합을 구합니다.");
    printf("n 값 : ");
    scanf("%d", & n);

    sum = 0;//현재 sum은 0
    for(i = 1; i <= n; i++)//1부터 n까지 i를 1씩 증가 시키면서 sum에 i 값을 더해준다.
    {
        sum += i;
    }

    printf("1부터 %d까지의 합은 %d입니다.\n", n, sum);//최종 합을 출력한다

    return 0;
}
```

5. do ~ while문을 이용한 1 ~ n까지의 합을 구하는 알고리즘 소스코드 (입력한 값을 양수로)

```C
//1 부터  n 까지의 합을 구하라
#include <stdio.h>

int main(int argc, char const *argv[])
{
    int i, n;
    int sum;

    puts("1부터 n까지의 합을 구합니다.");
    do//일단 한번 실행하고
    {
        printf("n값 : ");
        scanf("%d", & n);    
    } while (n <= 0);//조건을 충족 시키면 다시 실행한다.

    sum = 0;//sum 초기값 0

    for(i =1; i <= n; i++)// 반복문을 이용하여 1부터 n까지의 합을 구하고
    {
        sum += i;
    }
    
    printf("1부터 %d까지의합은 %d 입니다.\n", n, sum);//합을 출력

    return 0;
}

```

*보충 \
    구조적 프로그래밍 ( structured Programming ) 하나의 입구와 하나의 출구를 가진 구성 요소만을 계층적으로 배치하여 프로그램을 구성하는 방법을 구조적 프로그래밍 이라고 합니다. 구조적 프로그래밍은 순차, 선택, 반복,이라는 3종류의 제어 흐름을 사용합니다. 
    
6. do ~ while  2자리의 양수 (10 ~ 99)를 입력합니다.

```C
//2자리의 양수 (10 ~ 99)를 입력합니다.
#include <stdio.h>

int main(int argc, char const *argv[])
{
    int no;
    printf("2자리 정수를 입력하세요\n");
    do
    {
        printf("수는 : ");
        scanf("%d", &no);
    } while (no < 10 || no > 99);

    printf("변수 no 값은 %d이 되었습니다.\n", no);

    return 0;
}

```

7. 곱셈표를 출력하는 알고리즘 소스코드

```C
//곱셈표 출력
#include <stdio.h>

int main(int argc, char const *argv[])
{
    int i, j;
    
    printf("------곱셈표------");
    for(i = 0; i <= 9; i++) // i 행 루프
    {
        for(j = 0; j <= 9; j++) // j 열 루프
        {
            printf("% 3d", i * j);
        }
        putchar("\n");
    }

    return 0;
}

```

8. 왼쪽 아래가 직각인 이등변 삼각형을 출력합니다.

```C
//왼쪽아래가 직각인 이등변 삼각형을 출력합니다.

#include <stdio.h>

int main(int argc, char const *argv[])
{
    int i, j, n;
    do
    {
        printf("몇 단 삼각형입니까? : ");
        scanf("%d", & n);

    } while (n <= 0);

    for(i = 0; i <= n; i++)
    {
        for(j = 0; i <= n; i++)
        {
            putchar("*");
        }
        putchar('\n');
    }

    return 0;
}
```

## 에라토스테네스의 체
```C
void eratostenes(int n)
{
	if (n <= 1) return;    // 0과 1은 제외

	int primeArr[10001];    // 10000이하의 수를 담는 배열 생성

	for (int i = 2; i <= n; i++)    // 2부터 n까지의 수를
	{
		primeArr[i] = i;    // 배열에 대입
	}

	for (int i = 2; i * i <= n; i++)    // 2부터 n까지
	{
		if (primeArr[i] == 0)    // 소수가 아니라면
		{
			continue;    // 무시한다
		}
		else    // 소수라면
		{
			for (int j = i + i; j <= n; j += i)    // (예: i = 2) 2 이후의 배수는 약수로 2를 
												  // 가지게되므로 4, 6, 8...등은 소수가 아니다
			{
				primeArr[j] = 0;    // 소수가 아닌 2 이후의 배수들은 지워준다.
			}
		}
	}

	for (int i = 2; i <= n; i++)    // 2부터 n까지
	{
		if (primeArr[i]) cout << primeArr[i] << endl;    // 소수의 값만 출력한다.
	}
}
```
