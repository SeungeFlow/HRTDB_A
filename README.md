# HRTDB_A Track DB Source Surface

이 Branch는 HRTDB_A가 등록한 문서형 Track DB와 그 탐색·계보·Promotion 객체를 보관한다.

```text
One Track DB
=
One Registered Result.Data Document
```

## HRTDB_A → LRSDoNet_B

`LRSDoNet_B::gpt.xyzt`의 `gpt.think`가 Track DB를 원천 Data로 읽을 때 다음 순서를 사용한다.

```text
README.md
→ 06_track_db/00_interface/HRTDB_A_TO_LRSDoNet_B.md
→ 06_track_db/00_interface/TRACK_DB_CATALOG.json
→ 06_track_db/04_head/HEAD_INDEX.json
→ Relevant Shard
→ Relevant Head
→ Selected Full Track DB
```

Current Stable Entry:

- [`HRTDB_A_TO_LRSDoNet_B.md`](06_track_db/00_interface/HRTDB_A_TO_LRSDoNet_B.md)
- [`TRACK_DB_CATALOG.json`](06_track_db/00_interface/TRACK_DB_CATALOG.json)
- [`HEAD_INDEX.json`](06_track_db/04_head/HEAD_INDEX.json)
- [`Head Retrieval Contract`](06_track_db/04_head/contracts/cf7dcf65f3732777db4920563cd2f344e607540914bc226eac180ec0890f8deb.A.md)

## Dual Track DB Routes

### Rotation–Axis Relation Structure

- Title: Rotation–Axis Relation Structure
- Subject ID: `ROTATION_AXIS_RELATION_STRUCTURE`
- Exact Track DB Hash: `d11bd436902979cf4c5db1ace6f21887be1d3b29b3983e890f75304e0a7face2`
- Exact Body: [`d11bd436...A.md`](06_track_db/01_result_data/d11bd436902979cf4c5db1ace6f21887be1d3b29b3983e890f75304e0a7face2.A.md)
- Exact Index: [`bd6d054a...A.json`](06_track_db/02_index/bd6d054a19a60e0a3b67f588472131ff311403870e9bf71adfab685febe183ef.A.json)
- Exact Head: [`75e1b15e...A.json`](06_track_db/04_head/objects/75e1b15e38074ce5fe437a393f8f074bd2ee4bedddf6941cdd56e8191308bfbd.A.json)
- Promotion: `PASS_TRACK_DB_PROMOTION_ELIGIBLE_WITH_UNRESOLVED_ITEMS`
- Unresolved Items Present: `true`

### U.S. Equity Index Futures–Cash Opening Price State

- Title: U.S. Equity Index Futures–Cash Opening Boundary: Session, Auction, and Price-state Formation
- Subject ID: `US_EQUITY_INDEX_FUTURES_CASH_OPENING_PRICE_STATE`
- Exact Track DB Hash: `1523d068820c1ca704d3a23cc86b7fb1e3d62711c5646c3afef3b4ab84928c88`
- Exact Body: [`1523d068...A.md`](06_track_db/01_result_data/1523d068820c1ca704d3a23cc86b7fb1e3d62711c5646c3afef3b4ab84928c88.A.md)
- Exact Index: [`14354c1b...A.json`](06_track_db/02_index/14354c1bb3e470cf89e93950a6ba625a993df9ae00edaefdb102e8ec6f9ffeb5.A.json)
- Exact Head: [`f30be95b...A.json`](06_track_db/04_head/objects/f30be95b349cb0f60c7fc4ca31ecd8b72124df295a820d61a0d57cc93147beff.A.json)
- Promotion: `PASS_TRACK_DB_PROMOTION_ELIGIBLE_WITH_UNRESOLVED_ITEMS`
- Unresolved Items Present: `true`

```text
Catalog ≠ Track DB
Head ≠ Track DB
Track DB ≠ Hash DB
Source Intake ≠ Repository Merge
relation is not merge.
```

---

## Inherited Repository Alignment Context

아래 내용은 원격 `TrackDB/README.md`에 존재하던 Repository Alignment Context다.

```text
Predecessor Git Blob Exact Byte SHA-256:
57e213f8402f0e3fc9df3f07029e6fd57336fbc7ff6d0f822444eb0e56db1b63
```

새 Track DB 진입경로를 앞에 추가하되, 아래의 기존 4,287바이트는 삭제·요약·재작성하지 않고 원문 Byte 순서대로 보존한다.

# for_instance

`for_instance`는 AI Instance를 현재 작업의 기능 자리(Seat)에 정렬하고,
Relation의 Function Requirement를 실제 Instance Assignment로 연결하는 저장소다.

## Relation과의 분리

- Relation은 Function과 Requirement를 정의한다.
- for_instance는 Requirement를 수행할 Instance와 Seat Profile을 배정한다.
- Relation 원본, DB Seed, 9Dot0 자료, SeungeFlow 역사자료는 저장하지 않는다.

## Function · Instance · Seat

- **Function**: 수행할 Method 계약
- **Instance**: 실제 실행주체
- **Seat**: 현재 작업에서 Instance에 배정되는 기능자리
- 하나의 Instance는 하나 이상의 Seat를 점유할 수 있다.

## X · Y · Z · T

- X — Source_Input
- Y — Relation_Interpretation
- Z — Structure_Verification
- T — Time_Process_Transition

T는 git이 아니다. git은 선택 Adapter다.

## 15개 Seat Profile

X, Y, Z, T, XY, XZ, XT, YZ, YT, ZT, XYZ, XYT, XZT, YZT, XYZT

## 첫 사용 경로

1. [00_manifest](00_manifest/REPO_IDENTITY.md)
2. [01_seat_model](01_seat_model/README.md)
3. [02_instance_registry](02_instance_registry/README.md)
4. [03_relation_interface](03_relation_interface/README.md)
5. [04_assignment](04_assignment/README.md)
6. [05_team_profiles](05_team_profiles/README.md)
7. [06_operation](06_operation/ASSIGNMENT_METHOD.md)
8. [07_tests](07_tests/README.md)

## Relation 요청과 for_instance 응답

- 요청: `03_relation_interface/instance_assignment_request.yaml`
- 응답: `03_relation_interface/instance_assignment_response.yaml`
- Handoff: `03_relation_interface/instance_handoff.yaml`

## Mutation Authority

원격 변경권한은 Instance의 일반 역할과 분리한다.
승인되지 않은 원격 mutation은 금지하며,
`06_operation/MUTATION_AUTHORITY.md`를 기준으로 기록한다.

## 실제 예제

- Single X: `04_assignment/examples/single_X.yaml`
- Dual XY: `04_assignment/examples/dual_XY.yaml`
- Triple XYZ: `04_assignment/examples/triple_XYZ.yaml`
- Full XYZT: `04_assignment/examples/full_XYZT.yaml`

<!-- ACTIVE_SCHEMA_V2_BINDING_START -->
## Active_Schema Version 2.0.0 System Binding

- Version DOI: https://doi.org/10.5281/zenodo.21453793
- Exact ZIP SHA-256: `0b0317dadfd333c151c9b3f5e4c930d048c76e39fe037914f01ae9767c6d2b30`
- Binding: `09_active_schema_binding/versions/2.0.0/`
- Seat projection: `01_seat_model/active_schema_v2/`
- Operation projection: `06_operation/active_schema_v2/`
- Full body mirror: `SeungeFlow/Relation@main:06_active_schema/releases/2.0.0/Active_Schema/`

The full Active_Schema body and Track DB payloads are not stored in for_instance.
<!-- ACTIVE_SCHEMA_V2_BINDING_END -->

<!-- HRTDB_SEAT_STATE_DIRECTIVE_EXTENSION_START -->
## HRTDB Seat-State-Directive Extension

```text
for_instance
=
Seat + Instance + Capability + Assignment + Handoff + Mutation Authority + History
를 결속하는 AI Instance Alignment Repository
```

```text
공통지시문
→ 최소 공통문법·Guard·Identity 계약
→ 단독 실행지시문이 아님

개별 인스턴스 지시문
→ 수신자 1
→ Seat 1
→ Stage 1
→ Occupation 1
→ 현재 상태값 1
→ 직접 입력집합 1
→ 출력계약 1

Cycle Manifest
→ 주제·순서·완료·HOLD 기록
→ 실행지시문이 아님
```

```text
문서 업로드·인덱싱
→ READY_FOR_DIRECTIVE
→ 개별지시문 1개
→ 출력
→ 특이점 표시
→ gpt.xyzt Gate
→ 다음 지시문 1개
```
<!-- HRTDB_SEAT_STATE_DIRECTIVE_EXTENSION_END -->

<!-- HRTDB_A_ROOT_DEFINITION_START -->
## HRTDB_A

```text
HRTDB
=
Track DB 기반 지식자산 형성 DB Engine
```

```yaml
repository_seat:
  code: A
  current_name: HRTDB_A
  given_name: HRTDB
  family_name_seat_code: A
  former_name: for_instance
  inherited_across_repository_rename: true
  seat_code_is_immutable: true
```

```text
1d → 2d → 3d → 2d → 3d
Data → Function → Result → Function → Result.Data
Result.Data → 등록 Gate → Track DB
```

```text
Track DB is not Hash DB.
Knowledge Asset is not Analysis Asset.
```

```text
LRSDoNet_B → Hash DB 분석·응용 DB System
Principle_C → 구조원리·공통문법·분석기준 Data자산
```

```text
Canonical Exact Object Filename:
<sha256>.A.<extension>
```
<!-- HRTDB_A_ROOT_DEFINITION_END -->
