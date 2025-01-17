<p align="center">
<h2 align="center">⚡ LangChain Apps on Production with Jina & FastAPI 🚀</h2>
</p>

<p align=center>
<a href="https://pypi.org/project/langchain-serve/"><img alt="PyPI" src="https://img.shields.io/pypi/v/langchain-serve?label=Release&style=flat-square"></a>
<a href="https://discord.jina.ai"><img src="https://img.shields.io/discord/1106542220112302130?logo=discord&logoColor=white&style=flat-square"></a>
<a href="https://pypistats.org/packages/langchain-serve"><img alt="PyPI - Downloads from official pypistats" src="https://img.shields.io/pypi/dm/langchain-serve?style=flat-square"></a>
<a href="https://github.com/jina-ai/langchain-serve/actions/workflows/cd.yml"><img alt="Github CD status" src="https://github.com/jina-ai/langchain-serve/actions/workflows/cd.yml/badge.svg"></a>
</p>


[Jina](https://github.com/jina-ai/jina) is an open-source framework for building scalable multi modal AI apps on Production. [LangChain](https://python.langchain.com/en/latest/index.html) is another open-source framework for building applications powered by LLMs.

**langchain-serve** helps you deploy your LangChain apps on Jina AI Cloud in a matter of seconds. You can benefit from the scalability and serverless architecture of the cloud without sacrificing the ease and convenience of local development. And if you prefer, you can also deploy your LangChain apps on your own infrastructure to ensure data privacy. With langchain-serve, you can craft REST/Websocket APIs, spin up LLM-powered conversational Slack bots, or wrap your LangChain apps into FastAPI packages on cloud or on-premises.

> Give us a :star: and tell us what more you'd like to see! 

# ☁️ LLM Apps as-a-service

langchain-serve currently wraps following apps as a service to be deployed on Jina AI Cloud with one command.

## 🔮 AutoGPT-as-a-service

[AutoGPT](https://github.com/Significant-Gravitas/Auto-GPT) is an "AI agent" that given a goal in natural language, will attempt to achieve it by breaking it into sub-tasks and using the internet and other tools in an automatic loop.

<details>
<summary>Show usage</summary>

- Deploy `autogpt` on Jina AI Cloud with one command

  ```bash
  lc-serve deploy autogpt
  ```

  <details>
  <summary>Show command output</summary>

  ```text
  ╭──────────────┬────────────────────────────────────────────────────────────────────────────────────────────────────────╮
  │ App ID       │                                           autogpt-6cbd489454                                           │
  ├──────────────┼────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ Phase        │                                                Serving                                                 │
  ├──────────────┼────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ Endpoint     │                                 wss://autogpt-6cbd489454.wolf.jina.ai                                  │
  ├──────────────┼────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ App logs     │                                        dashboards.wolf.jina.ai                                         │
  ├──────────────┼────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ Swagger UI   │                              https://autogpt-6cbd489454.wolf.jina.ai/docs                              │
  ├──────────────┼────────────────────────────────────────────────────────────────────────────────────────────────────────┤
  │ OpenAPI JSON │                          https://autogpt-6cbd489454.wolf.jina.ai/openapi.json                          │
  ╰──────────────┴────────────────────────────────────────────────────────────────────────────────────────────────────────╯
  ```

  </details>

- Integrate autogpt with external services using APIs. Get a flavor of the integration on your CLI with 
    
  ```bash
  lc-serve playground autogpt
  ```

  <details>
  <summary>Show playground</summary>
  <img src=".github/images/autogpt-playground.gif" title="autogpt-as-a-service Playground">
  </details>

</details>

## 🧠 Babyagi-as-a-service

[Babyagi](https://github.com/yoheinakajima/babyagi) is a task-driven autonomous agent that uses LLMs to create, prioritize, and execute tasks. It is a general-purpose AI agent that can be used to automate a wide variety of tasks.

<details>
<summary>Show usage</summary>

- Deploy `babyagi` on Jina AI Cloud with one command

  ```bash
  lc-serve deploy babyagi
  ```

- Integrate babyagi with external services using our Websocket API. Get a flavor of the integration on your CLI with 
    
  ```bash
  lc-serve playground babyagi
  ```

  <details>
  <summary>Show playground</summary>
  <img src=".github/images/babyagi-playground.gif" title="Babyagi-as-a-service Playground">
  </details>

</details>

## :panda_face: pandas-ai-as-a-service

[pandas-ai](https://github.com/gventuri/pandas-ai) integrates LLM capabilities into Pandas, to make dataframes conversational in Python code. Thanks to langchain-serve, we can now expose pandas-ai APIs on Jina AI Cloud in just a matter of seconds.

<details>
<summary>Show usage</summary>

- Deploy **pandas-ai** on Jina AI Cloud

  ```bash
  lc-serve deploy pandas-ai
  ```

  <details>
  <summary>Show command output</summary>

  ```text
  ╭──────────────┬─────────────────────────────────────────────────────────────────────────────────╮
  │ App ID       │                               pandasai-06879349ca                               │
  ├──────────────┼─────────────────────────────────────────────────────────────────────────────────┤
  │ Phase        │                                     Serving                                     │
  ├──────────────┼─────────────────────────────────────────────────────────────────────────────────┤
  │ Endpoint     │                     wss://pandasai-06879349ca.wolf.jina.ai                      │
  ├──────────────┼─────────────────────────────────────────────────────────────────────────────────┤
  │ App logs     │                             dashboards.wolf.jina.ai                             │
  ├──────────────┼─────────────────────────────────────────────────────────────────────────────────┤
  │ Swagger UI   │                  https://pandasai-06879349ca.wolf.jina.ai/docs                  │
  ├──────────────┼─────────────────────────────────────────────────────────────────────────────────┤
  │ OpenAPI JSON │              https://pandasai-06879349ca.wolf.jina.ai/openapi.json              │
  ╰──────────────┴─────────────────────────────────────────────────────────────────────────────────╯
  ```

  </details>

- Upload your DataFrame to Jina AI Cloud (Optional - you can also use a publicly available CSV)

  - Define your DataFrame in a Python file
    
    ```python
    # dataframe.py
    import pandas as pd
    df = pd.DataFrame(some_data)
    ```

  - Upload your DataFrame to Jina AI Cloud using `<module>:<variable>` syntax
    
    ```bash
    lc-serve util upload-df dataframe:df
    ```

- Conversationalize your DataFrame using pandas-ai APIs. Get a flavor of the integration with a local playground on your CLI with 
  
  ```bash
  lc-serve playground pandas-ai <host>
  ```
  <details>
  <summary>Show playground</summary>
  <img src=".github/images/pandas-ai-playground.gif" title="pandas-ai-as-a-service Playground">
  </details>

</details>

## 💬 Question Answer Bot on PDFs

`pdfqna` is a simple question answering bot that uses LLMs to answer questions on PDF documents, showcasing the how easy it is to integrate langchain apps on Jina AI Cloud.

<details>
<summary>Show usage</summary>

- Deploy `pdf_qna` on Jina AI Cloud with one command

  ```bash
  lc-serve deploy pdf-qna
  ```

- Get a flavor of the integration with Streamlit playground on your CLI with 
    
  ```bash
  lc-serve playground pdf-qna
  ```
  <details>
  <summary>Show playground</summary>
  <img src=".github/images/pdf_qna_demo.gif" title="pdf_qna Playground">
  </details>

- Expand the Q&A bot to multiple languages, different document types & integrate with external services using simple REST APIs.

  https://github.com/jina-ai/langchain-serve/blob/8f7a9272e99490a5357655becfc5da3569655f38/lcserve/apps/pdf_qna/app.py#L8-L12

</details>

# 💪 Features

### 🎉 LLM Apps on production
  
  - 👉 **[Define your API using `@serving` decorator](#-rest-apis-using-serving-decorator)** 
  - 👉 **[Build, deploy & distribute Slack bots using `@slackbot` decorator](#-build-deploy--distribute-slack-bots-built-with-langchain)**
  - 👉 **[Bring your own FastAPI app](#-bring-your-own-fastapi-app)**

### 🔥 Secure, Scalable, Serverless, Streaming REST/Websocket APIs on [Jina AI Cloud](https://cloud.jina.ai/).

  - 🌎 Globally available REST/Websocket APIs with automatic TLS certs.
  - 🌊 Stream LLM interactions in real-time with Websockets.
  - 👥 Enable human in the loop for your agents.
  - 💬 Build, deploy & distribute Slack bots built with langchain.
  - 🔑 Protect your APIs with [API authorization](#-authorize-your-apis) using Bearer tokens. 
  - 📄 Swagger UI, and OpenAPI spec included with your APIs.
  - ⚡️ Serverless, autoscaling apps that scales automatically with your traffic.
  - 🗝️ Secure handling of secrets and environment variables.
  - 📁 Persistent storage (EFS) mounted on your app for your data.
  - ⏱️ Trigger one-time jobs to run asynchronously, allowing for non-blocking execution.
  - 📊 Builtin logging, monitoring, and traces for your APIs.
  - 🤖 No need to change your code to manage APIs, or manage dockerfiles, or worry about infrastructure!


### 🏠 Self-host LLM Apps with Docker Compose or Kubernetes

  - 🚀 Export your apps as Kubernetes or Docker Compose YAMLs with single command.
  - 👉 `lc-serve export app --kind <kubernetes/docker-compose> --path .`
  - 📦 Deploy your app on your own internal infrastructure with your own security policies.
  - 📞 [Talk to us if you need all the features of Jina AI Cloud on your own infrastructure.](#-reach-out-to-us)

# 🧰 Usage

Let's first install `langchain-serve` using pip.

```bash
pip install langchain-serve
```

## 🔄 REST APIs using `@serving` decorator

👉 Let's go through a [step-by-step guide](examples/rest/README.md) to build, deploy and use a REST API using `@serving` decorator.

---

## 🤖💬 Build, Deploy & Distribute Slack bots built with LangChain

langchain-serve exposes a `@slackbot` decorator to quickly build, deploy & distribute LLM-powered Slack bots without worrying about the infrastructure. It provides a simple interface to any langchain app on and makes them super accessible to users a platform they're already comfortable with.

✨ Ready to dive in? 

- There's a [step-by-step guide in the repository](lcserve/apps/slackbot/) to help you build your own bot for helping with reasoning.
- Here's another [step-by-step guide](examples/hrbot/README.md) to help you chat over own internal HR-realted documents (like onboarding, policies etc.) with your employees right inside your Slack workspace.

---

## 🔐 Authorize your APIs

To add an extra layer of security, we can integrate any custom API authorization by adding a `auth` argument to the `@serving` decorator. 

<details>
<summary>Show code & gotchas</summary>

```python
from lcserve import serving

def authorizer(token: str) -> Any:
    if not token == 'mysecrettoken':            # Change this to add your own authorization logic
        raise Exception('Unauthorized')         # Raise an exception if the request is not authorized

    return 'userid'                             # Return any user id or object

@serving(auth=authorizer)
def ask(question: str, **kwargs) -> str:
    auth_response = kwargs['auth_response']     # This will be 'userid'
    return ...

@serving(websocket=True, auth=authorizer)
async def talk(question: str, **kwargs) -> str:
    auth_response = kwargs['auth_response']     # This will be 'userid'
    return ...
```

##### 🤔 Gotchas about the `auth` function

- Should accept only one argument `token`.
- Should raise an Exception if the request is not authorized.
- Can return any object, which will be passed to the `auth_response` object under `kwargs` to the functions.
- Expects Bearer token in the `Authorization` header of the request.
- Sample HTTP request with `curl`:
  ```bash
  curl -X 'POST' 'http://localhost:8080/ask' -H 'Authorization: Bearer mysecrettoken' -d '{ "question": "...", "envs": {} }'
  ```
- Sample WebSocket request with `wscat`:
  ```bash
  wscat -H "Authorization: Bearer mysecrettoken" -c ws://localhost:8080/talk
  ```

</details>

---

## 🙋‍♂️ Enable streaming & human-in-the-loop (HITL) with WebSockets

HITL for LangChain agents on production can be challenging since the agents are typically running on servers where humans don't have direct access. **langchain-serve** bridges this gap by enabling websocket APIs that allow for real-time interaction and feedback between the agent and a human operator.

Check out this [example](examples/websockets/hitl/README.md) to see how you can enable HITL for your agents.

## 📁 Persistent storage on Jina AI Cloud

Every app deployed on Jina AI Cloud gets a persistent storage (EFS) mounted locally which can be accessed via `workspace` kwarg in the `@serving` function.

<details>
<summary>Show code</summary>

```python
from lcserve import serving

@serving
def store(text: str, **kwargs):
    workspace: str = kwargs.get('workspace')
    path = f'{workspace}/store.txt'
    print(f'Writing to {path}')
    with open(path, 'a') as f:
        f.writelines(text + '\n')
    return 'OK'


@serving(websocket=True)
async def stream(**kwargs):
    workspace: str = kwargs.get('workspace')
    websocket: WebSocket = kwargs.get('websocket')
    path = f'{workspace}/store.txt'
    print(f'Streaming {path}')
    async with aiofiles.open(path, 'r') as f:
        async for line in f:
            await websocket.send_text(line)
    return 'OK'
```

Here, we are using the `workspace` to store the incoming text in a file via the REST endpoint and streaming the contents of the file via the WebSocket endpoint.

</details>

## 🚀 Bring your own FastAPI app

If you already have a FastAPI app with pre-defined endpoints, you can use `lc-serve` to deploy it on Jina AI Cloud. 

```bash
lc-serve deploy jcloud --app filename:app 
```

<details>
<summary>Show details</summary>

Let's take an example of a simple FastAPI app with directory structure

```bash
.
└── endpoints.py
```

```python
# endpoints.py
from typing import Union

from fastapi import FastAPI

app = FastAPI()


@app.get("/status")
def read_root():
    return {"Hello": "World"}


@app.get("/items/{item_id}")
def read_item(item_id: int, q: Union[str, None] = None):
    return {"item_id": item_id, "q": q}
```

```bash
lc-serve deploy jcloud --app endpoints:app
```

</details>

## 🗝️ Using Secrets during Deployment

You can use secrets during app deployment by passing a secrets file to deployment with the `--secrets` flag. The secrets file should be a `.env` file containing the secrets.

```bash
lcserve deploy jcloud app --secrets .env
```

<details>
<summary>Show details</summary>

Let's take an example of a simple app that uses `OPENAI_API_KEY` stored as secrets.

This app directory contains the following files:

```
.
├── main.py             # The app
├── jcloud.yml          # JCloud deployment config file
├── README.md           # This README file
├── requirements.txt    # The requirements file for the app
└── secrets.env         # The secrets file containing the redis credentials
```

> **Note**
> `secret.env` in this directory is a dummy file. You should replace it with your own secrets after creating a Redis instance. (For example with [Upstash](https://upstash.com/)), such as:

```text
OPENAI_API_KEY=sk-xxx
```

`main.py` will look like:

```python
# main.py
from lcserve import serving
from langchain.prompts import PromptTemplate
from langchain.chains import LLMChain
from langchain.chat_models import ChatOpenAI

prompt = PromptTemplate(
    input_variables=["subject"],
    template="Write me a short poem about {subject}?",
)


@serving(openai_tracing=True)
def poem(subject: str, **kwargs):
    tracing_handler = kwargs.get("tracing_handler")

    chat = ChatOpenAI(temperature=0.5, callbacks=[tracing_handler])
    chain = LLMChain(llm=chat, prompt=prompt, callbacks=[tracing_handler])

    return chain.run(subject)
```

In the above example, the app will use `OPENAI_API_KEY` provided by the secrets to interact with OpenAI.

Then you can deploy using the following command and interact with the deployed endpoint.

```bash
lc-serve deploy jcloud main --secrets secrets.env
```

</details>

## ⏱️ Trigger one-time jobs to run asynchronously

Here's a [step-by-step guide](examples/job/README.md) to trigger one-time jobs to run asynchronously using `@job` decorator.

## 💻 `lc-serve` CLI

`lc-serve` is a simple CLI that helps you to deploy your agents on Jina AI Cloud (JCloud) 


| Description | Command | 
| --- | ---: |
| Deploy your app locally | `lc-serve deploy local app` |
| Export your app as Kubernetes YAML | `lc-serve export app --kind kubernetes --path .` |
| Export your app as Docker Compose YAML | `lc-serve export app --kind docker-compose --path .` |
| Deploy your app on JCloud | `lc-serve deploy jcloud app` |
| Deploy FastAPI app on JCloud | `lc-serve deploy jcloud --app <app-name>:<app-object>` |
| Update existing app on JCloud | `lc-serve deploy jcloud app --app-id <app-id>` |
| Get app status on JCloud | `lc-serve status <app-id>` |
| List all apps on JCloud | `lc-serve list` |
| Remove app on JCloud | `lc-serve remove <app-id>` |
| Pause app on JCloud | `lc-serve pause <app-id>` |
| Resume app on JCloud | `lc-serve resume <app-id>` |

# 💡 JCloud Deployment
## ⚙️ Configurations

For JCloud deployment, you can configure your application infrastructure by providing a YAML configuration file using the `--config` option. The supported configurations are:

  - Instance type (`instance`), as defined by [Jina AI Cloud](https://docs.jina.ai/concepts/jcloud/configuration/#cpu-tiers).
  - Minimum number of replicas for your application (`autoscale_min`). Setting it 0 enables [serverless](https://en.wikipedia.org/wiki/Serverless_computing).
  - Disk size (`disk_size`), in GB. The default value is 1 GB.

For example:

```
instance: C4
autoscale_min: 0
disk_size: 1.5G
```

You can alternatively include a `jcloud.yaml` file in your application directory with the desired configurations. However, please note that if the `--config` option is explicitly used in the command line interface, the local jcloud.yaml file will be disregarded. The command line provided configuration file will take precedence.

If you don't provide a configuration file or a specific configuration isn't specified, the following default settings will be applied: 

```
instance: C3
autoscale_min: 1
disk_size: 1G
```

## 💰 Pricing

Applications hosted on JCloud are priced in two categories:

**Base credits**

- Base credits are charged to ensure high availability for your application by maintaining at least one instance running continuously, ready to handle incoming requests. If you wish to stop the serving application, you can either remove the app completely or put it on pause, the latter allows you to resume the app serving based on persisted configurations (refer to [`lc-serve` CLI section](#-lc-serve-cli) for more information). Both options will halt the consumption of credits.
- Actual credits charged for base credits are calculated based on the [instance type as defined by Jina AI Cloud](https://docs.jina.ai/concepts/jcloud/configuration/#cpu-tiers).
- By default, instance type `C3` is used with a minimum of 1 instance and [Amazon EFS](https://aws.amazon.com/efs/) disk of size 1G, which means that if your application is served on JCloud, you will be charged ~10 credits per hour.
- You can change the instance type and the minimum number of instances by providing a YAML configuration file using the `--config` option. For example, if you want to use instance type `C4` with a minimum of 0 replicas, and 2G EFS disk, you can provide the following configuration file:
  ```yaml
  instance: C4
  autoscale_min: 0
  disk_size: 2G
  ```

**Serving credits**

- Serving credits are charged when your application is actively serving incoming requests.
- Actual credits charged for serving credits are calculated based on the credits for the instance type multiplied by the duration for which your application serves requests. 
- You are charged for each second your application is serving requests.


**Total credits charged = Base credits + Serving credits**. ([Jina AI Cloud](https://cloud.jina.ai/pricing) defines each credit as €0.005)

### Examples

<details>
<summary><b>Example 1</b></summary>

Consider an HTTP application that has served requests for `10` minutes in the last hour and uses a custom config:
```
instance: C4
autoscale_min: 0
disk_size: 2G
```

Total credits per hour charged would be `3.33`. The calculation is as follows:
```
C4 instance has an hourly credit rate of 20.
EFS has hourly credit rate of 0.104 per GB.
Base credits = 0 + 2 * 0.104 = 0.208 (since `autoscale_min` is 0)
Serving credits = 20 * 10/60 = 3.33
Total credits per hour = 0.208 + 3.33 = 3.538
```

</details>


<details>
<summary><b>Example 2</b></summary>

Consider a WebSocket application that had active connections for 20 minutes in the last hour and uses the default configuration.
```
instance: C3
autoscale_min: 1
disk_size: 1G
```

Total credits per hour charged would be `13.33`. The calculation is as follows:
```
C3 instance has an hourly credit rate of 10.
EFS has hourly credit rate of 0.104 per GB.
Base credits = 10 + 1 * 0.104 = 10.104 (since `autoscale_min` is 1)
Serving credits = 10 * 20/60 = 3.33
Total credits per hour = 10.104 + 3.33 = 13.434
```

</details>

# ❓ Frequently Asked Questions

- [`lc-serve` command not found](#lc-serve-command-not-found)
- [My client that connects to the JCloud hosted App gets timed-out, what should I do?](#my-client-that-connects-to-the-jcloud-hosted-app-gets-timed-out-what-should-I-do)
- [How to pass environment variables to the app?](#how-to-pass-environment-variables-to-the-app)
- [JCloud deployment failed at pushing image to Jina Hubble, what should I do?](#jcloud-deployment-failed-at-pushing-image-to-jina-hubble-what-should-i-di)
- [Debug babyagi playground request/response for external integration](#debug-babyagi-playground-requestresponse-for-external-integration)

### `lc-serve` command not found

<details>
<summary><b>Expand</b></summary>

`lc-serve` command is registered during `langchain-serve` installation. If you get `command not found: lc-serve` error, please replace `lc-serve` command with `python -m lcserve` & retry.
  
</details>

### My client that connects to the JCloud hosted App gets timed-out, what should I do?

<details>
<summary><b>Expand</b></summary>

If you make long HTTP/ WebSocket requests, the default timeout value (2 minutes) might not be suitable for your use case. You can provide a custom timeout value during JCloud deployment by using the `--timeout` argument.

Additionally, for HTTP, you may also experience timeouts due to limitations in the OSS we used in `langchain-serve`. While we are working to permanently address this issue, we recommend using HTTP/1.1 in your client as a temporary workaround.

For WebSocket, please note that the connection will be closed if idle for more than 5 minutes.

</details>

### How to pass environment variables to the app?

<details>
<summary><b>Expand</b></summary>

We provide 2 options to pass environment variables:

1. Use `--env` during app deployment to load env variables from a `.env` file. For example, `lc-serve deploy jcloud app --env some.env` will load all env variables from `some.env` file and pass them to the app. These env variables will be available in the app as `os.environ['ENV_VAR_NAME']`.

2. You can also pass env variables while sending requests to the app both in HTTP and WebSocket. `envs` field in the request body is used to pass env variables. For example
  
    ```json
    {
        "question": "What is the meaning of life?",
        "envs": {
            "ENV_VAR_NAME": "ENV_VAR_VALUE"
        }
    }
    ```

</details>

### JCloud deployment failed at pushing image to Jina Hubble, what should I do?

<details>
<summary><b>Expand</b></summary>

Please use `--verbose` and retry to get more information. If you are operating on computer with `arm64` arch, please retry with `--platform linux/amd64` so the image can be built correctly.

</details>

### Debug babyagi playground request/response for external integration

<details>
<summary><b>Expand</b></summary>
1. Start textual console in a terminal (exclude following groups to reduce the noise in logging)
    
    ```bash
    textual console -x EVENT -x SYSTEM -x DEBUG
    ```

2. Start the playground with `--verbose` flag. Start interacting and see the logs in the console.
    
    ```bash
    lc-serve playground babyagi --verbose
    ```

</details>

# 📣 Reach out to us

Want to deploy your LLM apps on your own infrastructure with all capabilities of Jina AI Cloud? 

  - Serverless
  - Autoscaling
  - TLS certs
  - Persistent storage
  - End to end LLM observability
  - and more on auto-pilot!

[Join us on Discord](https://discord.jina.ai) and we'd be happy to hear more about your use case.
