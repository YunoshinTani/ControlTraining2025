# 制御講習 第1回 コード例

## 1. 課題1 (条件式の計算)

### 1. 問1

コード  

```cpp
int main() {
    bool x, y;

    x = 5==5;
    y = 5==3;
}
```

変数の内容  

```bash
x: 1
y: 0
```

### 1. 問2

コード  

```cpp
int main() {
    bool z;
    int w = 5; // 例の値3

    z = w>3;
}
```

変数の内容  

```bash
z: 1
```

## 2. 課題2 (条件文)

### 2. 問1

コード  

```cpp
#include <mbed.h>

int main() {
    int x = 5; // 例の値5

    if (x == 2) {
        printf("Two\n");
    }

    if (x == 5) {
        printf("Five\n");
    }
}
```

出力  

```bash
Five
```

### 2. 問2

コード  

```cpp
#include <mbed.h>

int main() {
    int n = 5; // 例の値5

    if ((3 < n) && (n <= 10)) {
        printf("IN\n");
    } else {
        printf("OUT\n");
    }
}
```

出力  

```bash
IN
```

## 3. 課題3 (繰り返し文)

### 3. 問1

コード(while文)  

```cpp
#include <mbed.h>

int main() {
    int i = 2;

    while (i <= 10) {
        printf("%d ", i);
        i++; // i = i + 1; と同じ インクリメントという
    }

    printf("\n");
}
```

コード(for文)  

```cpp
#include <mbed.h>

int main() {
    for (int i = 2; i <= 10; i++) {
        printf("%d ", i);
    }

    printf("\n");
}
```

出力  

```bash
2 3 4 5 6 7 8 9 10 
```

### 3. 問2

コード(while文)  

```cpp
#include <mbed.h>

int main() {
    int i = 5;

    while (i <= 30) {
        printf("%d ", i);
        i += 5;
    }

    printf("\n");
}
```

コード(for文)  

```cpp
#include <mbed.h>

int main() {
    for (int i = 5; i <= 30; i += 5) {
        printf("%d ", i);
    }

    printf("\n");
}
```

出力  

```bash
5 10 15 20 25 30 
```

## 4. まとめ課題

### 4. 問1

コード  

```cpp
#include <mbed.h>

int main() {
    for (int i = 0; i <= 10; i++) {
        if (i != 0) {
            printf("%dの逆数は: %f\n", i, 1.0/i);
        }
    }
}
```

出力  

```bash
1の逆数は: 1.000000
2の逆数は: 0.500000
3の逆数は: 0.333333
4の逆数は: 0.250000
5の逆数は: 0.200000
6の逆数は: 0.166667
7の逆数は: 0.142857
8の逆数は: 0.125000
9の逆数は: 0.111111
10の逆数は: 0.100000
```

### 4. 問2

コード  

```cpp
#include <mbed.h>

int main() {
    for (int i = 1; i <= 30; i++) {
        printf("%d : ", i);
        if ((i % 3 == 0) && (i % 5 == 0)) {
            printf("FizzBuzz\n");
        } else if (i % 3 == 0) {
            printf("Fizz\n");
        } else if (i % 5 == 0) {
            printf("Buzz\n");
        } else {
            printf("\n");
        }
    }
}
```

出力  

```bash
1 : 
2 : 
3 : Fizz
4 : 
5 : Buzz
6 : Fizz
7 : 
8 : 
9 : Fizz
10 : Buzz
11 : 
12 : Fizz
13 : 
14 : 
15 : FizzBuzz
16 : 
17 : 
18 : Fizz
19 : 
20 : Buzz
21 : Fizz
22 : 
23 : 
24 : Fizz
25 : Buzz
26 : 
27 : Fizz
28 : 
29 : 
30 : FizzBuzz
```

### 4. 問3

コード  

```cpp
#include <mbed.h>

#define ON 0
#define OFF 1

int main() {
    DigitalOut led(LED1);
    DigitalIn button(BUTTON1);
    bool prev = false;

    while (true) {
        if ((button == ON) && (prev == OFF)) {  // ボタンが押された瞬間を検知
            led = !led;  // LEDの状態を反転
        }

        prev = button;  // 現在のボタン状態を保存

        ThisThread::sleep_for(10ms);  // チャタリング(複数の入力)防止
    }
}
```

prevはpreviousの略 前ループのボタンの状態を保存する．
