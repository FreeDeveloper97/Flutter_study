# Flutter 설치과정


## 1. 간단히 플러터 설치과정

[macOS install](https://flutter.dev/docs/get-started/install/macos)

- 공식사이트에 접속하여서 zip파일을 받아서 만들어진 flutter 폴더를 terminal 에서

```bash
cd ~
mkdir Developer
```

- 즉, Developer 폴더를 만드신 후에 다운로드 된 flutter 폴더를 옮깁니다.
- MacOS 카날리나 이후의 zsh 방식의 terminal의 경우 .zshrc를 열어 PATH를 추가한다.

[[Flutter] 맥에서 Flutter SDK 설치하기](https://eunjin3786.tistory.com/221)

```bash
open ~/.zshrc //또는, vim .zshrc를 통해 편집기를 열어 I를 눌러 수정
export PATH=$PATH:~/Developer/flutter/bin //위 코드처럼 flutter 내의 bin 폴더까지 경로를 알맞게 추가 후 저장
// vim의 경우 ESC 누른 후 :wq! 하여 저장 후 나온다
source ~/.zshrc
```

<img width="682" alt="1" src="https://user-images.githubusercontent.com/65349445/126901137-61e7e64f-a3bd-42e7-a307-fe669b402497.png">

- 이 상태까지 정상적으로 왔다면

```bash
flutter --version
```

- 입력했을때 아래 사진처럼 실행이 되어야 정상적이다.

<img width="682" alt="2" src="https://user-images.githubusercontent.com/65349445/126901140-d4bbb13a-5ab0-49b2-a165-5ced1f88861e.png">

- 그런다음에 flutter doctor를 입력하여 모든 체크사항을 알맞게 설치하면 된다.
- 아래 사진처럼 모두 통과되기 위해서는 Android Studio, Xcode가 설치가 필요하다.

<img width="724" alt="3" src="https://user-images.githubusercontent.com/65349445/126901142-cb8031cb-2238-4eec-8fce-fb629243e63d.png">

- 이건 까먹었는데.. 아무튼 해당 명령어를 넣는게 좋을? 것이다.

```bash
flutter doctor --android-licenses
```

<img width="724" alt="4" src="https://user-images.githubusercontent.com/65349445/126901143-c27c7890-51ee-4ed1-9e24-03c581b5eaa5.png">

## 2. Android 시뮬레이터 실행

- Android Studio를 설치했다면, 아래의 Configure → Plugins 에서 Flutter를 설치한다.

<img width="912" alt="5" src="https://user-images.githubusercontent.com/65349445/126901145-f91f4c63-747d-43cb-9c1c-31d97079ba2d.png">

- 재시작 후 Create New Flutter Project를 눌러 프로젝트를 생성한다.

<img width="778" alt="6" src="https://user-images.githubusercontent.com/65349445/126901146-2cd79780-5800-4c7c-8643-8942a508b044.png">

- 그러고 나서 시뮬레이터 기본설정까지 되어있다면 기본 어플이 실행된다!

<img width="1444" alt="7" src="https://user-images.githubusercontent.com/65349445/126901148-71c197c7-a779-4636-8a75-6838b445a858.png">

## 3. iPhone 에뮬레이터 실행

- 공식페이지 아래쪽 iOS setup 내용을 토대로 terminal에서 아래 코드를 입력한다.

```bash
sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
sudo xcodebuild -runFirstLaunch
```

<img width="724" alt="8" src="https://user-images.githubusercontent.com/65349445/126901151-8d134b53-04dc-45d9-b6f7-737f566db262.png">

- 그다음 아래코드를 입력시 아이폰 시뮬레이터가 정상적으로 실행되어야 한다.

```bash
open -a Simulator
```

- 그러면 Android Studio 에서 기기선택에 iPhone이 잡히는 모습이 보인다!

<img width="1444" alt="9" src="https://user-images.githubusercontent.com/65349445/126901154-2018fc82-b752-4868-b033-1bf8b339026b.png">

- 잠깐 물마시고 돌아오면(2~3분정도 걸리는 느낌...) 실행이 되어있을것!

<img width="1444" alt="10" src="https://user-images.githubusercontent.com/65349445/126901155-0989a9b7-4c86-43f0-bbf9-e3a7201c9d56.png">

- 이러면 여기까지 두가지 시뮬레이터를 정상적으로 실행했다!

<img width="1444" alt="11" src="https://user-images.githubusercontent.com/65349445/126901156-c267c308-9525-47ff-9849-81dc25d509f6.png">

## 4. iPhone 실기기 추가설정과정

- 하지만 위 과정만으로는 실제 아이폰 기기에서 실행할수가 없다. 추가적인 작업이 필요하다.
- flutter 폴더 → iOS 폴더 내에 pod를 init, install 한다.

<img width="724" alt="12" src="https://user-images.githubusercontent.com/65349445/126901157-59c34f03-f3b0-4f15-9479-d4197de7a346.png">

- 이런식으로 xcworkpace 파일이 생겨야 정상이다.

<img width="679" alt="13" src="https://user-images.githubusercontent.com/65349445/126901161-3cd95da7-1f3d-440f-8b94-69eb84c29fb9.png">

- Android Studio 에서 iOS 폴더 우클릭 → Flutter → Open iOS module in Xcode
- 또는, 위 사진에 만들어진 Runner.xcworkspace를 눌러 Xcode를 실행시킨다.

<img width="1444" alt="14" src="https://user-images.githubusercontent.com/65349445/126901162-800d2b0d-c0b7-40e3-9e6e-7113024743d3.png">

- Signing & Capabilities 에서 Team : None을 본인 계정으로 수정을 해줘야 한다.

<img width="1512" alt="15" src="https://user-images.githubusercontent.com/65349445/126901165-40adb251-6feb-4f2b-82b7-84a611f369f6.png">

- 여기까지만 해도 유선으로 연결하여 실기기 테스트가 가능한데, 케이블 빼고 아이폰에서 다시 실행시 검은색 화면에 이상한 영어가 보이면서 사용할 수 없게 된다.
- 이 현상의 해결책은 Xcode 상단의 Product → Scheme → Edit Scheme 들어가서

<img width="1399" alt="16" src="https://user-images.githubusercontent.com/65349445/126901170-50113269-9f3d-41ec-b5f5-b36dcce0d64d.png">

- Run : Info : Build Configuration 값 : Debug → Release 로 변경 후 Close 한다.

<img width="1399" alt="17" src="https://user-images.githubusercontent.com/65349445/126901171-061c244b-6a77-4bdf-ac2d-ea6bf22586fe.png">
- 그러면 정상적으로 유선 해제 후에도 아이폰에서 다시 실행할 수 있다!

## 5. 간단 코드 실행

- 공식사이트의 예제 코드를 조금 변경해서 실행해봤다.

[Write your first Flutter app, part 1](https://flutter.dev/docs/get-started/codelab)

```dart
// Copyright 2018 The Flutter team. All rights reserved.
// Use of this source code is governed by a BSD-style license that can be
// found in the LICENSE file.

import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Welcome to Flutter',
      home: Scaffold(
        appBar: AppBar(
          title: const Text('Welcome to Flutter'),
        ),
        body: const Center(
          child: Text('Hello World/nDeveloper FDEE🙌'),
        ),
      ),
    );
  }
}
```

- 해당코드를 실행한 결과사진이다!

<img width="1440" alt="18" src="https://user-images.githubusercontent.com/65349445/126901172-f903dc37-9be8-464d-9447-529c869a9364.png">







# Flustter 기본문법 : Youtube 정리
[Youtube Link](https://www.youtube.com/watch?v=2g8DsOSreqk)
```dart
void main() {
  print("hello world!");
  
  var name = "S002";
  print(name);
  
  int num1 = 12;
  print(num1);
  double num2 = 20.0;
  print(num2);
  
  String name2 = "S002";
  print(name2);
  
  String name3 = "슬기";
  String group = "레드벨벳";
  print(name3+"는 "+group);
  print("$name3는 $group 멤버입니다");
  print("${name3 + " " + group} 멤버입니다");
}
```

```dart
void main() {
  bool isTrue = true;
  bool isFalse = false;
  print(isTrue);
  print(isFalse);
  
  var name;
  name = "코드팩토리";
  print(name);
  
  name = "레드벨벳";
  print(name);
  name = 1;
  print(name);
}
```

```dart
void main() {
  List btsList = [
    '진','슈가', '제이홉'
  ];
  List<String> redVelvetList = [
    '아이린','슬기','웬디'
  ];
  print(btsList);
  print(redVelvetList);
  print(redVelvetList[0]);
  print(redVelvetList.length);
}
```

```dart
void main() {
  Map dictionary = {
    "Harry Potter" : "해리포터",
    'Ron Weasley' : '론 위즐리'
  };
  Map<String, String> dictionary2 = {
    'Harry Potter' : '해리포터',
    'Ron Weasley' : '론 위즐리',
  };
  
  dictionary2.addAll({
    'Hermione Granger' : '헤르미온느',
  });
  print(dictionary2);
  
  dictionary2["Hermione Granger"] = "코드팩토리";
  print(dictionary2);
  
  dictionary2.remove("Hermione Granger");
  print(dictionary2);
  
  print(dictionary2.keys);
  print(dictionary2.keys.toList());
  print(dictionary2.values.toList());
}
```

```dart
void main() {
  final name = '블랙핑크';
  final String name2 = '코드팩토리';
//   name = '변경 불가';
  
  final now = new DateTime.now();
  print(now);
  /* const의 경우 buildTime의 값이 변경불가 하므로 runTime에 값이 설정되는 경우 사용 불가 */
//   const now2 = new DateTime.now();
//   print(now2);
}
```

```dart
enum Status {
  approved, rejected, pending,
}

void main() {
  Status status = Status.approved;
  
  switch(status) {
    case Status.approved:
      print('승인 상태입니다');
      break;
    case Status.rejected:
      print('거절 상태입니다.');
      break;
    default:
      print('어디에도 해당되지 않습니다');
      break;
  }
}
```

```dart
void main() {
  int number = 2;
  if(number%3 == 0) {
    print('3의 배수입니다.');
  } else if(number%4 == 0) {
    print('4의 배수입니다.');
  } else {
    print('어떤 배수인지 알 수 없습니다.');
  }

  switch(number%3) {
    case 1:
      print('나머지가 1입니다.');
      break;
    case 2:
      print('나머지가 2입니다.');
      break;
    default:
      print('어떤 조건에도 해당되지 않습니다');
      break;
  }
}
```

```dart
void main() {
  int total = 0;
  List<int> numbersList = [1,1,2,3,5,8];
  
  for(int i=0; i<numbersList.length; i++) {
    total += numbersList[i];
  }
  print(total);
  
  total = 0;
  for(int number in numbersList) {
    total += number;
  }
  print(total);
}
```

```dart
void main() {
  int total = 0;
  
  while(total < 10) {
    print(total);
    total++;
  }
  
  total = 0;
  do {
    print(total);
    total++;
  } while(total < 10);
  
  while(total < 20) {
    print(total);
    
    if(total == 15) {
      break;
    }
    
    total++;
  }
  
  for (int i=0; i<20; i++) {
    if(i == 15) {
//       break;
      continue;
    }
    print(i);
  }
}
```

```dart
void main() {
  double res = linearExp(1,b: 2,x: 3);
  print(res);
  double res2 = linearExp(1,b: 2, x: 3);
  print(res2);
}
double linearExp(double a, {double b = 0, double x = 0}) { //[] : 옵셔널 파라미터(없는경우 기본값으로 계산됨)
  return a*x+b;
}
```

```dart
void main() {
  calculate(1, 2, add);
  calculate(1, 2, subtract);
}
typedef Operation(int x, int y);

void add(int x, int y) {
  print("결과값 : ${x+y}");
}

void subtract(int x, int y) {
  print("결과값 : ${x-y}");
}

void calculate(int x, int y, Operation oper) {
  oper(x, y);
}
```

```dart
void main() {
  Idol redVelvet = new Idol();
  redVelvet.sayName();
}
class Idol {
  String name = "레드벨벳";
  void sayName() {
    print("저는 ${this.name} 입니다.");
  }
}
```

```dart
/* constructor */
void main() {
  Idol seulgi = new Idol("슬기", "레드벨벳", 1);
  Idol rm = new Idol("RM", "BTS", 2);
  
  seulgi.sayName();
  rm.sayName();
  
  Idol seulgi2 = new Idol.fromMap({
    "name":"슬기","group":"레드벨벳", "id":3
  });
  seulgi2.sayName();
  print(seulgi2._id); //private 값은 파일단위, 같은파일내 경우 접근 가능
  
  Idol seulgi3 = new Idol("슬기", "레드벨벳", 1);
  print(seulgi3.id);
  seulgi3.setid = 20;
  print(seulgi3.id);
  
  BoyGroup rm2 = new BoyGroup("RM", "BTS", 1);
  GirlGroup seulgi4 = new GirlGroup("슬기", "레드벨벳", 2);
  
  rm2.sayMale();
  seulgi4.sayFemale();
}

class Idol {
  final name;
  final group;
  int _id; //private 변수 설정 : _ 붙여서 지정
  
  Idol(String name, String group, int id)
    : this.name = name,
      this.group = group,
      this._id = id;
  
  Idol.fromMap(Map values)
    : this.name = values["name"],
      this.group = values["group"],
      this._id = values["id"];
  
  void sayName() {
    print("저는 ${this.name} 입니다.");
  }
  
  get id {
    return this._id;
  }
  
  set setid(int id){
    this._id = id; //final 변수의 경우 수정 불가하므로 그냥 int형으로 수정
  }
}

class BoyGroup extends Idol {
  BoyGroup(String name, String group, int _id)
    : super(name, group, _id);
  
  void sayMale() {
    print("저는 남자 아이돌입니다.");
  }
}

class GirlGroup extends Idol {
  GirlGroup(String name, String group, int _id)
    : super(name, group, _id);
  
  void sayFemale() {
    print("저는 여자 아이돌입니다.");
  }
}
```

```dart
void main() {
  Parent parent = new Parent(3);
  int result = parent.calculate();
  print(result);
  
  Child child = new Child(3);
  int result2 = child.calculate();
  print(result2);
}

class Parent {
  final int number;
  
  Parent(int number)
    : this.number = number;
  
  int calculate() {
    return this.number * this.number;
  }
}

class Child extends Parent {
  Child(int number)
    : super(number);
  
  @override
  int calculate() {
//     return this.number + this.number;
    int result = super.calculate();
    return result + result;
  }
}
```

```dart
void main() {
  Employee seulgi = new Employee("슬기");
  Employee shorong = new Employee("초롱");
  
  Employee.building = "레드벨벳";
  
  print("----슬기----");
  seulgi.printNameAndBuilding();
  print("----초롱----");
  shorong.printNameAndBuilding();
  
  Employee.building = "강남 CGV";
  
  print("----슬기----");
  seulgi.printNameAndBuilding();
  print("----초롱----");
  shorong.printNameAndBuilding();
  
  Employee.printBuilding();
}

class Employee {
  static String building = "위워크";
  String name;
  
  Employee(String name)
    : this.name = name;
  
  void printNameAndBuilding() {
    print("제 이름은 $name 입니다. $building 건물에서 근무하고 있습니다.");
  }
  
  static void printBuilding() {
    print("저희 회사 직원들은 $building 건물에서 근무중입니다.");
  }
}
```

```dart
void main() {
  BoyGroup bts = new BoyGroup("BTS");
  bts.sayName();
  bts.sayGroup();
  
  new BoyGroup("BTS")
    ..sayName() ..sayGroup();
}

class IdolInterface {
  void sayName() {}
}

class BoyGroup implements IdolInterface {
  String name;
  String group = "BTS";
  
  BoyGroup(String name)
    : this.name = name;
  
  void sayName() {
    print("제 이름은 $name 입니다.");
  }
  
  void sayGroup() {
    print("저는 $group 소속입니다.");
  }
}

class GirlGroup implements IdolInterface {
  String name;
  
  GirlGroup(String name)
    : this.name = name;
  
  void sayName() {
    print("제 이름은 $name 입니다.");
  }
}
```

```dart
void main() {
  List redVelvet = [
    "아이린","슬기","웬디","조이","예리"
  ];
  
  print(redVelvet.first);
  print(redVelvet.isEmpty);
  print(redVelvet.isNotEmpty);
  print(redVelvet.length);
  print(redVelvet.last);
  print(redVelvet.reversed);
  
  redVelvet.add("코드팩토리");
  redVelvet.addAll(["코드팩토리", "코드팩토리2"]);
  print(redVelvet);
}
```

```dart
void main() {
  List membersList = [
    { "id":0, "name":"슬기"},
    { "id":1, "name":"아이린"},
    { "id":2, "name":"조이"}
  ];
  
  var item = membersList.firstWhere((item) => item["id"] == 1);
  print(item); //id = 1인 값 출력
  var index = membersList.indexWhere((item) => item["id"] == 1);
  print(index); //id= 1인 값의 index 출력
  
  var index2 = [10, 20, 30].indexOf(20);
  print(index2);
  
  var contains = [10, 20, 30].contains(30);
  print(contains);
}
```

```dart
void main() {
  
  List membersList = [
    { "id":0, "group":"레드벨벳", "name":"아이린"},
    { "id":1, "group":"BTS", "name":"RM"},
    { "id":2, "group":"레드벨벳", "name":"슬기"},
  ];
  
  membersList.forEach((item){
    print(item);
  });
  
  var newList = membersList.map((item) {
    return item["name"];
  });
  
  print(newList);
  
//   var fold = membersList.fold(0, (t, e) {
//     return t + e["id"];
//   });
//   print(fold);
  
  var reduce = [1,2,3,4,5].reduce((t, i) => t+i);
  print(reduce);
}
```

```dart
void main() {
  List numbersList = [10, 20, 30, 40, 50];
  numbersList.remove(10);
  print(numbersList);
  
  numbersList.removeAt(1);
  print(numbersList);
  
  numbersList.removeWhere((e) => e == 50);
  print(numbersList);
  
  List numbersList2 = [10,20,30,40,50];
  numbersList2.shuffle();
  print(numbersList2);
}
```

```dart
void main() {
  Map price = {
    "iphone":1500000,
    "Galaxy":1000000,
    "Apple Watch":500000
  };
  
  print(price.isEmpty);
  print(price.isNotEmpty);
  print(price.keys);
  print(price.values);
  print(price.length);
  
  price.addAll({
    "Airpods":390000,
    "Trackpad":100000
  });
  print(price);
  
  price.addEntries([
    MapEntry("Xiaomi", 500000),
//     MapEntry("Macbook", 2500000)
  ]);
  print(price);
  
  price["test"] = 99999;
  print(price);
  
  price.update("iphone", (prev) {
    return prev * 10;
  });
  print(price);
  
  price.update("macbook", (prev) {
    return prev * 10;
  }, ifAbsent: () {
    return 22222;
  });
  print(price);
  
  price.putIfAbsent("Macbook Pro", () => 333333);
  print(price);
  
  price.updateAll((k, v) {
    return v.toString() + "원";
  });
  
  print(price);
  
  price.remove("Apple Watch");
  print(price);
  price.removeWhere((k, v) {
    return k == "iphone";
  });
  print(price);
}
```
