# #2. Object Oriented Programming

- OOP
    - 클래스 기반 프로그래밍
        - 보통 class의 변수는 final로 생성
            
            (추후 변경됨을 방지하기 위해)
            

```dart
// class 선언
Idol bts = Idol.fromList(['RM', '진', '슈가'], 
												 ['BTS']);

class Idol{
	final String name;
	final List <String> members;

	Idol(String name, List <String> members)
	: this.name = name,
		this.members = members

	// const Idol(this.name, this.members);
	**// const 추가하면 선언에서도 const로 선언 !!**

	Idol.fromList(List values)
	:this.members = values[0],
	 this.name = values[1];

	void sayHello()
	{
		print('${this.name}' 입니다);
	}
}
```

- getter/setter
    - final 선언해도 값이 변경되기 때문에 요즘에는 거의 사용하지 않고 있음

```dart
String get firstMember{
	return this.members[0];
}

set firstMember(String name){
	this.name = name;
}
```

- 상속

```dart
class Idol{
	String name;
	int membersCount;
	Idol({
		// non-null인 경우 required를 붙여줌
		required this.name,
		required this.membersCount
	});
}

class BoyGroup extends Idol{
	BoyGroup(
		String name,
		int membersCount,
		) : super(		**// super 부모값의 상속**
					name : name,
					membersCount : membersCount,
				);
}
```

- override
    
    ```dart
    @override
    int calculate(){
    	return super.number * 4;
    }
    ```
    
- static은 instance에 귀속되지 않고 class에 귀속된다.
    
    `인스턴스를 선언하지 않아도 사용 및 대입 가능` 
    
- generic - 타입을 외부에서 받을 때 사용

```dart
class Lecture<T> {
	final T id;
	Lecture(this.id)
}
```

- 모든 class의 최상위는 object 이다.