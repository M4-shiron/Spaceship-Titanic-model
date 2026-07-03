# Spaceship Titanic Prediction

Kaggle「Spaceship Titanic」の乗客データを使い、乗客が異次元へ転送されたかを予測する二値分類プロジェクトです。

## Result

- GridSearchCV best cross-validation accuracy: **0.7958**
- Best parameters: max_depth=10, n_estimators=100

## Approach

1. 数値特徴量を中央値、カテゴリ特徴量を最頻値で補完
2. カテゴリ変数を pd.get_dummies で数値化
3. train / testの列を align で統一
4. Random Forestを5分割交差検証でチューニング
5. Cabinを deck / side に分解して特徴量を追加
6. Kaggle提出用の submission.csv を出力

## Tech Stack

- Python
- pandas / NumPy
- scikit-learn
- Jupyter Notebook / Kaggle Notebook

## Files

- sf-titanic.ipynb — ベースラインモデル
- sf-titanicgenuine.ipynb — グリッドサーチと特徴量エンジニアリングを含む改善版

## What I Learned

欠損値処理、one-hot encoding、交差検証によるハイパーパラメータ探索、客室情報の特徴量エンジニアリングを実践しました。
