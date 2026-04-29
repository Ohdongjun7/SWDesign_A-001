```mermaid
classDiagram
    class User {
        - id: String
        - pw: String
        - name: String
        - phone: String
        - address: String
        + registerUser(id: String, pw: String, name: String, phone: String, address: String): void
        + updateUser(id: String, pw: String, name: String, phone: String, address: String): void
        + deleteUser(id: String): void
        + searchUser(id: String): User
    }

    class Account {
        - number: String
        - balance: long
        + deposit(id: String, amount: long): void
        + withdraw(id: String, amount: long): void
        + transfer(id: String, targetAccountNumber: String, amount: long): void
        + computeBalances(): long
    }

    class BankUI {
        + displayMenu(): void
        + requestTransaction(): void
    }

    %% 관계 설정
    %% User 1개당 Account 1개 이상 (1 to 1..*)
    %% Account에서 User로 사용자 조회를 위한 연관관계
    User "1" <-- "1..*" Account : search user

    %% BankUI가 Account에 의존함
    BankUI ..> Account : uses