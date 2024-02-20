### Problem
아래와 같이 docker option에 `gpus`를 지정해주었을 때 Error 발생
```
$ sudo docker run --gpus all -it --rm --ipc=host nvcr.io/nvidia/pytorch:23.10-py3

docker: Error response from daemon: could not select device driver "" with capabilities: [[gpu]].
```

### Solution
`nvidia-container-tollkit`을 설치한다
1. Nvidia Repository 추가
``` 
$ distribution=$(. /etc/os-release;echo $ID$VERSION_ID) \
   && curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add - \
   && curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
   ```
2. `apt-get`으로 `nvidia-container-toolkit` 설치
```
$ sudo apt-get update && sudo apt-get install -y nvidia-container-toolkit
```
3. `docker service` 재시작
```
$ sudo systemctl restart docker
```
