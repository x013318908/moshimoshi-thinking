# 横断KJ運用: ideas + wiki_*

作成日: 2026-05-14

## 位置づけ
このディレクトリは、`methodology.md` の方法を複数コーパスにまたがって実践するための横断入口である。

各コーパスの原文、正規化資料、既存KJ処理物は移動しない。ここには、コーパス横断で探索するときの対象範囲、ID規則、探索キャッシュを置く。

## 対象コーパス

| 接頭辞 | 対象 | 一次資料 | 探索用資料 | 既存KJ資料 |
|---|---|---|---|---|
| IDEA | `ideas/` | `ideas/*.md` | 同左 | `ideas/kj/` |
| WC | `wiki_chatgpt_ideas/` | `wiki_chatgpt_ideas/sources/*.html` | `wiki_chatgpt_ideas/normalized_sources/*.md` | `wiki_chatgpt_ideas/kj/` |
| WA | `wiki_all_ideas/` | `wiki_all_ideas/tar20260505.tar.gz`, `wiki_all_ideas/raw_sources/*.wiki.txt` | `wiki_all_ideas/normalized_sources/*.md`, `manifest.json` | `wiki_all_ideas/kj/` |
| CONV | このセッションの会話由来メモ | `kj/conversation-source-cards.md` | 同左 | 未作成 |

現時点では `renmemo_ideas/` は対象外。必要になったら、別途接頭辞と処理範囲を決めてから加える。

## 参照IDルール

横断メモでは、ローカルな `F001` や `F0001` だけで参照しない。必ずコーパス接頭辞を付ける。

- `ideas/` の原文カード: `IDEA-A1` から `IDEA-A7`
- `ideas/` の断片: `IDEA-F001` から `IDEA-F039`
- `ideas/` の上位ラベル: `IDEA-L1` から `IDEA-L8`, `IDEA-UL1`
- `wiki_chatgpt_ideas/` の原文カード: `WC001` から `WC031`
- `wiki_chatgpt_ideas/` の断片: `WC-F0001` から
- `wiki_chatgpt_ideas/` の上位ラベル: `WC-UL01` から
- `wiki_all_ideas/` の原文カード: `WA0001` から `WA3979`
- `wiki_all_ideas/` の一括抽出断片: `WA-F00001` から
- `wiki_all_ideas/` の個別採用断片: `WA-VF-*`
- `wiki_all_ideas/` の上位ラベル: `WA-UL01` から
- 横断上位ラベル: `XUL01` から
- 会話由来の原文カード: `CONV001` から

既存ファイル内のIDはそのまま維持する。横断ファイルでだけ、接頭辞を補って衝突を避ける。

## 探索順

横断探索では、最初から全ファイルを読むのではなく、既存のKJ処理物から入る。

1. `ideas/kj/` で、現在の方法論に近い断片と上位ラベルを確認する。
2. `wiki_chatgpt_ideas/kj/` で、ChatGPT×Wikiに絞られた断片と上位ラベルを確認する。
3. `wiki_all_ideas/kj/adopted_fragments/` と `wiki_all_ideas/kj/exploration_cache_index.md` で、個別採用済みの断片と探索済みテーマを確認する。
4. 広い探索が必要なときだけ、`wiki_all_ideas/normalized_sources/` と `manifest.json` を検索する。
5. 断片を採用する前に、正規化資料だけでなく一次資料または原文へ戻る。

## 横断探索キャッシュ

複数コーパスをまたぐ探索キャッシュは、このディレクトリに作る。

命名:
- `exploration-cache-YYYY-MM-DD-<theme>.md`

含めるもの:
- 探索語
- 実際に使った探索語
- 対象コーパス
- 作成理由
- 採用基準
- 除外記録
- 辿った経路
- 見つかった断片
- 関連する原文カード
- 既存上位ラベルとの接続
- 探索結果の要約
- 横断仮ラベル
- 未決の論点

単一コーパス内で完結する探索キャッシュは、そのコーパス内の `kj/` に残してよい。

## 横断上位ラベル整理

複数コーパスをまたぐ上位ラベル整理は、既存ラベルの置き換えではなく、既存ラベル同士を一時的につなぐ仮の対応表として作る。

命名:
- `cross-upper-labels-YYYY-MM-DD.md`

含めるもの:
- 作成理由
- 運用ルール
- 横断上位ラベル
- 対応する既存ラベル
- 重なりが強いラベル
- 未決の論点

横断上位ラベルは `XUL01` から始める。
`XUL` も完成した分類ではなく、再探索で変更される仮ラベルとして扱う。

## 現時点の処理済み範囲

- `ideas/`: 初回7カードから `IDEA-F001` から `IDEA-F039`、`IDEA-L1` から `IDEA-L8`、`IDEA-UL1` が作成済み。
- `wiki_chatgpt_ideas/`: 31ファイルから原文カード、断片候補、上位ラベル候補が作成済み。
- `wiki_all_ideas/`: 3979ページから原文カード、一括抽出断片、上位ラベル候補が作成済み。
- `wiki_all_ideas/`: `ChatGPT×Wiki`、`モシモシモノリス`、`発想支援方法` は個別採用断片として昇格済み。

## 運用メモ

横断ラベルは既存ラベルの置き換えではない。複数コーパスをまたいで見えた仮説として扱い、本人が採用・修正するまで候補のまま残す。

`wiki_all_ideas/` は件数が大きいため、検索結果に出ただけでは採用しない。採用済み断片から逆算して採用基準を作り、実際に候補に出たが採用しなかったものだけを除外記録に残す。
