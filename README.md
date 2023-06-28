# Exam Automation Template

Files for exams done with [AMC](https://www.auto-multiple-choice.net/) latex package.

There is an extensive documentation on how to use AMC [here](https://www.auto-multiple-choice.net/auto-multiple-choice.en/).

There was an effort to avoid repetition of questions, so the questions are stored in a separate file and imported to the exam file.

Some questions use lua code to generate random numbers, so the questions are different for each student.
These questions depend on having [LuaLaTex](https://www.luatex.org/) installed.

Some questions use python code to generate random numbers, so the questions are different for each student.
These questions depend on having [Python](https://www.python.org/) installed and the LaTex distribution having the [PythonTex](https://github.com/gpoore/pythontex) package.
