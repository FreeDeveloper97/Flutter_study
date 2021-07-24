# Flutter_study
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
