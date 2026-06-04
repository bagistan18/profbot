# PROTO - Пропорциональный генератор

## ER-диаграмма

```mermaid
erDiagram
    USER ||--o{ TEST_RESULT : has
    USER {
        int id PK
        bigint telegram_id UK
        string full_name
        int age
        string role
    }
    QUESTION ||--o{ ANSWER : contains
    QUESTION {
        int id PK 
        string text
        int order_num
    }
    ANSWER {
        int id PK
        int question_id FK
        string answer_text
        int points
    }
    PROFESSION ||--o{ TEST_RESULT : recommended
    PROFESSION {
        int id PK
        string name
        string description
    }
    TEST_RESULT {
        int id PK
        int user_id FK
        int profession_id FK
        int total_points
    }
