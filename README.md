# dockerfile-memo
## FROM RUN CMDの違い

* FROM・・・Docker imageのベースの指定（ubuntuやpythonなど）

- RUN・・・コマンドを実行（image layerを作成）

- CMD・・・docker imageのデフォルトのコマンドを指定（["/bin/bash"]が基本？　["ls"]にしたらdocker run時、ターミナルにリストが開いた
