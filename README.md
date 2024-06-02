# UML-diagram
```mermaid
sequenceDiagram
    autonumber
    participant Admin as Women Leader (Admin)
    participant App as Community Tab
    participant System as System
    participant Seeker as Rescue Seeker

    Admin->>System: Login with credentials
    System-->>Admin: Land on home page
    System-->>Admin: Display list of nearby women leaders

    Admin->>App: Click on community tab
    Admin->>App: Click on create group icon
    Admin->>App: Enter group details
    Admin->>App: Click on create group
    App-->>System: Create group
    System-->>Admin: Group created
    System-->>Seeker: Group reflected in community tab

    Seeker->>System: Login into the app
    Seeker->>App: Click on community tab
    Seeker->>App: Select group to join
    Seeker->>App: Click on join button
    App-->>System: Send join request to admin
    System-->>Admin: Notify of join request

    Admin->>App: Accept join request
    App-->>System: Accept join request
    System-->>Seeker: Notify of admin acceptance

    Seeker->>App: View announcements in the group
