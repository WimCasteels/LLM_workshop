# Hands-on AI Application Development with Large Language Models

In this workshop, we will develop an application featuring an online user interface powered by a large language model (LLM). You'll learn different ways to access and use LLMs, including API access or self-hosting. The workshop consists of three parts:

1. **Calling a large language model**
2. **Building a user interface with Streamlit**
3. **Developing an LLM-powered application**

You can find an example of the application you will develop here: https://ahumain-ai-app.streamlit.app/  

## Preliminaries

To get started, ensure that the required Python libraries are installed. They are listed in the `requirements.txt` file and can be installed by running the following command in your Python environment:

```bash
pip install -r requirements.txt
```

---

## Part 1: Accessing Language Models

In this section, we will treat the LLM as a black box: it takes text as input and returns text as output. Most people are familiar with using LLMs through online interfaces like [ChatGPT](https://chatgpt.com/) from OpenAI or [Google Gemini](https://gemini.google.com/app).

To compare the performance of various chatbots, you can check the [Chatbot Leaderboard](https://huggingface.co/spaces/lmsys/chatbot-arena-leaderboard), which ranks LLMs based on user feedback.

### Accessing Through an API

To build an application with an LLM, we need programmatic access via an API. Many companies offer this service, usually charging based on the number of tokens sent or received from the model. Some popular options include:

- [OpenAI Developer Platform](https://platform.openai.com/)
- [Mistral](https://mistral.ai/)
- [Google Gemini](https://ai.google.dev/gemini-api/docs/quickstart?lang=python)
- [Hugging Face API](https://huggingface.co/docs/api-inference/index)
- [Wit](https://wit.ai/)
- [Cohere](https://cohere.com/)

For this workshop, we will use the free tier of Cohere. You can read more about Cohere’s free tier [here](https://cohere.com/blog/free-developer-tier-announcement). Once you’ve registered, you'll receive an API key to access their models.

In the `llm` folder of this project, you'll find a Jupyter notebook (`cohere.ipynb`) that provides starter code for accessing the Cohere API using Python.

#### **Exercise**: 
1. Register on the Cohere website and obtain your API key.
2. Modify the code in `cohere.ipynb` to call the LLM with your API key.
3. Add functionality for a web search fallback when the LLM doesn't know the answer.

**Tip**: Store API keys as environment variables to avoid sharing sensitive information in your code.

### Self-hosting an LLM

Another option is to run an LLM locally. Not all LLMs are proprietary; many are available under open-source licenses. You can explore various models on the [Hugging Face](https://huggingface.co/) platform or with [Ollama](https://ollama.com/).

In this workshop, we will use the [Hugging Face Transformers](https://huggingface.co/docs/transformers) library to download and run a language model locally. Since most LLMs require significant GPU resources, we will experiment with GPT-2, an earlier model from OpenAI which contains *only* 1.5 billion parameters.

In the `llm` folder, you'll find the notebook `GPT2.ipynb`, which contains code to download and run GPT-2. You can also refer to the [GPT-2 Model Card](https://huggingface.co/openai-community/gpt2) for more details.

#### **Exercise**: 
1. Run GPT-2 locally and experiment with different prompts.
2. Compare GPT-2's responses with more modern LLM's you are familiar with.
3. Download and experiment with another open-source model from Hugging Face.

---

## Part 2: Building a Front-end User Interface

To make your application usable, you'll need to create a front-end. We'll use [Streamlit](https://streamlit.io/), a Python framework for building data-driven apps.

To verify Streamlit is installed in your environment, run:

```bash
streamlit hello
```

This will open a demo app in your browser. To close it, simply press `CTRL + C` in your terminal. Next, navigate to the `streamlit` folder and run the `helloworld_app.py` script:

```bash
streamlit run helloworld_app.py
```

You can add user interaction to your apps. For a simple example, try running `age_app.py` in the same folder.

#### **Exercise**: 
1. Create a Streamlit app that includes at least one new element from the [Streamlit API documentation](https://docs.streamlit.io/develop/api-reference).

---

## Part 3: Building an LLM-powered Application

Now that we have explored how to call an LLM and build a UI, we will combine these steps to build a complete application. In the main folder, you will find `AI_app.py`, a Streamlit app that interacts with an LLM using the Cohere API.

You can launch the app with:

```bash
streamlit run AI_app.py
```

In the `AI_app.py` file, you'll find a function called `generate_response`, which builds a prompt based on user input and sends it to the LLM via the Cohere API. The resulting text is displayed through the user interface.

#### **Exercise**: 
1. Create your own Streamlit app that integrates an LLM of your choice.

### Deploying Your App

Streamlit allows you to easily deploy your app online for free using their community cloud. All you need to do is upload your app to a GitHub repository. Follow the instructions on the [Streamlit Cloud website](https://streamlit.io/cloud).

#### **Exercise**: 
1. Deploy your app online using the Streamlit Community Cloud.

---

This workshop was created for the Data Science and AI Training 2024 at the Ardhi University in Dar es Salaam, Tanzania, as part of the [AHUMAIN](https://ahumain.africa/) Erasmus+ project, co-funded by the European Union.