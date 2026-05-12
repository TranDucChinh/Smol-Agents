# 🤖 SmolAgents

Thực hành xây dựng **AI Agents** với thư viện [`smolagents`](https://github.com/huggingface/smolagents) của Hugging Face.

## Nội dung

| Notebook | Mô tả |
|----------|-------|
| `basic_agents.ipynb` | CodeAgent (thời tiết, Fibonacci) & ToolCallingAgent (tìm kiếm web) |
| `summary_new_agent.ipynb` | Agent thu thập và tóm tắt tin tức AI |

## Cài đặt

```bash
pip install smolagents python-dotenv requests
```

Tạo file `.env` từ template:

```bash
cp .env.example .env
# Điền HF_TOKEN vào .env
```

Lấy token tại: [huggingface.co/settings/tokens](https://huggingface.co/settings/tokens)

## Example

```python
import os
from dotenv import load_dotenv
from smolagents import CodeAgent, InferenceClientModel

load_dotenv()

agent = CodeAgent(
    tools=[],
    model=InferenceClientModel(token=os.getenv("HF_TOKEN"))
)
agent.run("Số Fibonacci thứ 50 là bao nhiêu?")
```

