# docker fileの作成

## 「docker」フォルダを作成する
```ubuntu
mkdir docker
```
## 「dockerフォルダの中にテキストエディタで「Dockerfile」を作成する
```ubuntu
gedit DOckerfile
 ※テキストエディタはなんでもいい
 ```
 
 ## 書き込む
 ```text
 （例）
 FROM ubuntu:latest
 RUN touch test
 CMD ["/bin/bash"]
 ```
### FROM RUN CMDとは

- FROM・・・Docker imageのベースの指定（ubuntuやpythonなど）

- RUN・・・コマンドを実行（image layerを作成）

- CMD・・・docker imageのデフォルトのコマンドを指定（["/bin/bash"]が基本？　["ls"]にしたらdocker run時、ターミナルにリストが開いた

## Dockerfileからdocker imageを作成する
```ubuntu
docker build <directory>
 ※Dockerfileのあるディレクトリに移動してから打ち込むことが基本だから「docker build .」の形で覚えるとよい
```

## （注）RUNは書き方に気を付ける
- 各コマンドごとにレイヤーが作成されるため、まとめて実行するように記述すると良い
- (例)RUN apt-get update && apt-get install -y \  
 　　curl \
     cvs \
     nginx 
- 「&&」であぷで、インストールを同時にし「\」で複数のモジュールを入れたりできる
- レイヤーが増えると見ずらかったり容量が増える原因に（まとめたほうが容量少ない）
