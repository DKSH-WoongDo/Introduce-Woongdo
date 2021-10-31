<h1>[Woong API] - 책 정보 조회</h1>

> ## `GET` /api/v2/search
- **Headers**
    | # | Name | Description | Required |
    | -- | -- | -- | -- |
    | 1 | `woongdo_client_token` | SHA512로 암호화 된 토큰 값 | O |

- **Parameters**
    | # | Name | Description | Data Type | Required |
    | -- | -- | -- | -- | -- |
    | 1 | `query ` | | `String` | O |
    | 2 | `option` | title, author, company... | `String` | X |

- **Response Classes**
    | # | Name | Data Type | Description |
    | -- | -- | -- | -- |
    | 1 | `code` | `String` | |
    | 2 | `message` | `String` | |
    | 3 | `length` | `Number` | 책 데이터 갯수 |
    | 4 | `data` | `Array<BookData>` | BookData에 대한 자료형은 하단 참조 |

    - **BookData**

        | # | Name | Data Type | Description |
        | -- | -- | -- | -- |
        | 1 | `idx` | `Number` | |
        | 2 | `title` | `String` | 책 제목 |
        | 3 | `author` | `String` | 책 작가 |
        | 4 | `company` | `String` | 책 출판사 |
        | 5 | `status` | `Number` | 책 상태 (0: `대출가능`, 1: `대출중`, 2: `대출불가`) |

- **Response Errors**
    | # | HTTP STATUS CODE | Reason | Description |
    | -- | -- | -- | -- |
    | 1 | `400` | Bad Request | 생략된 Parameter 값이 있음. |
    | 1 | `401` | Unauthorized | 생략된 Request Header 값이 있음. |
    | 2 | `403` | Forbidden | 알맞지 않은 헤더 값이 참조됨. |
    | 3 | `404` | Not Found | Query에 따른 데이터가 존재하지 않음. |
