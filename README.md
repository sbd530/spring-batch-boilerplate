## JobLauncher

- 스프링부트 배치 구동시 Bean 자동 생성

- Job 실행
  - `JobLauncher.run(job, jobParameters)`
  - `JobLauncherApplicationRunner`가 자동적으로 `JobLauncher`를 실행
  - 동기적 실행
    - `taskExecutor` = `SyncTaskExecutor` (기본값)
    - 배치 처리 완료 후 `JobExecution` 반환 (ExitStatus=FINISHED or FAILED)
    - 스케줄러에 의한 배치처리에 적합
  - 비동기적 실행
    - `taskExecutor` = `SimpleAsyncTaskExecutor`
    - `JobExecution` 바로 반환후 (ExitStatus=UNKNOWN) 배치처리를 완료 (ExitStatus=FINISHED or FAILED)
    - HTTP 요청 등에 의한 배치처리에 적합