イメージビルドを行う。

```bash
docker build -t agents .
```

ホストマシン(ローカル環境)上のカレントディレクトリ内のファイルをコンテナ内の`/usr/src/app`にマウントしてコンテナを起動する。
これでローカル環境での修正がコンテナにも反映される(Dockerfile 内の`COPY . .`は不要となる)。
また、`-env-file`で`.env`をコンテナに渡す。

```bash
docker run --env-file .env -v $(pwd):/usr/src/app -it agents
```

コンテナを起動するとコンテナ内の bash シェルが立ち上がる。
以下のコマンドでスクリプトが実行される。

```bash
python main.py
```
