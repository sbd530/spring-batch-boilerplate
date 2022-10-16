## Job 실행 중간에 Step 이 실패한 경우 

- Step1 COMPLETED -> Step2 FAILED -> Step3 No Status
- Job FAILED

와 같은 상황에서 같은 상황에서 같은 Job 을 다시 실행시키면

- Step1 Skip
- Step2 Try
- If Step2 COMPLETED, Step3 Try

와 같이 성공한 Step 은 기본적으로 생략된다. 성공한 스텝도 실행시키려면 설정을 넣어줘야 한다. 

## StepContribution

- readCount : 성공적으로 읽은 수
- readSkipCount : 실패해서 읽기 실패한 수
- filterCount : ItemProcessor 에서 필터링된 수
- filterSkipCount : 필터링 실패한 수
- writeCount : 성공적으로 쓴 수
- writeSkipCount : 실패해서 쓰기 실패한 수
- parentSkipCount : 부모 StepExecution 의 총 skip 수
- ExitStatus : 실행결과 -> [UNKNOWN, EXECUTING, COMPLETED, NOOP, FAILED, STOPPED]
- stepExecution : 현재 StepExecution
