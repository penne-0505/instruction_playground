# Instruction Playground

LLM 向けの instruction / prompt を保管・比較・改善するためのワークスペースです。完成版の instruction だけでなく、試行中の草稿、評価用テストプロンプト、設計意図のメモ、過去バージョンのアーカイブもまとめて管理しています。

## このリポジトリでやっていること

- 普段使う instruction の管理
- モデル別の差分管理
- 新しい instruction 案やプロンプト構成の試作
- テストプロンプトによるモデル傾向の観察
- 評価観点や設計思想のメモ化
- 旧版や没案のアーカイブ

## クイックスタート

- 現在使用中の instruction: [CURRENTRY_USING.md](CURRENTRY_USING.md)
- 実運用寄りの instruction:
  - [general_instructions/chatgpt/INSTRUCTION.md](general_instructions/chatgpt/INSTRUCTION.md)
  - [general_instructions/gemini/INSTRUCTION.md](general_instructions/gemini/INSTRUCTION.md)
  - [general_instructions/claude/INSTRUCTION.md](general_instructions/claude/INSTRUCTION.md)
  - [general_instructions/GENERAL/INSTRUCTION.md](general_instructions/GENERAL/INSTRUCTION.md)
- テストプロンプト一覧: [test_prompts/README.md](test_prompts/README.md)
  ([こちら](https://github.com/penne-0505/llm_evalution/)にこれをパイプライン化したものがあります)

## ディレクトリ構成

```text
.
|-- CURRENTRY_USING.md
|-- general_instructions/
|   |-- GENERAL/
|   |-- chatgpt/
|   |-- claude/
|   `-- gemini/
|-- meta_contents/
|   |-- idea_snipet/
|   |-- intent/
|   |-- old_or_current/
|   |-- old_test_prompts/
|   `-- meta_snipet.md
|-- playground/
|   |-- ... 各種試作・比較・作業メモ
|   `-- scorering/
|-- test_prompts/
|-- LICENSE.txt
`-- README.md
```

### `general_instructions/`

モデルごとの instruction と、その土台になるベース instruction を置く場所です。

- `GENERAL/`
  - 共通的なベース instruction を置くディレクトリです。
- `chatgpt/`, `claude/`, `gemini/`
  - 各モデル向けに調整した instruction を置いています。
  - 同じ思想を共有しつつ、モデルごとの癖や出力傾向に合わせて差分を持たせる前提です。

### `meta_contents/`

instruction の周辺にある設計思想、目的、旧版、補助メモをまとめた場所です。

- `intent/`
  - このリポジトリで何を目指しているか、どんな制約や前提を置いているかのメモです。
- `old_or_current/`
  - 旧版 instruction や、過去から現在にかけての比較資料を置いています。
- `old_test_prompts/`
  - 以前使っていたテストプロンプト群の保存場所です。
- `idea_snipet/`
  - 小さなアイデア断片や補助メモです。
- `meta_snipet.md`
  - instruction 適用時に添える補助スニペットです。

### `playground/`

未完成の instruction、実験中の構成、比較メモ、出力サンプルなどを置く作業場です。

ここには次のようなものが混在します。

- 新しい instruction の草稿
- あるモデル向けに特化した試作
- 比較出力の保存
- personality や tone の検討メモ
- 評価方法そのものの試作

たとえば `playground/scorering/` には、`llm as a judge` 的な評価機構のドラフトがあります。実際の評価パイプライン本体はこのリポジトリではなく、別リポジトリで管理する想定です。

### `test_prompts/`

モデルの傾向や instruction の効き方を確認するためのリファレンス用テストプロンプト集です。

- 各ファイルは特定の能力や観点をチェックするためのカテゴリ単位になっています
- 詳細な説明は [test_prompts/README.md](test_prompts/README.md) を参照してください
- 現在の構成では、文脈理解、抽象推論、第一原理、情報統合、事実検索、文体模写、安全性などを分けて見られるようになっています

## 使い方の目安

### 1. 実際に使う instruction を見たいとき

`CURRENTRY_USING.md` から現在の参照先をたどるのが最短です。

### 2. instruction を改善したいとき

以下の順で見ると流れを追いやすいです。

1. `general_instructions/` で現行版を確認する
2. `playground/` で草稿や比較メモを見る
3. `meta_contents/intent/` や `meta_contents/old_or_current/` で背景や旧版を確認する
4. `test_prompts/` で評価観点を確認する

### 3. モデルの挙動を比べたいとき

`test_prompts/` の各カテゴリを使い、`general_instructions/` 配下の各 instruction を差し替えて比較する運用を想定しています。

## この README で扱わないもの

- 実行用スクリプトの詳細
- 自動評価パイプラインのコード
- デプロイ手順やパッケージセットアップ

このリポジトリは主にドキュメントと作業メモの集積であり、ソフトウェア配布用の構成にはなっていません。

## 補足

- ファイル名やディレクトリ名には、試作段階の名残や一時的な命名が含まれています
- `playground/` と `meta_contents/old_or_current/` には、現役のものとアーカイブ寄りのものが混在しています
- 説明の厳密さよりも、まず探索しやすいことを優先して整理しています

## ライセンス

詳細は [LICENSE.txt](LICENSE.txt) を参照してください。

このテキストはLLMによって記述されました。
