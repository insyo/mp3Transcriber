# mp3Transcriber

## これは何？

mp3ファイルの音声をVOSK/Kaldiで文字起こしし、OpenAI APIにて文字起こしした文章を生成するプログラムです。

## 準備

- ffmpegのインストール

    ```bash
    sudo apt -y install ffmpeg
    ```

- 依存パッケージインストール

    ```bash
    pip install vosk pydub openai
    ```

- モデルのダウンロード

    ```bash
    wget https://alphacephei.com/vosk/models/vosk-model-ja-0.22.zip
    unzip vosk-model-ja-0.22.zip
    rm vosk-model-ja-0.22.zip
    ```

## 使い方

```bash
python3 mp3transcriber.py <mp3file>
```

## ToDo

尺の長い音声の場合、文字起こし量が多くなり、ChatGPTでの整形でToken数オーバーが発生する。

LangChainのRecursiveCharacterTextSplitterなどを使用して、適当なサイズに文字起こしテキストを分割したあとに、個別に整形する必要がある。
