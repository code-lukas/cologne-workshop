# Help us help you

- Incomplete issues will not be worked on
- Do **not** post pictures of code or error messages if you can copy and paste them instead
- Do your best to isolate the error and provide a minimal working example
- Do provide log files/code if possible
- Keep separate issue separate: Do **not** combine multiple issues in one post

## Description

This paragraph should contain a concise description of your problem:

What is the general task you are trying to achieve?

### Bad

I get the following error:

ModuleNotFoundError: No module named 'numpy'

### Good

I am running a model training of the following model: <https://detectron2.readthedocs.io/en/latest/>  
The container used on KITE is `kubeflownotebookswg/codeserver-python:v1.7.0`

The full error message is as follows:

```bash
(base) user@project:~# python3 train.py --some-argument=42 --some-flag=False
ModuleNotFoundError: No module named 'numpy'
```

## Steps to reproduce

1. `git clone [repository_name]`
2. `git checkout [branch/feature]`
3. etc.

## Expected behavior

Detailed description of expected behavior. Don't write statements like 'I expect it to work'.
Instead, be as precise as possible.
