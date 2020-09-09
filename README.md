# SSH 원격 Jupyter Notebook 접속하기

### ssh 설치 완료 기준



## 1. ssh [ID]@[IP] 접속

```
#server
conda activate [name]
conda install jupyter
jupyter notebook --generate-config
```

## 2. Jupyter 설정

```
#server
sudo gedit .jupyter/jupyer_notebook_config.py

#True로 파일 수정
c.NotebookApp.allow_remote_access=True
```

## 3. jupyter 비밀번호 설정

```
#server
jupyter notebook password
```

## 4.서버에서 no browser 옵션 실행 포트지정 루트권한

```
#server
jupyter notebook --allow-root --port=9000 --no-browser
```

## 5.서버 9000포트와 local:8888 포트 연결

```
#local
ssh -N -f -L 8888:localhost:9000 [ID]@[IP]
```

## 6. local에서 localhost:8888 접속 jupyter notebook비밀번호 입력

```
#local
http://localhost:8888
```

