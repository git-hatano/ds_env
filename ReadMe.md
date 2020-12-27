# Data Sience env.
JupyterLabのコンテナを作成

## Dockerfile build
buildフォルダで以下コマンドを実行　
-t : image_name
```
docker build -t ds_env .
```

## IMAGE IDを確認
ds_envというREPOSITRYがあるはず
```
docker images
```

## JupyterLabのコンテナ起動 (初回時)
ds_envフォルダで以下コマンドを実行
```
docker run -p 8888:8888 -v /Users/kazu/Documents/ds_env/ds_python/:/work --name my-lab <IMAGE ID>
```
ex.
```
docker run -p 8888:8888 -v /Users/kazu/Documents/ds_env/ds_python/:/work --name my-lab 0ac5e85211e7
``` 

## JupyterLabにアクセス
ブラウザ上で以下を検索
```
localhost:8888
```

## JupyterLabのコンテナ起動 (2回目以降)
### my-labのCONTAINER IDを確認
```
docker ps -a
```

### JupyterLabのコンテナのSTATUSをUPに
```
docker restart <CONTAINER ID>
```

### JupyterLabにアクセス
ブラウザ上で以下を検索
```
localhost:8888
```
