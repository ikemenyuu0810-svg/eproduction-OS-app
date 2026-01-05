project-root/
│
├── backend/                        # Javaバックエンド全体
│   ├── src/main/java/app/           # Javaコードのルートパッケージ
│   │   ├── domain/                  # ビジネスルール・エンティティ
│   │   │   └── user/
│   │   │       ├── User.java        # ユーザー情報のモデル
│   │   │       ├── UserId.java      # ユーザーIDを型安全に管理
│   │   │       ├── UserService.java # ドメインサービス（ロジック）
│   │   │       └── UserRepository.java # DBアクセスのインターフェース
│   │   │
│   │   ├── application/             # ユースケース層（ビジネスフロー）
│   │   │   └── user/
│   │   │       ├── CreateUserUseCase.java
│   │   │       ├── GetUserUseCase.java
│   │   │       └── DeleteUserUseCase.java
│   │   │
│   │   ├── adapter_api/             # API/UIとの接続
│   │   │   └── user/
│   │   │       ├── UserController.java  # REST APIコントローラー
│   │   │       ├── UserRequest.java     # APIリクエスト用DTO
│   │   │       └── UserResponse.java    # APIレスポンス用DTO
│   │   │
│   │   ├── adapter_db/              # DB接続層
│   │   │   ├── sqlite/
│   │   │   │   └── SQLiteUserRepository.java
│   │   │   └── postgres/            # 将来の拡張用
│   │   │       └── PostgresUserRepository.java
│   │   │
│   │   ├── event/                   # イベント駆動用
│   │   │   ├── UserCreatedEvent.java
│   │   │   └── EventPublisher.java
│   │   │
│   │   ├── feature/                 # 機能のオンオフ切り替え
│   │   │   └── FeatureToggle.java
│   │   │
│   │   └── App.java                 # エントリポイント
│   │
│   └── resources/
│       ├── application.yml          # 設定ファイル
│       └── db/migration/            # FlywayなどのDBマイグレーション
│
├── frontend/                        # TypeScriptフロントエンド
│   ├── web/                         # Webアプリ（React / TS）
│   │   ├── src/
│   │   │   ├── assets/              # 画像・アイコン・フォント・CSS
│   │   │   │   ├── images/          # ロゴやアバター画像
│   │   │   │   ├── icons/           # SVGアイコン
│   │   │   │   ├── fonts/           # フォントファイル
│   │   │   │   └── css/             # グローバルCSS
│   │   │   ├── components/          # 再利用コンポーネント
│   │   │   ├── pages/               # ページ単位のコンポーネント
│   │   │   ├── services/            # API通信クラス
│   │   │   └── types/               # TypeScript型定義（DTOなど）
│   │   └── package.json
│   │
│   ├── desktop/                      # Electron / JavaFX用（オプション）
│   └── mobile/                       # React Native / Flutter用（オプション）
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
    ├── API.md                        # API仕様書
    └── ARCHITECTURE.md               # 構造や設計方針の説明
