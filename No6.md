# 制御講習 第6回 コード例

```cpp
#include <mbed.h>
```

は省略しています.

## 1. 課題1

### 1. 問1

コード  

```cpp
int main() {
  printf("start\n");
  while (true) {
    printf("HelloWorld\n");
  }
}
```

## 3. 課題3

### 3. 問1

コード例

```cpp
int add3(int num) {
    return num + 3;
}

int main() {
    int x;
    x = add3(7);
    printf("x:%d\n", x);
}
```

出力

```bash
x:10
```

### 3. 問2

コード例

```cpp
float CdsVoltage() {
    AnalogIn cds(A0);
    return cds.read() * 3.3f; // 0~3.3V
}

int main() {
    while (true) {
        float voltage = CdsVoltage();
        printf("Cds Voltage: %.2f V\n", voltage);
        ThisThread::sleep_for(500ms); // 0.5秒待つ(見やすさのため)
    }
}
```

出力例

```bash
Cds Voltage: 1.23 V
Cds Voltage: 1.25 V
Cds Voltage: 1.22 V
Cds Voltage: 1.20 V
```

### 3. 問3

コード例

```cpp
void Cds2Led() {
    AnalogIn cds(A0);
    PwmOut led(PA_5); // ピン番号はLED1でも可

    while (true) {
        float voltage = cds.read(); // 0.0~1.0
        led.write(voltage);         // 0.0~1.0
        ThisThread::sleep_for(10ms);
    }
}

int main() {
    Cds2Led();
}
```

## 4. 最終課題

コード例

```cpp
void Cds2Led(float light_level) {
    AnalogIn cds(A0);
    DigitalOut led(PA_5); // ピン番号はLED1でも可

    while (true) {
        float voltage = cds.read(); // 0.0~1.0

        if (voltage < light_level) {
            led = 1; // LED ON
        }
        else {
            led = 0; // LED OFF
        }
        ThisThread::sleep_for(10ms);
    }
}

int main() {
    Cds2Led(0.5f); // 閾値0.5
}
```

> [!NOTE]
> 閾値(しきいち)とは  
> ある基準となる値のこと  
> 例: 明るさのしきい値0.5 → 明るさが0.5未満ならLED点灯, 0.5以上なら消灯  
