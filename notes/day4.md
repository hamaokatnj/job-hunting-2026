# Day4

## やったこと

* データを保存できるAPIを実装（items_db）
* POSTでデータ追加
* GETで一覧取得
* GETで個別取得（index指定）
* LeetCode「Remove Element」「Move Zeroes」

---

## 理解したこと

### APIの流れ

* docsから入力（JSON）
* APIに送信（POST）
* Pythonの関数が受け取る
* 処理する
* 結果を返す

👉 docsは「データを送るための画面」

---

### GETとPOST

* GET → データを取得する
* POST → データを追加する

👉 本質は「役割の違い」

---

### データ保存

```python
items_db = []
```

* リストでデータを保持
* appendで追加
* GETで中身を返す

---

### JSON

```json
{
  "name": "apple",
  "price": 120
}
```

* キーと値のセット
* Pythonのdictとほぼ同じ

---

### リスト操作（重要）

#### for文

```python
for x in nums:
```

👉 リストの中身を順番に取り出す

---

#### 上書き

```python
nums[k] = x
```

👉 元のリストを書き換える（新しいリストではない）

---

## LeetCode

### Remove Element

* 不要な値を除外
* 前に詰める
* kで個数管理

```python
k = 0
for x in nums:
    if x != val:
        nums[k] = x
        k += 1
```

---

### Move Zeroes

* 0以外を前に詰める
* 残りを0で埋める
* returnしない（in-place）

```python
for x in nums:
    if x != 0:
        nums[k] = x
        k += 1

for i in range(k, len(nums)):
    nums[i] = 0
```

---

## 重要なポイント

* 新しいリストを作るのではなく「上書き」
* Pythonはリストを直接変更できる
* 問題によってreturnの有無が違う

---

## つまずいたこと

* docsとAPIの関係が分からなかった
* numsがどこから来るか分からなかった
* 新しいリストと上書きの違い

---

## 学び

* APIは「URLに応じて関数が動く」
* docsは単なる入力画面
* 配列操作は面接で重要
* 理解しながら書くことが大事

---

## 次やること（Day5）

* DELETE（データ削除）
* APIの機能追加
* LeetCode継続
