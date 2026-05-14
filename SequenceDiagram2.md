sequenceDiagram

&#x20;   autonumber

&#x20;   participant UI as Search\_Sungjuk\_UI

&#x20;   participant S as 성적

&#x20;   participant P as 교수

&#x20;   

&#x20;   %% 학생id 파라미터 추가 완료

&#x20;   UI->>+S: 학점조회(교수id, 학생id)

&#x20;   S->>+P: 교수체크(교수id)

&#x20;   P-->>-S: 인증 결과 (true/false)

&#x20;   

&#x20;   alt 인증 결과 == true

&#x20;       S->>S: 평균 기준 학점 판별

&#x20;       S-->>-UI: 학점 결과(A/B/C) 반환

&#x20;   else 인증 결과 == false

&#x20;       S-->>-UI: 권한 오류 메시지 반환

&#x20;   end

