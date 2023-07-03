# MetaGPT: The Multi-Role Meta Programming Framework

[English](./README.md) / [中文](./README_CN.md)

[![Discord Follow](https://dcbadge.vercel.app/api/server/wCp6Q3fsAk?compact=true&style=flat)](https://discord.gg/wCp6Q3fsAk)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Currently, we have managed to enable GPT to work in software company, collaborating to tackle more complex tasks.

1. The team can handle **Boss's one line Requirement** cooperate and generate **user stories / competetive analysis / requirements / data structures / apis / files etc.**
2. The team consists of **product manager / architect / project manager / engineer**, it provides the full process of a **software company.**

![A software company consists of LLM-based roles](./resources/software_company_cd.jpeg)

## Examples (fully generated by GPT-4)

For example, if you type `python startup.py "Design a RecSys like Toutiao"`, you would get many outputs, one of them is data & api design

![Jinri Toutiao Recsys Data & API Design](resources/workspace/content_rec_sys/resources/data_api_design.png)

It requires around **$0.2** (GPT-4 api's costs) to generate one example with analysis and design, around **$2.0** to a full project.

## Installation

```bash
# Step 1: Ensure that NPM is installed on your system. Then install mermaid-js.
npm --version
sudo npm install -g @mermaid-js/mermaid-cli

# Step 2: Ensure that Python 3.9+ is installed on your system. You can check this by using:
python --version

# Step 3: Clone the repository to your local machine, and install it.
git clone https://github.com/geekan/metagpt
cd metagpt
python setup.py install
```

## Configuration

- Configure your `OPENAI_API_KEY` in any of `config/key.yaml / config/config.yaml / env`
- Priority order: `config/key.yaml > config/config.yaml > env`

```bash
# Copy the configuration file and make the necessary modifications.
cp config/config.yaml config/key.yaml
```

| Variable Name                              | config/key.yaml                           | env                            |
|--------------------------------------------|-------------------------------------------|--------------------------------|
| OPENAI_API_KEY # Replace with your own key | OPENAI_API_KEY: "sk-..."                  | export OPENAI_API_KEY="sk-..." |
| OPENAI_API_BASE # Optional                            | OPENAI_API_BASE: "https://<YOUR_SITE>/v1" | export OPENAI_API_BASE="https://<YOUR_SITE>/v1"   |

## Tutorial: Initiating a startup

```shell
python startup.py "Write a cli snake game"
```

After running the script, you can find your new project in the `workspace/` directory.

### Code walkthrough

```python
from metagpt.software_company import SoftwareCompany
from metagpt.roles import ProjectManager, ProductManager, Architect, Engineer

async def startup(idea: str, investment: str = '$3.0', n_round: int = 5):
    """Run a startup. Be a boss."""
    company = SoftwareCompany()
    company.hire([ProductManager(), Architect(), ProjectManager(), Engineer()])
    company.invest(investment)
    company.start_project(idea)
    await company.run(n_round=n_round)
```

You can check `examples` for more details on single role (with knowledge base) and LLM only examples.

## Contact Information

If you have any questions or feedback about this project, please feel free to contact us. We highly appreciate your suggestions!

- **Email:** alexanderwu@fuzhi.ai
- **GitHub Issues:** For more technical inquiries, you can also create a new issue in our [GitHub repository](https://github.com/geekan/metagpt/issues).

We will respond to all inquiries within 2-3 business days.

## Demo

https://github.com/geekan/MetaGPT/assets/2707039/5e8c1062-8c35-440f-bb20-2b0320f8d27d
