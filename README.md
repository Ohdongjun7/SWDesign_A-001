```mermaid
graph LR
    %% Actor Definition
    User((사용자))
    Admin((관리자))

    subgraph "도서대여 시스템"
        %% Use Cases
        UC1(사용자 등록)
        UC2(사용자수정)
        UC3(사용자삭제)
        UC4(도서 대여)
        UC5(도서 반납)
        UC6(도서등록)
        UC7(도서수정)
        UC8(도서삭제)
        UC9(도서id조회)
        UC10(사용자id조회)
        UC11(대여상태확인)
        UC12(연체확인)

        %% Relationships within System
        UC4 -. "<<include>>" .-> UC9
        UC4 -. "<<include>>" .-> UC10
        UC4 -. "<<include>>" .-> UC11
        
        UC5 -. "<<include>>" .-> UC9
        UC5 -. "<<include>>" .-> UC10
        UC5 -. "<<extend>>" .-> UC12
    end

    %% Actor Relationships
    User --> UC1
    User --> UC2
    User --> UC3
    User --> UC4
    User --> UC5

    Admin --> UC6
    Admin --> UC7
    Admin --> UC8
    Admin --> UC11
    Admin --> UC12