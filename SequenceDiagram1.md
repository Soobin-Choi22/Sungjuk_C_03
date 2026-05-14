sequenceDiagram

&#x20;   autonumber

&#x20;   participant UI as Add\_Sungjuk\_UI

&#x20;   participant S as 성적

&#x20;   participant P as 교수

&#x20;   

&#x20;   UI->>+S: 성적입력(교수id, 학생id, 자바, DB, 보안)

&#x20;   S->>+P: 교수체크(교수id)

&#x20;   P-->>-S: 인증 결과 (true/false)

&#x20;   

&#x20;   alt 인증 결과 == true

&#x20;       S->>S: 총점/평균 계산

&#x20;       S-->>-UI: 입력 성공 메시지 반환

&#x20;   else 인증 결과 == false

&#x20;       S-->>-UI: 권한 오류 메시지 반환

&#x20;   end

