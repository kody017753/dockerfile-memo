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
 
### FROM RUN CMDの違い

* FROM・・・Docker imageのベースの指定（ubuntuやpythonなど）

- RUN・・・コマンドを実行（image layerを作成）

- CMD・・・docker imageのデフォルトのコマンドを指定（["/bin/bash"]が基本？　["ls"]にしたらdocker run時、ターミナルにリストが開いた
