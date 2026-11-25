# merik-models

Core ML models used by the Merik iPad app to make stems and aligned lyrics from a song, on the device. The app downloads them on first use.

| File | What | Source |
|---|---|---|
| `HTDemucs6.mlmodelc.zip` | Source separation (drums, bass, other, vocals, guitar, piano): the network of Demucs `htdemucs_6s` without the STFT/iSTFT, fixed 7.8 s window, float32 | Demucs (Meta AI Research), MIT license, https://github.com/facebookresearch/demucs |
| `W2V.mlmodelc.zip` | CTC letter model for forced alignment of English lyrics: `wav2vec2-base-960h`, fixed 20 s window, float32 | wav2vec 2.0 (Meta AI / fairseq), MIT license, https://github.com/facebookresearch/fairseq ; torchaudio `WAV2VEC2_ASR_BASE_960H` |

Converted with coremltools; the conversion scripts are in the Merik iPad repository (`scripts/convert-htdemucs.py`, `scripts/convert-wav2vec.py`).

SHA-256 of the zip files:
```
b23bd01b0ce5dd8aabcaf83e8418798e06fdf8caa666e9df8a4147f7dcd9d1d0  HTDemucs6.mlmodelc.zip
2bae1a227af0fa30ff168fc797b1a004aae8c1b04cb0e978587a95a5f30e75be  W2V.mlmodelc.zip
```
