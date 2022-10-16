## JobRepository

- `@EnableBatchProcessing` 선언하면 자동으로 `JobRepository`가 생성됨
- `BatchConfigurer` 인터페이스를 구현하고나 `BasicBatchConfigurer` 를 상속해서 `JobRepository` 설정을 커스터마이징할 수 있다.
  - JDBC 방식으로 설정 - `JobRepositoryFactoryBean`
    - AOP 기술로 트랜잭션 처리
    - 트랜잭션 isolation 의 기본값은 최고수준 SERIALIZABLE. 다른 레벨로도 지정 가능
    - 메타테이블의 Table Prefix 변경 가능. 기본값은 `BATCH_`
  - In Memory 방식으로 설정 - `MapJobRepositoryFactoryBean`
    - 성능 등의 이유로 도메인 데이터를 DB에 저장하지 않고 싶은 경우
    - 빠른 프로토타입 개발이 필요할 경우