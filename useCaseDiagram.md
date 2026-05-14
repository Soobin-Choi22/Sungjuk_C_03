```mermaid
usecaseDiagram
    actor "교수" as Prof
    
    package "성적 처리 시스템" {
        usecase "성적입력" as UC\_Input
        usecase "학점조회" as UC\_Search
        usecase "교수체크" as UC\_Check
    }
    
    Prof --> UC\_Input
    Prof --> UC\_Search
    
    %% 포함 관계: 성적입력과 학점조회 시 반드시 교수체크 수행
    UC\_Input ..> UC\_Check : <<include>>
    UC\_Search ..> UC\_Check : <<include>>

