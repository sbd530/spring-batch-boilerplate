## ExecutionContext

- Execution 객체의 상태를 저장하는 공유 객체
- DB 에 직렬화(JSON) 한 값으로 저장
- 각 StepExecution 는 Step 간 공유 불가
- 각 JobExecution 는 Job 간 공유 불가하지만, Job 안의 Step 간에는 공유 가능