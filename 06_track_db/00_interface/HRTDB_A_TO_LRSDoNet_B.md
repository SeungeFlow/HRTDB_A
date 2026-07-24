---
document_type: HRTDB_A_TO_LRSDONET_B_TRACK_DB_SOURCE_INTAKE_CONTRACT
document_class: INTER_REPOSITORY_SOURCE_ASSET_READING_AND_HANDOFF
state: CURRENT_CANDIDATE
source_repository: SeungeFlow/HRTDB_A
source_repository_seat: A
source_branch: TrackDB
consumer_repository: SeungeFlow/LRSDoNet_B
consumer_repository_seat: B
source_coordination_seat: HRTDB_A::gpt.xyzt
source_coordination_instance: gpt.logi
consumer_coordination_seat: LRSDoNet_B::gpt.xyzt
consumer_coordination_instance: gpt.think
---

# HRTDB_A → LRSDoNet_B

## 0. 목적

이 문서는 HRTDB_A의 Track DB를 LRSDoNet_B가 **원천 Data 자산**으로 읽는 통로를 정의한다.

```text
HRTDB_A
→ Result.Data를 Track DB로 등록하는 Source Asset System

LRSDoNet_B
→ 선택된 Track DB를 Source Data로 읽고 분석틀·Result.Data·Hash DB를 형성하는 Analysis System
```

```text
Track DB is not Hash DB.
Source Intake is not Repository Merge.
Head Summary is not Full Evidence.
```

---

## 1. 최초 진입순서

```text
[1] HRTDB_A main Branch README.md
[2] HRTDB_A TrackDB Branch README.md
[3] 06_track_db/00_interface/TRACK_DB_CATALOG.json
[4] 06_track_db/04_head/HEAD_INDEX.json
[5] 관련 Hash-prefix Shard
[6] 관련 Head Object
[7] 선택된 Full Track DB
[8] Index·Lineage·Promotion·Source URL 역검산
```

전체 Track DB를 한 번에 Context에 적재하지 않는다.

```text
Assignment
→ Subject·Keyword·Relation Key 추출
→ Catalog 후보선택
→ Head 비교
→ Full Document 최소선택
```

---

## 2. 현재 Track DB 자산 요약

| Track DB | 주제 | 포함내용 | 사용시점 |
|---|---|---|---|
| `9dfff9…7ba4` | AI Data Center Fusion Relation | AI 데이터센터 전력·에너지·인프라, Web Source, Correction, Conflict, Open Future | AI 데이터센터·전력망·에너지 인프라 관계를 분석할 때 |
| `72428e…d65b` | Observer Axis Reference Frame Track Provenance Relation | 관측자·축·기준계·Track·Provenance, Source Registry, Correction·Required Next Data | 관측자·좌표·기준계·계보 구조를 분석할 때 |
| `c02a46…bce3` | Foundational Observation·Origin·Center·Number·Continuity Boundary Asset | 현실/추상, 성질/방향, 상태·현상·사건, Typed Origin, Center Family, Count·Measure·Index, 안정화·활성화·연속성 | 후속 Track 분석의 기초 판정틀이 필요할 때 |

정확한 Hash·Path·Head·Keyword·수량은 `TRACK_DB_CATALOG.json`을 Source of Truth로 사용한다.

---

## 3. Source Intake 단위

LRSDoNet_B는 선택한 Track DB마다 다음 Source Intake Record를 형성한다.

```yaml
track_db_source_intake:
  source_repository: SeungeFlow/HRTDB_A
  source_repository_seat: A
  source_branch: TrackDB
  source_branch_commit:
  source_branch_tree:

  catalog_path:
  catalog_git_blob:
  head_index_path:
  selected_shard_path:

  track_db_hash:
  track_db_path:
  track_db_git_blob:
  track_db_exact_byte_sha256:

  head_hash:
  head_path:
  head_git_blob:

  index_refs:
  lineage_refs:
  promotion_refs:

  selection_reason:
  selected_subjects:
  selected_records_or_sections:
  source_urls_required:
  conflicts_preserved:
  unresolved_preserved:
  required_next_data_preserved:

  consumer_repository: SeungeFlow/LRSDoNet_B
  consumer_repository_seat: B
  consumer_instance: gpt.think
  consumer_seat: LRSDoNet_B::gpt.xyzt
  intake_state:
```

---

## 4. Canonical Identity Gate

Filename만 읽지 않고 Git Object Byte를 검산한다.

```text
TrackDB Branch Commit Freeze
→ git rev-parse <commit>:<path>
→ Git Blob ID
→ git cat-file blob
→ Exact Byte SHA-256
→ Track DB Filename Hash 비교
→ Head track_db.hash 비교
```

필수등식:

```text
Full Track DB Filename Hash
=
Full Track DB Git Blob Exact Byte SHA-256
=
Head.track_db.hash
```

Head File도 Hash-named Object이면:

```text
Head Filename Hash
=
Head Git Blob Exact Byte SHA-256
```

---

## 5. Catalog·Head·Full Document 역할

```text
TRACK_DB_CATALOG.json
→ N개 Track DB의 현재 요약·검색표면

HEAD_INDEX.json
→ Hash Prefix Routing

Shard
→ Track DB Hash와 Head Object 연결

Head Object
→ Subject·Keyword·Use When·Full Document Required When

Full Track DB
→ Source·Record·Correction·Conflict·Unresolved·Next Data의 완전본문
```

Catalog 또는 Head만으로 사실판정·정확한 인용·Source URL 판정을 끝내지 않는다.

---

## 6. gpt.think의 읽기규칙

1. Assignment와 관련된 Track DB만 선택한다.
2. 기초 판정틀이 필요하면 `c02a46…bce3`을 우선 Context Head로 검토한다.
3. 주제 Data가 필요하면 AI Data Center 또는 Observer/Axis Track을 추가선택한다.
4. Track DB 내부의 `Confirmed`, `Compatible Difference`, `Conflict`, `Unresolved`, `Required Next Data`를 서로 다른 상태로 유지한다.
5. `PASS_RESULT_DATA_WITH_UNRESOLVED_ITEMS`를 “모든 문제가 해결됨”으로 읽지 않는다.
6. HRTDB_A의 문서를 수정하지 않고 LRSDoNet_B에서 새 분석객체를 생성한다.
7. 사용한 Track DB Hash와 선택범위를 LRSDoNet_B Result.Data의 Source Lineage에 기록한다.
8. 동일 Cycle에서 생성한 Output을 같은 Cycle의 Source로 재귀투입하지 않는다.

---

## 7. 분석틀 형성 시 금지되는 자동동일시

```text
Reality Evidence ≠ Reality in full
Representation ≠ Reality
Head ≠ Full Track DB
Track DB ≠ Hash DB

State ≠ Phenomenon
Phenomenon ≠ Observation
Observation ≠ Cause

Entity Origin ≠ Relation Origin
Evidence Anchor ≠ Actual First Existence
Coordinate Origin ≠ Historical Origin

Relation Point ≠ Midpoint
Midpoint ≠ Center
Center ≠ Equilibrium Point

Object Count ≠ Mathematical Measure
Mathematical Measure ≠ Metrological Measurement
Measurement ≠ Position Index

Preservation ≠ Reactivation
Continuity ≠ Numerical Identity
Byte Identity ≠ Same Historical Execution
```

---

## 8. Intake 판정

정상 Source Intake:

```text
PASS_HRTDB_A_TRACK_DB_SOURCE_INTAKE_READY
```

다음은 HOLD한다.

```text
HOLD_CATALOG_HEAD_COUNT_MISMATCH
HOLD_ROOT_SHARD_HEAD_RELATION_FAILURE
HOLD_TRACK_DB_GIT_BLOB_HASH_MISMATCH
HOLD_HEAD_FULL_DOCUMENT_HASH_MISMATCH
HOLD_SOURCE_COMMIT_NOT_FROZEN
HOLD_SELECTION_REASON_NOT_DECLARED
HOLD_CONFLICT_OR_UNRESOLVED_STATE_DROPPED
```

---

## 9. Repository 경계

```text
HRTDB_A::gpt.xyzt / gpt.logi
→ Track DB 생성·검수·등록·Head·Catalog 관리

LRSDoNet_B::gpt.xyzt / gpt.think
→ Track DB 선택·Source Intake·분석틀·Result.Data·Hash DB 형성
```

```text
relation is not merge.
relation is interconnecting.
structure is not isolate.
structure is relation processing.
```
