## Job 
Dependencies are
- JobRepository
- Step[]
- name

Example of a Job configuration:
```xml
<job id= "videoGameJob">
  <step id="loadCharacters" parent="s1" next="loadWeapons"/>
  <step id="loadWeapons" parent="s2" next="loadContext" />
  <step id="loadContext" parent="s3" />
 </job>
```  

A job instance can be set to not be restartable, meaning the developer will need to instantiate another instance of the Job class 
in order to run the job again ([Sring Batch Documentation])(http://docs.spring.io/spring-batch/reference/html/configureJob.html):

```java
Job job = new SimpleJob();
job.setRestartable(false);

JobParameters jobParameters = new JobParameters();

JobExecution firstExecution = jobRepository.createJobExecution(job, jobParameters);
jobRepository.saveOrUpdate(firstExecution);
```

## Steps 
Consist of
- ItemReader
- ItemWriter
- ItemProcessor
