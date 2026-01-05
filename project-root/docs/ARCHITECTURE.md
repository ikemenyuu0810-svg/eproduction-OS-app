project-root/
├── backend/
│   ├── src/
│   │   ├── domain/
│   │   │   └── user/
│   │   │       ├── User.ts
│   │   │       │  # ユーザー情報のデータモデル
│   │   │       │  # 名前・メールなどの属性を定義
│   │   │       │  # 追加：新しい属性はここに追加
│   │   │       ├── UserId.ts
│   │   │       │  # ユーザーの固有ID型
│   │   │       │  # UUIDや連番など、ID生成ルールをまとめる
│   │   │       ├── UserService.ts
│   │   │       │  # ユーザー関連のビジネスロジック
│   │   │       │  # ドメインルール（名前の重複禁止など）を実装
│   │   │       └── UserRepository.ts
│   │   │          # DB操作の抽象インターフェース
│   │   │          # 保存・取得・削除メソッドを定義
│   │   │          # 実際のDB実装はadapter_dbで行う
│   │   │
│   │   ├── application/
│   │   │   └── user/
│   │   │       ├── CreateUserUseCase.ts
│   │   │       │  # ユーザー作成の処理手順をまとめる
│   │   │       │  # Controllerから呼ばれ、UserServiceとRepositoryを利用
│   │   │       ├── GetUserUseCase.ts
│   │   │       │  # ユーザー取得処理
│   │   │       └── DeleteUserUseCase.ts
│   │   │          # ユーザー削除処理
│   │   │
│   │   ├── adapter_api/
│   │   │   └── user/
│   │   │       ├── UserController.ts
│   │   │       │  # HTTPリクエストを受ける入口
│   │   │       │  # UseCaseを呼び出して結果を返す
│   │   │       ├── UserRequest.ts
│   │   │       │  # APIの入力型（Request DTO）
│   │   │       │  # 型チェックやバリデーションに利用
│   │   │       └── UserResponse.ts
│   │   │          # APIの出力型（Response DTO）
│   │   │          # 必要に応じて返すデータを加工して返す
│   │   │
│   │   ├── adapter_db/
│   │   │   ├── sqlite/
│   │   │   │   └── SQLiteUserRepository.ts
│   │   │   │      # SQLite用のUserRepository実装
│   │   │   │      # SQL操作をここに書く
│   │   │   └── postgres/
│   │   │       └── PostgresUserRepository.ts
│   │   │          # Postgres用の実装（将来切替用）
│   │   │
│   │   ├── event/
│   │   │   ├── UserCreatedEvent.ts
│   │   │   │  # ユーザー作成イベントのデータ型
│   │   │   └── EventPublisher.ts
│   │   │      # イベントを発行する処理
│   │   │      # メール通知やログ出力などに利用
│   │   │
│   │   ├── feature/
│   │   │   └── FeatureToggle.ts
│   │   │      # 新機能のON/OFF切替
│   │   │      # 将来機能追加時に既存コードを壊さず対応
│   │   │
│   │   └── app.ts
│   │      # サーバー起動ポイント
│   │      # Expressルート設定、DB接続、CORS設定など
│   │
│   └── config/
│       ├── database.ts
│       │  # DB接続設定
│       │  # SQLite/Postgresの接続先、認証情報を定義
│       └── appConfig.ts
│          # アプリ全体の設定（ポート番号、環境変数）
│
├── frontend/
│   ├── web/
│   │   ├── src/
│   │   │   ├── assets/
│   │   │   │   ├── images/
│   │   │   │   │   ├── logo.svg
│   │   │   │   │   └── avatar-default.png
│   │   │   │   │      # UIで使う画像
│   │   │   │   ├── icons/
│   │   │   │   │   ├── user.svg
│   │   │   │   │   └── add.svg
│   │   │   │   │      # UIアイコン
│   │   │   │   ├── fonts/
│   │   │   │   │   └── custom-font.woff2
│   │   │   │   │      # Webフォント
│   │   │   │   └── css/
│   │   │   │       └── global.css
│   │   │   │          # 共通スタイル
│   │   │   ├── components/
│   │   │   │   ├── Button.tsx
│   │   │   │   │  # 再利用UI部品
│   │   │   │   │  # 他のページでも使える
│   │   │   │   └── UserCard.tsx
│   │   │   │      # ユーザー情報表示カード
│   │   │   ├── pages/
│   │   │   │   ├── HomePage.tsx
│   │   │   │   │  # トップページ
│   │   │   │   └── UserPage.tsx
│   │   │   │      # ユーザー一覧・管理ページ
│   │   │   ├── services/
│   │   │   │   └── userService.ts
│   │   │   │      # API通信処理
│   │   │   │      # GET/POST/DELETEなど
│   │   │   └── types/
│   │   │       └── User.ts
│   │   │          # TypeScript型定義
│   │   │          # APIレスポンスや内部データの型
│   │   └── package.json
│
├── tests/
│   ├── backend/
│   │   └── user/
│   │       ├── CreateUserTest.ts
│   │       │  # CreateUserUseCaseの挙動確認
│   │       └── SQLiteUserRepositoryTest.ts
│   │          # SQLiteUserRepositoryの挙動確認
│   └── frontend/
│       └── web/
│          # フロントエンドのページ・コンポーネント・サービスのテスト
│
└── docs/
    ├── API.md
    │  # API仕様書
    │  # エンドポイント、リクエスト/レスポンス型を記載
    └── ARCHITECTURE.md
       # フォルダ構成、Clean Architectureの説明
       # 誰でも理解できるように図解
