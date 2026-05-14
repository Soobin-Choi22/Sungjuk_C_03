sequenceDiagram
    autonumber
    participant UI as Add_Sungjuk_UI
    participant S as 성적
    participant P as 교수
    
    UI->>+S: 성적입력(교수id, 학생id, 자바, DB, 보안)
    S->>+P: 교수체크(교수id)
    P-->>-S: 인증 결과 (true/false)
    
    alt 인증 결과 == true
        S->>S: 총점/평균 계산
        S-->>-UI: 입력 성공 메시지 반환
    else 인증 결과 == false
        S-->>-UI: 권한 오류 메시지 반환
    end
