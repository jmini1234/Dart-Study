# #3. functional programming

- 함수형 프로그래밍은 chaining 가능, 계속해서 새로운 형태를 만들어 낼 수 있다.
- 보통 명령형 프로그래밍과 비교해서 `어떻게가 아니라 무엇에 초점을 맞춘다.`
- 장점
    - 코드 간결 & 표현력 향상
    - 모듈화
    - 문제를 더 작은 조각으로 나눔 !

```dart
void main(){
	final _result = _numbers.where((number) => number%2 ==0).toList();
	print(_result);
		items.where((e)=> e % 2 ==0).map((e) => '숫자 $e').forEach(print);
}
const _numbers = [1, 2, 3, 4, 5];

```

- 코드가 간결해진다는 장점

```dart
List <String> blackPink = ['로제', '지수', '리사', '제니'];
blackPink.asMap();
blackPint.toSet();

final newBlackPink = blackPink.map((x) {
	return '블랙핑크 $x';
});

final newBlackPink2 = blackPink.map((x) => '블랙핑크 $x');

List<Map<String, String>> people = [
		{
			'name' : '로제',
			'group' : '블랙핑크,
		},
		{
			'name' : '제니',
			'group' : '블랙핑크,
		},
		{
			'name' : '뷔',
			'group' : 'BTS',
		}];

people.where((x) => x['group'] == '블랙핑크').toList();
```

- reduce 함수 : 각각 다 더하기

```dart
List<int> numbers = [1, 3, 5, 7, 9];
final result = numbers.reduce((prev, next) => prev + next);
// 25 (총 값을 다 더해줌)
```

- fold 함수 : 각각 다 더하지만 원하는 형태의 값으로 바꿀 수 있음

```dart
List <String> blackPink = ['로제', '지수', '리사', '제니'];

final sentence = blackPink.fold<int>(0, (prev, next) => prev + next.length);
```
