# apt & apt-get

## 1. apt와 apt-get

apt는 apt-get의 단점을 보완하기 위해 등장한 패키지 관리 도구이다.

기존에는:

- apt-get
- apt-cache
- dpkg -l

등 여러 명령어를 따로 사용해야 했지만, apt는 이 기능들을 통합하여 더 편리하게 사용할 수 있도록 만들어졌다.

apt는 **Advanced Package Tool**의 약자이다.

일부 명령어(install, remove, upgrade 등)는 root 권한이 필요하므로 sudo와 함께 사용한다.

```bash
apt [옵션] [명령어]
```

---

## 2. 주요 명령어

| 명령어 | 설명 |
|------|------|
| list | 패키지 목록 출력 |
| search [검색어] | 패키지 검색 |
| show [패키지 이름] | 패키지 정보 출력 |
| install [패키지 이름] | 패키지 설치 |
| reinstall [패키지 이름] | 패키지 재설치 |
| remove [패키지 이름] | 패키지 삭제 |
| update | 패키지 목록 업데이트 |
| upgrade | 패키지 업그레이드 |

---

## 3. 패키지 목록 업데이트

프로그램 설치 전에는 패키지 저장소 정보를 최신 상태로 갱신하는 것이 좋다.

```bash
$ sudo apt update
```

- 패키지 저장소 정보를 최신 상태로 업데이트한다.

---

## 4. 패키지 업그레이드

설치된 패키지들을 최신 버전으로 업그레이드한다.

```bash
$ sudo apt upgrade
```

---

## 5. update와 upgrade 함께 사용

패키지 설치 전 아래 명령어를 자주 사용한다.

```bash
$ sudo apt update -y && sudo apt upgrade -y
```

### 설명

- `update`
  → 저장소 정보 갱신

- `upgrade`
  → 설치된 패키지 최신 버전으로 업데이트

- `&&`
  → 앞 명령어 성공 시 다음 명령 실행

- `-y`
  → 모든 질문에 자동으로 yes 입력

패키지 저장소 정보와 설치된 패키지 버전을 최신 상태로 유지하여 충돌이나 오류 가능성을 줄일 수 있다.

---

## 6. 패키지 검색

```bash
$ apt search gdb
```

- gdb 관련 패키지를 검색한다.

---

## 7. 패키지 정보 확인

```bash
$ apt show gdb
```

- gdb 패키지의 상세 정보를 출력한다.

---

## 8. 패키지 설치

```bash
$ sudo apt install gdb-multiarch
```

- gdb-multiarch 패키지를 설치한다.

---

## 9. 패키지 제거

```bash
$ sudo apt remove gdb-multiarch
```

- gdb-multiarch 패키지를 제거한다.

---

## 10. 핵심 정리

- apt는 apt-get을 개선한 패키지 관리 도구이다.
- 패키지 설치, 제거, 검색 등을 수행할 수 있다.
- update는 저장소 정보를 갱신한다.
- upgrade는 설치된 패키지를 업그레이드한다.
- install은 패키지를 설치한다.
- 일반적으로 sudo와 함께 사용한다.
