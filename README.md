# LangGraph

- LangGraph 如果你更喜欢基于图形的可视化工作流程来构建复杂的 LLM 任务。非常适合需要清晰和结构的用户。
	- 官方参考 https://langchain-ai.github.io/langgraph/
- LangChain 如果你需要一个强大、灵活的解决方案来以编程方式创建语言模型应用。它多功能且非常适合构建生产级应用的开发者。
- LangSmith 如果你的重点是LLM应用的可观察性和调试。非常适合在开发或生产环境中监控和优化工作流程。 [无法独立部署 可免费注册] [Langfuse开源平替]


## Get started

Install LangGraph:

```
pip install -U langgraph
```

Then, create an agent [using prebuilt components](https://langchain-ai.github.io/langgraph/agents/agents/):

```python
# pip install -qU "langchain[anthropic]" to call the model

from langgraph.prebuilt import create_react_agent

def get_weather(city: str) -> str:
    """Get weather for a given city."""
    return f"It's always sunny in {city}!"

agent = create_react_agent(
    model="anthropic:claude-3-7-sonnet-latest",
    tools=[get_weather],
    prompt="You are a helpful assistant"
)

# Run the agent
agent.invoke(
    {"messages": [{"role": "user", "content": "what is the weather in sf"}]}
)
```

