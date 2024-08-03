# ollama_test

## Intall

```
curl -fsSL https://ollama.com/install.sh | sh
pip install langchain-community
pip install ollama
ollama serve
ollama pull gemma2
ollama list
```

## test

```python ollama_verbose_mode.py
from langchain_community.llms import Ollama

def get_ollama_response(prompt):
    try:
        # verbose モードを有効にしてOllamaインスタンスを作成
        llm = Ollama(model="gemma2", verbose=True)
        
        print(f"プロンプト: {prompt}")
        response = llm.invoke(prompt)
        
        print(f"応答: {response}")
        # verbose モードが有効な場合、評価時間などの詳細情報は
        # 自動的にコンソールに出力されます
    except Exception as e:
        print(f"エラーが発生しました: {e}")

if __name__ == "__main__":
    prompt = "Why is the sky blue?"
    get_ollama_response(prompt)
```
    
