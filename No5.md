# 制御講習 第5回 コード例

```cpp
#include <mbed.h>
```

は省略しています.

## 1. 課題1

### 1. 問1

コード例1

```cpp
int main() {
    PwmOut led(PA_5); // ピン番号はLED1でも可
    while (true) {
        for (float duty = 0.0f; duty <= 1.0f; duty += 0.01f) {
            led.write(duty);
            ThisThread::sleep_for(10ms);
        }
    }
}
```

### 1. 問2

コード例

```cpp
int main() {
    PwmOut led(PA_5); // ピン番号はLED1でも可
    while (true) {
        for (float duty = 0.0f; duty <= 1.0f; duty += 0.01f) {
            led.write(duty);
            ThisThread::sleep_for(10ms);
        }
        for (float duty = 1.0f; duty >= 0.0f; duty -= 0.01f) {
            led.write(duty);
            ThisThread::sleep_for(10ms);
        }
    }
}
```

## 2.  課題2

### 2. 問1

コード例

```cpp
#define ON 0
int main() {
    PwmOut servo(D3);
    DigitalIn button(PC_13); // ピン番号はBUTTON1でも可

    servo.period_ms(20); // 20ms周期

    while (true) {
        if (button == ON) {
            servo.pulsewidth_us(1000); // 1ms
        }
        else {
            servo.pulsewidth_us(2000); // 2ms
        }
    }
}
```

## 3. 課題3

コード例

```cpp
int main() {
    int answer = 0;
    answer = pow(3, 4); // 3の4乗
    printf("3の4乗は%d\n", answer);

    answer = abs(-10); // 絶対値
    printf("-10の絶対値は%d\n", answer);

    answer = sqrt(16); // 平方根
    printf("16の平方根は%d\n", answer);

    answer = sin(0); // サイン
    printf("sin(0)は%d\n", answer);
}
```

出力

```bash
3の4乗は81
-10の絶対値は10
16の平方根は4
sin(0)は0
```

> [!NOTE]
>これらの関数はは浮動小数点数(`float`)を返すので, `int`に代入するときに丸め誤差が発生する可能性がある.
>`sin`の引数はラジアンである. 度を使いたい場合は, `sin(deg * 3.14159 / 180.0)`のように変換する.
> ほかにもround, ceil, floor, cos, tan, log, expなどがある.

## 課題4

### 4. 問1

コード例

```cpp
void DegServo(int deg) {
    PwmOut servo(D3);
    servo.period_ms(20);
    servo.pulsewidth_us(1000 + (deg / 180 * 1000)); // 1ms + (角度/180)*1ms
}
```

### 4. 問2

コード例

```cpp
// 摂氏を華氏に変換
float CelToFah(float cel) {
    return (cel * 9.0f / 5.0f) + 32.0f;
}

// 華氏を摂氏に変換
float FahToCel(float fah) {
    return (fah - 32.0f) * 5.0f / 9.0f;
}
```
