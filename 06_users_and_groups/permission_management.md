# 소유자, 그룹 및 권한 변경

## 1. 그룹 변경 (chgrp)

### chgrp

chgrp는 **change group**의 약자로 파일 또는 디렉터리의 그룹을 변경할 때 사용한다.

```bash
chgrp [옵션] [소유그룹] [파일/디렉터리]
```

### 주요 옵션

| 옵션 | 설명 |
|------|------|
| -c | 변경된 파일만 출력 |
| -f | 오류 메시지 출력 안 함 |
| -v | 자세한 정보 출력 |

---

### 실습

```bash
$ sudo chgrp test test_file
```

```bash
$ ls -al
```

```bash
-rw-r--r-- 1 CKIRUser test 0 May 10 15:41 test_file
```

- 파일의 그룹이 `test`로 변경된 것을 확인할 수 있다.
- sudo를 사용한 이유는 현재 사용자가 해당 그룹 권한을 가지고 있지 않기 때문이다.

---

## 2. 소유자 및 그룹 변경 (chown)

### chown

chown은 **change owner**의 약자로 파일 또는 디렉터리의 소유자와 그룹을 변경할 때 사용한다.

```bash
chown [옵션] [소유자:소유그룹] [파일/디렉터리]
```

### 주요 옵션

| 옵션 | 설명 |
|------|------|
| -c | 변경된 파일만 출력 |
| -f | 오류 메시지 출력 안 함 |
| -v | 자세한 정보 출력 |

---

### 실습

```bash
$ sudo chown test:test test_dir
```

```bash
$ ls -al
```

```bash
drwxr-xr-x 1 test test 0 May 10 15:41 test_dir
```

- 디렉터리의 소유자와 그룹이 변경된 것을 확인할 수 있다.

---

## 3. 권한 변경 (chmod)

### chmod

chmod는 **change mode**의 약자로 파일의 권한을 변경할 때 사용한다.

```bash
chmod [옵션] [권한] [파일/디렉터리]
```

### 주요 옵션

| 옵션 | 설명 |
|------|------|
| -c | 변경된 파일만 출력 |
| -f | 오류 메시지 출력 안 함 |
| -v | 자세한 정보 출력 |

---

## 4. 숫자 방식 권한 설정

권한은 다음 순서로 구성된다.

```text
[특수 권한][소유자 권한][그룹 권한][기타 사용자 권한]
```

예시:

```text
4752
```

```text
4 : setuid
7 : rwx
5 : r-x
2 : -w-
```

즉:

```text
-rwsr-x-w-
```

권한이 된다.

---

### 실습

```bash
$ chmod 4752 test_file
```

```bash
$ ls -al
```

```bash
-rwsr-x-w- 1 CKIRUser 197121 0 May 10 15:41 test_file
```

- setuid와 권한이 적용된 것을 확인할 수 있다.
- setuid는 실행 권한(x)이 존재할 때 `s`로 표시된다.

---

## 5. 문자 방식 권한 설정

chmod는 숫자 방식뿐 아니라 문자 방식도 지원한다.

```text
[객체][+/-][권한]
```

### 객체

| 객체 | 의미 |
|------|------|
| u | user |
| g | group |
| o | other |

### 권한

| 권한 | 의미 |
|------|------|
| r | read |
| w | write |
| x | execute |
| s | setuid/setgid |
| t | sticky bit |

- `+` : 권한 추가
- `-` : 권한 제거

객체를 지정하지 않으면 모든 객체에 적용된다.

---

### 실습

```bash
$ chmod g+w test_file
```

```bash
$ ls -al
```

```bash
-rwsrwx-w- 1 CKIRUser 197121 0 May 10 15:41 test_file
```

- 그룹에 쓰기 권한이 추가된 것을 확인할 수 있다.

---

## 6. 핵심 정리

- chgrp: 그룹 변경
- chown: 소유자 및 그룹 변경
- chmod: 파일 권한 변경
- chmod는 숫자 방식과 문자 방식을 모두 지원
- setuid는 실행 권한이 있을 때 `s`로 표시됨
