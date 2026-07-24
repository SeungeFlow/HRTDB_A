---
document_type: REPOSITORY_IDENTITY_CONTRACT
document_class: STABLE_AI_INSTANCE_OPERATING_WORKSPACE_IDENTITY
state: CURRENT
repository: SeungeFlow/HRTDB_A
repository_seat_code: A
primary_reader: AI_INSTANCE
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

workspace:
  class: AI_INSTANCE_OPERATING_WORKSPACE
  primary_reader: AI_INSTANCE
  human_role:
    - EXTERNAL_DESIGN
    - APPROVAL
    - EXECUTION
    - INSTANCE_HANDOFF

repository_system:
  role: TRACK_DB_KNOWLEDGE_ASSET_ENGINE
  primary_output_class: TRACK_DB_DOCUMENT
  database_unit_contract: ONE_DATABASE_EQUALS_ONE_REGISTERED_RESULT_DATA_DOCUMENT

internal_rule_layer:
  name: for_instance
  role: INSTANCE_SEAT_ROLE_ASSIGNMENT_AND_ALIGNMENT
  state: ACTIVE

overall_coordination:
  fixed_seat: HRTDB_A::gpt.xyzt
  role: RESULT_DATA_TO_TRACK_DB_PROMOTION_AND_REFERENCE_HANDOFF
  current_occupant_source: 00_manifest/CURRENT_STATUS.yaml

canonical_control_surfaces:
  bootstrap_entry: README.md
  current_state: 00_manifest/CURRENT_STATUS.yaml
  seat_resolution_index: 01_seat_model/INSTANCE_GENERATION_INDEX.md
  mutation_authority: 06_operation/MUTATION_AUTHORITY.md
  history: 08_history/
  active_schema_binding: 09_active_schema_binding/
```

## Identity Boundaries

```text
HRTDB_A
≠ for_instance

HRTDB_A
→ Repository Seat A의 Track DB 지식자산 Engine

for_instance
→ HRTDB_A 내부의 Instance 자리·역할·배정·정렬 규칙층
```

```text
Repository Seat A
≠ gpt.xyzt Seat
≠ gpt.logi Runtime Instance
```

```text
A
→ Repository 이름과 Tree가 바뀌어도 승계되는 고정자리값

HRTDB_A::gpt.xyzt
→ Overall Coordination 고정 Seat

gpt.logi
→ CURRENT_STATUS에서 확인하는 현재 Runtime Occupant
```

## Database Unit Contract

```text
One Track DB
=
One Database-character Document
```

```text
TrackDB Branch
≠ One Track DB

Directory
≠ One Track DB

Aggregate Index
≠ One Track DB
```

Branch와 Directory는 Track DB 문서를 보관하는 저장표면이며, Index는 여러 Track DB 문서를 찾는 Registry다.

## Cross-Repository Boundary

```yaml
repository_seats:
  A:
    repository: HRTDB_A
    role: TRACK_DB_KNOWLEDGE_ASSET_ENGINE

  B:
    repository: LRSDoNet_B
    role: HASH_DB_ANALYSIS_AND_APPLICATION_SYSTEM

  C:
    repository: Principle_C
    role: PRINCIPLE_AND_CRITERION_ASSET_FIELD
```

```text
gpt.logi
→ External Web Data + AI-held Data + verified prior GitHub assets
→ Result.Data
→ Track DB Document

gpt.think
→ Track DB Document
→ Result.Data
→ Hash DB Document
```

## Non-Claims

이 Identity Contract는 다음을 주장하지 않는다.

```text
현재 Occupant가 영구적으로 gpt.logi다.
Result.Data가 Track DB와 동일하다.
TrackDB Branch가 하나의 Track DB다.
for_instance가 제거해야 할 Legacy 문자열이다.
README가 Current State 정본이다.
Repository Identity가 실행지시문이다.
```

## Required Reading

```text
README.md
→ 00_manifest/REPO_IDENTITY.md
→ 00_manifest/CURRENT_STATUS.yaml
→ 01_seat_model/INSTANCE_GENERATION_INDEX.md
→ 자신의 Seat 문서
```


## Mandatory Structural Contracts

```text
File Object Identity
→ 00_manifest/7e317d73e0695187852ee80c4af5c175208be3833a9d6bef6f68c7e206a8e6a4.A.md

Track DB Head·Context Head
→ HRTDB_A@TrackDB:06_track_db/04_head/contracts/cf7dcf65f3732777db4920563cd2f344e607540914bc226eac180ec0890f8deb.A.md

Track DB Head Root Index
→ HRTDB_A@TrackDB:06_track_db/04_head/HEAD_INDEX.json
```
