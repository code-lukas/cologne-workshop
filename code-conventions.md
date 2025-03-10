# Spaghetti code sucks - a case for writing clean, readable code
## My code runs just fine, why should I read this?
Adhering to code style guidelines is about more than just writing code that runs. Recount how many lines of poorly documented, ill-formatted code you have read in your life: do you recall this as a joyful experience? Simple checks before commiting / pushing code to a repository allows you to focus on tasks at hand, and spend less time on understanding, maintaining and refactoring code.  
  
**We can all write code that runs, but following conventions allows you to make the transition from writing code purely for yourself to writing code for yourself and others.**

This document is meant to **convince** you that this is an endeavour worth your time and not to let you feel like joining a cult or like you are in an encounter with Jehova's witnesses at your doorstep.  
In most programming languages, there is more than one way of doing things.
Languages like Python are well aware of this and serve you the meaningful, yet a little esoteric ``Zen of Python`` when prompted.  
Open a terminal and type

```sh
python3 -c "import this"
```

This will show you the following:

```
The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```

A few lines stand out in this context:  
1. ``Readability counts.``
2. ``Special cases aren't special enough to break the rules.``
3. ``In the face of ambiguity, refuse the temptation to guess.``
4. ``If the implementation is hard to explain, it's a bad idea.``
5. ``If the implementation is easy to explain, it may be a good idea.``

A few less vague recommendations may come in handy for everyone who isn't Dutch, but let's conclude with a short summary first.

## TLDR: __Following a predefined set of rules (that everybody agrees on) comes with a responsibility that gives you benefits in return__

Responsibilities:
- You take accountability for the code that you write and the commits you push
- You follow the conventions of your project group to the best of your abilities

Benefits:
- The code in a joint project will be easy to read and thus easier to understand
- Consequently, you will spend less time on refactoring, debugging and maintaining code
- Your codebase will look presentable and professional to anyone looking at your code. In this context it doesn't matter if this is a potential business partner, a higher-up, a colleague, a collaborator or - if you are a student - a supervisor grading your work

## Count me in, how do I proceed?

First, ask yourself if you are writing code for yourself or production code.  
Ideally, the task at hand shouldn't determine the quality of the code you write, but personal projects as well as research can already be hectic enough.  
The guiding question should be: Will someone other than me read this code?  
If your answer is ''no'', the following steps may not be strictly necessary in your case, but they won't hurt you.

## Three steps to success
1. Code formatting: `black`  
`black` is a code formatting tool that is readily available as a plugins for most IDEs.
It removes the need to manually format your code by e.g. running in the background or via a pre-commit hook.

2. Code style validation: `ruff`  
`ruff` is a tool that checks your code regarding its syntax and provides instructions on how to improve it. It
includes many popular tools (like e.g. `pydocstyle`) in one joint framework written in Rust. Contrary to e.g. `flake8`,
`ruff` is able to fix a multitude of occurring problems on its own, removing the need for tedious manual correction in 
a lot of cases.

3. Git best practices & conventional commits
   - Fork the Project
   - Create your feature branch (`git checkout -b feature/AmazingFeature`)
   - Commit your changes (`'git commit -m 'feat: Add some amazing feature'`)
        - Use [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/) either via a plugin for your IDE of choice or via a pre-commit hook 
   - Push to the branch (`git push origin feature/AmazingFeature`)
   - Open a Pull Request

>You feel like this missing something? Let's talk about it!

## Installation guide:
1. Install `pre-commit`
```sh
pip install pre-commit
```
(Optional: Add `pre-commit` to your `requirements.txt`)

3. Configure and add `.pre-commit-config.yaml` to the root of your project  
An exemplary `.pre-commit-config.yaml` with suggested configurations can be found [here](./.pre-commit-config.yaml).

4. Run
```sh
pre-commit install
```
5. Done!  
That's it, you are good to go!
