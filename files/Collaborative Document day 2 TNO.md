![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document day 2

2024-07-02 Good practices in research software development @ TNO

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

This is the Document for today: https://tinyurl.com/good-practices-2

Collaborative Document day 1: https://tinyurl.com/good-practices-1

Collaborative Document day 2: https://tinyurl.com/good-practices-2

##  🫱🏽‍🫲🏻 Code of Conduct

Participants are expected to follow these guidelines:
* Use welcoming and inclusive language.
* Be respectful of different viewpoints and experiences.
* Gracefully accept constructive criticism.
* Focus on what is best for the community.
* Show courtesy and respect towards other community members.
 
## ⚖️ License

All content is publicly available under the Creative Commons Attribution License: [creativecommons.org/licenses/by/4.0/](https://creativecommons.org/licenses/by/4.0/).

## 🙋Getting help

To ask a question, just raise your hand.

If you need help from a helper, place a pink post-it note on your laptop lid. A helper will come to assist you as soon as possible.

## 🖥 Workshop website

https://esciencecenter-digital-skills.github.io/2024-07-02-ds-cr-tno/

🛠 Setup

https://esciencecenter-digital-skills.github.io/2024-07-02-ds-cr-tno/#setup

## 👩‍🏫👩‍💻🎓 Instructors

Sven van der Burg, Dani Bodor, John Hidding, Olga Lyashevska

## 🗓️ Agenda
* 09:30	Welcome and icebreaker
* 09:35 Recap yesterday (specifically about linting & code style conventions)
* 09:40 Virtual environments, dependencies & templates
* 09:45	Documentation
* 10:30	Coffee break
* 10:45	Introduction to testing
* 11:30	Coffee break
* 11:45	Introduction to testing
* 12:30	Lunch Break
* 13:30	Introduction to Continuous Integration
* 14:15	Coffee break
* 14:30	Introduction to Continuous Integration
* 15:15	Coffee break
* 15:30	Q&A
* 16:15	Wrap-up
* 16:30	END

## 🏢 Location logistics
* Coffee
* Toilets
* Wifi
* Emergency exit

## 🎓 Certificate of attendance
If you attend the full workshop you can request a certificate of attendance by emailing to training@esciencecenter.nl.
Please request your certificate within 8 months after the workshop, as we will delete all personal identifyable information after this period.

## Start
- Icebreaker
- Feedback yesterday
- Questions (linting + code style conventions)

## ❄️ Icebreaker: Good practices 30 seconds
### Score board
| **Group** | round 1 | round 2 | round 3 | Total |
|-----------|---------|---------|---------|-------|
| 1         |   5     |    3    |    2    |  10   |
| 2         |   4     |    3    |    4    |  11   |
| 3         |   2     |    2    |    2    |   6   |
| 4         |   5     |    1    |    2    |   8   |
| 5         |   1     |    2    |    3    |   6   |
| 6         |   4     |    1    |    3    |   8   |
| 7         |   4     |    0    |    4    |   8   |
| 8         |   4     |    2    |    3    |   9   |

### Round 1
- Linter
- Modular code
- TNO
- Commit
- The blue curve

### Round 2
- Code style conventions
- Software architecture
- Reproducibility
- The terminal
- Merge request

### Round 3
- Reusability
- Code smell
- `temperature_conversion.py`
- Peer review
- `git push`

## 🔧 Exercises
### Exercise: Think of good and bad examples 
Write down your thoughts in the collaborative documents.
Respond with emojis :+1: :scream_cat: to your colleagues' answers.
- Think of projects of which you like the documentation. What do you like about them?
- Think of projects for which you don’t like the documentation. What don’t you like about them? Are you missing anything?

**NB: You can choose a mature library with lots of users for this exercise, but try to also think of less mature projects you had to collaborate on, or papers you had to reproduce.**

- group 1:
    - Good documentation: 
        - Commenting functions (More clear what a function does)
        - Documentation of in- and output files of the code
    - Bad documentation:
        - Scattered documents all over the place
        - Un-maintained / un-updated documentation
- group 2:
    - good:
        - https://plotly.com/python/plotly-express/
            - lots of explanation and examples
            - 
    - bad: 
        - matplotlib lists all parameters but rarely gives examples directly. You have to hunt them down
- group 3:
    - good: [`pandas`](https://pandas.pydata.org/docs/reference/index.html)
        - Good explanation of all function arguments
        - Nice examples
    - good: [`nicegui`](https://nicegui.io/documentation)
        - Shows brief input and the output, with the option to see the full input options.
    - less good, but still OK: [`polars`](https://docs.pola.rs/api/python/stable/reference/index.html)
        - Shorter explanation of arguments, still complete, but assumes certain knowledge
    - less good:[`matplotlib`](https://matplotlib.org/stable/api/index.html):
        - Nested properties are hard to find, you need to click through a lot of layers before you find the way to change the properties you want to change in e.g. a scatter plot.
- group 4:
    - Good: clear explanation at begin of a function with the goal of the function, the required input and the output (including units).
    - Improvement possible: To much explanation of what code is doing which should already be already clear when you write good/clear code.
- group 5:
    - Poor examples: 
        - Not self-explantory variable names and typing: (https://2021.help.altair.com/2021/hwdesktop/hwd/topics/reference/tcl/tcl_tk_syntax_r.htm)  
    - Good examples:
        - Doc-strings explaining the functions (https://developer.rhino3d.com/api/RhinoScriptSyntax/#curve-CloseCurve)
        - Inclusion of doxygen/mermaid to show the software layout/markdown graph (https://github.blog/2022-02-14-include-diagrams-markdown-files-mermaid/)
            - https://pypi.org/project/python-mermaid/
            - https://www.doxygen.nl/manual/docblocks.html
        - Inclusion of examples with the code: 
            - https://pandas.pydata.org/docs/reference/api/pandas.pivot.html#pandas.pivot
- group 6:
    - Good example: Technical documentation guide and validation guide, CFAST
    - Bad example: Older versions of documentation indexed on google
- group 7: 
    - Good examples: 
        - Docstring compatible with intellisense
        - Up to date readme files 
        - Matlab, numpy, scipy.
        - Expected types if not strongly typed
        - Code snippets as example
    - Bad examples:
        - Qt
        - Our own projects which use code without comments
        - Unreadable with few comments
- group 8: 
    - We like when it is user friendly / pretty. (plotly)
    - It needs a list of all functions, their use, and an *example* 
    - Docstrings
    - Has a very specific purpose (eurostat)

### Exercise: Pytest

In the code below (as in slides)

1. Add a test to catch "problematic" behavior of the function.
    - don't fix the function (yet)
2. Run pytest to see what the response looks like. 
    - what information can you gather from the response?
3. Fix the function and rerun the test


```python
def fahrenheit_to_celsius(temp_list, converted_temps=[]):
    for temp in temp_list:
        temp_c = (temp - 32.0) * (5.0/9.0)
        converted_temps.append(temp_c)
    return converted_temps

def test_convert():
    assert fahrenheit_to_celsius([32.0, 77.0]) == [0.0, 25.0]
    assert (fahrenheit_to_celsius([100], converted_temps = [0.0, 25.0])
            == [0.0, 25.0, 37.77777777777778])
```

### Exercise: Test-driven development

The function `fizz_buzz()` takes an integer argument and returns it, BUT:

- It fails on zero or negative numbers
- It returns "Fizz" on multiples of 3
- It returns "Buzz" on multiples of 5
- It instead returns "FizzBuzz" on multiples of 3 and 5

You will use test-driven development to write this function.

1. Create an empty function `fizz_buzz()`
2. Go through the conditions listed above, one by one:
    1. Write a test for the condition
    2. Edit the `fizz_buzz()` function until the test passes
3. Share your tests in the collaborative document.


```` python

from fizz_buzz import fizz_buzz
import pytest

def test_zero_fail():
    test_numbers = [-3, -2, 0]
    for test_number in test_numbers:
        with pytest.raises(ValueError):
            fizz_buzz(test_number)



def test_fizz():
    test_numbers = [3, 6, 9]
    for test_number in test_numbers:
        assert fizz_buzz(test_number) == 'Fizz'

def test_buzz():
    test_numbers = [5, 10, 20]
    for test_number in test_numbers:
        assert fizz_buzz(test_number) == 'Buzz'


def test_fizzbuzz():
    test_numbers = [15, 30, 45]
    for test_number in test_numbers:
        assert fizz_buzz(test_number) == 'FizzBuzz'
````


``` python
# Working function (after failing test because badly implemented negative test)
def fizz_buzz(number):
    if number > 0:
        if number % 3 == 0:
            if number % 5 == 0:
                return 'FizzBuzz'
            else:
                return 'Fizz'
        if number % 5 == 0 and number % 3 != 0:
            return 'Buzz'
        else:
            return number
        
    else:
        raise ValueError
```

### Tests using pytest parametrize
```python
import pytest


def fizz_buzz(x):
    if x <= 0:
        raise ValueError
    if (x % 3 == 0) and (x % 5 == 0):
        return "FizzBuzz"
    elif x % 3 == 0:
        return "Fizz"
    elif x % 5 == 0:
        return "Buzz"
    else:
        return x


def test_fail_zero():
    with pytest.raises(ValueError):
        fizz_buzz(0)


def test_fail_negative():
    with pytest.raises(ValueError):
        fizz_buzz(-10)


@pytest.mark.parametrize(
    "x,expected", [(3, "Fizz"), (6, "Fizz"), (9, "Fizz"), (4731, "Fizz")]
)
def test_multiple_three(x, expected):
    assert fizz_buzz(x) == expected


@pytest.mark.parametrize(
    "x,expected", [(5, "Buzz"), (10, "Buzz"), (440, "Buzz"), (4730, "Buzz")]
)
def test_multiple_five(x, expected):
    assert fizz_buzz(x) == expected


@pytest.mark.parametrize(
    "x,expected",
    [(15, "FizzBuzz"), (90, "FizzBuzz"), (300, "FizzBuzz"), (540, "FizzBuzz")],
)
def test_multiple_three_five(x, expected):
    assert fizz_buzz(x) == expected


@pytest.mark.parametrize("x", [2, 4, 8, 13])
def test_other(x):
    assert fizz_buzz(x) == x

```

Q: What did you think of this style of developing?
A: This is syntax I needed to look up to understand. +1


### Exercise: Full-cycle collaborative workflow

The exercise takes 30-40 minutes.

In this exercise, everybody will:

A. Set up automated tests with GitLab-CI
B. Make test fail / find a bug in their repository
C. Open an issue in their repository
D. Then each one will clone the repo of one of their exercise partners, fix the bug, and open a merge request (GitLab)
E. Everybody then merges their co-worker’s change

Linting: Try to introduce a linting problem e.g. one blank line, instead of two surrounding top-level function (https://peps.python.org/pep-0008/#blank-lines). Discover through automated test and fix it.

#### Step 1: Create a new repository on GitLab

- Select a different repository name than your colleagues (otherwise forking the same name will be strange)
- Before you create the repository, select “Initialize this repository with a README” (otherwise you try to clone an empty repo).
- Share the repository URL with your exercise group via shared document or chat

#### Step 2: Clone your own repository, add code, commit, and push

Clone the repository.

Add a file `example.py` containing:

```python=
def add(a, b):
    return a + b

def subtract(a, b):
    return a + b  # do not change this line until prompted to do so.
```

Write a test function `def test_add()` for `add` to check that this function is working properly. Do NOT add a test function for `subtract` (yet).
Run pytest to ensure it works 

Then stage the file (`git add <filename>`), commit (`git commit -m "some commit message"`),
and push the changes (`git push`).


#### Step 3: Enable automated testing

In this step we will enable GitLab CI.
   Select "Build" -> "Pipelines" from your Gitlab sidebar of the project. You get to a page
   "Get started with GitLab CI/CD". Click on the "Try test template" button, this will open a browser with a template workflow. (Instead you can also just add a `.gitlab-ci.yml` file the result is identical).

   Replace the template with the following code snippet. Gitlab will save it as `.gitlab-ci.yml`.
   Add `pytest example.py` to the last line:

   ```{code-block} yaml
   # This workflow will install Python dependencies, run tests and lint with a single version of Python
   # For more information see: https://gitlab.com/gitlab-org/gitlab/-/blob/master/lib/gitlab/ci/templates/Python.gitlab-ci.yml

   image: python:latest
   stages:
     - linting
     - test
   before_script:
     - cat /proc/version #print out operations system
     - python -V  # Print out python version for debugging
     - pip install pytest flake8
     - if [ -f requirements.txt ]; then pip install -r requirements.txt;fi

   linting:
     stage: linting
     script:
       - flake8 . --count --select=E9,F63,F7,F82 --show-source --statistics
       - flake8 . --count --max-complexity=10 --max-line-length=127 --statistics

   test:
     stage: test
     script:
       - pytest example.py

   ```

   Commit the change by pressing the "Commit changes" button:

   ![](https://codimd.carpentries.org/uploads/upload_a4831dce44fc25a5955e898d421820e1.png)


#### Step 4: Verify that tests have been automatically run

Observe in the repository how the test succeeds. While the test is executing, the repository has a yellow marker.
This is replaced with a green check mark, once the test succeeds.

![](https://codimd.carpentries.org/uploads/upload_0844da445452615b30d2ef10189eb001.png)

Green check means passed.

Also browse the “Pipelines” tab and look at the steps there and their output.

#### Step 5: Add a test which reveals a problem

After you committed the workflow file, your GitHub repository will be ahead of your local cloned repository. Update your local cloned repository:

```
$ git pull origin main
```

Next, add a test function `test_subtract` to check that the `subtract` function can subtract two numbers from each other, and push it to your remote repository.
Verify that the test suite now fails on the “Pipelines” tab.


#### Step 6: Open an issue on GitLab
Open a new issue in your repository about the broken test (click the “Issues” button on GitLab and write a title for the issue). The plan is that your colleague will fix the issue through a pull request

#### Step 7: Fork and clone the repository of your colleague

Fork the repository using the GitLab web interface. 
Make sure you clone the fork after you have forked it. Do not clone your colleague’s repository directly.


#### Step 8: Fix the broken test

Fix the function now and run pytest to check that it works.
Then push to _your fork_. Check whether the action now also passes.

#### Step 9: Open a merge request (GitLab)

Then before accepting the pull request from your colleague, observe how GitLab CI automatically tested the code.

If you forgot to reference the issue number in the commit message, you can still add it to the pull request: `my pull request title, closes #NUMBEROFTHEISSUE`

#### Step 10

Observe how accepting the merge request automatically closes the issue (provided the commit message or the pull request contained the correct issue number).

Discuss whether this is a useful feature. And if it is, why do you think is it useful?

### Exercise (Optional): Install self-managed GitLab runner.
TNO Coding guild Docker guide: https://codingguild.tno.nl/coding-at-tno/programming-environments/?h=docker#docker (VPN needed)

Please refer to this guide for various choices: 
https://docs.gitlab.com/runner/install/docker.html

But in summary, the steps are: 

0. Make sure you have docker installed on your machine.
1. Install GitLab runner 

```
docker run -d --name gitlab-runner --restart always \
  -v /srv/gitlab-runner/config:/etc/gitlab-runner \
  -v /var/run/docker.sock:/var/run/docker.sock \
  gitlab/gitlab-runner:latest

```
2. Create a shared runner (via GitLab interface)

`Runners -> New group runner (Select Run untagged jobs) -> Create runner`

You will see a command to register you runner, copy it and paste in the following step.


3. Register the runner

```
docker exec -it gitlab-runner /bin/bash
gitlab-runner register --url <<url>> --token <<token>>
```
Use `docker` executer, you can specify `python:latest` when you are asked for a default docker image. 
Enjoy it! :woman-with-bunny-ears-partying: 

## 🎁 Wrap-up
### What did we learn in this workshop?
#### Collaboration with Git and GitLab 😻😻😻😻😻😻😻😻😻
* Creating merge requests 😻
* Review process 😻
* Good practices for collaboration
* Contributing to repositories with forks

#### Modular Code Development 😻😻😻😻😻
* How can you create blocks of code that can be reused? 😻

#### Software development as a process
* How can we design and write ‘good’ software that meets its goals and requirements?

#### Software architecture and design 😻😻😻
* Why should we invest time in software design?
* What should we consider when designing software?

#### Code style conventions 😻😻😻
* Why should you follow software code style conventions? 😻

#### Verifying code style using linters 😻😻😻😻
* What tools can help with maintaining a consistent code style? 😻
* How can we automate code style checking? 😻

#### Managing dependencies 😻😻😻😻😻
- Use a virtual environment manager like `poetry`, `conda`, or `venv`
- Document your dependencies, in Python in a `requirements.txt` file

#### Code Documentation 😻😻😻😻😻😻😻😻😻😻😻
* In-code documentation 😻😻😻
* Readme files
* Deploying user documentation to Gitlab Pages 😻

#### Testing 😻😻😻😻😻😻😻😻😻😻😻😻😻😻
* Introduction to testing: motivation, unit testing, integration testing
* Writing tests with `pytest` 😻

#### Continuous Integration 😻😻😻😻😻😻😻😻
* Introduction to Continuous Integration
* Setting up Continuous Integration with GitLab CI/CD 😻😻😻😻
* Use Continuous Integration to automatically run unit tests and linting when changes are pushed to GitLab 😻😻

### Wrap-up exercise
Read through what we learned in this workshop (see above) and reflect on:
- Whether there are any incremental improvements that can benefit your projects?
- What’s nice that we learnt but is overkill for your current work?

#### Apply to your own project
- Pick a topic that will benefit your project most.
- Add a 😻 to that topic so we can learn which topics resonate the most for you.
- Start improving!
#### Coffee breaks ;) 😻😻😻😻😻
- drink coffee😻
- have a cold water, or sparkling😻
- chat with peers😻

## 🧠 Collaborative Notes
### Virtual environments + dependencies
Virtual environments are:
- like islands: a separate environment where you can mess with things without affecting the rest of your computer
- like time capsules: a snapshot of the packages and their versions that worked in a specific point in time

### Templates
You can use the [TNO Python template](https://ci.tno.nl/gitlab/alm-user-group/templates/tno-python-template), it should be available to you when creating a new project in GitLab and picking 'Create from template':
![](https://codimd.carpentries.org/uploads/upload_0937c2b2fede9d4bf6875efeb103fb58.png)
![](https://codimd.carpentries.org/uploads/upload_da06dd7178a9c7a3e6e4d6556dc4c7f7.png)


### Documentation
#### Slides
https://lyashevska.github.io/ds-cr-slides/documentation/

#### What is a good README?
- Who is your audience? (colleagues, someone who wants to use your code)
- Installation instructions
- Quick start
- Link to documentation
- Licensing
- Acknowledgements
- Contributing guide

#### Docstrings and comments
The syntax:
```python
# this is a comment
def function_name(a, b):
    """This is a docstring"""
    return a + b
```

An example:
```python
from math import sqrt

# need this to compute hypothenuse
def pythagoras(a, b):
    """Compute the length of the hypothenuse."""
    return sqrt(a**2 + b**2)
```

Add type hinting:
```python
def pythagoras(a: float, b: float) -> float:
```

#### Literate programming
Mixing documentation and programming.

Adding formulas in markdown:
$$a^2 + b^2 = c^2$$

### Testing
#### Slides
https://lyashevska.github.io/ds-cr-slides/testing/

### Continuous Integration
#### Slides
https://lyashevska.github.io/ds-cr-slides/ci/

## Feedback morning
### What went well? 🏆
- Icebreaker was fun!
- Great answers to question and general knowledge of instructors. And great advice about tools to use.
- Nice exercises, really gives something to learn and think about
- Good explanation of Johan about comments vs. docstrings and demonstration of why this is useful
- Nice to have a bit more time for the excercises
- Explanations of the tasks were too short.
- Learning and Using the test function was usefull. Good example and after that use it on a self created script
- Good to have the exercises again, also valuable info about documentation
- i liked the presentation on testing which was clear
- you ending each section with some key take-away points is very helpful
- I liked having hand-on exercises to practice what was preached
- The exercises are simple but usefull!
- Interesting tools mentioned
- Everyone is very helpfull and no questions are dumb, nice learning enviorement

### What can be improved? 🤔
- It would have been nice to be able to go deeper into some topics and look at actual implementation in our actual workflows (but I imagine that this is a limitation related to the length of the course.)
- The testing exercise for the fahrenheit to celsius function could've been introduced better, as now it took some time for me to understand what the goal was and what the added value was w.r.t. to the fizzbuzz testing exercise.
    - A possibility to improve would be to use a more straightforward "wrong" function to test.
- I would have been nice to also dive into the choosing of tests, what do you want/need to test and how do you do that.
- Sometimes a bit too much on software development in general and not about the application in our context, because most of our work is not about developing, but more about changing our way of working and changing how we think about our work (not for thrash, but for reusability).
- (yesterdays) discussion on software engineering process: we discussed each others problems but it would have been nice to also conclude with some solutions. needed more direction
- Width vs depth of course; covering too many topics?
- Exercises were sometimes a little vague, but OK with some explanation
- Some of the exercises were quite tough because they used types of functions i was not yet familiar with. Also the solution mentions parametrization but this has not been discussed. What does it mean?
- would have been nice to delve a little deeper into testing with more advanced methods/strats.
- Hands on experience with documentation and creating docstrings would have been nice. This part was now more theoretical instead of practical
- i would like to see some examples of how larger software engineering projects look / how they do their testing and documentation when things become more complicated
- Would like a bit more advanced testing examples (or help with first steps to start including testing in a large already-mostly-developed model)

### Summary:
- Preference to go more in depth into the topics. 
- (But for some people they would like less focus on things specific to (prodcution) software development and more on the scientific usecase)
- Exercises for testing need improvement


## 📚 Resources
- [stackoverflow question on anaconda license](https://stackoverflow.com/questions/74762863/are-conda-miniconda-and-anaconda-free-to-use-and-open-source)
- [esciencecenter Python template](https://github.com/NLeSC/python-template), but you also have your own template at TNO
- [type hinting cheatsheet](https://mypy.readthedocs.io/en/stable/cheat_sheet_py3.html)
- [Literate programming with entangled](https://entangled.github.io/)

## Post-workshop survey
https://www.surveymonkey.com/r/DMK6832