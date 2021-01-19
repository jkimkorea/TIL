# ArrayList의 여러가지 명령어

> 출처: 코딩 펙토리

## **ArrayList 사용법**

### **ArrayList 선언**

```
ArrayList list = new ArrayList();//타입 미설정 Object로 선언된다.
ArrayList<Student> members = new ArrayList<Student>();//타입설정 Student객체만 사용가능
ArrayList<Integer> num = new ArrayList<Integer>();//타입설정 int타입만 사용가능
ArrayList<Integer> num2 = new ArrayList<>();//new에서 타입 파라미터 생략가능
ArrayList<Integer> num3 = new ArrayList<Integer>(10);//초기 용량(capacity)지정
ArrayList<Integer> list2 = new ArrayList<Integer>(Arrays.asList(1,2,3));//생성시 값추가

```

ArrayList선언시 ArrayList list = new ArrayList()로 선언 후 내부에 임의의 값을 넣고 사용할수도 있지만 이렇게 사용할경우 값을 뽑아내기 위해서는 캐스팅(Casting) 연산이 필요하고 잘못된 타입으로 캐스팅을 한 경우에는 에러가 발생하기에 위와 같은 방식은 추천하지 않습니다. ArrayList를 사용할시에는 ArrayList에 타입을 명시해주는것이 좋습니다. JDK 5.0이후부터 자료형의 안정성을 위해 제너릭스(Generics)라는 개념이 도입되었습니다. ArrayLIst<String> list = new ArrayList<String>(); 이라고 되어있다면 String객체들만 add되어질수있고 다른 타입의 객체는 사용이 불가능합니다.

> ※제네릭스는 선언할 수 있는 타입이 객체 타입입니다. int는 기본자료형이기 때문에 들어갈수 없으므로 int를 객체화시킨 wrapper클래스를 사용해야 합니다.

[ava] 래퍼 클래스(Wrapper Class)란 무엇인가? (박싱, 언박싱)](https://coding-factory.tistory.com/547)

### **ArrayList 값 추가**

```
ArrayList<Integer> list = new ArrayList<Integer>();
list.add(3); //값 추가
list.add(null); //null값도 add가능
list.add(1,10); //index 1뒤에 10 삽입

```

```
ArrayList<Student> members = new ArrayList<Student>();
Student student = new Student(name,age);
members.add(student);
members.add(new Member("홍길동",15));

```

ArrayList에 값을 추가하려면 ArrayList의 add(index, value) 메소드를 사용하면 됩니다. index를 생략하면 ArrayList 맨 뒤에 데이터가 추가되며 index중간에 값을 추가하면 해당 인덱스부터 마지막 인덱스까지 모두 1씩 뒤로 밀려납니다.

![https://blog.kakaocdn.net/dn/bd9xgH/btqEiM3wKkP/k6YlzEPE3414PzuO1zse00/img.png](https://blog.kakaocdn.net/dn/bd9xgH/btqEiM3wKkP/k6YlzEPE3414PzuO1zse00/img.png)

### **ArrayList 값 삭제**

```
ArrayList<Integer> list = new ArrayList<Integer>(Arrays.asList(1,2,3));
list.remove(1);  //index 1 제거
list.clear();  //모든 값 제거

```

ArrayList에 값을 제거하려면 ArrayList의 remove(index) 메소드를 사용하면 됩니다. remove()함수를 사용하여 특정 인덱스의 객체를 제거하면 바로 뒤 인덱스부터 마지막 인덱스까지 모두 앞으로 1씩 당겨집니다. 모든 값을 제거하려면 clear() 메소드를 사용하면 됩니다.

### **ArrayList 크기 구하기**

```
ArrayList<Integer> list = new ArrayList<Integer>(Arrays.asList(1,2,3));
System.out.println(list.size()); //list 크기 : 3

```

ArrayList의 크기를 구하려면 ArrayList의 size() 메소드를 사용하면 됩니다.

### **ArrayList 값 출력**

```
ArrayList<Integer> list = new ArrayList<Integer>(Arrays.asList(1,2,3));

System.out.println(list.get(0));//0번째 index 출력
		
for(Integer i : list) { //for문을 통한 전체출력
    System.out.println(i);
}

Iterator iter = list.iterator(); //Iterator 선언 
while(iter.hasNext()){//다음값이 있는지 체크
    System.out.println(iter.next()); //값 출력
}

```

ArrayList의 get(index) 메소드를 사용하면 ArrayList의 원하는 index의 값이 리턴됩니다. 전체출력은 대부분 for문을 통해서 출력을하고 Iterator를 사용해서 출력을 할수도 있습니다.

### **ArrayList 값 검색**

```
ArrayList<Integer> list = new ArrayList<Integer>(Arrays.asList(1,2,3));
System.out.println(list.contains(1)); //list에 1이 있는지 검색 : true
System.out.println(list.indexOf(1)); //1이 있는 index반환 없으면 -1

```

ArrayList에서 찾고자 하는 값을 검색하려면 ArrayList의 contains(value) 메소드를 사용하면 됩니다. 만약 값이 있다면 true가 리턴되고 값이 없다면 false가 리턴됩니다. 값을 있는 index를 찾으려면 indexOf(value) 메소드를 사용하면 되고 만약 값이 없다면 -1을 리턴합니다.
