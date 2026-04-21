# grep

grep은 vi의 명령어인 **grep (global, regular expression, print)**에서 유래한 것으로,  
표준 입력 또는 파일에서 **정규식을 만족하는 문자열을 출력**하는 명령어이다.

---

## 1. 기본 사용법

```bash
grep [옵션] [패턴] [파일명/디렉터리명]
```

- 파일 대신 파이프(`|`)로 입력을 받을 수도 있다.

---

## 2. 주요 옵션

| 옵션 | 설명 |
|------|------|
| -c | 매칭된 라인의 개수 출력 |
| -o | 매칭된 부분만 출력 |
| -i | 대소문자 구분 없이 검색 |
| -h | 파일 이름 출력 제외 |
| -l | 매칭된 파일 이름만 출력 |
| -v | 매칭되지 않는 라인 출력 |
| -r | 하위 디렉터리까지 재귀 검색 |
| -n | 라인 번호와 함께 출력 |
| -w | 정확히 일치하는 단어만 검색 |

---

## 3. 파이프와 함께 사용

```bash
$ cat redirection.txt | grep "redirect"
```

```bash
hello redirection
hello redirection2
```

- `cat`: 파일 내용 출력  
- `grep`: "redirect" 포함된 라인 필터링  
- 결과: 해당 문자열이 포함된 줄 출력

---

## 4. 파일 직접 검색

```bash
$ grep "redirect" redirection.txt
```

```bash
hello redirection
hello redirection2
```

- 파일을 직접 지정하여 검색 가능

---

## 5. 정규식 사용

```bash
$ grep "on$" redirection.txt
```

```bash
hello redirection
```

- `on$`: "on"으로 끝나는 문자열 검색  
- 결과: 조건에 맞는 라인만 출력

---

## 6. 디렉터리 검색

```bash
$ grep -r "redirect" ./
```

```bash
./redirection.txt:hello redirection
./redirection.txt:hello redirection2
```

- `-r`: 현재 디렉터리 이하 모든 파일 검색  
- 결과: 파일 경로와 함께 출력

---

## 7. 핵심 정리

- grep은 문자열 검색 명령어이다.
- 정규식을 사용하여 다양한 패턴 검색 가능
- 파일 또는 표준 입력 모두 처리 가능
- 파이프(`|`)와 함께 사용하면 매우 강력하다
