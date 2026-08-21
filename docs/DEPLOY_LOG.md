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
