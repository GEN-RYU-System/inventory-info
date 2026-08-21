# デプロイログ

## 2026-08-21 実施

| 項目 | 値 |
|------|-----|
| 実施日時 | 2026-08-21 14:00 JST |
| 公開URL | https://shingo-ops.github.io/inventory-info/ |
| merge commit SHA | 8298825e4625f24c40ce74cb478f8292ff5d871e |
| index.html SHA256 | 72934f56f3bcfd3b5531561c35b2866ecdfbdc6e630e905c3250b026cefe49b0 |

## 検証結果

| 合格条件 | 実測値 | 判定 |
|----------|--------|------|
| A: HTTP 200 | 200 (試行2回目 / 約30秒後) | **合格** |
| B: SHA256一致 | 72934f56f3bcfd3b5531561c35b2866ecdfbdc6e630e905c3250b026cefe49b0 | **合格** |

## ロールバック手順

- 内容を戻す: `git revert 8298825e4625f24c40ce74cb478f8292ff5d871e` → push
- 公開を止める: `gh api repos/shingo-ops/inventory-info/pages -X DELETE`
- リポジトリごと消す: `gh repo delete shingo-ops/inventory-info`（実行は人間の判断待ち。CCは提案のみ）

---

## 2026-08-21 v3更新 実施

| 項目 | 値 |
|------|-----|
| 実施日時 | 2026-08-21 JST |
| 公開URL | https://shingo-ops.github.io/inventory-info/ |
| merge commit SHA | aff6563ac317e0a5e28d2e238f06cb82d551bc59 |
| index.html SHA256 | a21c4fd5c57e46cc51fadccb98ad57b8f8b394492573a3d042c09e366429e85a |

## 変更概要

配色v3（白地維持・紺基調・赤橙#c43a18を「最安」タグとverdict帯の2箇所のみに適用・区切りを中立グレー#f2f4f6に変更・CTA文言は「詳細はLINEにてお問い合わせください。」）

理由: WCAGコントラスト実測（黄は対白1.63:1で不可、赤橙深は5.30:1で合格）と孤立効果に基づくアクセント限定運用

## 検証結果

| 合格条件 | 実測値 | 判定 |
|----------|--------|------|
| A: HTTP 200 | 200 (試行1回目) | **合格** |
| B: SHA256一致 | a21c4fd5c57e46cc51fadccb98ad57b8f8b394492573a3d042c09e366429e85a（試行2回目 / 約30秒後） | **合格** |

## ロールバック手順

`git revert aff6563ac317e0a5e28d2e238f06cb82d551bc59` → push（前versionに即復帰）

---

## 2026-08-21 v5.9最終版公開 実施

| 項目 | 値 |
|------|-----|
| 実施日時 | 2026-08-21 17:15 JST |
| 公開URL | https://shingo-ops.github.io/inventory-info/ |
| merge commit SHA | d8bea133a067e6c9de78d87b2a451c5eac91ed74 |
| PR | https://github.com/shingo-ops/inventory-info/pull/3 |
| index.html SHA256 | 2213dee31a379065f6fe44cdfa2e30472858d3df425e71f8497f076662d5adfe |
| LINE公式アイコン | line-icon.png 同梱（PNG 1001×1000 RGBA） |

## 変更概要

v3.0 → v5.9 全差分:
- accent定義バグ修正（--accent:#c43a18 定義1箇所・var(--accent) 3箇所使用）
- 結論ファースト見出しに改訂
- 水平比較01-03 + 人物アイコン追加
- 問題文の強調ボックス化
- 数字リザルト Before→After 白カード化
- CTAをLINE DM誘導に変更
- 掲載数字をエビデンス確定値に修正: 約70通/日・約115名・約1,400通
  （根拠: 通知行412件除外の厳密計測 = 1,385通/20日 = 69.2通・発言者116名）
- LINE公式アイコン（line-icon.png）同梱

## 検証結果

| 合格条件 | 実測値 | 判定 |
|----------|--------|------|
| A: HTTP 200 | 200（試行2回目 / 約30秒後） | **合格** |
| B: SHA256一致 | 2213dee31a379065f6fe44cdfa2e30472858d3df425e71f8497f076662d5adfe | **合格** |
| C: --accent:#c43a18 存在 | 1箇所（grep実測） | **合格** |
| D: line-icon.png HTTP 200 | 200 | **合格** |

## ロールバック手順

`git revert d8bea133a067e6c9de78d87b2a451c5eac91ed74` → push

---

## 2026-08-21 v6.1公開反映 + GEN-RYU-System移管 実施

| 項目 | 値 |
|------|-----|
| 実施日時 | 2026-08-21 17:28–17:34 JST |
| フェーズ1 PR | https://github.com/shingo-ops/inventory-info/pull/4 |
| v6.1 merge commit SHA | 5692115c170aa480815b5cdd61e784fecc709e66 |
| index.html SHA256 | eba840417193ab7ec18883240cfcbf2958c91fa0481d35d33d2d799cf3be5640 |
| 移管前 owner | shingo-ops |
| 移管後 owner | GEN-RYU-System |
| 旧公開URL | https://shingo-ops.github.io/inventory-info/ (リダイレクト有・GitHubポリシー依存) |
| 新公開URL | https://gen-ryu-system.github.io/inventory-info/ |

## 変更概要 (v5.9→v6.1)

- 幅 750px → 1080px 化
- 金型スケーリング導入: BASE=1080px 原寸を transform:scale で全画面幅に同一比率適用
- スマホ折返しフォールバック撤去

## フェーズ1検証結果 (旧URL)

| 合格条件 | 実測値 | 判定 |
|----------|--------|------|
| HTTP 200 | 200（試行2回目 / 約30秒後） | **合格** |
| SHA256一致 | eba840417193ab7ec18883240cfcbf2958c91fa0481d35d33d2d799cf3be5640 | **合格** |

## フェーズ2検証結果 (新URL)

| 合格条件 | 実測値 | 判定 |
|----------|--------|------|
| A: HTTP 200 | 200（試行1回目） | **合格** |
| B: SHA256一致 | eba840417193ab7ec18883240cfcbf2958c91fa0481d35d33d2d799cf3be5640 | **合格** |
| C: line-icon.png HTTP 200 | 200 | **合格** |

## ロールバック手順

- 内容を戻す: `git revert 5692115c170aa480815b5cdd61e784fecc709e66` → push (GEN-RYU-System/inventory-info main)
- 移管の取消: GEN-RYU-System側から shingo-ops へ再transfer (実行は人間判断)
