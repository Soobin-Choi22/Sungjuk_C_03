```mermaid
sequenceDiagram
    autonumber
    participant UI as Search_Sungjuk_UI
    participant S as 성적
    participant P as 교수
    
    UI->>S: 학점조회(교수id, 학생id)
    S->>P: 교수체크(교수id)
    P-->>S: 인증 결과 (true/false)
    
    alt 인증 결과 == true
        S->>S: 평균 기준 학점 판별
        S-->>UI: 학점 결과(A/B/C) 반환
    else 인증 결과 == false
        S-->>UI: 권한 오류 메시지 반환
    end
