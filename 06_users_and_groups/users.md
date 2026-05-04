# 사용자 관리

## 1. 사용자 생성 (useradd, adduser)

### useradd

useradd는 새로운 사용자를 생성하는 명령어이다.  
일반적으로 root 권한이 필요하다.

```bash
$ sudo useradd test
```

### 생성 확인

```bash
$ cat /etc/passwd | grep test
```

```bash
test:x:1001:1001::/home/test:/bin/bash
```

---

### adduser

```bash
$ sudo adduser test
```

- 사용자 정보를 입력받아 계정을 생성
- useradd보다 직관적인 방식

---

## 2. 사용자 수정 (usermod)

usermod는 기존 사용자 정보를 변경하는 명령어이다.  
root 권한이 필요하다.

```bash
usermod [옵션] [유저이름]
```

### 주요 옵션

| 옵션 | 설명 |
|------|------|
| -d | 홈 디렉터리 변경 |
| -u | UID 변경 |
| -g | 기본 그룹 변경 |
| -c | 사용자 설명 변경 |
| -s | 로그인 쉘 변경 |
| -m | 홈 디렉터리 이동 |
| -l | 사용자 이름 변경 |
| -L | 계정 잠금 |
| -U | 계정 잠금 해제 |

---

## 3. 사용자 삭제 (userdel)

userdel은 사용자를 삭제하는 명령어이다.

```bash
$ sudo userdel test
```

### 옵션

| 옵션 | 설명 |
|------|------|
| -r | 홈 디렉터리까지 삭제 |
| -f | 강제 삭제 |

---

## 4. 핵심 정리

- useradd / adduser: 사용자 생성
- usermod: 사용자 정보 변경
- userdel: 사용자 삭제
- 대부분 root 권한 필요
