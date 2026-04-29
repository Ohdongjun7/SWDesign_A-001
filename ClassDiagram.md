classDiagram
    class User {
        -id: String
        -pw: String
        -name: String
        +registerUser(id: String, pw: String, name: String)boolean
        +updateUser(id: String, pw: String, name: String)boolean
        +deleteUser(id: String)boolean
        +searchUserId(id: String)boolean
    }

    class Book {
        -bookId: String
        -title: String
        -publisher: String
        -rentalStatus: boolean
        +registerBook(bookId: String, title: String, publisher: String, rentalStatus: boolean)boolean
        +updateBook(bookId: String, title: String, publisher: String, rentalStatus: boolean)boolean
        +deleteBook(bookId: String)boolean
        +searchBookId(bookId: String)boolean
        +checkRentalStatus(bookId: String)boolean
    }

    class RentalInfo {
        -rentalId: String
        -id: String
        -bookId: String
        -rentalDate: int
        -dueDate: int
        -returnDate: int
        +rentBook(id: String, bookId: String, dueDate : int, returnDate:int)String
        +returnBook(id: String, bookId: String, dueDate : int, returnDate:int)String
        +checkOverdue(returnDate: int, dueDate: int)boolean
    }

    %% 연관 및 의존 관계 설정
    RentalInfo ..> User : <<use>> searchUserId
    RentalInfo ..> Book : <<use>> searchBookId / checkStatus