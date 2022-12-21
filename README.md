# adsf-direnv-test

This is a test of asdf version manager's workflow with direnv.

## When starting a new project:
```zsh
# create repo
git init

# create .gitignore
echo .direnv/ > .gitignore

# create .tool_versions
asdf local python latest

# create venv
echo "layout python" > .envrc
direnv allow

# install packages
pip install pendulum

# export requirements
pip freeze > requirements.txt
```

## When working on an existing project:
```zsh
# clone repo
git clone https://...

# install python
asdf install

# create venv
echo "layout python" > .envrc
direnv allow

# install packages
pip install -r requirements.txt

# make binaries accessible from PATH
asdf reshim python
```

# Environment Variables

Environment variables are set in `.envrc`, there is no need for `.env`.

```
layout python

export API_KEY=123
```