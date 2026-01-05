1 バックエンドに新しい機能を追加する
① ドメイン層（domain/）

新しいビジネスルールやエンティティを追加

既存のエンティティを拡張する場合もここ

例：Product 機能を追加する場合

backend/src/main/java/app/domain/product/
├── Product.java
├── ProductId.java
├── ProductService.java
└── ProductRepository.java


ProductRepository は DB 接続のポート（インターフェース）

ProductService はドメインロジック

② ユースケース層（application/）

ドメインの操作をまとめて、外部から呼べるようにする

UseCaseクラスを作る

例：

backend/src/main/java/app/application/product/
├── CreateProductUseCase.java
├── GetProductUseCase.java
└── DeleteProductUseCase.java


UseCase は基本的に ドメインを呼ぶだけ

APIやUI層にはここを通してアクセス

③ API層（adapter_api/）

フロントや他サービスから呼ばれる入口

DTO（Request / Response）を作ってUseCaseに渡す

例：

backend/src/main/java/app/adapter_api/product/
├── ProductController.java
├── ProductRequest.java
└── ProductResponse.java


Controller が HTTP リクエストを受け取って UseCase に渡す

Request/Response はJSONの形に対応

④ DB層（adapter_db/）

DBアクセスの具体実装を追加

SQLiteやPostgresなど、DBごとにクラスを作る

例：

backend/src/main/java/app/adapter_db/sqlite/ProductSqliteRepository.java
backend/src/main/java/app/adapter_db/postgres/ProductPostgresRepository.java


ドメインの ProductRepository インターフェースを実装する

将来DBを変えるときもこの層だけ書き換えればOK

⑤ イベント・Feature Toggle

新機能にイベントが必要なら event/ に追加

例：ProductCreatedEvent.java

フラグでON/OFFしたい場合は feature/FeatureToggle.java を活用

2 フロントに新しい機能を追加する
① ページやコンポーネント

新しい画面は pages/ に追加

再利用コンポーネントは components/ に追加

例：

frontend/web/src/pages/ProductPage.tsx
frontend/web/src/components/ProductCard.tsx

② APIサービス

バックエンドAPIと通信するクラスを services/ に作る

例：

frontend/web/src/services/productService.ts


fetch / axios を使って CreateProductUseCase や GetProductUseCase を呼ぶ

TS型は types/ に定義して型安全にする

frontend/web/src/types/Product.ts

③ 素材（画像・アイコン）

新しいUI素材は assets/ に追加

例：

frontend/web/src/assets/images/product.png
frontend/web/src/assets/icons/add-product.svg


コンポーネントで import して使用

import ProductIcon from "../assets/icons/add-product.svg";

3 テストの追加
① バックエンド

tests/backend/ にユースケースやDBアクセスのテストを作る

tests/backend/product/
├── CreateProductTest.java
└── ProductSqliteRepositoryTest.java


テストは ドメイン・ユースケース・DBごとに分けると拡張性◎

② フロント

tests/frontend/web/ にページ・サービスのテストを作る

Jest + React Testing Libraryが一般的

tests/frontend/web/pages/ProductPage.test.tsx
tests/frontend/web/services/productService.test.ts

4 素材の追加

フロント専用素材 → frontend/web/src/assets/ に追加

バックエンド配信用素材 → backend/src/main/resources/static/ に追加

共通で使う場合 → frontend/shared-assets/ にまとめて、ビルド時にコピー

🔹 追加の手順まとめ

ドメイン層 → 新しいビジネスルールやエンティティ

ユースケース層 → UseCaseを作る

API層 → Controller / Request / Response を作る

DB層 → Repository実装を追加

イベント / Feature → 必要に応じて追加

フロント → ページ / コンポーネント / サービス / 型

素材 → assets に画像・アイコン・CSSを追加

テスト → バックエンド・フロント両方に追加