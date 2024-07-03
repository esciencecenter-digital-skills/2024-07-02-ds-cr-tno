![](https://i.imgur.com/iywjz8s.png)


# Collaborative Document day 1

2024-07-02 Good practices in research software development @ TNO

Welcome to The Workshop Collaborative Document.

This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

----------------------------------------------------------------------------

This is the Document for today: https://tinyurl.com/good-practices-1

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
* 09:45	Coding guild and TNO coding principles & guidelines
* 10:00	Best practices in research software engineering
* 10:15	Collaboration with Git and GitLab
* 10:30	Coffee break
* 10:45	Collaboration with Git and GitLab
* 11:30	Coffee break
* 11:45	Collaboration with Git and GitLab
* 12:30	Lunch Break
* 13:30	Modular code development
* 14:15	Coffee break
* 14:30	Modular code development
* 15:00	Software development as a process
* 15:15	Coffee break
* 15:30	Software development as a process
* 15:30	Software architecture and design
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
- icebreaker:
    - What did you have for breakfast?
    - At which TNO location do you work?
    - How do you feel today?
    - How many years (or months) of programming experience?
- pre-workshop survey
    - Some people without Git experience? 
    - Mostly Python, 1 person coding in FORTRAN 💪
    - Some requests for talking about data: make sure to ask
- 

## 🔧 Exercises
### Exercise: Working as a project collaborator (in groups):
- Log into Gitlab and create a new repository with a README.md file
- If a README.md file was not created by GitLab. Make sure to follow the instructions on the repo to create one locally and push it to the main branch.
- Clone it to your desktop
- Add some code
- Push the changes to the repository.
- Add one person as a collaborator. 
- Clone that repo
- Make changes on a new branch
- Push the changes
- Submit a Merge Request
- Wait for approval
- At the same time review a collaborators Merge Request

#### (Optional, if you are done):
* Learn about and try out [protecting branches](https://docs.gitlab.com/ee/user/project/protected_branches.html)
* Try to create a merge conflict (two people editing the same line of code) and solve it.

### Exercise: Modularity 1

Look at the following code.

Extract functions from it without changing its functionality.

What functions did you create?
What strategies did you use to identify them?

Share your answers in the collaborative document

```python=
def convert_temperature(temperature, unit):
    if unit == "F":
        # Convert Fahrenheit to Celsius
        celsius = (temperature - 32) * (5 / 9)
        if celsius < -273.15:
            # Invalid temperature, below absolute zero
            return "Invalid temperature"
        else:
            # Convert Celsius to Kelvin
            kelvin = celsius + 273.15
            if kelvin < 0:
                # Invalid temperature, below absolute zero
                return "Invalid temperature"
            else:
                fahrenheit = (celsius * (9 / 5)) + 32
                if fahrenheit < -459.67:
                    # Invalid temperature, below absolute zero
                    return "Invalid temperature"
                else:
                    return celsius, kelvin
    elif unit == "C":
        # Convert Celsius to Fahrenheit
        fahrenheit = (temperature * (9 / 5)) + 32
        if fahrenheit < -459.67:
            # Invalid temperature, below absolute zero
            return "Invalid temperature"
        else:
            # Convert Celsius to Kelvin
            kelvin = temperature + 273.15
            if kelvin < 0:
                # Invalid temperature, below absolute zero
                return "Invalid temperature"
            else:
                return fahrenheit, kelvin
    elif unit == "K":
        # Convert Kelvin to Celsius
        celsius = temperature - 273.15
        if celsius < -273.15:
            # Invalid temperature, below absolute zero
            return "Invalid temperature"
        else:
            # Convert Celsius to Fahrenheit
            fahrenheit = (celsius * (9 / 5)) + 32
            if fahrenheit < -459.67:
                # Invalid temperature, below absolute zero
                return "Invalid temperature"
            else:
                return celsius, fahrenheit
    else:
        return "Invalid unit"

```
### ANSWERS

- Check the input minimum beforehand with a separate function so you don't have to do this everytime. I assume that when the input is above the minimum, the converted value will also be valid.
    ```py
    def check_temperature_minimum(temperature, unit):
        if unit == "F":
            assert temperature >= -459.67, "Invalid Fahrenheit temperature"
        if unit == "C":
            assert temperature >= -273.15, "Invalid Celsius temperature"
        if unit == "K":
            assert temperature >= 0, "Invalid Kelvin temperature"
    ``` 
- make functions that assert errors instead of making numerous if error statements like:
  ```py
  def celsius_to_fahrenheit(celsius):
    assert celsius > -273.15, "Invalid Temperature"
    fahrenheit = (celsius * (9 / 5)) + 32
    return (fahrenheit)
  ```
- Make a dict to store valid units and their absolute zero value:
     ```py
    valid_units = {"K":0, "F":-459.67, "C":-273.15}
    if unit not in valid_units:
        return f"Invalid unit, use one of {valid_units.keys()}"
    
     ```



- Removed the constants: 
```python
def fahrenheit_to_kelvin(temperature: float) -> float:
    if temperature < kelvin_to_fahrenheit(0):
        raise ValueError("Temperature is below absolute zero")

    kelvin = fahrenheit_to_celsius(temperature) - 273.16
    return kelvin
```



    
- 
```python
def is_valid_temperature(temperature, unit):
    absolute_zero = {"Celsius": -273.15, "Fahrenheit": -459.67, "Kelvin": -273.15}
    if temperature < absolute_zero[unit]:
        raise ValueError("Invalid temperature")
        return False
    return True
```

Convert Fahrenheit to Celsius

```python
def FtoC (temperature):
        celsius = (temperature - 32) * (5 / 9)
        if celsius < -273.15:
            # Invalid temperature, below absolute zero
            return "Invalid temperature"
        else:
            return celsius
```

- always convert everything to keep it readable 
```python
def convert_temperature(temperature, unit):

    # Conversion formulas
    def fahrenheit_to_celsius(f): return (f - 32) * 5.0 / 9.0
    def celsius_to_fahrenheit(c): return (c * 9.0 / 5.0) + 32
    def celsius_to_kelvin(c): return c + 273.15
    def kelvin_to_celsius(k): return k - 273.15

    # Convert input to Kelvin
    if unit == 'F':
        celsius = fahrenheit_to_celsius(temperature)
        kelvin = celsius_to_kelvin(celsius)
    elif unit == 'C':
        kelvin = celsius_to_kelvin(temperature)
    elif unit == 'K':
        kelvin = temperature
    else:
        return "Invalid unit"

    # Check if the temperature is below absolute zero in Kelvin
    if kelvin < 0:
        return "Invalid temperature: Below absolute zero"

    # Convert from Kelvin to other units
    celsius = kelvin_to_celsius(kelvin)
    fahrenheit = celsius_to_fahrenheit(celsius)
    
    # Return the converted values
    return {'F': fahrenheit, 'C': celsius, 'K': kelvin}
```


- Boom:
```python
def convert_temperature(temperature, unit):
    if unit == "F":
        celsius = fahrenheitToCelsius(temperature)
        kelvin = celsiusToKelvin(celsius)
        return celsius, kelvin    
        
    elif unit == "C":
        kelvin = celsiusToKelvin(temperature)
        fahrenheit = celsiusToFahrenheit(temperature)
        return kelvin, fahrenheit    
        
    elif unit == "K":
        celsius = kelvinTocelsius(temperature)
        fahrenheit = celsiusToFahrenheit(celsius)
        return celsius, fahrenheit
    else:
        return "Invalid unit for the input"       

def celsiusToKelvin(celsius):
    assert celsius < -273.15, "Invalid temperature"   
    return kelvin = celsius + 273.15
    
def fahrenheitToCelsius(fahrenheit):
    assert fahrenheit < -459.67, "Invalid temperature"
    return celsius = (fahrenheit - 32) * (5 / 9)

def celsiusToFahrenheit(celsius):
    assert celsius < -273.15, "Invalid temperature"
    return fahrenheit = (celsius * (9 / 5)) + 32
    
def kelvinTocelsius(kelvin):
    assert kelvin < 0, "Invalid temperature"
    return kelvin = kelvin + 273.15


``` python
Omar:
def test_temperature_validity(temperature, source_unit):
    possible_units = ['Celsius', 'Fahrenheit', 'Kelvin']
    absolute_zeroes = [-273.15, -459.57, 0]
    absolute_zeroes_per_unit = dict(zip(possible_units, absolute_zeroes))
    return temperature >= absolute_zeroes_per_unit(source_unit)


def from_Celsius(source_unit):
    return source_unit == 'Celsius'

def temperature_slope(source_unit, destination_unit):
    if source_unit == 'Fahrenhreit':
        return 5/9
    elif source_unit == 'Celsius' and destination_unit == 'Fahrenheit':
        return 9/5
    else:
        return 1
def temperature_shift(source_unit, destination_unit):
    if source_unit == 'Fahrenhreit':
        if destination_unit == 'Celsius':
            return -32
        else:
            return -32+273.15
    elif source_unit == 'Celsius':
        if destination_unit == 'Fahrenheit':
            return 32
        else:
            return 32+273.15

def convert_temperature(temperature, source_unit, destination_unit):

    test_temperature_validity(temperature, source_unit)

    if test_temperature_validity(temperature, source_unit):
        if from_Celsius(source_unit):
            converted_temperature = (
                temperature - temperature_shift(source_unit, destination_unit)
            ) * temperature_slope(source_unit, destination_unit)
        else:
            converted_temperature * temperature_slope(
                source_unit, destination_unit
            ) + temperature_shift(source_unit, destination_unit)
        return f'{converted_temperature} {destination_unit}'
    else:
        return 'Invalid temperature'
    
    
    

```
- Switch statement
```python
def celsius_to_kelvin(temperature):
    return temperature + 273.15

def celsius_to_fahrenheit(temperature):
    return temperature * (9 / 5) + 32

def fahrenheit_to_celsius(temperature):
    return (temperature - 32) * (5 / 9)

def fahrenheit_to_kelvin(temperature):
    return (temperature - 32) * (5 / 9) + 273.15

def kelvin_to_celsius(temperature):
    return temperature - 273.15

def kelvin_to_fahrenheit(temperature):
    return (temperature - 273.15) * (9 / 5) + 32

def convert_temperature(temperature, input_unit):
    """"
    Given a temperature in a given unit, convert it to both other unit options.
    The considered units are (degrees) Celsius, (degrees) Fahrenheit and Kelvin
    """

    absolute_zeros = {"F": -459.67, "C": -273.15, "K": 0.0}
    if temperature < absolute_zeros[input_unit]:
        return "Invalid temperature"

    match input_unit:
        case "F":
            return fahrenheit_to_celsius(temperature), fahrenheit_to_kelvin(temperature)
        case "C":
            return celsius_to_fahrenheit(temperature), celsius_to_kelvin(temperature)
        case "K":
            return kelvin_to_celsius(temperature), kelvin_to_fahrenheit(temperature)
        case _:
            return "Invalid unit"

```

#### Exercise: Modularity 2 (Optional)

Look into one of your own repositories and identify parts than can benefit from more modularity (don't start refactoring now, though). Signs include: highly nested code, (near) repetition, and poor readability. 
What do you think, will it end up saving time or costing time to improve the modularity? And more generally, will the benefits outweigh the costs?

### Exercise: Code style conventions & linting
#### Exercise: Run a linter
You are going to check the code you wrote so far to see if it matches
the Python code style conventions.

First install the Python linter `flake8`
```shell
pip install flake8
```
Save the code you wrote so far in a file called `temperature_conversion.py`.

You can run `flake8` on this file specifically: 

```shell
flake8 temperature_conversion.py
```

Or run `flake8` in the current folder:
```shell
flake8
```

1. What is the output that you get? Which code style conventions did you violate?
2. Try to make some code style fixes and run the linter again. What do you see?

#### (optional): Code style guides
Find code style guides for your programming language in [this awesome list of guidelines](https://github.com/Kristories/awesome-guidelines). Read through them (please note: you need days or even weeks to learn about all guidelines, focus on understanding 2-3 guidelines)
1. Are there are any guidelines that can benefit your projects?
2. Which guidelins are nice to learn about, but overkill for your current work?


## 🧠 Collaborative Notes
### Introduction
No notes, you can check the slides here: https://lyashevska.github.io/ds-cr-slides/good_practices/

### Collaboration with Git and GitLab
No notes

### Modular coding
Check the slides here: https://lyashevska.github.io/ds-cr-slides/code_modularization/
Q: Can you give another example of an impure function?
A: For example when the output of a function depends on a specific value in a database or a configuration file.

Q: What about a random number generator?
A: You can have the function accept a random seed to make the output predictable

Code smell: An indication (such as bad readability) that there is a deeper problem to your code

Q: What if a module is reused in different projects?
A: You can put your code in a generic package and import it into other projects

Do not reinvent the wheel

### Software engineering as a process & software architecture
See slides here: https://lyashevska.github.io/ds-software-dev-slides/


## 💬 Feedback morning
Can you give us some feedback? Think about the pace, the setup instructions, the instructors, the exercises, the balance between exercises and theory, anything!

Try to write down one thing that went well and one thing that can be improved.
### 👍 What went well??
- Good and clear answers to questions
- I like the idea with the post-its to flag a question or that you're done with an exercise, it's clear and makes sure that everyone is "heard".
- Sven is good at conveying the message clearly and calmly.
- Great, practical stuff!
- Maybe writing a simple Python file and test it ((run it, add/commit/push) should be added to the preparation of the training.
- Nice mix of theory and practice
- Questions were answered really quickly -> I agree
- Very positive and open vibe
- The practice really gave a lot of insights and food for thought
- I think the practice section was very insightful and worked well. 
- Great to get some time to put theory in practice
- nice balance between exercises and theory 2x
- -Good to have the practise session, practise wasn't too long so that some people were finished for a long time
- Preperation was well structured. Therefore, everybode is quickly up to speed this morning
- instant answers to your questions
- I liked that the explanation was using the command line, because Im not using VS code and I think this is the best way to learn it
- Lunch was great (everyone except ...)
- Plenty of people to help
- Great that everyone can edit at once this document👍

### 👎 What can be improved?
- Showing the workflow and actions in VS code (in addition to the command line) might help people more familiar with that.
- Setup instructions were a bit unclear
- The part where Johan did not have SSH access yet setup was actually very realistic and would've made a great opportunity to show step-by-step (e.g. following some tutorial) on how to resolve this. Now it went by a bit too fast.
- If in the part where the code review is demonstrated I would've found it more clear if there was a visual step-by-step representation of what was happening, perhaps even on the whiteboard. I.e.: visually showing remote and local branches, what happens when someone presses "merge" on a merge request, etc...
- I think many of us use VS code (maybe ask if this is true), using command line makes it accessible for everyone, but less relevant for many 
    - not true for me
    - not true for me as well (either :P)
- Too many people edit this at once
- Checking if the explanation is clear, sometims it went really quick. Or say that it is not important for now and you can ask later.
- The basics of git are clear to me, however its the errors and exceptions and what to do when it goes south where i want to improve
- The GIT story could be improved with a short visual roadmap on what was done, now it went so quick that I lost track on what was being done at the moment.
- Maybe you can add screen sharing during the demo, so people in the back can watch on their own screen.
- the live demo of using git went a bit too fast and could have had more explanation whilst being written
- I had prepared my SSH for gitlab.tsn.tno.nl instead of ci.tno.nl
- Fast tempo during demo
- Maybe prepare the demo a bit more, so it goes a bit faster, because we were waiting sometimes on not very interesting stuff
- We are currently all working with command line here, this gives some nice insights into git, but how many people will actually use the command line?
- I have ci.tno and a tsn.tno gitlab and I dont understand how to make sure that works with the command line interaction with git 
- Changing instances to the new branch went really quickly and wasn't immediately clear
- We should use version control for this feedback section
- there are different roads to Rome but it was not clear at first which we should take. 
- a second screen at the back of the room would be helpful
- 

### Summary:
- Mixing of theory and practice goes well
- Getting quick answers to questions (not for everyone though)
- The setup with gitlab didn't go smooth
- Make sure as instructors to prepare the GitLab demo well (especially in a private instance GitLab like ci.tno)
- Sometimes it goes too fast, we will try to slow down a bit or check more frequently if everyone is still following.

## 💬 Feedback afternoon
### What went well?
- Good mix between theory, practice and breaks
- i like the discussions with each other to learn about colleagues' known issues
- Nice interactions which are a bit more specific of current challenges with course leaders
- quick short sessions
- Interesting topics, different topics as well

### What can be improved?
- i would've liked to have seen a more practical exercise for software design
- We are with a big group of people, it is really interesting to hear everyones opinion and experiences, but sometimes it can maybe be a bit quicker (:
- larger classroom and tv screen
- It would be nice to hear more in what way we could be better organised within our group to encourage cooperation and modular design

### Feedback summary
- All the new tools can be overwhelming. Take your time to get used to them
- We will try to have less plenary discussions on the more advanced details, there is enough time to discuss this with the teachers during exercises.
- Yes, bigger screen! Let us know if we have to zoom in
- Organise cooperation --> ask during exercises

## 📚 Resources
- An excellent Git course can be found in the great Pro Git book by Scott Chacon and Ben Straub. The book is available online for free at git-scm.com/book.
- How to manage having different versions of a module that I reuse in different projects?:
    - Package your code using (this sounds difficult, but if you did it once, it is quite simple). You can follow [this lesson material](https://carpentries-incubator.github.io/python-intermediate-development/43-software-release/index.html)
    - Put your code on GitLab
    - Do a [release](https://docs.gitlab.com/ee/user/project/releases/index.html) that attaches a [tag](https://docs.gitlab.com/ee/user/project/repository/tags/) to a specific commit, for example v0.1.0 . 
    - Then, in a project that uses your generic package you can install the generic package referring to that tag: `pip install git+https://gitlab.com/user/generic-project.git@v0.1.0`.
    - Then in that project you can do `from name_of_generic_package import generic_function`

