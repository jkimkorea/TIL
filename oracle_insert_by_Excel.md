# Oracle 데이터 자동 insert

**엑셀로 테이블에 데이터 삽입하는 방법**

> 출처: 코딩하는 흑구

**1. sql developer에서 삽입할 테이블의 구조를 확인한다.( 컬럼명만 확인하면 됨 사이즈가 있는 경우 엑셀 파일에서 해당 사이즈 넘지 않도록 조절한다.)**

[https://t1.daumcdn.net/cfile/tistory/994A5D435CBC367136](https://t1.daumcdn.net/cfile/tistory/994A5D435CBC367136)

**설계한 테이블의 정보.**

[https://t1.daumcdn.net/cfile/tistory/9939C2435CBC36711F](https://t1.daumcdn.net/cfile/tistory/9939C2435CBC36711F)

**2. 컬럼명에 맞춰서 데이터를 기입한다.(컬럼명의 대소문자는 오라클에서는 오브젝트의 대소문자를 구분하지 않기 때문에 상관X)**

[https://t1.daumcdn.net/cfile/tistory/99722A435CBC367229](https://t1.daumcdn.net/cfile/tistory/99722A435CBC367229)

**3. sql developer에서 사용자의 테이블을 우클릭 후 "데이터 임포트"를 클릭한다**

[https://t1.daumcdn.net/cfile/tistory/99E602435CBC367223](https://t1.daumcdn.net/cfile/tistory/99E602435CBC367223)

**4. 데이터 임포트 마법사가 열리면 로컬에서 엑셀파일을 찾아 업로드 한후 다음을 클릭한다.**

[https://t1.daumcdn.net/cfile/tistory/991DF9435CBC367337](https://t1.daumcdn.net/cfile/tistory/991DF9435CBC367337)

**5. 계속 다음을 누르면서 완료버튼을 누른다.**

[https://t1.daumcdn.net/cfile/tistory/992F78435CBC36732A](https://t1.daumcdn.net/cfile/tistory/992F78435CBC36732A)

**6. 데이터를 성공적으로 임포트 했다면 다음과 같은 알림창이 뜰 것이다.**

[https://t1.daumcdn.net/cfile/tistory/99DE54435CBC367430](https://t1.daumcdn.net/cfile/tistory/99DE54435CBC367430)

**주의사항**

- 삽입하는 테이블에 insert 트리거가 걸려있는 경우 엑셀로 임포트하는 경우도 트리거에 걸리기 때문에 이를 잘 고려하여 에러가 나지 않도록 유효한 데이터를 삽입해야 한다.
- 자동커밋되므로 트랜잭션 관리에 유의해야한다.
- 삽입도중 특정 레코드에서 에러가 발생했을 경우에는 일단 삽입을 취소한 후 에러를 알아보고 한큐에 삽입하는 편이 정신건강에 좋다.
