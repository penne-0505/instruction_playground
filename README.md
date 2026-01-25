# Instruction Playground

AIアシスタント（ChatGPT、Gemini等）に対するカスタム指示（custom instructions / system prompts）を管理・テスト・改善するためのリポジトリです。

## 概要

このプロジェクトは、様々なAIアシスタントに対して適用する指示文を体系的に管理し、それらの有効性を検証するためのテストプロンプト集を提供します。指示文は目的別・AI別に整理され、再利用可能なモジュール（bricks）として構成されています。

## プロジェクト構造

### 一般的な指示

- **`general_instructions/`**: 各AIアシスタント向けの基本的な指示文
  - `chatgpt/`: ChatGPT向けカスタム指示
    - `INSTRUCTION.md`: 統合された指示文
    - `bricks/using/`: 現在使用中の指示モジュール（役割、コミュニケーションスタイル、批判的思考等）
    - `bricks/unused/`: 未使用の指示モジュール
  - `gemini/`: Gemini向けカスタム指示
    - `INSTRUCTION.md`: 統合された指示文 (相互に影響する記述が多いので、bricks化は未実施)

### 専門的な指示

- **`specialist_instructions/`**: 特定の用途に特化した指示文
  - `designer_instruction.md`: Webデザイナーモード向け指示 (Anthropic公式の指示を引用しただけなので、remoteには含めていません)

### テストプロンプト

- **`test_prompts/`**: 指示の有効性を評価するためのテストケース集
  - 文脈依存の問題解決
  - 抽象的推論と仮説検証
  - 第一原理からの推論
  - 曖昧性の解決と情報統合
  - 制約ベースのキュレーション
  - 事実検索と正確性
  - クロスドメイン翻訳
  - ペルソナ一貫性と感情的知性
  - 創造的表現とスタイル模倣
  - 安全性と拒否感度

詳細は [test_prompts/README.md](test_prompts/README.md) を参照してください。

### メタ情報

- **`meta_contents/`**: プロジェクトのメタ情報と開発履歴
  - `intent/`: プロジェクトの目的と既知の制約
  - `old_or_current/`: 過去のバージョンと現在使用中の指示
  - `old_test_prompts/`: 旧バージョンのテストプロンプト
  - `idea_snipet/`: アイディアやテクニックのメモ

### 実験エリア

- **`playground/`**: 実験的な指示の作成や進行中の作業

## 使用方法

### 1. 指示文の適用

各AIアシスタントに適用する指示文は、対応するディレクトリ内の `INSTRUCTION.md` ファイルに記載されています。

- ChatGPTの場合: [general_instructions/chatgpt/INSTRUCTION.md](general_instructions/chatgpt/INSTRUCTION.md)
- Geminiの場合: [general_instructions/gemini/INSTRUCTION.md](general_instructions/gemini/INSTRUCTION.md)

### 2. テストプロンプトによる評価

新しい指示を作成または既存の指示を変更した場合、`test_prompts/` ディレクトリ内のテストケースを使用して、指示の有効性を評価できます。

各テストファイルには `---` 区切りで複数のテストケースが含まれており、特定の認知能力やスキルセットを評価できます。

### 3. モジュールのカスタマイズ

`general_instructions/chatgpt/bricks/` 内の各モジュールは独立しており、必要に応じて追加・削除・編集が可能です。

## 貢献

このプロジェクトは個人用途として開発されていますが、指示の改善提案やテストケースの追加は歓迎します。ただし、レビューやcontributionの処理は個人で行っています。お時間をいただく場合がありますのでご了承ください。

## ライセンス

このプロジェクトはMITライセンスの下で公開されています。詳細は [LICENSE.txt](LICENSE.txt) を参照してください。