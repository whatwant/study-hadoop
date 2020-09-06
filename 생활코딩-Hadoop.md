
## #1 하둡소개
- https://www.youtube.com/watch?v=HCR1ILMROfI

### Terms
- 빅데이터: 한대의 컴퓨터로는 저장하거나 연산하기 어려운 규모의 거대 데이터
- 분산: 여러 대의 컴퓨터로 나눠서 일을 처리함
- 저장: 데이터를 저장한다
- 분석: 데이터가 저장된 컴퓨터에서 데이터를 분석하고 그 결과를 합친다

## #2 하둡 - 소개 helloworld
- https://www.youtube.com/watch?v=AZ136kwcsz8

### 기본 구성
- 3개의 노드 구성: 네임노드 1개, 데이터노드 2개
- 네임노드: 어떤 데이터가 어떤 데이터노드에 있는지 나눠주는 역할

### 기본 실습
- 현재 파일 목록 확인
```
$ hadoop fs -ls
```
- 파일 삭제
```
$ hadoop fs -rm <filepath>
```
- 디렉토리 삭제
```
$ hadoop fs -rms <dirpath>
```
- 파일 등록
  - 이렇게 파일을 등록(저장)할 때 분산되어서 저장되는 것이다.
```
$ hadoop fs -put <from filepath> <target dirpath>
```

### 샘플 실습 : Word Counting
- Hadoop은 Java로 개발되었다.
- Hadoop에 기본 포함된 examples를 이용해서 실습
- Hadoop에서 제공하는 Map Reduce를 이용
```
$ hadoop jar hadoop-examples-1.0.4.jar wordcount <filepath in Hadoop> <output dirpath>
```
- 작은 파일을 처리하는 것 치고는 느림. because 대용량에 맞춰진 시스템이기 때문에...
- 결과 확인
```
$ hadoop fs -la <output dirpath>
$ hadoop fs -cat <output dirpath>/part-r-00000
```
