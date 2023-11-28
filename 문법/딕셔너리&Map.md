✍#`Map` #`딕셔너리`
# JAVA
자바에는 "딕셔너리" 자료구조가 없다. 하지만 'Map' 을 통해 키-값 쌍을 저장하고 관리한다.<br><br>
**'Map'의 여러 구현체** <br>
① HashMap<br>
② TreeMap<br>
③ LinkedHashMap<br><br>

#### ✔ Map 인터페이스
* key-value 쌍의 집합
* 각 키는 중복이 불가
* Map 안에서 key-value에 따른 순서 없음

```java
Map<String, Integer> myMap = new HashMap<>();
myMap.put("One", 1); // Map 안에 값 넣기
myMap.put("Two", 2);
myMap.put("Three", 3);

myMap.size(); // Map 크기 확인

myMap.replace(one, 4); // value 값 변경

System.out.println(myMap.get("Two")); // Map 안의 값 가져오기
// 출력: 2

// 모두 출력
myMap.forEach((k, v) -> {
  System.out.println(k + " " + v);
});
// 출력:
// One 4
// Two 2
// Three 3

```

#### ✔ TreeMap
* 삽입 순서에 따라 정렬
