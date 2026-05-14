```mermaid
flowchart LR
    %% 1. 액터 정의 (원형 모양)
    Prof((교수))
    
    %% 2. 시스템 경계 정의 (subgraph 사용)
    subgraph System [성적 처리 시스템]
        direction TB
        UC_Input([성적입력])
        UC_Search([학점조회])
        UC_Check([교수체크])
    end
    
    %% 3. 액터와 유스케이스 간의 관계 (실선)
    Prof --> UC_Input
    Prof --> UC_Search
    
    %% 4. 포함(include) 관계 (점선 화살표 및 라벨)
    UC_Input -. "<<include>>" .-> UC_Check
    UC_Search -. "<<include>>" .-> UC_Check
