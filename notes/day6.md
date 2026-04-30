# Day6 学習ログ（Two Sum 完全理解）

## ■ 今日の目的
- Two Sum（二重ループ版）の理解
- dict版の理解
- 「記憶ゲー」からの脱却

---

## ■ 二重ループ版の理解

### コード
for i in range(len(nums)):
    for j in range(i+1, len(nums)):
        if nums[i] + nums[j] == target:
            return [i, j]

### ポイント
- j を i+1 から始める理由
  - 同じ要素（i == j）を防ぐ
  - (0,1) と (1,0) の重複を防ぐ
- 計算量：O(n^2)

---

## ■ dict版（最重要）

### 完成コード
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        seen = {}

        for i in range(len(nums)):
            need = target - nums[i]

            if need in seen:
                return [seen[need], i]

            seen[nums[i]] = i

---

## ■ dictの使い方

seen[数] = インデックス

例：
seen = {
    2: 0,
    7: 1
}

→ seen[2] = 0（インデックス取得）

---

## ■ アルゴリズムの流れ（超重要）

1. 空の辞書を用意
2. 配列を順番に見る
3. 今の数に対して必要な値（need）を計算
4. need が辞書にあるか確認
5. あればインデックスを返す
6. なければ今の数を辞書に保存

---

## ■ 本質

「今の数に対して、必要な相手が過去にあるか？」

---

## ■ なぜ速いのか

- 二重ループ → O(n^2)
- dict版 → O(n)

理由：
- 探しに行く → 遅い
- あるか聞くだけ → 速い

---

## ■ 今日の気づき

- コードを覚えるだけでは弱い
- 「なぜその処理をするか」を説明できることが重要
- printで流れを確認するのが大事
- 難しい問題は無理に進めない方が良い

---

## ■ 今の課題

- 記憶ベースでコードを書いてしまう
- dictの理解は進んだが、言語化がまだ弱い

---

## ■ 明日の方針

1. Two Sum をもう一度「説明 → コード化」
2. Daily Temperatures に再挑戦（スタック）
3. printで処理の流れを確認

---

## ■ 一言

今日の進み方は正しい
「分からない」を潰した日が一番価値がある