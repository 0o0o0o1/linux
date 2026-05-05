# 그룹 관리

## 1. 그룹 생성 (groupadd, addgroup)

### groupadd

groupadd는 새로운 그룹을 생성하는 명령어이다.  
root 권한이 필요하다.

```bash
$ sudo groupadd -g 12345 test
```

### 생성 확인

```bash
$ cat /etc/group | grep test
```

```bash
test:x:12345:
```

---

### addgroup

```bash
$ sudo addgroup test
```

- 간편하게 그룹 생성 가능

---

## 2. 그룹 수정 (groupmod)

groupmod는 그룹 정보를 변경하는 명령어이다.  
root 권한이 필요하다.

```bash
groupmod [옵션] [그룹이름]
```

### 주요 옵션

| 옵션 | 설명 |
|------|------|
| -g | GID 변경 |
| -n | 그룹 이름 변경 |

---

### 예시

```bash
$ sudo groupmod -g 23456 test
```

```bash
$ cat /etc/group | grep test
```

```bash
test:x:23456:
```

---

## 3. 그룹 관리 (gpasswd)

gpasswd는 그룹의 사용자 및 암호를 관리하는 명령어이다.  
root 권한이 필요하다.

```bash
gpasswd [옵션] [그룹이름]
```

### 주요 옵션

| 옵션 | 설명 |
|------|------|
| -a [user] | 사용자 추가 |
| -d [user] | 사용자 제거 |
| -A [user] | 관리자 지정 |
| -r | 그룹 암호 제거 |
| -R | 그룹 접근 제한 |
| -m [user] | 여러 사용자 지정 |

---

### 사용자 추가

```bash
$ sudo gpasswd -a user test
```

```bash
$ cat /etc/group | grep test
```

```bash
test:x:23456:user
```

---

### 사용자 제거

```bash
$ sudo gpasswd -d user test
```

```bash
$ cat /etc/group | grep test
```

```bash
test:x:23456:
```

---

## 4. 그룹 삭제 (groupdel)

groupdel은 그룹을 삭제하는 명령어이다.

```bash
$ sudo groupdel test
```

### 옵션

| 옵션 | 설명 |
|------|------|
| -f | 강제 삭제 |

---

## 5. 핵심 정리

- groupadd / addgroup: 그룹 생성
- groupmod: 그룹 정보 변경
- gpasswd: 그룹 사용자 관리
- groupdel: 그룹 삭제
- 대부분 root 권한 필요
