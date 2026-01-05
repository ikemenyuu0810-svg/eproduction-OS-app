project-root/
├── backend/
│   ├── src/main/java/app/
│   │   ├── domain/
│   │   │   └── user/
│   │   │       ├── User.java
│   │   │       ├── UserId.java
│   │   │       ├── UserService.java
│   │   │       └── UserRepository.java
│   │   │
│   │   ├── application/
│   │   │   └── user/
│   │   │       ├── CreateUserUseCase.java
│   │   │       ├── GetUserUseCase.java
│   │   │       └── DeleteUserUseCase.java
│   │   │
│   │   ├── adapter_api/
│   │   │   └── user/
│   │   │       ├── UserController.java
│   │   │       ├── UserRequest.java
│   │   │       └── UserResponse.java
│   │   │
│   │   ├── adapter_db/
│   │   │   ├── sqlite/
│   │   │   │   └── SQLiteUserRepository.java
│   │   │   └── postgres/
│   │   │       └── PostgresUserRepository.java
│   │   │
│   │   ├── event/
│   │   │   ├── UserCreatedEvent.java
│   │   │   └── EventPublisher.java
│   │   │
│   │   ├── feature/
│   │   │   └── FeatureToggle.java
│   │   │
│   │   └── App.java
│   │
│   └── resources/
│       ├── application.yml
│       └── db/migration/
│
├── frontend/
│   ├── web/
│   │   ├── src/
│   │   │   ├── assets/
│   │   │   │   ├── images/
│   │   │   │   │   ├── logo.svg
│   │   │   │   │   └── avatar-default.png
│   │   │   │   ├── icons/
│   │   │   │   │   ├── user.svg
│   │   │   │   │   └── add.svg
│   │   │   │   ├── fonts/
│   │   │   │   │   └── custom-font.woff2
│   │   │   │   └── css/
│   │   │   │       └── global.css
│   │   │   ├── components/
│   │   │   ├── pages/
│   │   │   ├── services/
│   │   │   └── types/
│   │   └── package.json
│   │
│   ├── desktop/
│   └── mobile/
│
├── tests/
│   ├── backend/
│   │   └── user/
│   │       ├── CreateUserTest.java
│   │       └── SQLiteUserRepositoryTest.java
│   └── frontend/
│       └── web/
│
└── docs/
    ├── API.md
    └── ARCHITECTURE.md
