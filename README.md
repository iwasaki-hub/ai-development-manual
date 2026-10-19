# AI Development Manual

AIと協力して、さまざまなソフトウェア開発を進めるための共通マニュアルです。

## Languages

- [日本語版（Japanese）](./ja/README.md)
- [English version](./en/README.md)

## Purpose

このリポジトリでは、AIを活用した開発の進め方、指示の出し方、作業の進捗管理、テスト、GitHub運用などの共通ルールを管理します。

## How to Use

1. 使用する言語のフォルダを開きます。
2. `AI_DEVELOPMENT_MANUAL.md` を読みます。
3. 新規・既存どちらのプロジェクトでも、使用言語に対応する開始プロンプトをAIへの指示に利用できます。
4. 分かる範囲でプロジェクト情報を記入し、未確定の項目はAIと相談します。
5. 既存プロジェクトでは、作業前に `AGENTS.md` などの指示ファイル、関連コード、Git状態を確認し、既存変更を保持します。
6. プロジェクト固有の技術構成、要件、制約は別途指定し、既存のプロジェクトルールを尊重します。

## Project Start Templates

Use the matching prompt when starting either a new or an existing project with AI.

- [日本語版：プロジェクト開始テンプレート](./templates/PROJECT_START_PROMPT.md)
- [English: Project Start Prompt](./templates/PROJECT_START_PROMPT.en.md)

Choose your preferred language, copy the prompt into your AI conversation, and fill in the information you know. For an existing project, provide its location so the AI can inspect the repository instructions, relevant code, and Git status before making changes.

## Repository Structure

```text
ai-development-manual/
├── README.md
├── AGENTS.md
├── ja/
│   ├── README.md
│   ├── AI_DEVELOPMENT_MANUAL.md
│   └── PROJECT_START_GUIDE.md
├── en/
│   ├── README.md
│   └── AI_DEVELOPMENT_MANUAL.md
└── templates/
    ├── PROJECT_START_PROMPT.md
    └── PROJECT_START_PROMPT.en.md
```

## Maintenance

日本語版と英語版を更新するときは、両方の内容に矛盾がないか確認してください。
