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
