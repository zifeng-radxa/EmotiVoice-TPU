# Run Emoti-OpenVoice on your Airbox
This repo is a BM1684X-adapted demo of EmotiVoice(@NetEase Youdao) and OpenVoice(@MyShell.ai).

## 1. Download bmodels.
- Download the bmodels for EmotiVoice.
```sh
python3 -m pip install dfn
python3 -m dfn --url https://disk.sophgo.vip/sharing/KymDuWLGw
```
- Download bmodels of OpenVoice tone color converter [here](https://drive.google.com/file/d/1ErVDiMFvTwRj649pyoJI7rRDAh5pTGVT/view?usp=drive_link) and run `tar zxfv checkpoints.tar.gz`.

- The `model_file`` directory should be organized as:
```
model_file
├── converter
│   ├── checkpoint.pth
│   ├── config.json
│   ├── decoder_1024_f16.bmodel
│   └── decoder_2048_f16.bmodel
├── simbert-base-chinese
│   ├── config.json
│   └── vocab.txt
└── tts
    ├── am_durationpred-1_512_384-1_512_1.bmodel
    ├── am_energypred-1_512_384-1_512_1.bmodel
    ├── am_pitchpred-1_512_384-1_512_1.bmodel
    ├── am_rest_weight.pth
    ├── bert_poolout1-768_1-512_1-512_1-512.bmodel
    ├── hifigan_1-80-1024_F16.bmodel
    ├── jit_am_encoder_1-512-384_1-1-512.bmodel
    └── onnx_am_decoder_1-2048-384.bmodel
```


## 2. Run web demo:
```sh
sudo apt-get install libsndfile1 -y
pip3 install torch torchaudio
pip3 install numpy numba scipy transformers==4.26.1 librosa soundfile yacs g2p_en jieba pypinyin whisper_timestamped onnxruntime gradio
mv master.zip ~/.cache/torch/hub/
python3 demo_page.py
```

## For more detailed usage, please refer to the README from the original repo of [EmotiVoice](https://github.com/netease-youdao/EmotiVoice) and [OpenVoice](https://github.com/myshell-ai/OpenVoice).
