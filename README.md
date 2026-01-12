%%{init: {'flowchart': {'curve': 'linear'}}}%%
flowchart LR
    %% 왼쪽 그룹: 단말장치
    subgraph Terminals ["단말장치"]
        direction TB
        D1[디지털]
        D3[디지털]
        A1[아날로그]
    end

    %% 중앙 장치들
    M["전화선 (아날로그)<br/><font color='blue'>모뎀</font>"]
    DSU["전용선 (디지털)<br/><font color='red'>DSU</font>"]
    C["전용선 (디지털)<br/><font color='green'>코덱</font>"]
    
    
    
    %% 오른쪽 그룹: 컴퓨터
    subgraph Computers ["컴퓨터"]
        direction TB
        D2[디지털]
        D4[디지털]
        A2[아날로그]
    end

    %% 연결 관계 (직선 유지를 위해 ---> 사용)
    D1 ---> M ---> D2
    D3 ---> DSU ---> D4
    A1 ---> C ---> A2

    %% 스타일 설정
    linkStyle 0,1 stroke:blue,stroke-width:2px;
    linkStyle 2,3 stroke:red,stroke-width:2px;
    linkStyle 4,5 stroke:green,stroke-width:2px;

    %% 서브그래프 및 노드 스타일
    style Terminals fill:#f9f9f9,stroke:#333,stroke-dasharray: 5 5
    style Computers fill:#f9f9f9,stroke:#333,stroke-dasharray: 5 5
    classDef default fill:#fff,stroke:#333,stroke-width:1px;
