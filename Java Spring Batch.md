** Job **
Dependencies are
- JobRepository
- Step[]
- name

Example of a Job configuration:
```xml
<job id= "videoGameJob">
  <step id="loadCharacters" parent="s1" next="loadWeapons"/>
  <step id="loadWeapons" parent="s2" next="loadContext" />
  <step id="loadContext parent="s3" />
 </job>
```  

** Steps **
Consist of
- ItemReader
- ItemWriter
- ItemProcessor
