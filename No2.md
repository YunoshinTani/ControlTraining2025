# 制御講習第2回のお手本コードです

## 課題1 (整数の四則演算)
### 問1
```cpp
#include <mbed.h>

int main() {
  int x;
  x = 3 + 5 + 10 + 17;
  printf("x:%d\n", x);     // 35
}
```

### 問2
```cpp
#include <mbed.h>

int main() {
  int x, y;
  x = 7 / 5;
  y = 7 % 5;
  printf("x:%d, y:%d\n", x, y);     // 1, 2
}
```

### 問3
```cpp
#include <mbed.h>

int main() {
  int x;
  x = (3 + 7) * (51 + 31) - 10;
  printf("x:%d\n", x);     // 810
}
```

### 問4
```cpp
#include <mbed.h>

int main() {
  int x;
  x = 1 / 2;
  printf("x:%d\n", x);     // 0
}
```

## 課題2 (小数の四則演算)
### 問1
```cpp
#include <mbed.h>

int main() {
  double x;
  x = 0.3 + 3.5 + 1.01 + 2.7;
  printf("x:%lf\n", x);     // 7.51
}
```

### 問2
```cpp
#include <mbed.h>

int main() {
  double x;
  x = 4 * 0.5 / 2;
  printf("x:%lf\n", x);     // 1.0
}
```

### 問3
```cpp
#include <mbed.h>

int main() {
  double x;
  x = 1.0 / 2.0;
  printf("x:%lf\n", x);     // 0.5
}
```

### 問4
```cpp
#include <mbed.h>

int main() {
  double x;
  x = 1 / 2;
  printf("x:%lf\n", x);     // 0.0
}
```

## まとめ課題
### 問1
```cpp
#include <mbed.h>

int main() {
  double x = 5.0;     // このように初期値を設定することもできる
  double s;
  s = x * x * 1.732 / 4;
  printf("s:%lf\n", s);     // 10.825...
}
```

### 問2
```cpp
#include <mbed.h>

int main() {
  int n = 7;
  int c;
  c = (n + 3) / 4;
  printf("c:%d\n", c);     // 2
}
```

### 問3
```cpp
#include <mbed.h>

int main() {
  int n = 987;
  int d;
  d = (n / 10) % 10;     // ()はなくても動くが，わかりやすくすることも大切
  printf("d:%d\n", d);     // 8
}
```
