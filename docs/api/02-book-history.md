<h1>[Woong API] - 책 대출내역</h1>

> ## `GET` /api/v2/history
- **Headers**
    | # | Name | Description | Required |
    | -- | -- | -- | -- |
    | 1 | `woongdo_client_token` | SHA512로 암호화 된 토큰 값 | O |

- **Parameters**
    | # | Name | Description | Data Type | Required |
    | -- | -- | -- | -- | -- |
    | 1 | `userID` | 암호화 되지 않은 userID 값 | `String` | O |
    | 2 | `isLoanned` | `true` or `false` | `Boolean` | X |

- **Response Classes**
    | # | Name | Data Type | Description |
    | -- | -- | -- | -- |
    | 1 | `code` | `String` | |
    | 2 | `message` | `String` | |
    | 3 | `length` | `Number` | 대출 내역 데이터 갯수 |
    | 4 | `data` | `Array<LoannedBookData>` | BookData에 대한 자료형은 하단 참조 |

    - **LoannedBookData**

        | # | Name | Data Type | Description |
        | -- | -- | -- | -- |
        | 1 | `idx` | `Number` | |
        | 2 | `userName` | `String` | 대출자 이름 |
        | 3 | `userID` | `String` | 대출자 아이디 |
        | 4 | `bookTitle` | `String` | 대출된 책 제목 |
        | 5 | `bookAuthor` | `String` | 대출된 책 작가 |
        | 6 | `bookCompany` | `String` | 대출된 책 출판사 |
        | 7 | `bookID` | `String` | 대출된 책 UUID |
        | 8 | `fromDate` | `String` | 대출 날짜 |
        | 9 | `endDate` | `String` | 반납 날짜 |
        | 10 | `status` | `Number` | 책 상태 (0: `반납완료`, 1: `반납미완료`) |

- **Response Errors**
    | # | HTTP STATUS CODE | Reason | Description |
    | -- | -- | -- | -- |
    | 1 | `401` | Unauthorized | 생략된 Request Header 값이 있음. |
    | 2 | `403` | Forbidden | 알맞지 않은 헤더 값이 참조됨. |
    | 3 | `404` | Not Found | 대출 내역 데이터가 존재하지 않음. |
