# Child와 Children의 차이점

> **child 매개변수와 children 매개변수는 위젯에 하위 위젯을 추가할 때 사용**
> child는 하나만, children은 여러개 추가 가능

## Child

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(
    MaterialApp(
        home: Scaffold(
            body: Center(
                // 하나의 위젯만 가운데 정렬 가능
                child: Text('Hello Wortld'),
            ),
        ),
    ),
  );
}
```

### 실행결과

![실행결과1_Hello World](../../assets/Chapter%2006/06_실행결과_1.png)

## Children

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(
    MaterialApp(
      debugShowCheckedModeBanner: false,
      home: Scaffold(
        body: SizedBox(
          width: double.infinity,
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            // 여러 위젯을 Coulumn 위젯에 입력 가능
            // 리스트 안에 원하는 만큼의 위젯 입력 가능
            children: [
              Text('Code'),
              Text('Factory'),
            ],
          ),
        ),
      ),
    ),
  );
}
```
### 실행결과

![실행결과2_Code Factory](../../assets/Chapter%2006/06_실행결과_2.png)


