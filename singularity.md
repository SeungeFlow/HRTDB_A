# HRTDB_A Singularity Register

```yaml
repository: SeungeFlow/HRTDB_A
branch: main
document_role: SINGULARITY_AND_RULE_BOUNDARY_REGISTER
state: ACTIVE
record_policy: APPEND_ONLY
source_authority: 승이
coordination_authority: gpt.logi
created_at: 2026-08-03T21:54:00+09:00
```

이 문서는 HRTDB_A의 진행 중 발견된 특이점과 그에 따른 경계판정·해결사항·후속 Rule을 기록한다.

특이점은 단순 오류목록이 아니다. 이미 진행 중인 구조가 기존 Rule로는 안전하게 설명되지 않거나, 객체 Identity·전달경계·역할경계·진행방향을 다시 고정해야 하는 중대한 지점이다.

---

## 1. Rule 불변성 원칙

```text
Rule은 과정 시작 전에 고정한다.
과정이 시작된 뒤에는 그 과정 도중 Rule을 변경하지 않는다.
```

Rule 변경이 필요한 특이점이 발견되면 다음 순서를 따른다.

```text
특이점 발견
→ 현재 Mutation 정지
→ 실제 Byte·Hash·Lineage·State 증거 고정
→ 현재 과정의 Rule을 소급 변경하지 않음
→ 현재 과정을 기존 Rule로 종결하거나 명시적으로 HOLD·Close
→ 다음 Successor 과정의 시작경계에서 새 Rule 적용
→ singularity.md에 판정과 적용시점 기록
```

### 1.1 소급변경 금지

새 Rule은 이미 생성·실행된 과거 객체를 다시 정의하거나 과거 계보를 고쳐 쓰지 않는다.

```text
Historical Object
→ 당시 Rule과 실제 Byte를 그대로 보존

Successor Object
→ 새 Rule을 적용하여 새 Hash와 새 Lineage로 생성
```

### 1.2 공통지시문 노출 금지

대상 객체가 여러 지시문 중 자신의 부분만 선택하도록 요구하지 않는다.

```text
공통지시문을 입력받음
→ 선택하지 않은 내용도 Context에 들어옴
→ 읽지 않으려 해도 이미 알려진 상태가 됨
```

따라서 다음 방식은 신규 작업에서 금지한다.

```text
여러 대상의 지시문을 하나의 ZIP에 넣기
여러 파일 중 자신에게 맞는 것을 찾아 읽게 하기
다른 대상 지시문은 인덱싱만 하라고 지시하기
공통 Manifest로 여러 대상을 동시에 결속하기
```

대상별 지시는 대상별 독립 Token으로 전달한다.

---

# Singularity S-001 — Hash-named ZIP의 후행 변경

```yaml
singularity_id: HRTDB_A-S-001
detected_at: 2026-08-03
scope: C03_CYCLE3_2D_XZ_DIRECTIVE
state: RESOLVED
track_db_rebuild_required: false
registry_revision_required: false
```

## 2. 발견된 현상

Track DB Registry의 Cycle 3 No.15 정본은 다음 객체다.

```yaml
cycle: 3
order: 15
role: GPT_XZ_CYCLE3_2D_DIRECTIVE
sha256: 6c1291a014df47dbc83204f299761b6ebc04ae0a026d5f576d52d514c9b86da3
bytes: 6343
member_count: 2
```

정본 내부는 정확히 다음 두 Member로 구성된다.

```text
1022301bc3da7b8e57b26b19483b82e31f472ef230931209cfbdb5759cdb550e.A.md
c997f9a1d6d6a19ded798449749581a66355433f7a2d46b455183c653e4e4a.A.json
```

Windows Downloads에는 한때 `6c1291...A.zip`이라는 이름이지만 실제 Byte Identity가 다른 파일이 존재했다.

```yaml
filename_claim: 6c1291a014df47dbc83204f299761b6ebc04ae0a026d5f576d52d514c9b86da3
actual_sha256: 7561ee3ebea9fc16757fb94fea88d7dc34b7839bed3a71eeb578aa5a243576cb
actual_bytes: 12963
member_count: 3
```

그 객체 내부에는 정식 XZ 지시문의 MD·JSON 외에 다음 ZIP이 추가되어 있었다.

```text
46d80a69667f822eb9e1aaa84a6cd8a4eccd35846b81ec4650b71c120d7c8d41.A.zip
```

이는 별도의 `gpt.xy` Cycle 3 2d 지시 Token이다.

## 3. 원인분류

```yaml
root_cause_class: POST_HASH_CONTAINER_MUTATION
cryptographic_hash_failure: false
registry_failure: false
track_db_failure: false
```

정상 객체에 Hash 이름을 부여한 뒤 그 ZIP을 다시 열어 다른 파일을 추가하고 저장한 결과, 실제 Byte와 Hash가 바뀌었으나 이전 파일명이 남았다.

```text
정상 2-Member ZIP Close
→ SHA-256 계산
→ 6c1291... 이름 부여
→ 이후 ZIP 재개방
→ 다른 ZIP Member 추가
→ 실제 Hash가 7561ee...로 변경
→ 과거 파일명은 그대로 남음
```

파일명은 Content Identity 자체가 아니다.

```text
Filename
≠ Actual Byte SHA-256
```

## 4. 해결사항

```yaml
canonical_object:
  sha256: 6c1291a014df47dbc83204f299761b6ebc04ae0a026d5f576d52d514c9b86da3
  bytes: 6343
  member_count: 2
  state: RESTORED_AND_VERIFIED

noncanonical_object:
  sha256: 7561ee3ebea9fc16757fb94fea88d7dc34b7839bed3a71eeb578aa5a243576cb
  state: EXCLUDED_FROM_REGISTRY_AND_TOKEN_DB
```

- gpt.logi가 생성한 정식 `6c1291...` 파일을 다시 다운로드했다.
- 실제 SHA-256이 파일명과 일치함을 확인했다.
- 이전의 잘못 결속된 물리적 파일은 정본으로 사용하지 않는다.
- 자동번호가 붙은 Transport Filename은 Identity로 사용하지 않고 Actual SHA-256으로 판정한다.
- 무엇이 ZIP을 후행 변경했는지는 더 추적하지 않는다.
- Registry 62개와 Final Track DB는 수정하지 않는다.

## 5. 기존 객체 `7faff...`의 처리

```yaml
sha256: 7faff320ea1ed348b52a33bb878c726376de556b570b845c1af07212b841745b
role: CYCLE2_1D_DIRECTIVE_SET
state: PRESERVE_AS_HISTORICAL_OBJECT
registry_member: true
track_db_member: true
```

이 객체는 내부에 ZIP을 다시 넣은 객체가 아니며, 당시 형성된 다중문서 지시문 세트의 실제 Historical Object다.

따라서 분리·재작성·대체하지 않는다. 다만 그 형성방식은 신규 지시문 생성에 재사용하지 않는다.

```text
Historical Object 보존
≠ Historical Pattern 재사용
```

---

## 6. Successor Token Rule

이 특이점 이후 새로 생성되는 Token은 다음 불변계약을 따른다.

```text
<Outer ZIP 실제 SHA-256>.A.zip
├─ <MD 실제 SHA-256>.A.md
└─ <JSON 실제 SHA-256>.A.json
```

```yaml
outer_member_count: 2
markdown_count: 1
json_count: 1
nested_zip_count: 0
other_member_count: 0
directory_entry_count: 0
base64_body: false
target_count_per_directive_token: 1
```

### 6.1 생성순서

```text
임시 이름으로 새 ZIP 생성
→ 대상 전용 MD 1개 기록
→ 그 MD에 종속된 JSON 1개 기록
→ ZIP Close
→ CRC·Member Count·Member Hash 검산
→ 최종 ZIP Byte SHA-256 계산
→ <SHA-256>.A.zip으로 Atomic Rename
→ Rename 후 실제 SHA-256 재검산
→ 이후 Append·Update 금지
```

### 6.2 전달규칙

```text
gpt.x → gpt.x 전용 Token 하나
gpt.y → gpt.y 전용 Token 하나
gpt.z → gpt.z 전용 Token 하나
```

한 대상에게 다른 대상의 지시문을 함께 전달하지 않는다.

---

## 7. Singularity 기록절차

향후 중대한 특이점이 발견되면 이 파일에 새 항목을 덧붙인다.

각 기록은 최소 다음을 포함한다.

```yaml
singularity_id:
detected_at:
scope:
observed_state:
actual_byte_evidence:
lineage_evidence:
mutation_frozen:
current_rule_preserved:
resolution:
successor_rule:
successor_rule_effective_from:
historical_objects_rewritten: false
final_state:
```

이 파일의 기존 기록을 삭제하거나 과거 판정을 새 Rule에 맞춰 다시 쓰지 않는다. 정정이 필요하면 기존 항목을 보존하고 별도의 Successor Correction 항목을 추가한다.

---

## 8. 현재 결론

```yaml
HRTDB_A-S-001: RESOLVED
canonical_cycle3_xz_directive: 6c1291a014df47dbc83204f299761b6ebc04ae0a026d5f576d52d514c9b86da3
noncanonical_composite: 7561ee3ebea9fc16757fb94fea88d7dc34b7839bed3a71eeb578aa5a243576cb
registry_token_count: 62
track_db_sha256: fc73f67e6e1c7bc7acdc9702e87d0a25eba1fe385d287c541e351ffe18ed4287
track_db_state: USE_AS_CREATED
historical_7faff_object: PRESERVED
next_github_route: RESTART_EXACT_62_TOKEN_PREFLIGHT_AND_TRACKDB_REGISTRATION
```
