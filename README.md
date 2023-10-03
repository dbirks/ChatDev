# ChatDev playground

Original readme: [README.upstream.md](./README.upstream.md)

## Setup

Start the vscode devcontainer if you'd like. And then:

```
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

export OPENAI_API_KEY=blah

python run.py --task "Create a NextJS app that displays Github PRs for a given user." --name pr_viewer_1
```

## Log of runs

### Run 1

Prompt:

```
python run.py --task "Create a NextJS app that displays Github PRs for a given user." --name pr_viewer_1
```

Code: [WareHouse/pr_viewer_1_DefaultOrganization_20231003035722](./WareHouse/pr_viewer_1_DefaultOrganization_20231003035722/)

Comments: Didn't make a nextjs app. I think the index.js file it made might've run if there was a package.json with `type` set to `module`. Had weird other files in there, like a plain `.py` file with the nextjs starter npx command as a string.

### Run 2

Prompt:

```
python run.py --task "Create a full NextJS app in TypeScript that lists Github PRs for a given user." --name pr_viewer_2
```

Code: [WareHouse/pr_viewer_2_DefaultOrganization_20231003041042](./WareHouse/pr_viewer_2_DefaultOrganization_20231003041042/)

Comments: Crashed pretty early on with the error:

```
Traceback (most recent call last):
  File "/workspaces/ChatDev/run.py", line 111, in <module>
    chat_chain.execute_chain()
  File "/workspaces/ChatDev/chatdev/chat_chain.py", line 160, in execute_chain
    self.execute_step(phase_item)
  File "/workspaces/ChatDev/chatdev/chat_chain.py", line 130, in execute_step
    self.chat_env = self.phases[phase].execute(self.chat_env,
                    ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/workspaces/ChatDev/chatdev/phase.py", line 304, in execute
    chat_env = self.update_chat_env(chat_env)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/workspaces/ChatDev/chatdev/phase.py", line 356, in update_chat_env
    raise ValueError("No Valid Codes.")
ValueError: No Valid Codes.
```

### Run 3

Prompt:

```
python run.py --task "Create a single page app that displays the current distance from Earth to the planet Jupiter. 
Use TypeScript, React, and Vite, as well as any other libraries or tools that you think would be good to include." --name basic_site_1
```

