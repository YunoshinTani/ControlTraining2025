# 制御講習第1回 コード例

## 1. printf() 課題

### 1. 問1

コード  

```cpp
#include <mbed.h>

int main() {
  printf("start\n");
  while (true) {
    printf("HelloWorld\n");
  }
}
```

出力  

```bash
start
HelloWorld
HelloWorld
HelloWorld
...
```

一回のみ、startが表示され、そのあとはHelloWorldがずっと表示される。  

### 1. 問2

コード  

```cpp
#include <mbed.h>

int main() {
  printf("start\n");
  while (true) {
    printf("My name is YunoshinTani.\n");
    printf("私の名前は谷優之心です。\n");
  }
}
```

出力  

```bash
My name is YunoshinTani.
私の名前は谷優之心です。
```

あくまで一例  

### 1. 問3

```bash
startHelloWorldHelloWorldHelloWorld...
```

改行されず、横に出力されていく。  
> [!NOTE]
> マイコンでの動作だと、改行コードがないと出力されないことがあるようです。基本的には改行コードは改行するための文字ですが、マイコンでのプログラミングの際は入れておきましょう。

## 2. ThisThread::sleep_for() 課題

### 2. 問1

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

## 3. まとめ課題

### 3. 問1

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

### 3. 問2

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

### 3. 問3

```cpp
#include <mbed.h>

int main() {
  while (true) {
    printf("HelloWorld ");
    
    printf("HelloWorld ");
    
    printf("HelloWorld\n");

    ThisThread::sleep_for(500ms);
  }
}
```
