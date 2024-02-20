### Problem
Official pypi server가 느려서 `pip install`시에 오랜 시간이 걸리거나, `ReadTimeoutError`가 발생한다.

### How to do
Official pypi 서버 대신 다른 mirror server를 이용한다. 

`pip install` 시에 `-i` 옵션을 주고 mirror server url을 명시해주면 된다.

```
pip install -i <mirror server url> <package name>
```

- 에러가 발생하거나 경고가 보기 싫으면 `--trsuted-host` 옵션을 추가해 준다.

``` 
pip install -i <mirror server url> --trusted-host <sample.host.com> <package_name>
```

나는 선문대학교 mirror 서버를 이용했다.
```
pip install -i https://mirrors.sustech.edu.cn/pypi/simple <package name>
```
