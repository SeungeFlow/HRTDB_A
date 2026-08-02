---
document_type: REPOSITORY_IDENTITY_CONTRACT
document_class: HRTDB_INSTANCE_OPERATING_SYSTEM_IDENTITY
state: CURRENT
repository: SeungeFlow/HRTDB_A
repository_seat_code: A
source_authority: 승이
execution_authority: NONE
---
# Repository Identity — HRTDB_A

```yaml
repository:
  owner: SeungeFlow
  current_name: HRTDB_A
  qualified_name: SeungeFlow/HRTDB_A
  fixed_seat_code: A
  former_name: for_instance
  default_branch: main

system:
  class: HRTDB_INSTANCE_BASED_OPERATING_SYSTEM
  role: THREE_CYCLE_TRACK_DB_FORMATION_AND_REFERENCE_ENGINE
  primary_output_class: TRACK_DB_ACTIVE_SCHEMA_ZIP

internal_rule_layer:
  name: for_instance
  role: INSTANCE_SEAT_OCCUPATION_ASSIGNMENT_AND_ALIGNMENT
  state: ACTIVE

overall_coordination:
  fixed_seat: HRTDB_A::gpt.xyzt
  current_occupant: gpt.logi
  current_occupant_name_immutable: true
```

## Identity Boundary

```text
HRTDB_A
→ Repository Seat A의 HRTDB 운영·Track DB 형성 System

for_instance
→ HRTDB_A 내부의 Seat·Instance·Occupation·Authority 규칙층
```

```text
Repository Seat A ≠ HRTDB_A::gpt.xyzt ≠ gpt.logi
```

## Database Contract

```text
Token.Data
→ 한 Process의 Exact SHA-256 ZIP

Token DB
→ 한 Cycle의 검수된 Token.Data 관계계

Track DB
→ 3-Cycle Token DB + Reference Axis + Evidence·Gap·Validation을 담은 Active_Schema ZIP
```

```text
One Registered Result.Data Document ≠ Current Track DB
One Markdown Document ≠ Current Track DB
Track DB Identity = Outer ZIP Exact-byte SHA-256
```

기존 TrackDB Branch의 Hash-named MD·Index·Head·Closure는 이전 계약과 History의 자산으로 보존한다. 현재 계약으로 보이게 덮어쓰지 않고 Current Canonical 문서에서 경계를 명시한다.

## Operating Instances

```yaml
immutable_names:
  - gpt.logi
  - gpt.work
  - gpt.think
  - gpt.github
```

- `gpt.logi`: HRTDB Overall Coordination
- `gpt.work`: External Observation·Data Intake
- `gpt.github`: Approved GitHub Implementation
- `gpt.think`: Downstream Overall Coordination

## Canonical Control Surfaces

```yaml
bootstrap_entry: README.md
current_state: 00_manifest/CURRENT_STATUS.yaml
seat_resolution_pointer: 01_seat_model/INSTANCE_GENERATION_INDEX.md
overall_seat_contract: 01_seat_model/gpt.xyzt.md
current_summary: 01_seat_model/active_schema_v2/SEAT_SYSTEM_SUMMARY.md
intro_entry_router: SeungeFlow/Intro@main:01_entry/INSTANCE_GENERATION_INDEX.md
```

```text
relation is not merge.
relation is interconnecting.
```
