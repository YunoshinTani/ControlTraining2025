# 制御講習第2回のお手本コードです

## 1. 課題1 (整数の四則演算)

### 1. 問1

コード  

```cpp
#include <mbed.h>

int main() {
  int x;

  x = 3 + 5 + 10 + 17;

  printf("x:%d\n", x);    // 35
}
```

出力  

```bash
35
```

### 1. 問2

コード  

```cpp
#include <mbed.h>

int main() {
  int x, y;

  x = 7 / 5;
  y = 7 % 5;

  printf("x:%d, y:%d\n", x, y);    // 1, 2
}
```

出力  

```bash
1, 2
```

### 1. 問3

コード  

```cpp
#include <mbed.h>

int main() {
  int x;

  x = (3 + 7) * (51 + 31) - 10;

  printf("x:%d\n", x);    // 810
}
```

出力  

```bash
810
```

### 1. 問4

```cpp
#include <mbed.h>

int main() {
  int x;

  x = 1 / 2;

  printf("x:%d\n", x);    // 0
}
```

出力  

```bash
0
```

## 2. 課題2 (小数の四則演算)

### 2. 問1

コード  

```cpp
#include <mbed.h>

int main() {
  double x;

  x = 0.3 + 3.5 + 1.01 + 2.7;

  printf("x:%lf\n", x);    // 7.51
}
```

出力  

```bash
7.510000
```

%lfは小数以下6桁を表示する．この桁数は指定することもできる．  

### 2. 問2

コード  

```cpp
#include <mbed.h>

int main() {
  double x;

  x = 4 * 0.5 / 2;

  printf("x:%lf\n", x);    // 1.0
}
```

出力  

```bash
1.000000
```

### 2. 問3

コード  

```cpp
#include <mbed.h>

int main() {
  double x;

  x = 1.0 / 2.0;

  printf("x:%lf\n", x);    // 0.5
}
```

出力  

```bash
0.500000
```

### 2. 問4

コード  

```cpp
#include <mbed.h>

int main() {
  double x;

  x = 1 / 2;

  printf("x:%lf\n", x);    // 0.0
}
```

出力  

```bash
0.000000
```

## 3. まとめ課題

### 3. 問1

コード  

```cpp
#include <mbed.h>

int main() {
  double x = 5.0;    // このように初期値を設定することもできる
  double s;

  s = x * x * 1.732 / 4;

  printf("s:%lf\n", s);    // 10.825
}
```

出力  

```bash
10.825000
```

### 3. 問2

コード  

```cpp
#include <mbed.h>

int main() {
  int n = 7;
  int c;

  c = (n + 3) / 4;

  printf("c:%d\n", c);    // 2
}
```

出力  

```bash
2
```

### 3. 問3

コード  

```cpp
#include <mbed.h>

int main() {
  int n = 987;
  int d;

  d = (n / 10) % 10;    // ()はなくても動くが，わかりやすくすることも大切

  printf("d:%d\n", d);    // 8
}
```

出力  

```bash
8
```
