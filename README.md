# Autogen
A framework that enables the development of LLM applications using multiple agents that can converse with each other to solve tasks. [More](https://github.com/microsoft/autogen/tree/main)

![](https://github.com/natnew/Autogen/blob/main/Images/autogen_agentchat.png)

## 👋 Welcome! 
Welcome to this "Autogen" GitHub repository! AutoGen is a powerful framework designed to empower the development of Large Language Model (LLM) applications that thrive on collaboration between multiple agents. These agents are not only customizable and conversable but also seamlessly integrate human participation into the process. With AutoGen, you can create applications that can tackle a wide range of tasks by combining the strengths of LLMs, human inputs, and specialized tools. [Original Repo](https://github.com/microsoft/autogen)

## ⭐ Before getting started:

    🍴 To incorporate this repository into your own project, you can fork it. 
    ⭐ In order to receive notifications about future improvements, please consider starring this repository.

## Examples

#### Notebook - agentchat_groupchat.ipynb <br>
> **User_proxy (to chat_manager):** = Find a latest paper about gpt-4 on arxiv and find its potential applications in software.`<br><br>
 
> **Coder (to chat_manager):** Sure. First, we need to browse Arxiv to search for the latest papers mentioning "gpt-4". Python's BeautifulSoup package and the requests module can be used to parse the HTML of the search results page. Here's a script that queries Arxiv for "gpt-4" and prints the title, author, and short summary of the most recent paper that comes up...
<br><br>

```Python is the scripting language used in the following block
# filename: arxiv_search.py
import requests
from bs4 import BeautifulSoup
import re

# send a GET request to Arxiv's search page with "gpt-4" as the query string
response = requests.get('https://arxiv.org/search/?query=gpt-4&searchtype=all&abstracts=show&order=-announced_date_first&size=25')

# parse the response content with BeautifulSoup
soup = BeautifulSoup(response.content, 'html.parser')

# find the first paper in the search results
results = soup.find('li', class_='arxiv-result')
if results is None:
    print("No paper found")
else:
    title = results.find('p', class_='title is-5 mathjax').text.strip()
    authors = results.find('p', class_='authors').text.strip()
    summary = results.find('span', class_='abstract-full has-text-grey-dark mathjax').text.strip()
    submitted_date = results.find('p', class_='is-size-7').text.strip()

    print(f'Paper Title: {title}\nAuthors: {authors}\nSummary: {summary}\nSubmission Date: {submitted_date}')
```
> Please run the python script by using the command `python arxiv_search.py`. The script will print the details about the latest paper related to GPT-4. After you get the latest paper's title and summary, we can proceed to the next step regarding potential applications in software.

> **Product_manager (to chat_manager):** The latest paper titled "JudgeLM: Fine-tuned Large Language Models are Scalable Judges" offers a wealth of potential applications in software. The paper essentially talks about using Large Language Models (LLMs) to evaluate other LLMs in open-ended scenarios, including the creation of a comprehensive dataset and new benchmark for evaluating these models.Based on this premise, here are potential applications in software: <br><br>

> 1. **Automated Code Review**: LLMs like JudgeLM could be used to assess the quality and efficiency of code written by developers, offering suggestions for improvements or identifying potential bugs and anti-patterns.
> 2. **Real-time AI Feedback**: In real-time AI applications involving user interaction, such as chatbots or virtual assistants, JudgeLM can be leveraged to perform ongoing reviews of the system's responses, identifying potential issues and suggest improvements. 
> 3. **Quality Assurance**: JudgeLM can assist in the QA process by evaluating LLMs output in software products. By assessing the LLMs performance in real-world application scenarios, this can promote the improvement of overall product quality.
> 4. **Multimodal Model Evaluation**: As noted in the paper, JudgeLM could be used to evaluate multimodal models, which integrate multiple types of data (like text, images, and sounds). In the software industry, such models are increasingly important for fields like computer vision and natural language processing.
> 5. **Improvement of AI Models**: By building software that incorporates JudgeLM for evaluating and fine-tuning AI models, the quality and efficiency of these models could be enhanced.
>
> Thus, considering the paper's content, several existing and potential applications could be enriched.


#### Notebook - agentchat_teaching.ipynb <br>



## Setup
- You can create a virtual environment with venv: `python3 -m venv autogen` `source autogen/bin/activate`. Another option is with Conda, `conda create -n autogen python=3.10  # python 3.10 is recommended as it's stable and not too old` `conda activate autogen`
- AutoGen requires Python version >= 3.8. It can be installed from pip: `pip install pyautogen`

## Documentation

- [Research](https://microsoft.github.io/autogen/docs/Research), [blogposts](https://microsoft.github.io/autogen/blog) 

- [Transparency FAQs](https://github.com/microsoft/autogen/blob/main/TRANSPARENCY_FAQS.md)

- [Discord](https://discord.gg/pAbnFJrkgZ)

- [Contributing guide](https://microsoft.github.io/autogen/docs/Contribute)

- [Roadmap](https://github.com/orgs/microsoft/projects/989/views/3)

- [FLAML](https://github.com/microsoft/FLAML)

- [Getting Started](https://microsoft.github.io/autogen/docs/Getting-Started)

- [Installation](https://microsoft.github.io/autogen/docs/Installation)

- [Multi-agent Conversation Framework](https://microsoft.github.io/autogen/docs/Use-Cases/agent_chat)

- [Enhanced Inference](https://microsoft.github.io/autogen/docs/Use-Cases/enhanced_inference/)

- [SDK](https://microsoft.github.io/autogen/docs/reference/agentchat/groupchat)


## Research

- [AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation Framework.](https://arxiv.org/abs/2308.08155) Qingyun Wu, Gagan Bansal, Jieyu Zhang, Yiran Wu, Shaokun Zhang, Erkang Zhu, Beibin Li, Li Jiang, Xiaoyun Zhang and Chi Wang. ArXiv 2023.<br>
- [An Empirical Study on Challenging Math Problem Solving with GPT-4.](https://arxiv.org/abs/2306.01337) Yiran Wu, Feiran Jia, Shaokun Zhang, Hangyu Li, Erkang Zhu, Yue Wang, Yin Tat Lee, Richard Peng, Qingyun Wu, Chi Wang. ArXiv preprint arXiv:2306.01337 (2023).<br>


