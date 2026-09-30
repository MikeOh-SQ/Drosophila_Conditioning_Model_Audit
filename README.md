# 초파리 연결망 참고 조건학습 모델의 재현성과 검증 경계

### Internal Reproducibility and Validation Limits of a Connectome-Informed Drosophila Conditioning Model

[한국어](#한국어) · [English](#english)

**저자 / Author:** 오경민 · **Oh Kyungmin**  
**소속 / Affiliation:** [연세대학교 심리과학이노베이션대학원 / Yonsei University Graduate School of Innovative Psychological Science](https://yongei.yonsei.ac.kr/psycinno/index.do)  
**문서 성격 / Status:** 공개 연구 기록 및 논문 형식의 요약 / Public research record in manuscript style; **동료 심사 논문이 아님 / not a peer-reviewed article**

## 한국어

### 초록

**배경:** 디지털 조건학습 모델에서 잘 작동한 훈련 조건이 실제 신경 연결
구조와 독립 행동 연구에도 적용되는지는 별도의 검증 문제다. 본 기록은
초파리 학습 회로 문헌을 참고한 계산 모델의 내부 효과와 그 검증 한계를
구분한다.

**방법:** 먼저 실제 감각 입력이 없는 기호 자극 A/B의 축약 rate 모델에서
연습 간격과 대조 조건을 비교했다(Stage 87–89). 다음으로 공개된 성체
암컷 FlyWire FAFB v783 연결 자료의 작은 **후각 후보 경로**를 별도의
계산 모델에 도입하고, 연결 섞기 대조 및 출력 후보·정규화 민감도를
검사했다(Stage 90–91). 마지막으로 독립 청각 조건학습 행동 연구와
자극, 보상 일정, 시간 단위, 행동 지표의 비교 가능성을 점검했다.

**결과:** 기호 모델에서는 짧은 간격에서 비강화 자극에 대한 계산 반응이
증가했고, 이전 자극의 학습 흔적을 제거하면 간격 효과가 사라졌다.
그러나 연결 자료를 도입한 사전 지정 훈련 조건의 마지막 기준 충족률은
38/144(26.39%)와 25/144(17.36%)로, 사전 기준 90%에 못 미쳤다.
출력 후보를 바꾼 탐색적 후속 검사에서도 24개 학습 설정 모두 기준에
미달했다. 독립 청각 행동 연구와는 입력·일정·시간·출력 측정이
불일치하여 **수치적 외부 검증을 수행할 수 없었다**.

**결론:** 계산 내부의 재현성은 확인했으나, 현재 모델을 실제 초파리의
조건학습이나 최적 훈련법의 예측기로 사용할 근거는 확보하지 못했다.
이는 실제 초파리의 학습 실패나 연결망 이론의 반증이 아니다.

### 1. 연구 질문과 범위

핵심 질문은 **“단순 모델에서 보이는 학습 조건의 순위가 실제 연결
구조와 외부 행동 연구를 거쳐도 유지되는가?”**였다. 이 공개 기록은
하나의 검증된 생물학적 모델을 발표하는 대신, 질문에 답하기 위해
거친 서로 다른 모델·대조·비교 문턱을 함께 제시한다. Stage 87의
기호 회로, Stage 90–91의 후각 연결망 참고 계산, 청각 경로 구조 감사,
청각 행동 논문 비교를 같은 실험으로 취급하지 않는다.

### 2. 방법

| 단계 | 입력·회로 | 계획과 분석 단위 | 측정과 계산의 경계 |
|---|---|---|---|
| [87: 연습 간격](data/stage87/) | 20개 기호 KC, 출력 2개와 보상 관련 단위 2개의 rate 축약; A/B 기호 자극 | 간격 2/10/40, 네 대조 조건, 강화 자극 역할 교대; 48개 기술 seed로 2,304 계산 session과 별도 동일 조건 재실행 | 시간·학습 계수는 무차원 가정. 실제 감각·몸·개체 자료 없음 |
| [88–89: 탐색](data/stage88/) · [보상 조건](data/stage89/) | 같은 계열의 공학적 조건학습 모델 | 자극 혼합·연습량·속도와 보상·처벌·중립 설정 탐색 | 모델 내부 설정 탐색이며 생체 최적화가 아님 |
| [90: 연결 구조](data/stage90/) | 공개 FAFB v783 암컷 뇌의 18개 ALPN, 511개 KC와 MBON11/03 후보; 추출 graph 694 node·8,179 directed pair edge | 조건당 24개 기술 seed × 6개 역할 = 144 session; 고정 90% 성공 기준과 연결 대응 섞기 대조 | 연결·synapse count는 구조 자료. 자극 활성, 계산상 효능, 출력 판독은 모델 가정 |
| [91: 민감도](data/stage91/) | MBON03/02 출력 후보, 입력 변환 3개, 정규화 2개 | 총 48개 셀 중 학습 조건 24개를 탐색; 동일 기술 반복 | Stage 90 실패를 본 뒤 설계한 탐색적 후속 분석이며 독립 생체 검증이 아님 |
| [외부 비교 문턱](data/final-gate/) | [Menda 등(2011)](https://doi.org/10.1242/jeb.055202)의 실제 청각 조건학습 프로토콜과 현재 모델의 실행 event 비교 | 자극·연습 수·보상 시점·실제 시간·PER 출력의 일치 여부 | 수치 적합도 검사가 아니라 **비교 가능성 사전 점검** |

모델의 보상·처벌은 외부에서 지정한 수치다. Stage 90–91에서 바뀌는 것은
존재하는 연결에 붙인 별도의 **계산상 효능**이며, 원 connectome의
synapse count·세포 ID·연결 방향은 바뀌지 않는다. Dopamine neuron
spike나 생물학적 시냅스 가소성을 측정하거나 구현하지 않았다.

### 3. 결과

**기호 모델의 내부 현상.** Stage 87에서 강화/비강화 자극 반응의
baseline 대비 구분 지표는 간격 2/10/40에서 각각 0.538375,
0.579869, 0.580472였다. 가장 짧은 간격의 비강화 자극 계산 반응은
0.050715였고 긴 간격에서는 거의 0이었다. 학습 흔적(eligibility)의
이월을 제거하자 간격별 가중치와 구분 지표가 동일해졌다. 비연합,
무보상, 학습 비활성 대조는 가중치 변화가 없었다. 별도 재실행의
전체 session·요약 파일은 바이트 단위로 일치했다. 이 값은 **모델 bias**이고
행동 정답률이나 실제 동물의 반응 확률이 아니다.

**연결 구조 도입 후 음성 결과.** Stage 90의 보상+처벌 빠른 조건은
실제 연결 배열 38/144(26.39%), 연결 대응을 섞은 대조 42/144(29.17%)가
마지막 기준을 충족했다. 절반 강도·긴 연습 조건은 실제 배열
25/144(17.36%)였다. 모두 사전 90% 기준에 미달했고, 실제 배열이
섞은 배열보다 일관되게 유리하지 않았다. 기호 모델과 연결 모델은
세포 수·희소성·출력·입력 변환·정규화가 함께 달라졌으므로 차이를
**연결 배열 하나의 인과 효과**로 돌릴 수 없다.

**출력 후보와 가정에 대한 민감도.** Stage 91에서 빠른 조건의
MBON03→MBON02 후보 변경은 같은 정규화에서 38/144(26.39%)를
62/144(43.06%)로 높였지만 여전히 사전 기준에 못 미쳤다. 공통
정규화를 쓰면 같은 MBON02 조건은 35/144(24.31%)였다. 검사한
학습 설정 24개 중 기준 통과는 **0개**였다. 이 탐색은 결과에 민감한
모델 선택 지점을 보여주며, MBON02의 실제 생체 기능을 검증하지 않는다.

**청각 근거와 외부 비교.** [청각 구조 후보 표](data/auditory-paths/)에는
주석 입력에서 출력 후보까지 4연결 순방향 경로 58개가 있다. 이는
측정된 소리 반응이나 학습 경로가 아니다. 최종 비교에서는 모델의
기호 A/B와 무차원 시간·계산 bias가 독립 연구의 400 Hz 소리,
지연 당 보상, 초 단위 일정 및 입 내밀기 반응(PER)에 대응하지 않았다.
따라서 외부 연구와 결과 수치를 맞추거나 생물학적 예측 성공·실패를
판정하지 않았다.

### 4. 해석과 한계

이 사례에서 중요한 차이는 **내부 재현성**과 **외부 타당성**이다.
동일 코드를 다시 실행해 같은 값이 나온다는 것은 계산 기록의
신뢰도를 높이지만, 그 값이 살아 있는 초파리의 학습을 설명한다는
뜻은 아니다. 특히 연결망의 구조 자료만으로 개별 세포의 자극 반응,
보상의 실제 전달, 기억 형성 및 행동 출력을 알 수 없다.

자료의 한계는 다음과 같다: 기호 자극에 실제 주파수·농도·초 단위가
없고, 연결 모델은 암컷 뇌의 작은 후각 후보 경로만 사용하며,
청각 세포 유형 문헌을 개별 MaleCNS 세포 측정으로 대입하지 않았다.
Stage 91은 Stage 90 결과 뒤의 탐색이고, 독립 행동 논문의 개체별
trial 표도 이 묶음에는 없다. 기존 오디오 판정
`ready_for_audio_onset_input=false`, **50.8 ms 실패**(v1.4.14),
`ready_for_real_music_pilot=false`(v1.5.0)는 그대로 유지한다.

### 5. 데이터, 재현 범위 및 참고문헌

[`data/manifest.json`](data/manifest.json)은 이 저장소용 파생 JSON/CSV
**13개**의 파일명·바이트 수·SHA-256을 기록한다. Stage 87의 session 행과
모든 seed는 실제 초파리 개체가 아닌 기술 반복이다. `source_runtime_path`는
생성 당시 경로이며 전체 runtime이 이 묶음에 들어 있다는 뜻이 아니다.
원본 사용자 음원, 인증정보, 외부 논문의 개체별 원자료 및 원본 connectome은
제외했다. **이 작은 공개 묶음만으로 전체 계산을 처음부터 재실행할 수는
없다.** 이 문서는 제출·동료 심사된 논문이 아니며, 후속 연구에는
입력·보상 일정·시간·행동 지표를 독립 자료와 먼저 맞춰야 한다.

1. [Jürgensen 등 (2024), *iScience*](https://doi.org/10.1016/j.isci.2023.108640). 학습식 참고; 원 spiking 모델의 완전 재현은 아님.
2. [FlyWire Consortium (2024), *Nature*](https://doi.org/10.1038/s41586-024-07558-y). Stage 90–91 구조 자료의 원출처; 원자료 재배포 없음.
3. [Baker 등 (2022), *Current Biology*](https://doi.org/10.1016/j.cub.2022.06.019) 및 [저자 자료](https://doi.org/10.34770/7zem-x425). 청각 세포 유형의 문헌 근거.
4. [Menda 등 (2011), *Journal of Experimental Biology*](https://doi.org/10.1242/jeb.055202). 독립 청각 조건학습 행동 연구; 현재 모델의 외부 검증 자료로 직접 사용할 수 없음.

---

## English

### Abstract

**Background.** A training schedule that appears effective in a digital
conditioning model requires separate tests against anatomical connectivity
and independent behavior. This record distinguishes internally reproducible
effects from biological predictive validity.

**Methods.** We first compared training intervals and controls in a reduced
rate model with symbolic cues A/B and no measured sensory input (Stages
87–89). We then introduced a small **olfactory candidate pathway** from
the published adult female FlyWire FAFB v783 connectome into a separate
computational model, tested a shuffled-connectivity control, and explored
output and normalization choices (Stages 90–91). Finally, we checked
whether the model's stimulus, reward schedule, time unit, and readout
matched an independent auditory conditioning study.

**Results.** The symbolic model showed a computed response to the
unreinforced cue at short intervals; removing the preceding cue's
eligibility trace removed the interval effect. With published connectivity,
the two prespecified training conditions reached the final criterion in
38/144 (26.39%) and 25/144 (17.36%) technical runs, below the 90%
threshold. None of 24 learning settings in the exploratory follow-up met
that threshold. The independent auditory study could **not** be used for
numerical external validation because the protocols and readouts differed.

**Conclusion.** We verified computational repeatability but did not
establish that the current model predicts conditioning or optimal training
in living flies. The negative findings do not show that Drosophila cannot
learn or that connectome-based theories are false.

### 1. Research question and scope

The guiding question was: **Does the ranking of training conditions in a
simple model persist when anatomical connectivity and independent behavior
are considered?** The symbolic circuit, the olfactory connectome-informed
calculation, the structural auditory-path audit, and the external auditory
protocol check are distinct stages. They are not one validated biological
experiment.

### 2. Methods

| Stage | Input and model | Design and unit of analysis | Evidence boundary |
|---|---|---|---|
| [87: spacing](data/stage87/) | Reduced rate model with 20 symbolic KCs, two outputs, two reward-related units, and cues A/B | Intervals 2/10/40, four controls and counterbalanced reinforced cue; 48 technical seeds, 2,304 computational sessions, and a separate repeat | Time and learning constants are dimensionless assumptions; no animal or measured stimulus data |
| [88: efficiency](data/stage88/) · [89: valence](data/stage89/) | Engineering conditioning model | Exploratory cue mixture, trial count, speed, reward, penalty, and neutral conditions | Model-internal parameter search, not biological optimization |
| [90: connectivity](data/stage90/) | Published female FAFB v783 candidate path with 18 ALPNs, 511 KCs, MBON11/03; extracted graph of 694 nodes and 8,179 directed pairs | 24 technical seeds × 6 cue-role assignments = 144 sessions per condition; fixed 90% criterion and a connectivity-shuffle control | Connections and synapse counts are structural data; activation, efficacy, and readout are modeled |
| [91: sensitivity](data/stage91/) | MBON03/02 outputs, three input transforms, two normalization schemes | 48 cells, including 24 learning-condition cells | Designed after seeing Stage 90; exploratory, not independent animal validation |
| [External gate](data/final-gate/) | Comparison with [Menda et al. (2011)](https://doi.org/10.1242/jeb.055202) | Check stimulus, trial count, reward timing, physical time, and proboscis extension response (PER) | A prerequisite comparability check, not a numerical model fit |

Reward and penalty are externally assigned numbers. In Stages 90–91,
learning changes **modeled efficacy** on existing edges; it does not
change connectome synapse counts, body IDs, or edge directions. Dopamine
neuron spikes and biological synaptic plasticity were neither measured
nor implemented.

### 3. Results

**Symbolic-model effect.** In Stage 87, baseline-adjusted discrimination
between reinforced and unreinforced cues was 0.538375, 0.579869, and
0.580472 for intervals 2, 10, and 40. The computed unreinforced-cue
response at the shortest interval was 0.050715 and approached zero at
the longest interval. Removing eligibility carryover made the weights
and discrimination results identical across intervals. Unpaired,
no-reward, and learning-disabled controls showed no weight change. A
separate repeat produced byte-identical session and summary files. These
are **model biases**, not behavioral accuracy or animal response rates.

**Negative finding after adding connectivity.** In Stage 90, the fast
reward-plus-penalty condition met the final criterion in 38/144 (26.39%)
technical runs with the observed connectivity and 42/144 (29.17%) with
shuffled correspondence. The lower-magnitude, longer condition reached
25/144 (17.36%) with observed connectivity. All were below the
prespecified 90% criterion, and the observed arrangement did not
consistently outperform the shuffle. Cell counts, sparsity, output
choice, input transforms, and normalization also changed between the
symbolic and connectome-informed models; their difference cannot be
attributed causally to connectivity alone.

**Sensitivity to modeled choices.** In the exploratory Stage 91 analysis,
replacing MBON03 with MBON02 raised the fast condition from 38/144
(26.39%) to 62/144 (43.06%) under the same per-output normalization,
still below the criterion. Common normalization reduced the MBON02
result to 35/144 (24.31%). **Zero of 24** learning settings passed.
This exposes model sensitivity; it does not establish MBON02's function
in living flies.

**Auditory evidence and external comparison.** The [auditory-path table](data/auditory-paths/)
contains 58 four-edge feedforward structural candidates from annotated
inputs to output candidates, not measured auditory responses or learning
paths. The current model's symbolic A/B cues, dimensionless time, and
computed bias do not match the independent study's 400 Hz sound,
delayed sugar reward, schedule in seconds, and measured PER. We therefore
did not fit numerical outcomes or classify biological prediction as a
success or failure.

### 4. Interpretation and limitations

**Internal reproducibility is not external validity.** Re-running code
to obtain the same numbers supports the integrity of a computational
record. It does not show that those numbers explain learning in an
animal. Structural connections alone do not specify stimulus responses,
reward signaling, memory formation, or behavioral output.

The symbolic model has no calibrated sound frequency, odor concentration,
or seconds. The connectome-informed model uses a small olfactory
candidate path from an adult female brain, not a full-brain auditory
learning circuit. Cell-type literature was not treated as measurements
from individual MaleCNS neurons. Stage 91 was exploratory after Stage
90, and individual trial data from the external behavioral paper are
not included here. Earlier audio gates remain unchanged:
`ready_for_audio_onset_input=false`, the **50.8 ms failure** (v1.4.14),
and `ready_for_real_music_pilot=false` (v1.5.0).

### 5. Data availability and references

[`data/manifest.json`](data/manifest.json) records the filenames, byte
counts, and SHA-256 hashes of **13** derived JSON/CSV files. Stage 87
session rows and all seeds are technical repeats, not individual flies.
`source_runtime_path` records provenance; full runtime data are not
included. Original user audio, credentials, raw connectome data, and
individual observations from external papers are excluded. **This
compact package alone cannot reproduce every original computation from
scratch.** It is a public research record, not a submitted or
peer-reviewed article. A future biological prediction study first needs
aligned stimuli, reward timing, physical time, observable behavior, and
independent data.

1. [Jürgensen et al. (2024), *iScience*](https://doi.org/10.1016/j.isci.2023.108640). Learning-rule inspiration; not a full reproduction of the authors' spiking model.
2. [FlyWire Consortium (2024), *Nature*](https://doi.org/10.1038/s41586-024-07558-y). Original connectivity source for Stages 90–91; raw data are not redistributed.
3. [Baker et al. (2022), *Current Biology*](https://doi.org/10.1016/j.cub.2022.06.019) and [author data](https://doi.org/10.34770/7zem-x425). Literature evidence concerning auditory cell types.
4. [Menda et al. (2011), *Journal of Experimental Biology*](https://doi.org/10.1242/jeb.055202). Independent behavioral study; its protocol and readout do not directly validate the current model.
