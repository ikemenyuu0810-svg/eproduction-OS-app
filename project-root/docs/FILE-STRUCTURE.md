project-root/
├── backend/
│   ├── src/
│   │   ├── domain/
│   │   │   └── user/
│   │   │       ├── User.ts
│   │   │       └── UserId.ts
│   │   │       ├── UserService.ts
│   │   │       └── UserRepository.ts
│   │   │
│   │   ├── application/
│   │   │   └── user/
│   │   │       ├── CreateUserUseCase.ts
│   │   │       ├── GetUserUseCase.ts
│   │   │       └── DeleteUserUseCase.ts
│   │   │
│   │   ├── adapter_api/
│   │   │   └── user/
│   │   │       ├── UserController.ts
│   │   │       ├── UserRequest.ts
│   │   │       └── UserResponse.ts
│   │   │
│   │   ├── adapter_db/
│   │   │   ├── sqlite/
│   │   │   │   └── SQLiteUserRepository.ts
│   │   │   └── postgres/
│   │   │       └── PostgresUserRepository.ts
│   │   │
│   │   ├── event/
│   │   │   ├── UserCreatedEvent.ts
│   │   │   └── EventPublisher.ts
│   │   │
│   │   ├── feature/
│   │   │   └── FeatureToggle.ts
│   │   │
│   │   └── app.ts
│   │
│   └── config/
│       ├── database.ts
│       └── appConfig.ts
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
│   │   │   │   ├── Button.tsx
│   │   │   │   └── UserCard.tsx
│   │   │   ├── pages/
│   │   │   │   ├── HomePage.tsx
│   │   │   │   └── UserPage.tsx
│   │   │   ├── services/
│   │   │   │   └── userService.ts
│   │   │   └── types/
│   │   │       └── User.ts
│   │   └── package.json
│
├── tests/
│   ├── backend/
│   │   └── user/
│   │       ├── CreateUserTest.ts
│   │       └── SQLiteUserRepositoryTest.ts
│   └── frontend/
│       └── web/
│
└── docs/
    ├── API.md
    └── ARCHITECTURE.md
