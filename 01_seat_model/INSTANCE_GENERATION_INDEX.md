---
document_type: INSTANCE_GENERATION_INDEX
document_class: AI_INSTANCE_SEAT_ENTRY_ROUTER
state: CURRENT_CANDIDATE
repository: SeungeFlow/HRTDB_A
repository_seat_code: A
branch: main
position: 01_seat_model
primary_reader: AI_INSTANCE
source_authority: 승이
overall_coordination_seat: HRTDB_A::gpt.xyzt
current_state_source: 00_manifest/CURRENT_STATUS.yaml
repository_identity_source: 00_manifest/REPO_IDENTITY.md
execution_authority: NONE
contract_version: 2.0.0
---

# Instance Generation Index

이 문서는 HRTDB_A에 진입한 AI 인스턴스가 **자신의 이름에 대응하는 고정 Seat 문서를 찾고 역할정렬을 시작하기 위한 Entry Router**다.

```text
Index Read
→ Matching Seat File Resolution
→ Seat·Role Alignment
→ Current State·Assignment·Directive Resolution
→ READY_FOR_ASSIGNED_WORK
```

이 Index 자체는 Stage를 실행하지 않으며, 원격 Mutation을 승인하지 않는다.

---

## 0. Entry Contract

현재 AI 인스턴스는 외부에서 부여받은 자신의 이름을 먼저 고정한다.

```text
Current Instance Name
→ Exact Name Match
→ Matching Seat Entry
```

다음을 추측하지 않는다.

```text
비슷한 이름
부분 일치
차원 수만 같은 Seat
이전 대화에서 사용된 이름
다른 Repository의 동일한 Seat 이름
```

정확히 일치하는 Seat Entry가 없으면:

```text
HOLD_SEAT_ENTRY_NOT_FOUND
```

를 표시하고 실행하지 않는다.

---

## 1. 이 Index가 생성하는 것과 생성하지 않는 것

```text
이 Index가 제공하는 것
→ 현재 인스턴스가 읽어야 할 Seat 주소
→ 고정 Seat·Role 진입경로
→ 다음 Required Reading
→ 실행 전 정지조건
```

```text
이 Index가 생성하지 않는 것
→ Runtime Instance 자체
→ 이전 Instance Memory 복구
→ Active Directive
→ Stage 실행권한
→ Git Mutation 권한
```

Seat 파일을 읽는 행위는 현재 인스턴스 안에 **역할정렬 상태**를 형성하지만, 과거의 같은 이름을 가진 인스턴스를 복원하지 않는다.

```text
same name
≠ same runtime object

same seat
≠ same occupant

same URL
≠ restored prior context
```

---

## 2. Canonical Seat Entry Table

Branch 기반 Web·Raw 주소는 Current Entry용 가변주소다. Closure Evidence에는 Commit SHA가 고정된 주소를 사용한다.

### 2.1 1d Data Seats

| Instance Name | Fixed Seat | Dimension | Primary Occupation | Web Entry | Raw Entry |
|---|---|---|---|---|---|
| `gpt.x` | `HRTDB_A::gpt.x` | `1d(x)` | `DATA_X` | https://github.com/SeungeFlow/HRTDB_A/blob/main/01_seat_model/gpt.x.md | https://raw.githubusercontent.com/SeungeFlow/HRTDB_A/main/01_seat_model/gpt.x.md |
| `gpt.y` | `HRTDB_A::gpt.y` | `1d(y)` | `DATA_Y` | https://github.com/SeungeFlow/HRTDB_A/blob/main/01_seat_model/gpt.y.md | https://raw.githubusercontent.com/SeungeFlow/HRTDB_A/main/01_seat_model/gpt.y.md |
| `gpt.z` | `HRTDB_A::gpt.z` | `1d(z)` | `DATA_Z` | https://github.com/SeungeFlow/HRTDB_A/blob/main/01_seat_model/gpt.z.md | https://raw.githubusercontent.com/SeungeFlow/HRTDB_A/main/01_seat_model/gpt.z.md |

### 2.2 2d Function Seats

| Instance Name | Fixed Seat | Dimension | Sequential Occupations | Web Entry | Raw Entry |
|---|---|---|---|---|---|
| `gpt.xy` | `HRTDB_A::gpt.xy` | `2d(x,y)` | `FUNCTION_1_XY`, `FUNCTION_2_XY` | https://github.com/SeungeFlow/HRTDB_A/blob/main/01_seat_model/gpt.xy.md | https://raw.githubusercontent.com/SeungeFlow/HRTDB_A/main/01_seat_model/gpt.xy.md |
| `gpt.xz` | `HRTDB_A::gpt.xz` | `2d(x,z)` | `FUNCTION_1_XZ`, `FUNCTION_2_XZ` | https://github.com/SeungeFlow/HRTDB_A/blob/main/01_seat_model/gpt.xz.md | https://raw.githubusercontent.com/SeungeFlow/HRTDB_A/main/01_seat_model/gpt.xz.md |
| `gpt.yz` | `HRTDB_A::gpt.yz` | `2d(y,z)` | `FUNCTION_1_YZ`, `FUNCTION_2_YZ` | https://github.com/SeungeFlow/HRTDB_A/blob/main/01_seat_model/gpt.yz.md | https://raw.githubusercontent.com/SeungeFlow/HRTDB_A/main/01_seat_model/gpt.yz.md |

### 2.3 3d Result Seat

| Instance Name | Fixed Seat | Dimension | Sequential Occupations | Web Entry | Raw Entry |
|---|---|---|---|---|---|
| `gpt.xyz` | `HRTDB_A::gpt.xyz` | `3d(x,y,z)` | `RESULT_XYZ`, `RESULT_DATA_XYZ` | https://github.com/SeungeFlow/HRTDB_A/blob/main/01_seat_model/gpt.xyz.md | https://raw.githubusercontent.com/SeungeFlow/HRTDB_A/main/01_seat_model/gpt.xyz.md |

### 2.4 4d Overall Coordination Seat

| Fixed Seat Name | Qualified Seat | Dimension | Role | Current Occupant Source | Web Entry | Raw Entry |
|---|---|---|---|---|---|---|
| `gpt.xyzt` | `HRTDB_A::gpt.xyzt` | `4d(x,y,z,t)` | `OVERALL_COORDINATION` | `00_manifest/CURRENT_STATUS.yaml` | https://github.com/SeungeFlow/HRTDB_A/blob/main/01_seat_model/gpt.xyzt.md | https://raw.githubusercontent.com/SeungeFlow/HRTDB_A/main/01_seat_model/gpt.xyzt.md |

```text
gpt.x ~ gpt.xyz
→ 7 analytic instance seats

gpt.xyzt
→ 1 overall coordination seat
→ analytic instance member가 아님
```

현재 `gpt.xyzt` 점유자 이름은 이 Index에 고정하지 않는다. `00_manifest/CURRENT_STATUS.yaml`에서 확인한다.

---

## 3. Current Instance Name Resolution

### 3.1 분석 Instance

```text
현재 이름이 gpt.x
→ gpt.x.md만 자신의 Seat Contract로 읽음

현재 이름이 gpt.xy
→ gpt.xy.md만 자신의 Seat Contract로 읽음

현재 이름이 gpt.xyz
→ gpt.xyz.md만 자신의 Seat Contract로 읽음
```

다른 Seat 문서는 Context가 될 수 있으나 자신의 Role Contract로 병합하지 않는다.

### 3.2 Overall Coordination Instance

현재 이름이 `gpt.logi`이고 Current State가 다음을 결속할 때:

```yaml
current_occupant: gpt.logi
fixed_seat: HRTDB_A::gpt.xyzt
```

진입경로는 다음이다.

```text
gpt.logi
→ 00_manifest/CURRENT_STATUS.yaml
→ 01_seat_model/gpt.xyzt.md
→ HRTDB_A::gpt.xyzt Overall Coordination
```

```text
gpt.logi
≠ gpt.xyzt

gpt.logi
→ current occupant

gpt.xyzt
→ fixed seat
```

### 3.3 이름이 Index에 없는 실행·전달 Instance

`gpt.github`와 같이 이 Index의 분석·통합관제 Seat 집합에 포함되지 않는 인스턴스는 이름을 유사 Seat에 임의 배치하지 않는다.

```text
Instance Registry
→ Approved Handoff
→ Mutation Authority
```

경로로 역할을 확인한다.

---

## 4. Canonical Processing Flow

```text
01 gpt.x  / DATA_X
02 gpt.y  / DATA_Y
03 gpt.z  / DATA_Z

04 gpt.xy / FUNCTION_1_XY
05 gpt.xz / FUNCTION_1_XZ
06 gpt.yz / FUNCTION_1_YZ

07 gpt.xyz / RESULT_XYZ

08 gpt.xy / FUNCTION_2_XY
09 gpt.xz / FUNCTION_2_XZ
10 gpt.yz / FUNCTION_2_YZ

11 gpt.xyz / RESULT_DATA_XYZ
```

그 후:

```text
Analytic Outputs
→ gpt.logi@HRTDB_A::gpt.xyzt
→ Integration·Verification
→ gpt.logi Result.Data
→ Promotion Gate
→ Track DB Document
```

```text
11 Sequential Occupations
≠ 11 Simultaneously Active Directives
```

---

## 5. Seat Entry 후 Required Reading

### 5.1 공통

```text
Matching Seat File
→ 00_manifest/CURRENT_STATUS.yaml
→ Current Assignment
→ Current Operation Object
→ Direct Input Set
→ Context-only Set
→ Output Contract
→ 07_tests
```

### 5.2 `gpt.logi`

```text
00_manifest/REPO_IDENTITY.md
→ 00_manifest/CURRENT_STATUS.yaml
→ 01_seat_model/gpt.xyzt.md
→ 06_operation/
→ Track DB Registry·Lineage·Closure
→ 09_active_schema_binding/
→ 08_history/ latest directed difference
```

### 5.3 분석 Instance

```text
Own Seat File
→ Current Assignment
→ Direct Input
→ Context-only Input
→ Current Individual Directive
→ Output Contract
→ Tests
→ Handoff
```

---

## 6. Execution Gate

Seat Entry는 실행이 아니다.

```text
Seat File Read
≠ Stage Execution

Seat Alignment
≠ Active Directive

Role Resolution
≠ Mutation Authority
```

실행 전 다음을 모두 확인한다.

```yaml
execution_gate:
  instance_name_resolved:
  fixed_seat_resolved:
  role_resolved:
  current_state_resolved:
  current_assignment_resolved:
  direct_input_set_resolved:
  context_only_set_resolved:
  active_directive_count:
  output_contract_resolved:
  anomaly_state_displayed:
  mutation_authority_resolved:
  next_safe_action_resolved:
```

```text
active_directive_count ∈ {0, 1}
```

`2 이상`이면 실행하지 않는다.

---

## 7. HOLD Conditions

다음 상태에서는 `READY_FOR_ASSIGNED_WORK`를 표시하지 않는다.

```text
Current Instance Name이 Exact Match되지 않음
Fixed Seat 문서가 존재하지 않음
Repository Identity가 HRTDB_A / Seat A와 결속되지 않음
Seat Contract와 CURRENT_STATUS가 충돌함
Seat와 Occupant가 병합됨
Current Assignment가 없음
Direct Input과 Context-only Input이 분리되지 않음
Active Directive가 2개 이상임
Current·Pending·Superseded·Historical 상태가 혼합됨
필수 Hash가 불일치함
Mutation Authority가 확인되지 않음
```

판정:

```text
HOLD_BOOTSTRAP_ALIGNMENT
```

---

## 8. Alignment Output Contract

Seat Entry와 Required Reading을 마친 인스턴스는 다음을 표시한다.

```yaml
instance_alignment_result:
  repository: SeungeFlow/HRTDB_A
  repository_seat: A
  instance_name:
  fixed_seat:
  dimension_property:
  role:
  current_occupation:
  current_state:
  direct_input_set:
  context_only_set:
  active_directive_count:
  anomaly_state:
  mutation_authority:
  output_contract:
  next_safe_action:
  readiness:
```

모든 Gate가 통과했을 때만:

```text
readiness: READY_FOR_ASSIGNED_WORK
```

를 표시한다.

---

## 9. Address and Readback Rule

Current Entry:

```text
https://github.com/SeungeFlow/HRTDB_A/blob/main/...
https://raw.githubusercontent.com/SeungeFlow/HRTDB_A/main/...
```

Closure Evidence:

```text
https://github.com/SeungeFlow/HRTDB_A/blob/<commit-sha>/...
https://raw.githubusercontent.com/SeungeFlow/HRTDB_A/<commit-sha>/...
```

Branch Web·Raw 표면은 변경 직후 일시적인 전파시간 차이가 생길 수 있다. 완료판정은 다음을 우선한다.

```text
Remote Ref
→ Commit
→ Tree
→ Blob
→ Exact Byte
→ Fresh Readback
→ Branch Web·Raw convergence
```

---

## 10. Guard

```text
source precedes interpretation.
process precedes result.
result is next data.

relation is not merge.
relation is interconnecting.

structure is not isolate.
structure is relation processing.
```

---

## 11. Non-Claims

이 Index는 다음을 주장하지 않는다.

```text
URL을 읽으면 과거 Instance Memory가 복원된다.
Seat Entry만으로 Stage가 실행된다.
gpt.xyzt가 7개 분석 Instance 중 하나다.
gpt.logi와 gpt.xyzt가 동일 Identity다.
11개 Occupation을 한 번에 활성화한다.
Branch 주소가 Closure Evidence다.
이 Index가 Current State 정본이다.
이 Index가 Git Mutation을 승인한다.
```


---

## 12. Mandatory File Identity and Track DB Retrieval Contracts

```text
File Object Identity
→ 00_manifest/7e317d73e0695187852ee80c4af5c175208be3833a9d6bef6f68c7e206a8e6a4.A.md

gpt.logi Track DB Retrieval
→ HRTDB_A@TrackDB:06_track_db/04_head/HEAD_INDEX.json
→ Relevant Prefix Shard
→ Relevant Head Object
→ Selected Full Track DB
```

Framework `(숫자)` suffix 또는 설명형 Filename만으로 입력을 선택하지 않는다.
