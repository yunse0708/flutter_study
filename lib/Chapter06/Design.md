# 디자인 관련 위젯

> **디자인 관련 위젯이란?**
> 배경을 추가하거나 간격을 추가하거나 패딩을 추가하는 등 디자인적 요소를 적용할 때 사용

## 01.Container 위젯

**Container 위젯은 말 그대로 다른 위젯을 담는데 사용 <br> 위젯의 높이와 높이를 지정하거나, 배경이나 테두리를 추가할 때 많이 사용**

```dart
class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        body: Center(
            child: Container(
            // 스타일 적용
          decoration: BoxDecoration(
            // 배경색 적용
              color: Colors.red,
              // 테두리 적용
              border: Border.all(
                // 테두리 굵기
                width: 16.0,
                // 테두리 색상
                color: Colors.black,
              ),
              // 모서리 둥굴게 만들기
              borderRadius: BorderRadius.circular(16.0)),
              // 높이
              height: 200.0,
              // 너비
              width: 100.0,
        )),
      ),
    );
  }
}
```

#### 실행결과

![](../../assets/Chapter%2006/Container.png)

---

## 02.SizedBox 위젯

**일반적으로 일정 크기의 공간을 공백으로 두고 싶을 떄 사용**

```dart
 @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        body: Center(
            child: SizedBox(
            // 높이 지정
          height: 200.0,
          // 너비 지정
          width: 200.0,
          // SizedBox는 색상이 없으므로 크기를 확인하는 용도로 Container 추가
          child: Container(
            color: Colors.red,
          ),
        )),
      ),
    );
  }
```

##### 실행결과

![](../../assets/Chapter%2006/SizedBox.png)

---  

## 03.Padding 위젯

**Padding은 적용된 위젯이 차지하는 크기 내부에서 간격이 추가된다.**

```dart
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        body: Center(
            child: Container(
          color: Colors.blue,
          child: Padding(
            // 상하, 좌우로 모두 16픽셀만큼 패딩 적용
            padding: EdgeInsets.all(
              16.0,
            ),
            child: Container(
              color: Colors.red,
              width: 50.0,
              height: 50.0,
            ),
          ),
        )),
      ),
    );
  }
```

#### 실행결과

![](https://wikidocs.net/images/page/227969/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2024-01-20_154920.png)

### margin과의 차이

**margin은 위젯의 바깥 간격을 추가(잘 사용하지 않음)**

```dart
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        body: Center(
            // 촤상위 검정 컨테이너 (margin이 적용되는 대상)
          child: Container(
              color: Colors.black,
              // 중간 파란 컨태이너              child: Container(
                color: Colors.blue,
                // 마진 적용 위치
                margin: EdgeInsets.all(16.0),
                // 패딩 적용
                child: Padding(
                  padding: EdgeInsets.all(
                    16.0,
                  ),
                  // 패딩이 적용된 빨간 컨테이너
                  child: Container(
                    color: Colors.red,
                    width: 50.0,
                    height: 50.0,
                  ),
                ),
              )),
        ),
      ),
  }
```

#### 실행결과
![](https://wikidocs.net/images/page/227969/%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7_2024-01-20_155223.png)

### EdgeInsets 클래스는 다양한 생성자 제공
![alt text](../../assets/Chapter%2006/EdegeInsets.png)

---

## 04.SafeArea
**기기별로 예외 처리를 하지 않고도 안전한 화면에서만 위젯 그리기 가능**

```dart
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        body: SafeArea(
            // 원하는 부위만 따로 적용 가능, true는 적용, false는 미적용
          top: true,
          bottom: true,
          left: true,
          right: true,
          child: Container(
            color: Colors.red,
            height: 300.0,
            width: 300.0,
          ),
        ),
      ),
    );
  }
```

#### 실행결과
![](../../assets/Chapter%2006/SafeArea.png)


