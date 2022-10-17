## BatchProperties

### JobLauncherApplicationRunner

- Spring Batch 작업을 시작하는 ApplicationRunner. BatchAutoConfiguration 에서 생성됨
- 스프링부트에서 제공하는 ApplicationRunner 의 구현체로 앱 구동되자마자 실행됨
- 디폴트로 Bean 으로 등록된 모든 Job 을 실행

### BatchProperties

- SpringBatch 의 환경 설정 클래스
- Job 이름, 스키마 초기화 설정, 테이블 Prefix 값 설정 가능
- application.yml 파일로 설정 가능

```yaml
spring:
  batch:
    job:
      name: ${job.name:NONE}
    jdbc:
      initialize-schema: NEVER
      tablePrefix: SYSTEM
      isolation-level-for-create: read_committed
```

### Job 실행 옵션

- 지정한 Job 만 실행하도록 설정 가능
- `spring.batch.job.names: ${job.name:NONE}`
- 앱 실행시 Program arguments 로 job 이름 입력
  - `--job.name=helloJob`
  - `--job.name=helloJob,simpleJob` (복수 Job 실행)