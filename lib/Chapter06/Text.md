# 텍스트 관련 위젯

> **Text 위젯이란?**
> 글자를 적고 스타일링하는 위젯

<br>

### style 네임드 파라미터 사용해 스타일 지정

```dart
void main() {
  runApp(
    MaterialApp(
      home: Scaffold(
        body: Center(
          child: Text(
            // 작성하고 싶은 텍스트
            '코드팩토리',
            // 텍스트에 스타일 적용
            style: TextStyle(
                // 글자 크기
                fontSize: 16.0,
                // 글자 굵기
                fontWeight: FontWeight.w700,
                // 글자 색상
                color: Colors.blue),
          ),
        ),
      ),
    ),
  );
}

```

### 실행결과
![실행결과3_코드팩토리](../../assets/Chapter%2006/06_실행결과_3.png)
