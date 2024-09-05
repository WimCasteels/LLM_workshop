# Hands-on application with large language model

During this workshop we will develop an application with an online user interface that is driven by a large language model. We will see different ways to access a language model, through an API or by hosting it yourself. The workshop exist from 3 parts:
1) Calling a large language model
2) Building a user interface with Streamlit
3) Developing an application that is fueled by a large language model

## Accessing Language models
For this workshop we consider the language model as a black box that we can use as a funtion which takes text as input and returns text as output. The way that most people are familiar with to access a language model is by using an online interface such as for example [ChatGPT](https://chatgpt.com/) from OpenAI or [Gemini](https://gemini.google.com/app) from Google.

A good tool to compare the accuracy of different chatbot is the [Chatbot Leaderboard](https://huggingface.co/spaces/lmsys/chatbot-arena-leaderboard) which ranks LLM's based on feedback by users.

### Access through an API

To build an application with an llm we need programmatic access. Many companies provide this service, they host LLM's on their servers and provide access through an Application Programming Interface (API). Typically they charge a certain amount per token that is send to/returned from the LLM. Some examples are:
- [OpenAI developer platform](https://platform.openai.com/)
- [mistral.ai](mistral.ai) 
- [Google Gemini](https://ai.google.dev/gemini-api/docs/quickstart?lang=python) 
- [HuggingFace API](https://huggingface.co/docs/api-inference/index)
- [wit](https://wit.ai/)
- [Cohere](https://cohere.com/)
- ...

There are many more options and many provide free credits to get started or a limited free tier to experiment with the API. For this workshop we use the free tier of Cohere but we encourage you to experiment with other providers. 

See [this link](https://cohere.com/blog/free-developer-tier-announcement) for more information about the accessing the free tier of cohere. Once you have set up an account you get an API key to access the model. In the *llm* folder there is a notebook called *cohere.ipynb* which provides some starter code to access the API with the python package of Cohere. 

**Exercise:** Register on the Cohere website and use you API key to access the llm. Have a look at the documentation and see if you can include the possibility of a websearch if the llm does not know the answer to a question. 

Beware with putting API keys in code! Best practise is to set them as an environment variable such that the code can be shared without sharing the key. 

### Self-hosting an llm

Another possibility is to run an LLM yourself. As you can see in the [Chatbot Arena](https://huggingface.co/spaces/lmsys/chatbot-arena-leaderboard) not all llm's are proprietary and many are publicly available through an open source license. Note that not all open source licenses are equally open and some still have restrictions on commercial use of the LLM. There are multiple ways to run your own LLM. The [HuggingFace](https://huggingface.co/) platform for example provides a way to share AI models and provides public access to many open source AI models. Another popular option specifically to host large language models is [Ollama](https://ollama.com/). 

