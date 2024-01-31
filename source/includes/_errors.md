# 사용정책

## 파티션 정책
| 구분     | Class A, 참여교수 | Class B, 교내교수 | Class C, 외부 사용자 | 비고           |
|----------|:-----------------:|:-----------------:|:--------------------:|:--------------:|
| A100-1   |         O         |                   |                      |                |
| A100-2   |         O         |                   |                      |                |
| A100-3   |         O         |         O         |          O           |                |
| A100-4   |         O         |         O         |          O           |                |
| A6000-1  |         O         |                   |                      |                |
| A6000-2  |         O         |                   |                      |                |
| A6000-3  |         O         |         O         |          O           |                |
| A6000-4  |         O         |         O         |          O           |                |
| A40-1    |         O         |                   |                      | LocalDisk 권장 |
| A40-2    |         O         |         O         |          O           | LocalDisk 권장 |
| A40-3    |         O         |         O         |          O           | LocalDisk 권장 |


## 컴퓨팅 자원 정책

- 기본 정책

| 구분 | 정책 | 비고 |
|---|---|---|
| 작업 당 최대 작업 시간 | <span style='background-color:#fff5b1; color:red'>7일</span> (7-00:00:00) | - 모든 작업에는 시간 지정 필수 <br> - 추가 작업 시간 필요 시 별도 요청 |
| 계정 당 저장 공간 용량 제한 | <span style='background-color:#fff5b1; color:red'>100G</span> | - 추가 공간 필요 시 사유와 함께 요청 |
| 계정 당 최대 작업 개수 | 100개 | - |
| 사용 가능 최대 GPU 개수 | a100: 4개/ a6000:4개/ a40:4개 | a40:4개 초과 신청 할 경우, 취소 될 수 있음 |
| 사용 가능 최대 CPU Core 개수 | a100: 20개/ a6000:6개/ a40:10개 | * 할당받은 GPU수 * 까지 사용 가능 (a40 4개 사용 경우, 40개) |

- NAS 정책

| 구분 | 경로 | 접근 권한 | 비고 |
|---|---|---|---|
| 공용 저장 공간 | /shared/public | 모든 계정 가능 | - |
| 계정 별 저장 공간 | /shared/home/계정명 | 본인 계정만 가능 | 계정 당 100GB |


## 로컬 디스크 사용 정책

| 구분 | 경로 | 노드 | 비고 |
|---|---|---|---|
| 계정 별 저장 공간 | <code>/raid/계정명</code> | sv8ka[n1-n3], sv4ka[n1-n4],a100[n1-n4] | 계정 당 최대 300GB |

<aside class="warning">
사용자가 많아져 해당 경로가 가득차면(Disk Full) 다른 사용자를 위해서 디렉토리의 데이터는 <b style='color:crimson'>삭제</b>될 수 있습니다. 수시로 로컬 디스크의 데이터를 백업하고 정리하시는 것을 추천 드립니다.
<br>
인공지능융합센터에서는 수시로 용량을 검사하며, <u>한달 이상 방치된 파일</u>은 <strong style='color:crimson'>삭제</strong> 될 수 있음을 알려드립니다.
</aside>