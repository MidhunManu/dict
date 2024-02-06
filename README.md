# Data Dictionary

## Table: avatars
| Column       | Type                   | Nullable | Default                                   | Description                                |
|--------------|------------------------|----------|-------------------------------------------|--------------------------------------------|
| a_id         | integer                | not null | nextval('avatars_a_id_seq'::regclass)   | Unique identifier for avatars              |
| avatar_url   | character varying(150) |          |                                           | URL of the avatar image                    |
| avatar_name  | character varying(100) |          |                                           | Name associated with the avatar           |

## Table: conversation
| Column           | Type    | Nullable | Default                                     | Description                                      |
|------------------|---------|----------|---------------------------------------------|--------------------------------------------------|
| con_id           | integer | not null | nextval('conversation_con_id_seq'::regclass)| Unique identifier for conversations              |
| participant1_id  | integer |          |                                             | User ID of participant 1                        |
| participant2_id  | integer |          |                                             | User ID of participant 2                        |

## Table: messages
| Column           | Type                     | Nullable | Default                                    | Description                                      |
|------------------|--------------------------|----------|--------------------------------------------|--------------------------------------------------|
| message_id       | integer                  | not null | nextval('messages_message_id_seq'::regclass)| Unique identifier for messages                   |
| con_id           | integer                  |          |                                            | Conversation ID                                 |
| sender_id        | integer                  |          |                                            | User ID of the message sender                    |
| message_content  | text                     |          |                                            | Content of the message                           |
| timestp          | timestamp with time zone |          | CURRENT_TIMESTAMP                          | Timestamp of when the message was sent           |

## Table: users
| Column       | Type                   | Nullable | Default                                | Description                                  |
|--------------|------------------------|----------|----------------------------------------|----------------------------------------------|
| u_id         | integer                | not null | nextval('users_u_id_seq'::regclass)  | Unique identifier for users                  |
| username     | character varying(40)  |          |                                        | User's username                              |
| email        | character varying(40)  |          |                                        | User's email                                 |
| password     | text                   |          |                                        | User's password                              |
| user_avatar  | character varying(100) |          |                                        | Name associated with the user's avatar       |
