# Virtual Drosophila Conditioning: Results and Negative Findings

**한국어** · [English](#english)

## 한국어

**정리: 오경민 (Oh Kyungmin)**  
**소속: [연세대학교 심리과학이노베이션대학원](https://yongei.yonsei.ac.kr/psycinno/index.do)**

이 저장소용 묶음은 초파리 연결망을 참고한 **계산 모델**의 조건학습
탐색과 실패 기록을 함께 공개하기 위해 준비했다. 실제 초파리의 학습,
신경 발화 또는 최적 훈련법을 측정·검증한 자료가 아니다.

### 핵심 결과

| 자료 | 확인한 내용 | 판정 |
|---|---|---|
| [Stage 87](data/stage87/) | 기호 자극 A/B의 연습 간격 | 짧은 간격에서 계산상 자극 혼입. 시간 단위는 실제 초가 아니다. |
| [Stage 88](data/stage88/) | 자극 비율·횟수·속도 | 공학 모델 내부의 효율 탐색. 생체 최적값은 아니다. |
| [Stage 89](data/stage89/) | 보상·처벌·중립 | 공학 모델 내부의 조건별 차이. 실제 동물의 처벌 반응은 아니다. |
| [Stage 90](data/stage90/) | 공개 연결 자료를 사용한 재계산 | 사전 성공 기준에 미달. |
| [Stage 91](data/stage91/) | 출력 후보·정규화 가정의 민감도 | 검사한 24개 학습 설정 모두 사전 성공 기준에 미달. |
| [청각 경로 후보](data/auditory-paths/) | 주석된 청각 입력과 출력 후보 사이의 구조 경로 | 58개 4연결 순방향 후보. 실제 청각 반응은 미측정. |
| [최종 비교 문턱](data/final-gate/) | 독립 청각 조건학습 연구와 직접 비교 가능한가 | 자극·보상 시점·시간 단위·행동 지표가 달라 **외부 검증 미성립**. |

앞선 오디오 연구도 성공으로 바꾸지 않았다: v1.4.14의
`ready_for_audio_onset_input=false`와 **50.8 ms 실패**, v1.5.0의
`ready_for_real_music_pilot=false`가 유지된다. Stage 90–91의 실패는
**현재 모델과 검사한 설정**의 실패이며 초파리 연결망 전체에서
학습이 불가능하다는 결론이 아니다.

### 데이터와 재현 범위

[`data/manifest.json`](data/manifest.json)은 파생 JSON/CSV 13개의
SHA-256과 바이트 수를 기록한다. Stage 87의 session 행은 실제 개체가
아닌 계산 반복이다. `source_runtime_path`는 생성 당시 경로의 기록이며
이 묶음에 원본 runtime 전체가 있다는 뜻은 아니다. 원본 사용자 음원,
인증정보, 원본 connectome 및 외부 논문의 개체별 원자료는 포함하지
않았다. 따라서 **이 묶음만으로 전체 실험을 처음부터 재실행할 수는
없다**. 연구 계획·코드·전체 실행 기록은 원 프로젝트의 관련 문서를
함께 검토해야 한다.

### 참조 논문과 자료

- [Jürgensen 등, 2024, *iScience*](https://doi.org/10.1016/j.isci.2023.108640): 학습 모델 참고. 저자 모델의 완전한 재현은 아니다.
- [FlyWire Consortium, 2024, *Nature*](https://doi.org/10.1038/s41586-024-07558-y): Stage 90–91 연결 자료의 원출처. 원본 자료는 재배포하지 않는다.
- [Baker 등, 2022, *Current Biology*](https://doi.org/10.1016/j.cub.2022.06.019) 및 [저자 공개 자료](https://doi.org/10.34770/7zem-x425): 청각 세포 유형에 대한 문헌 근거. 개별 MaleCNS 뉴런의 실제 반응으로 대입하지 않았다.
- [Menda 등, 2011, *Journal of Experimental Biology*](https://doi.org/10.1242/jeb.055202): 독립 청각 조건학습 행동 연구. 현재 모델은 실험 조건과 지표가 맞지 않아 이 연구로 검증되지 않았다.

**해석 경계:** 연결 수는 구조 측정, 세포 유형은 주석, 전달물질은
예측, 신호와 학습은 계산 결과다. dopamine 발화, 생물학적 시냅스
가소성, 실제 초파리의 학습·춤·비행을 확인한 결과가 아니다.

---

## English

**Prepared by: Oh Kyungmin (오경민)**  
**Affiliation: [Yonsei University Graduate School of Innovative Psychological Science](https://yongei.yonsei.ac.kr/psycinno/index.do)**

This package brings together exploratory **computational** results and
negative findings from a connectome-informed Drosophila conditioning
project. It does not measure or validate learning, neural firing, or an
optimal training protocol in living flies.

### Main findings

| Data | Question | Outcome |
|---|---|---|
| [Stage 87](data/stage87/) | Spacing between symbolic cues A and B | Short spacing produced interference within the model; its time unit is not a measured second. |
| [Stage 88](data/stage88/) | Cue mix, trial count, and speed | An engineering-model search, not a biological optimum. |
| [Stage 89](data/stage89/) | Reward, penalty, and neutral conditions | Differences within the engineering model, not measured animal responses. |
| [Stage 90](data/stage90/) | Recalculation with published connectivity | Failed the prespecified success criterion. |
| [Stage 91](data/stage91/) | Sensitivity to output candidates and normalization | All 24 tested learning settings failed the prespecified criterion. |
| [Auditory path candidates](data/auditory-paths/) | Structural paths from annotated auditory inputs to output candidates | 58 four-edge feedforward candidates; auditory responses were not measured. |
| [Final comparison gate](data/final-gate/) | Direct comparison with independent auditory conditioning | **External validation was not possible** because the stimulus, reward timing, time units, and behavioral readout did not match. |

Earlier negative results remain unchanged: v1.4.14 reported
`ready_for_audio_onset_input=false` and a **50.8 ms failure**; v1.5.0
reported `ready_for_real_music_pilot=false`. The Stage 90–91 failures
apply to this model and its tested assumptions. They do not establish
that learning is impossible in the fly connectome.

### Data and reproducibility boundary

[`data/manifest.json`](data/manifest.json) lists SHA-256 hashes and byte
counts for 13 derived JSON/CSV files. Stage 87 session rows are
computational repeats, not individual animals. `source_runtime_path`
records where a file was produced; the full runtime data are not bundled.
Original user audio, credentials, raw connectome data, and individual
observations from external papers are excluded. **This compact package
alone cannot rerun every original computation from scratch.** Consult
the associated protocols, code, and full run records in the source
project when assessing reproducibility.

### References and source data

- [Jürgensen et al., 2024, *iScience*](https://doi.org/10.1016/j.isci.2023.108640): inspiration for the learning model; this is not a full reproduction of their model.
- [FlyWire Consortium, 2024, *Nature*](https://doi.org/10.1038/s41586-024-07558-y): source of the Stage 90–91 connectivity. Raw data are not redistributed here.
- [Baker et al., 2022, *Current Biology*](https://doi.org/10.1016/j.cub.2022.06.019) and [author data](https://doi.org/10.34770/7zem-x425): evidence about auditory cell types, not measurements of individual MaleCNS neurons in this project.
- [Menda et al., 2011, *Journal of Experimental Biology*](https://doi.org/10.1242/jeb.055202): independent auditory conditioning study. The present model does not match its protocol or readout and has not been validated against it.

**Evidence boundary:** Connection counts are structural measurements;
cell types are annotations; transmitter identities are predictions; and
signal propagation and learning are model outputs. No dopamine spikes,
biological synaptic plasticity, or learning, dance, or flight in living
flies have been demonstrated by this package.
