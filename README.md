# NebulaFlow コーポレートサイト (`jobs/saas-corporate-site`)

本プロジェクトは、架空のエンタープライズ向け自律型AIワークフロー統合SaaS企業**「株式会社ネビュラフロー (NebulaFlow Inc.)」**の公式コーポレート・プロダクトランディングページです。

モダンなフロントエンドスタック（Astro + Tailwind CSS）を採用し、超高速な静的サイト（SSG）として Cloudflare Pages や Vercel 等へ完全無料でデプロイ・公開できるアーキテクチャで構築されています。

> [!WARNING]
> **【免責事項・架空サイトに関する規約】**
> 本サイトは、ポートフォリオおよびモダンフロントエンド設計の実証を目的として制作された**架空のWebサイト**です。実在する企業・団体・人物・商品等とは一切関係ありません。実在データ（個人情報、電話番号、住所）の混入防止、および架空サイトである旨の注記を必ずサイト内に維持してください。

---

## 1. プロジェクト概要 & コンセプト

- **架空企業名**: 株式会社ネビュラフロー (NebulaFlow Inc.)
- **プロダクト名**: NebulaFlow (ネビュラフロー)
- **プロダクト定義**: 企業の複雑な業務プロセスを、自律型マルチエージェントと100+のSaaSコネクタで完全自動化・オーケストレーションする次世代 B2B SaaS。
- **デザインコンセプト**:
  - 先進的なダークモード基調（Linear / Stripe / Vercel を彷彿とさせるグラスモーフィズムとサイバーグロー）。
  - 直感的でレスポンシブなUI、製品UIモックアップ、動的なROI指標、明快な料金プラン、安全なインタラクティブお問い合わせフォーム。

---

## 2. アーキテクチャ & 利用技術

- **フレームワーク**: [Astro v5.x](https://astro.build/) (Static Site Generation / SSG)
- **スタイリング**: [Tailwind CSS v3.x](https://tailwindcss.com/)
- **フォント**: Inter, Noto Sans JP
- **デプロイ先想定**: Cloudflare Pages / Vercel (GitHub 連携による完全無料・自動デプロイ)
- **SEO・安全対策**: `robots: noindex, nofollow` を標準設定（検索エンジンの誤認・誤インデックス防止）

---

## 3. ディレクトリ構成

```
jobs/saas-corporate-site/
├── README.md               # 【本ドキュメント】プロジェクト仕様・運用ガイド
├── package.json            # 依存関係・ビルドスクリプト
├── astro.config.mjs        # Astro設定（Tailwindインテグレーション）
├── tailwind.config.mjs     # テーマカラー（brand, dark）、カスタムGlow設定
├── tsconfig.json           # TypeScript設定
├── .gitignore              # Git除外設定（node_modules, dist 等）
├── public/                 # 静的アセット（favicon.svg 等）
└── src/
    ├── layouts/
    │   └── Layout.astro     # 全体レイアウト、架空バナー、メタタグ、フォント
    ├── styles/
    │   └── global.css       # グローバルCSS、グラスパネル、グラデーション
    ├── components/
    │   ├── Header.astro     # 固定ナビゲーションバー、ロゴ、CTA
    │   ├── Hero.astro       # ファーストビュー、キャッチコピー、製品UIモック
    │   ├── Features.astro   # 6大コア機能（マルチエージェント、100+コネクタ等）
    │   ├── Metrics.astro    # 導入効果（工数削減、処理速度、ROI数値）
    │   ├── Pricing.astro    # 料金プラン（Starter, Professional, Enterprise）
    │   ├── Company.astro    # 会社概要、ミッション、ビジョン
    │   ├── Contact.astro    # お問い合わせ・デモ申込フォーム（安全なモック）
    │   └── Footer.astro     # サイトマップ、著作権表記、免責事項全文
    └── pages/
        └── index.astro      # トップページ（全セクション統合）
```

---

## 4. ローカル開発 & 起動手順

### 4.1 依存パッケージのインストール
```bash
npm install
```

### 4.2 開発サーバーの起動
ローカルでプレビューおよびリアルタイム編集を行う場合：
```bash
npm run dev
```
起動後、ブラウザで `http://localhost:3000` を開きます。

### 4.3 プロダクションビルド
静的 HTML/CSS/JS を生成する場合：
```bash
npm run build
```
ビルド成果物は `dist/` ディレクトリ配下に完全な静的ファイルとして出力されます。

---

## 5. 無料ホスティング（Cloudflare Pages / Vercel）への公開手順

1. **GitHub リポジトリの作成**:
   - 本プロジェクト（`jobs/saas-corporate-site/`）を GitHub 上のプライベート/パブリックリポジトリに push します。
2. **ホスティングサービス連携**:
   - **Cloudflare Pages**: Cloudflare ダッシュボードで「Workers & Pages」→「作成」→「Pages」→「Git に接続」を選択し、リポジトリを連携。
     - フレームワークプリセット: `Astro`
     - ビルドコマンド: `npm run build`
     - ビルド出力ディレクトリ: `dist`
   - **Vercel**: Vercel ダッシュボードで「Add New...」→「Project」からリポジトリをインポートするだけで自動検出。
3. **公開完了**:
   - わずか数十秒で `https://xxx.pages.dev` や `https://xxx.vercel.app` にて世界中に公開されます。

---

## 6. プロジェクト固有の開発・運用ルール

1. **架空サイト免責事項の維持**:
   - ページ上部の告知バナー（`Layout.astro`）およびフッターの免責事項（`Footer.astro`）は絶対に削除・不可視化しないこと。
2. **ダミー連絡先情報の厳守**:
   - メールアドレスは `contact@example.com`、電話番号は `03-0000-0000`、住所は架空の住所を維持し、実在の個人・法人情報を誤って記載しないこと。
3. **独立リポジトリ運用の徹底**:
   - 本ディレクトリ直下の専用 Git リポジトリ（マルチレポ構成）でバージョン管理を行い、ルート（`sandbox`）へのコミット混入を防ぐこと。
