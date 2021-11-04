# ImageCache 만들기

어플리케이션은 한정된 자원(메모리)를 가지고, 동작을 시킨다. 용량이 큰 이미지 같은 것들을 계속 다운받고 사용하게 되면 리소스를 소모하게 된다. 재사용할만한 자원을 특정 영역에 저장을 해놓는 것을 캐싱이라고 한다.

캐싱 된 데이터가 있다면 추가적인 자원을 소모하지 않고, 캐싱 데이터를 가져다 쓸 수 있기 때문에 자원을 절약 할 수 있고, 애플리케이션의 처리속도가 향상 된다.

### Memory Caching VS Disk Caching

- Memory  Caching : 애플리케이션의 메모리 영역의 일부분을 Caching에 사용 하는 것. 애플리케이션이 종료되어 메모리에서 해제되면 이 영역에 있던 리소스들은 OS에 반환하면서 Memory Caching 되어 있던 리소스들은 사라지게 됨
- Disk Caching : 파일 형태로 디스크에 저장. 애플리케이션이 차지하고 있는 용량이 커지게 됨. 앱을 껐다 켜도 사라지지 않음.

### NSCache

Memory Caching에 사용하는 클래스

### 특징

- Caching 할 객체의 최대 수를 지정 할 수 있다.
- Caching Cost Limit을 정할 수 있다.
- 연결 리스트와 Dictionary를 함께 사용 한다.
    - Caching은 중간에 있는 데이터를 추가,삭제가 빈번 배열을 사용하면 데이터를 앞으로 당기거나 미는 작업이 필요 할 수 있음
    - 연결 리스트 O(n)이 발생, 동시에 Dictionary를 사용함으로써 key로 데이터를 접근할때 O(1)로 탐색
    
- limitation 을 넘어 갈 경우 적은 용량 cost의 데이터 부터 삭제
    - cost limitation을 먼저 체크하고 이후 count limitaion을 체크 함. NSDicardableContent 객체의 삭제는 연결리스트를 통해 삭제가 진행되는데, 이 연결리스트는 cost로 정렬된 연결 리스트 임. head부터 삭제가 진행되기 때문에 결과론적으로는 적은 cost데이터 부터 삭제가 됨.
    

### Disk Caching