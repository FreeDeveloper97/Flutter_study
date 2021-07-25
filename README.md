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
