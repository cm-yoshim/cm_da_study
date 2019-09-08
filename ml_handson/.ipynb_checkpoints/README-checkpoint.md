## 概要

[kaggle](https://www.kaggle.com/c/titanic)のタイタニックデータを使って機械学習をやってみよう！！！  

## 最初に
今回は「Pipenv」で仮想環境を構築して、そこで実行していきます。  
手順は下記の通りです。  

### 1.pipenvのインストール

```python
$ # インストール確認（入っていないようなら、インストールが必要）
$ pipenv --version

$ # インストールされていないようならインストール
$ brew install pipenv
```

### 2.pipenvで環境を作成

```python
$ # リポジトリをclone
$ git clone https://github.com/cm-yoshim/cm_da_study.git
$ # ディレクトリ移動
$ cd ml_handson
$ pipenv install -d
```

### 3.今作った仮想環境がJupyter nontebookで参照できるようにカーネルパスを通す

```python
$ # 仮想環境のアクティベート
$ pipenv shell
$ # パスを通す
$ python -m ipykernel install --user --name=`basename $VIRTUAL_ENV`
$ # jupyter labの起動
$ jupyter lab
```

### 4.notebookファイルを起動

![start_nontebook.png](docs/start_nontebook.png)


### 5.利用が終わったら

```
$ # 仮想環境を閉じる
$ pipenv exit
```

### 6.仮想環境の削除（オプション）
勉強が終わってこの環境が不要になったら、仮想環境を削除しましょう。

```python
$ # 対象のディレクトリに移動
$ cd ml_handson
$ # 仮想環境の削除
$ pipenvv --rm
$ # jupyterで参照するためにカーネルのパスを作成したが、仮想環境を削除したら不要なので削除
$ rm -r /Users/<user-name>/Library/Jupyter/kernels/<kernael-name>
```


## 目次

- 1.タスクとデータの概要を確認する(EDA)  
    - 1-1.タスクの概要　　
    - 1-2.データの中身を確認
    - 1-3.特徴量間、目的変数間の相関を確認　　
- 2.特徴量エンジニアリング  
    - 2-1.数値型
        - 欠損値の扱い
        - 正規化  
        - ビンニング  
    - 2-2.カテゴリカル型
        - 欠損値の扱い
        - one-hot-encoding  
        - Target-encoding
    - 2-3.特徴量選択
        - PCA
        - boruta
    - 2-4.特徴量の自動生成(オプション)
        - featuretools
- 3.モデルを学習＆評価  
    - 3-1.検証方法の検討
        - 交差検証
        - 混同行列
        - F1
        - AUC
    - 3-2.モデリング
        - 重回帰
        - catboost  
        - ハイパーパラメータのチューニング  
            - GridSearch
            - ハイパーパラメータのチューニングの自動化(optuna)
        - Neural Network(option)
            - keras
    - 3-3.推論結果を欲しい形で整形
        - 推論
        - 整形して出力
    