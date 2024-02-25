### Problem
vscode에서 ssh 연결을 할 때, 아래와 같은 에러가 발생했다.
```
VSCODE ssh 연결 실패 해결방법(could not establish connection to "") - 프로세스에서 없는 파이프에 쓰려고 했습니다.
```

### Solution
`known_hosts` 파일을 삭제한다.
``` 
C:\Users\Username\.ssh\known_host
   ```

