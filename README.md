# tfdf.keras.FeatureUsage()
TFDFにおける特徴量の使用方法定義するためのクラス  
モデルがどのように特徴量を使用するか細かく制御できる

主な用途
- 特徴量のセマンティクスの指定：数値特徴量をカテゴリカル特徴量として扱うなど，解釈を明示的に指定できる
- 特徴量ごとのハイパーパラメータ設定：特定の特徴量に対して，モデルの学習方法を調整するためのハイパーパラメータを設定可能
- モデルへの入力特徴量制限：モデルが使用する特徴量を制限することで，モデルの複雑さ調整したり，特定の情報に焦点をあてたりできる

基本的な使い方
1. オブジェクトの作成
2. 特徴量のセマンティクスやハイパーパラメータの設定
3. モデルへの適用

引数と戻り値  
- 引数：初期化時に引数は取らない 特徴量の設定はオブジェクトのメソッドを通じて行う
- 戻り値：FeatureUsageクラスの新しいインスタンスを返す

# tfdf.keras.GradientBoostedTreesModel()
勾配ブースティング決定木を初期化する関数  

引数  
- objective：モデルの目的関数を指定
- features：モデルが使用する特徴量を指定 tfdf.keras.FeatureUsageオブジェクトとして渡す
- exclude_non_specified_features：fearureで指定されていない特徴量をモデルが使用するか決める
- hyperparameters：決定木の成長戦略を指定
- num_tree：モデルが生成する木の数
- max_depth：最大深度
- random_seed：乱数生成のシード値を指定 モデルの再現性を確保するために使用
- verbose：ログ出力設定
- preprocessing：モデルに入力される特徴量に適応する前処理

戻り値  
インスタンスオブジェクト

# model.make_inspector()
学習済モデルの内部構造や特性を詳細に調査するためのInspectorオブジェクトを生成するメソッド

解析できること  
- 特徴量の重要度分析
- 決定木の構造分析
- モデルの統計情報の取得
- モデルのバイアスと分散の分析
- トレーニングログの確認

引数  
- 引数を取らない

戻り値  
インスタンス

# evaluation()
学習済モデルの評価指標を取得するために使用  
モデルの性能を定量的に把握し，改善のための洞察を得ることができる  
Inspecoterオブジェクトを通じて，モデルの評価指標を取得する  
例）損失，評価指標など  

- 損失：モデルの予測誤差を示す指標
- 正解率：分類タスクにおけるモデルの正解率
- 適合率：モデルが陽性と予測したデータのうち，実際に陽性である割合
- 再現率：実際に陽性であるデータのうち，モデルが陽性と予測できた割合
