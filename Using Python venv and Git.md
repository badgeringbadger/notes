# Python venv and Git 

| Document Information
| --------------------
| Author: Todd Fiedler
| Revised: 4/5/2022

## Description

Using Python venv and git on Windows

## Examples

I use Windows so my commands reflect that. If you don't, you'll have to sort them out.

1. setup the environment in the project folder

```
cd %HOMEPATH%\source\projectname
python3 -m venv .venv
```

2. add .venv to your .gitignore
3. use it

```
cd %HOMEPATH%\source\projectname
.venv\Scripts\activate.bat
```

4. Stop using it - of course, the expectation is that you are IN a venv when you run this command

```
deactivate
```




