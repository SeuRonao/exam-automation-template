# Exam Automation Template

Files for exams done with [AMC](https://www.auto-multiple-choice.net/) latex package.

There is an extensive documentation on how to use AMC [here](https://www.auto-multiple-choice.net/auto-multiple-choice.en/).

There was an effort to avoid repetition of questions, so the questions are stored in a separate file and imported to the exam file.

Some questions use lua code to generate random numbers, so the questions are different for each student.
These questions depend on having [LuaLaTex](https://www.luatex.org/) installed.

Some questions use python code to generate random numbers, so the questions are different for each student.
These questions depend on having [Python](https://www.python.org/) installed and the LaTex distribution having the [PythonTex](https://github.com/gpoore/pythontex) package.

## Requirements

- [AMC](https://www.auto-multiple-choice.net/)
- [LaTex](https://www.latex-project.org/) distribution (e.g. [TexLive](https://www.tug.org/texlive/))
- [LuaLaTex](https://www.luatex.org/) (optional if you don't use questions with lua code)
- [Python](https://www.python.org/) (optional if you don't use questions with python code)
  - [Numpy](https://numpy.org/) (optional if you don't use questions with python code that use it)
  - [Scipy](https://www.scipy.org/) (optional if you don't use questions with python code that use it)

For keeping versions of the exams, it is recommended to use a version control system like [Git](https://git-scm.com/).

For keeping the `python` code well formatted, it is recommended to use a code linters and formatters like [Black](https://github.com/psf/black), [isort](https://pycqa.github.io/isort/) and [pylint](https://github.com/pylint-dev/pylint).

For keeping the `latex` code well formatted, it is recommended to use a code linters and formatters like [latexindent.pl](https://ctan.org/pkg/latexindent?lang=en) and [chktex](https://www.nongnu.org/chktex/).
The `.chktexrc` file provide some defaults that work well with the template.

## Usage

1. Clone/Fork/Create the repository
2. Create code for the questions in the `questions` folder
3. Import the questions in the `source.tex` file
4. Add the questions to the exam using the `\copygroup` command so that the exam uses the same questions for all students, while allowing each question to have different numbers for each student.
5. Compile the exam to see if it works.
    If you are using `LuaLaTex` or `Python`, you may need to compile the exam multiple times.
    For example:
    ```bash
    lualatex source.tex
    pythontex source.tex
    lualatex source.tex
    ```
6. Create a new project in AMC and use the `source.tex` file as the source for the exam.
7. Remember to change all the path to absolute path in order for the file `source.tex` inside the AMC project to find the files in the `questions` folder.
8. Proceed as usual with AMC.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
