# 制御講習 第4回 コード例

```cpp
#include <mbed.h>
```

は省略しています.

## 1. 課題1

### 1. 問1

コード

```cpp
int main() {
    int x = 5; // 例の値5

    if (x == 2) {
        printf("Two\n");
    }
    if (x == 5) { // else if でも可
        printf("Five\n");
    }
}
```

出力

```bash
Five
```

### 1. 問2

コード

```cpp
int main() {
    int x = 7; // 例の値7

    if ((3 < n) && (n <= 10)) {
        printf("IN\n");
    }
    else {
        printf ("OUT\n");
    }
}
```

出力

```bash
IN
```

## 2. 課題2

### 2. 問1

```cpp
int main() {
    int i = 2;

    while (i <= 5) {
        printf("%d\n", i);
        i++; // インクリメント
    }
}
```

出力

```bash
2
3
4
5
```

### 2. 問2

コード

```cpp
int main() {
    int i = 5;

    while (i >= 2) {
        printf("%d\n", i);
        i--; // デクリメント
    }
}
```

出力

```bash
5
4
3
2
```

## 3. 課題3

### 3. 問1

コード

```cpp
int main() {
    for (int i = 2; i <= 5; i++) {
        printf("%d\n", i);
    }
}
```

出力

```bash
2
3
4
5
```

### 3. 問2

コード

```cpp
int main() {
    for (int i = 5; i >= 2; i--) {
        printf("%d\n", i);
    }
}
```

出力

```bash
5
4
3
2
```

## 4. 課題4

### 4. 問1

解答1

```cpp
int  main() {
    DigitalOut led1(PA_5); // ピン番号はLED1でも可
    DigitalIn button(PC_13); // ピン番号はBUTTON1でも可

    while (true) {
        if (button == 0) {
            led = 1;
        }
        else {
            led = 0;
        }
    }
}
```

別解

```cpp
int main() {
    DigitalOut led1(PA_5); // ピン番号はLED1でも可
    DigitalIn button(PC_13); // ピン番号はBUTTON1でも可

    while (true) {
        led = !button; // buttonが0のときledは1, buttonが1のときledは0
    }
}
```

### 4. 問2

解答1

```cpp
int main() {
    DigitalOut led1(PA_5); // ピン番号はLED1でも可
    DigitalIn button(PC_13); // ピン番号はBUTTON1でも可
    bool pushed = false; // 押されたかどうかのフラグ

    while (true) {
        if ((button == 0) && (pushed == true)) {
            led = !led; // LEDの状態を反転
        }
        pushed = button; // 現在のボタン状態を保存
        ThisThread::sleep_for(50ms); // チャタリング(複数の入力)防止
    }
}
```

別解(わかりやすい)

```cpp
#define ON 0
#define OFF 1

int main() {
    DigitalOut led(PA_5); // ピン番号はLED1でも可
    DigitalIn button(PC_13); // ピン番号はBUTTON1でも可
    bool pushed = false; // 前回のボタン状態

    while (true) {
        if ((button == ON) && (pushed == OFF)) {  // ボタンが押された瞬間を検知
            led = !led;  // LEDの状態を反転
        }

        pushed = button;  // 現在のボタン状態を保存
        ThisThread::sleep_for(50ms);  // チャタリング(複数の入力)防止
    }
}
```

## 5. まとめ課題

### 5. 問1

コード

```cpp
int main() {
    double inv;

    for (int i = -5; i <= 5; i++) {
        if (i != 0) {
            inv = 1.0 / i; // iが0のときは実行されない
            printf("1/%d = %lf\n", i, inv);
        }
    }
}
```

### 5. 問2

解答1

```cpp
int main() {
    for (int i = 0; i <= 30; i++) {
        if ((i % 3 == 0) && (i % 5 == 0)) {
            printf("%2d : FizzBuzz\n");
        }
        else if (i % 3 == 0) {
            printf("%2d : Fizz\n");
        }
        else if (i % 5 == 0) {
            printf("%2d : Buzz\n");
        }
        else {
            printf("%2d : None\n");
        }
    }
}
```

別解

```cpp
int main() {
    for (int i = 1; i <= 30; i++) {
        printf("%d : ", i);
        if ((i % 3 == 0) && (i % 5 == 0)) {
            printf("FizzBuzz");
        } else if (i % 3 == 0) {
            printf("Fizz");
        } else if (i % 5 == 0) {
            printf("Buzz");
        } else {
            printf("None");
        }
        printf("\n");
    }
}
```
