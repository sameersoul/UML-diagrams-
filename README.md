# UML-diagrams-
```mermaid
sequenceDiagram
    participant User
    participant ATM
    participant Account
    participant Transaction

    User->>ATM: insertCard()
    ATM->>Account: validateCard()
    Account-->>ATM: validationResult()
    User->>ATM: enterPIN()
    ATM->>Account: verifyPIN()
    Account-->>ATM: PINVerified()
    User->>ATM: selectTransaction()
    ATM->>Transaction: createTransaction()
    Transaction->>Account: debitAmount()
    Account-->>Transaction: debitResult()
    ATM-->>User: dispenseCash()
    ATM->>Transaction: completeTransaction()
    Transaction-->>ATM: transactionResult()
