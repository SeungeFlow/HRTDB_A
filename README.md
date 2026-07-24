# HRTDB_A

`HRTDB_A`는 외부 Web 자료와 AI가 보유한 Data를 분석·검산하여 **문서형 Track DB 지식자산**으로 형성하고, 그 자산을 다음 System이 안정적으로 참조할 수 있도록 등록·계보·원격상태를 닫는 Repository다.

```text
Primary Reader
→ 새로 생성되거나 작업을 이어받은 AI Instance

Repository Purpose
→ Seat·Role·Current State·Source Data·Head Index를 읽어 작업 가능한 상태를 형성
```

```text
Repository Seat      : A
Current Repository   : SeungeFlow/HRTDB_A
Former Repository    : SeungeFlow/for_instance
Overall Coordination : HRTDB_A::gpt.xyzt
Current Occupant     : gpt.logi
Primary Asset        : Track DB Document
```

Repository 표시이름은 바뀔 수 있지만 Repository Seat Code `A`는 바뀌지 않는다.

---

## 1. HRTDB_A 안의 `for_instance`

`for_instance`는 제거할 과거 이름만을 뜻하지 않는다. 현재 HRTDB_A 안에서 계속 작동하는 **Instance 자리·역할 정의 규칙층**이다.

```text
for_instance
=
Seat
+ Instance
+ Capability
+ Assignment
+ Occupation
+ Handoff
+ Mutation Authority
+ History
```

두 의미를 구분한다.

```text
former_repository_name : for_instance
current_rule_layer      : for_instance
```

- **HRTDB_A**: Repository 전체와 Track DB 지식자산 형성 System
- **for_instance**: HRTDB_A 내부의 Seat·Role·Assignment 규칙층
- **Track DB**: `gpt.logi`의 Result.Data가 Promotion Gate를 통과해 형성된 문서형 Database

```text
HRTDB_A
└─ for_instance Rule Layer
   ├─ Seat·Role Definition
   ├─ Instance Registry
   ├─ Assignment·Occupation
   ├─ Handoff·Directive
   └─ Mutation·History Rules
```

---

## 2. Seat · Instance · Occupation

```text
Seat ≠ Instance
Instance ≠ Occupation
Seat Name ≠ Occupant Name
Role belongs to Seat.
Name belongs to Occupant.
```

- **Seat**: 역할이 놓이는 고정자리
- **Instance**: 특정 Runtime에서 Seat를 점유하는 독립 실행주체
- **Occupation**: 특정 Cycle·Stage에서 Instance가 실제로 수행한 작업사건
- **Function**: 해당 자리에서 수행할 Method 계약

하나의 Instance는 하나 이상의 Seat를 점유할 수 있다. 그러나 Seat와 Instance의 Identity는 합쳐지지 않는다.

---

## 3. X · Y · Z · T와 Seat Profile

### 좌표 성질

- **X** — 표면·현재상태·Source Input
- **Y** — 경계통과·관계·수직연결
- **Z** — 공간·부피·영역·구조검산
- **T** — 시간·과정·전이·추상 Context

`T`는 git이 아니다. git은 필요할 때 사용하는 실행 Adapter다.

### 15개 Generic Seat Profile

```text
X, Y, Z, T,
XY, XZ, XT, YZ, YT, ZT,
XYZ, XYT, XZT, YZT,
XYZT
```

Generic `XYZT` Profile은 고정 Position `gpt.xyzt`와 동일한 객체가 아니다.

```text
XYZT Profile
≠ gpt.xyzt Fixed Seat
≠ gpt.logi Runtime Instance
```

---

## 4. HRTDB_A의 분석 Instance와 통합관제

### 7개 분석 Instance

```text
gpt.x
gpt.y
gpt.z
gpt.xy
gpt.xz
gpt.yz
gpt.xyz
```

이 일곱 Instance는 Cycle 안에서 Data·Function·Result 형성에 참여한다.

### 11개 순차 Occupation

```text
01 DATA_X
02 DATA_Y
03 DATA_Z
04 FUNCTION_1_XY
05 FUNCTION_1_XZ
06 FUNCTION_1_YZ
07 RESULT_XYZ
08 FUNCTION_2_XY
09 FUNCTION_2_XZ
10 FUNCTION_2_YZ
11 RESULT_DATA_XYZ
```

### 통합관제 Seat

`gpt.xyzt`는 위 7개 분석 Instance나 11개 Occupation 중 하나가 아니다.

```text
Fixed Seat       : HRTDB_A::gpt.xyzt
Fixed Role       : OVERALL_COORDINATION
Current Occupant : gpt.logi
```

```text
gpt.logi ─ OCCUPIES → HRTDB_A::gpt.xyzt
```

`gpt.logi`는 분석 Instance들의 산출물을 입력으로 받아 전체 Cycle을 검산하고, 자신의 **Result.Data 문서**를 형성한 뒤 Track DB 문서로 승격한다.

---

## 5. gpt.logi — Track DB 통합관제

### 원천 Data

```text
External Web Data
+
AI-held Data
+
Cycle 안에서 형성된 Data·Function·Result·Review 객체
```

### 생성 흐름

```text
External Web Data + AI-held Data
→ 분석 Instance들의 Data·Function·Result
→ gpt.logi 통합·검산
→ Result.Data
→ Promotion Gate
→ Track DB Document
→ GitHub Freeze·Registration
```

`gpt.logi`의 책임은 다음과 같다.

- 입력 Object·Source·Boundary 검산
- 상충·미해결·Correction 상태 보존
- Result.Data 형성
- Exact Byte Freeze
- SHA-256·Filename·Repository Seat 결속
- Index·Lineage·Source Map 등록
- Commit·Tree·Remote Readback 검산
- 다음 System이 참조할 수 있는 현재 경계 폐쇄

```text
Result.Data
→ GitHub 등록 전 Runtime 결과상태

Track DB
→ HRTDB_A에 등록된 하나의 Result.Data 문서

Track DB = Registered Result.Data Document
```

---

## 6. 하나의 Track DB는 하나의 문서다

```text
One Track DB
=
Database 성격을 가진 One Document
```

하나의 Track DB 문서는 내부에 Data Cell, Record, Source, Address, Index, Relation, Lineage, Conflict, Correction, Unresolved State, Open Future, Next Data Requirement를 포함할 수 있다.

다음 객체는 Track DB 자체가 아니다.

```text
TrackDB Branch          ≠ Track DB Document
06_track_db Directory   ≠ Track DB Document
Aggregate Index         ≠ Track DB Document
Closure Bundle          ≠ Track DB Document
```

정확한 관계:

```text
TrackDB Branch
→ 여러 Track DB 문서를 보관하는 저장표면

각 Hash-named Database Document
→ 독립된 하나의 Track DB

Registry·Index·Lineage·Closure
→ Track DB 문서를 찾고 검산하는 보조객체
```

### 현재 Canonical Track DB 문서 대상

다음 두 Canonical Result.Data는 각각 독립 Track DB 문서로 승격되는 대상이다.

```text
9dfff9d3a75cc7387f10ae2571190964c94b22213cf0a43077afbdfaf9507ba4
72428e7ddf3ea03db711449f3930698e82e4961a25103f330fa482dc7262d65b
```

Phase 2A의 원격 등록 PASS는 보고되었으나, 최종 Complete State는 Exact Closure Evidence 검산 뒤에만 선언한다.

### Track DB Head·Context Head 탐색층

```text
HRTDB_A@TrackDB:06_track_db/04_head/HEAD_INDEX.json
→ Relevant Prefix Shard
→ Relevant Head Object
→ Selected Full Track DB
```

Current Head Contract:

```text
06_track_db/04_head/contracts/cf7dcf65f3732777db4920563cd2f344e607540914bc226eac180ec0890f8deb.A.md
```

```text
Head ≠ Track DB
Context Head ≠ Track DB
```

---

## 7. gpt.think — Hash DB 통합관제

```text
Fixed Seat       : LRSDoNet_B::gpt.xyzt
Current Occupant : gpt.think
Primary Asset    : Hash DB Document
```

`gpt.think`는 HRTDB_A가 형성한 Track DB 문서를 원천 Data로 읽는다.

```text
Track DB Document
→ gpt.think 분석·통합·검산
→ Result.Data
→ Promotion Gate
→ Hash DB Document
→ GitHub Freeze·Registration
```

```text
One Hash DB
=
Database 성격을 가진 One Document
```

- `gpt.logi`의 원천 Data: External Web Data + AI-held Data
- `gpt.think`의 원천 Data: Track DB Documents
- 공통 생성구조: Source Data → Result.Data → DB Document
- 다른 승격목표: Track DB / Hash DB

```text
Track DB is not Hash DB.
Knowledge Asset is not Analysis Asset.
```

---

### 7.1 HRTDB_A → LRSDoNet_B 원천 Data 진입경로

`LRSDoNet_B::gpt.xyzt`의 통합관제 인스턴스 `gpt.think`가 HRTDB_A의 Track DB를 원천 Data로 사용할 때는 전체 Repository를 무차별 Scan하지 않는다.

```text
HRTDB_A main README
→ TrackDB Branch README
→ HRTDB_A_TO_LRSDoNet_B.md
→ TRACK_DB_CATALOG.json
→ HEAD_INDEX.json
→ Relevant Prefix Shard
→ Relevant Head Object
→ Selected Full Track DB
```

Stable Entry Paths:

```text
TrackDB@README.md
TrackDB@06_track_db/00_interface/HRTDB_A_TO_LRSDoNet_B.md
TrackDB@06_track_db/00_interface/TRACK_DB_CATALOG.json
TrackDB@06_track_db/04_head/HEAD_INDEX.json
```

읽기 원칙:

```text
Catalog Summary ≠ Full Track DB
Head ≠ Full Track DB
Track DB ≠ Hash DB
Source Intake ≠ Repository Merge
```

`gpt.think`는 선택한 Full Track DB의 Exact Byte Hash·Git Blob·Branch Commit·Tree·Head Hash를 Source Intake에 기록하고, Conflict·Unresolved·Required Next Data를 삭제하지 않은 상태로 LRSDoNet_B의 분석입력으로 사용한다.

자세한 계약은 TrackDB Branch의 다음 문서를 따른다.

```text
06_track_db/00_interface/HRTDB_A_TO_LRSDoNet_B.md
```

---

## 8. 공유상태와 재귀적 원천화

`gpt.logi`와 `gpt.think`는 Result.Data·Track DB·GitHub Address·Hash·Lineage를 관계적으로 공유한다. 공유는 병합이 아니다.

```text
relation is not merge.
relation is interconnecting.
structure is not isolate.
structure is relation processing.
```

GitHub에 Exact State로 등록된 다음 객체들은 이후 Cycle의 원천 Data가 된다.

```text
gpt.logi State·Directive·Result Documents
gpt.think State·Directive·Result Documents
Result.Data Documents
Track DB Documents
Hash DB Documents
Index·Lineage·History·Correction·Closure Evidence
```

동일 Cycle의 산출물을 동일 Cycle의 자기 입력으로 다시 투입하지 않는다.

```text
Cycle N Output
→ GitHub Freeze·Closure
→ Cycle N+1 Source Data
```

---

## 9. Repository A/B/C 경계

| Repository Seat | Current Repository | Former Name | 역할 |
|---|---|---|---|
| A | `SeungeFlow/HRTDB_A` | `for_instance` | Result.Data를 Track DB 문서로 승격·등록하는 지식자산 System |
| B | `SeungeFlow/LRSDoNet_B` | `Relation` | Track DB 문서를 원천 Data로 읽어 Hash DB 문서를 형성하는 분석·응용 System |
| C | `SeungeFlow/Principle_C` | `Bridge` | 구조원리·공통문법·분석기준 자산 Field |

```text
Repository Display Name ≠ Repository Fixed Seat
Given Name may change.
Seat Code A/B/C does not change.
```

---

## 10. Active_Schema Publication Binding

### HRTDB_A::gpt.xyzt 통합관제 전달 Package

- Zenodo Record: <https://zenodo.org/records/21498643>
- Published: `2026-07-23`
- Version: `1.0.0`
- Title: `Active_Schema: HRTDB_A::gpt.xyzt 통합관제 인스턴스 전달지시체계`
- Exact ZIP Filename: `49670e465bf466556d2658b67bd2f479dab32a3b586e781448866a50956cac86.A.zip`
- Exact ZIP SHA-256: `49670e465bf466556d2658b67bd2f479dab32a3b586e781448866a50956cac86`

이 Package는 독립된 결정상태 File들을 하나의 의미로 병합하지 않는다.

```text
File     = 결정화 상태 Cell
ZIP      = 다중 상태 운송체
Manifest = Current·Superseded·Pending·Historical 관계지도
```

Package 안의 `DOI_PENDING`은 게시 전 동결상태이며, 외부 Zenodo Record는 게시 후 상태다. 두 상태를 삭제·병합하지 않고 Publication Transition으로 읽는다.

---

## 11. File Identity와 등록주소

Current Contract:

```text
00_manifest/7e317d73e0695187852ee80c4af5c175208be3833a9d6bef6f68c7e206a8e6a4.A.md
```

AI 인스턴스는 설명형 파일명이나 Framework `(숫자)` suffix만으로 객체를 선택하지 않는다.

### Runtime Source Object

```text
<64 lowercase SHA-256 of exact bytes>.<extension>
```

### HRTDB_A Seat-A Registered Object

```text
<64 lowercase SHA-256 of source body>.A.<extension>
```

- SHA-256은 Exact File Byte Identity다.
- `.A`는 Repository Seat A 등록표지다.
- Byte가 바뀌면 새 Hash와 새 File을 만든다.
- 기존 Hash-named Object는 덮어쓰지 않는다.
- 다운로드 과정에서 붙은 `(1)`, `(2)` 같은 suffix는 Transport Name이며 Canonical Identity에서 제외한다.

---

## 12. Operation과 Mutation Authority

원격 변경권한은 일반 Instance 역할과 분리한다.

```text
승이·gpt.logi 구조판정
→ 변경대상 File 생성
→ Exact Byte·Hash 검산
→ gpt.github 실행지시
→ Terminal Git 작업
→ Commit·Push
→ Remote Readback
→ Closure Evidence
```

금지경계:

```text
force push 금지
force-with-lease 금지
reset 금지
history rewrite 금지
branch recreation 금지
branch delete 금지
repository delete·recreate 금지
승인 없는 GitHub Web Edit 금지
Atomic Push 실패 시 non-atomic fallback 금지
```

자세한 Mutation Authority는 [`06_operation/MUTATION_AUTHORITY.md`](06_operation/MUTATION_AUTHORITY.md)를 따른다.

---

## 13. 현재 운영상태

```yaml
repository:
  name: HRTDB_A
  seat_code: A
  former_name: for_instance

rule_layer:
  name: for_instance
  state: ACTIVE

overall_coordination:
  fixed_seat: HRTDB_A::gpt.xyzt
  current_occupant: gpt.logi

track_db:
  canonical_document_candidates: 2
  phase2A_registration: REPORTED_PASS_PENDING_EXACT_CLOSURE_VERIFICATION

LRSDoNet_B:
  phase2AB_readme_only_minimalization: NOT_YET_COMPLETE

complete_referenceable_state:
  verdict: HOLD
```

다음 판정은 현재 선언하지 않는다.

```text
PASS_HRTDB_A_COMPLETE_REFERENCEABLE_STATE
```

최소 Complete State Gate:

```text
Seat·Runtime 역할 고정
Object Set 폐쇄
Member Byte·Hash 검산
Current·Superseded·Pending 분리
Track DB Document·Registry·Lineage 결속
Repository Commit·Tree·Remote Readback
Active_Schema 외부 게시 Address 결속
다음 System Interface 선언
Blocking·Unresolved 상태 보존
```

---

## 14. Repository 읽기 경로

1. [`00_manifest`](00_manifest/REPO_IDENTITY.md) — Repository Identity·Purpose·Current State·Boundary
2. [`File Object Identity Contract`](00_manifest/7e317d73e0695187852ee80c4af5c175208be3833a9d6bef6f68c7e206a8e6a4.A.md) — Hash Filename·Transport Suffix·A/B/C Seat
3. [`01_seat_model`](01_seat_model/README.md) — Seat·Instance·Occupation·X/Y/Z/T
4. [`gpt.xyzt`](01_seat_model/gpt.xyzt.md) — 고정 통합관제 Seat와 현재 Occupant
5. [`02_instance_registry`](02_instance_registry/README.md) — Instance·Capability Registry
6. [`03_relation_interface`](03_relation_interface/README.md) — Assignment Request·Response·Handoff
7. [`04_assignment`](04_assignment/README.md) — Assignment 객체와 예제
8. [`05_team_profiles`](05_team_profiles/README.md) — Generic Seat Profile
9. [`06_operation`](06_operation/ASSIGNMENT_METHOD.md) — 운영·Directive·Mutation 계약
10. `HRTDB_A@TrackDB:06_track_db/04_head/HEAD_INDEX.json` — Track DB 선택검색 Root Index
11. [`07_tests`](07_tests/README.md) — 구조·운영 무결성 Test
12. [`08_history`](08_history/README.md) — 변경·교정·Closure 계보
13. [`09_active_schema_binding`](09_active_schema_binding/README.md) — Zenodo·Active_Schema 접속표면

---

## 15. Relation Interface

기존 `for_instance` Assignment Interface는 유지한다.

- Request: [`03_relation_interface/instance_assignment_request.yaml`](03_relation_interface/instance_assignment_request.yaml)
- Response: [`03_relation_interface/instance_assignment_response.yaml`](03_relation_interface/instance_assignment_response.yaml)
- Handoff: [`03_relation_interface/instance_handoff.yaml`](03_relation_interface/instance_handoff.yaml)

Generic Assignment와 HRTDB Cycle Occupation은 같은 객체가 아니다.

```text
Generic Seat Profile Assignment
≠ HRTDB Cycle Occupation Assignment
≠ Overall Coordination Occupancy
≠ GitHub Execution Assignment
```

---

## 16. Non-Claims

이 Repository와 현재 README는 다음을 주장하지 않는다.

```text
Result.Data가 Track DB와 동일하다.
TrackDB Branch가 하나의 Track DB다.
여러 Track DB 문서가 하나의 DB 문서로 병합된다.
gpt.logi가 Hash DB 분석을 직접 수행한다.
gpt.think가 외부 Web Data를 HRTDB_A와 같은 방식으로 원천수집한다.
gpt.xyzt와 gpt.logi가 동일한 Identity다.
for_instance가 제거해야 할 Legacy 문자열이다.
현재 Phase 2AB Remote Closure가 완료되었다.
현재 HRTDB_A가 이미 Complete Referenceable State다.
```

---

## 17. 핵심 구조 요약

```text
External Web Data + AI-held Data
→ gpt.logi@HRTDB_A::gpt.xyzt
→ Result.Data
→ Track DB Document
→ GitHub HRTDB_A
→ gpt.think@LRSDoNet_B::gpt.xyzt
→ Result.Data
→ Hash DB Document
→ GitHub LRSDoNet_B
→ Future Source Data
```

```text
source precedes interpretation.
process precedes result.
result is next data.
relation is not merge.
relation is interconnecting.
structure is not isolate.
structure is relation processing.
```
