# mp3Transcriber

## これは何？

mp3ファイル内の音声をVOSK/Kaldiを用いて文字起こしを行い、その後OpenAI APIを使って文章を整形するツールです。

## 準備

- ffmpegのインストール

    ```bash
    sudo apt -y install ffmpeg
    ```

- 必要な依存パッケージのインストール

    ```bash
    pip install vosk pydub openai
    ```

- モデルのダウンロードと展開

    ```bash
    wget https://alphacephei.com/vosk/models/vosk-model-ja-0.22.zip
    unzip vosk-model-ja-0.22.zip
    rm vosk-model-ja-0.22.zip
    ```

## 使い方

```bash
export OPENAI_API_KEY=your api key
python3 mp3transcriber.py <mp3file>
```

## ToDo

長い音声に関しては、文字起こし結果のテキスト量が多くなるため、ChatGPTを使用する際にトークン数オーバーが発生する場合がある。

LangChainのRecursiveCharacterTextSplitterなどを活用して、適切なサイズにテキストを分割した上で、それぞれを整形する必要がある。
