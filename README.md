# Welcome to Chainlit 👋

[![](https://dcbadge.vercel.app/api/server/ZThrUxbAYw?style=flat)](https://discord.gg/k73SQ3FyUh)
[![Twitter](https://img.shields.io/twitter/url/https/twitter.com/chainlit_io.svg?style=social&label=Follow%20%40chainlit_io)](https://twitter.com/chainlit_io)
[![CI](https://github.com/Chainlit/chainlit/actions/workflows/ci.yaml/badge.svg)](https://github.com/Chainlit/chainlit/actions/workflows/ci.yaml)

**Build a production ready Chat GPT like application in minutes ⚡️**

Chainlit is an open-source async Python framework that makes it incredibly fast to build Chat GPT like applications with your **own business logic and data**.

Key features:

- [💬 Multi Modal chats](https://docs.chainlit.io/chat-experience/elements)
- [💭 Chain of Thought visualisation](https://docs.chainlit.io/observability-iteration/chain-of-thought)
- [💾 Data persistence + human feedback](https://docs.chainlit.io/chat-data/overview)
- [🛝 In context Prompt Playground](https://docs.chainlit.io/observability-iteration/prompt-playground/overview)
- [👤 Authentication](https://docs.chainlit.io/authentication/overview)


https://github.com/Chainlit/chainlit/assets/13104895/cbcb8078-ab4d-4e4c-8e4e-7aaa51ca1fd0

## Installation

Open a terminal and run:

```bash
$ pip install chainlit
$ chainlit hello
```

If this opens the `hello app` in your browser, you're all set!

## 📖 Documentation

Please see [here](https://docs.chainlit.io) for full documentation on:

- Getting started (installation, simple examples)
- Examples
- Reference (full API docs)

## 🚀 Quickstart

### 🐍 Pure Python

Create a new file `demo.py` with the following code:

```python
import chainlit as cl


@cl.on_message  # this function will be called every time a user inputs a message in the UI
async def main(message: cl.Message):
    """
    This function is called every time a user inputs a message in the UI.
    It sends back an intermediate response from Tool 1, followed by the final answer.

    Args:
        message: The user's message.

    Returns:
        None.
    """

    # Send an intermediate response from Tool 1.
    await cl.Message(
        author="Tool 1",
        content=f"Response from tool1",
        parent_id=message.id,
    ).send()

    # Send the final answer.
    await cl.Message(content=f"This is the final answer").send()
```

Now run it!

```
$ chainlit run demo.py -w
```

<img src="/images/quick-start.png" alt="Quick Start"></img>

### 🔗 Integrations

Chainlit is compatible with all Python programs and libraries. That being said, it comes with pre-built integrations for [Langchain](https://docs.chainlit.io/integrations/langchain), [Llama Index](https://docs.chainlit.io/integrations/llama-index), [Haystack](https://docs.chainlit.io/integrations/haystack) and [Langflow](https://docs.chainlit.io/integrations/langflow).

### 📚 More Examples - Cookbook

You can find various examples of Chainlit apps [here](https://github.com/Chainlit/cookbook) that leverage tools and services such as OpenAI, Anthropiс, LangChain, LlamaIndex, ChromaDB, Pinecone and more.

## 🛣 Roadmap

- [ ] Selectable chat profiles (at the beginning of a chat)
- [ ] One click chat sharing
- New clients:
  - [ ] Slack
  - [ ] Discord
  - [ ] Website embbed

Tell us what you would like to see added in Chainlit using the Github issues or on [Discord](https://discord.gg/k73SQ3FyUh).

## 🏢 Enterprise support

For entreprise grade features and self hosting, please visit this [page](https://docs.chainlit.io/cloud/persistence/enterprise) and fill the form.

## 💁 Contributing

As an open-source initiative in a rapidly evolving domain, we welcome contributions, be it through the addition of new features or the improvement of documentation.

For detailed information on how to contribute, see [here](.github/CONTRIBUTING.md).

## 📃 License

Chainlit is open-source and licensed under the [Apache 2.0](LICENSE) license.
