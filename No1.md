# 制御講習第一回 の お手本コードです

## printf() 課題
### 問①
```bash
start
HelloWorld
HelloWorld
HelloWorld
...
```
一回のみ、startが表示され、そのあとはHelloWorldがずっと表示される。  

### 問②
```cpp
#include <mbed.h>

int main() {
  printf("start\n");
  while (true) {
    printf("My name is YunoshinTani\n");
  }
}
```
あくまで一例  

### 問③
```bash
startHelloWorldHelloWorldHelloWorld...
```
改行されず、横に出力されていく。  

## ThisThread::sleep_for() 課題
### 問①
```cpp
#include <mbed.h>

int main() {
  printf("start\n");
  while (true) {
    printf("My name is YunoshinTani\n");
    ThisThread::sleep_for(100ms);
  }
}
```
100ミリ秒ごとにprintf()を実行する。  

## まとめ課題
### 問①
```cpp
#include <mbed.h>

int main() {
  printf("HelloWorld\n");
  ThisThread::sleep_for(1s);
  
  printf("HelloWorld\n");
  ThisThread::sleep_for(1s);
  
  printf("HelloWorld\n");
  ThisThread::sleep_for(1s);
}
```

### 問②
```cpp
#include <mbed.h>

int main() {
  while (true) {
    printf("HelloWorld ");
    
    printf("HelloWorld ");
    
    printf("HelloWorld\n");
  }
}
```

### 問
```cpp
#include <mbed.h>

int main() {
  while (true) {
    printf("HelloWorld ");
    
    printf("HelloWorld ");
    
    printf("HelloWorld\n");

    ThisThread::sleep_for(5000ms);
  }
}
```
