# git-flow training
 
## ブランチ
### メインブランチ
1. master
    * 常にリリース可能な状態を保持するブランチ。
    * リリース時にはタグを付ける。
1. develop
    * 常に最新の開発結果を保持するブランチ。
                                                                                                                                                                                                                                          
### サポートブランチ
1. feature
    * 新しい機能を開発するブランチ。
    * `develop`から分岐し、`develop`へマージする。
    * 機能が確定するまで`develop`を変更しないことが重要。
1. release
    * リリース準備を行うブランチ。
    * `develop`から分岐し、`master`と`develop`にマージする。
    * 機能の開発が確定したところで`develop`から分岐することにより、`develop`は次のリリースに向けた開発を進めることができる。
1. hotfix
    * リリース後に発生した不具合を修正するブランチ。
    * `master`から分岐し、`master`と`develop`にマージする。
    * `master`と`develop`の時差を考慮した上で即座に不具合に対応できることが重要。
    * `master`から分岐するため、`develop`で開発を進めていてもリリース環境と同様の環境で対応可能。
 
## コマンド
### 初期化
ブランチ構成の作成。`develop`が作成される。
```
$ git flow init
```
 
### サポートブランチ
#### サポートブランチの開始操作。
指定したサポートブランチが作成される。
```
$ git flow [feature|release|hotfix] start <ブランチ名>
```
 
#### サポートブランチの終了操作。
指定したサポートブランチがマージされ、削除される。
```
$ git flow [feature|release|hotfix] finish <ブランチ名>
```

### 開発フロー
#### feature
開発開始。
```
$ git flow feature start <ブランチ名>
```

開発終了。
```
$ git flow feature finish <ブランチ名>
```
