# UML-diagram
```mermaid
%% Define swimlanes and title
---
title: Activity Diagram for Rescue Seeker and Women Leader
---
flowchart TD
    subgraph RescueSeeker[Rescue Seeker]
        direction TB
        A1(Start):::startEnd --> B1(AI Face Detection):::process
        B1 -->|Female| B2(Sign-up):::process
        B1 -->|Male| B3(Not Allowed to Sign-up):::process
        B2 --> B4(Email/Phone Verification):::process
        B4 --> B5(Set Password):::process
        B5 --> B6(Login):::process
        B6 --> B7(View List of Women Leaders):::process
        B7 --> B8(Turn on Panic Mode):::process
        B8 --> B9(Send Geo-location to Women Leader):::process
        B9 -->|Fork| B10(Record Video/Audio/Send Text):::process
        B10 --> B11{Help Received?}:::decision
        B11 -->|Yes| B12(Turn off Panic Mode):::process
        B12 --> A2(End):::startEnd
    end
    
    subgraph WomenLeader[Women Leader]
        direction TB
        C1(Start):::startEnd --> C2(View List of Rescue Seekers):::process
        B9 --> C3(Receive Panic Alert and Geo-location):::process
        C3 --> C4(Display Countdown Timer):::process
        C4 --> C5(Notification Section):::process
        C5 --> C6(Provide Assistance):::process
        C6 --> C7(Help Received Confirmation):::process
        C7 --> C8(End):::startEnd
    end

    %% Define Classes
    classDef startEnd fill:#32CD32,stroke:#333,stroke-width:2px,shape:circle;
    classDef process fill:#FFD700,stroke:#333,stroke-width:2px;
    classDef decision fill:#FF4500,stroke:#333,stroke-width:2px,shape:diamond;
    classDef user1 fill:#FFDDC1,stroke:#333,stroke-width:2px;
    classDef user2 fill:#C1E1FF,stroke:#333,stroke-width:2px;

    %% Link Swimlanes
    B8 -.-> C3
    B9 -.-> C3
    C7 --> B11
