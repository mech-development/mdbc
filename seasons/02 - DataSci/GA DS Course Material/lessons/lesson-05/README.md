---
title: Flex lab
duration: "1:45"
creator:
    name: Angelo Klin
    city: MEL
---

# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Flex lesson
DS | Lesson 5

### LEARNING OBJECTIVES
**After this lesson, you will be able to:**

- Identify the Data Science toolkit
- Navigate Git and the Command Line
- Describe Probability vs Odds

### STUDENT PRE-WORK
**Before this lesson, you should already be able to:**

- Use descriptive stats to understand your data

### LESSON GUIDE

| TIMING | TYPE | TOPIC |
|:-:|---|---|
| 5 min | [Opening](#opening) | Lesson Objectives |
| 5 min | [Introduction](#introduction1) | Common Data Science Tools|
| 10 min | [Command Line Demonstration](#demo1) | Command Line Demonstration |
| 10 min | [Text Editor Demonstration](#demo2) | Text Editor Demonstration |
| 10 min | [Jupyter Notebook](#intro2) | Jupyter Notebooks |
| 10 min | [Git Tools](#intro3) | Introduction to Git |
| 50 min | [Independent Practice](#lab1) | GIT and Command Line |
| 5 min | [Introduction](#intro4) | Odds and Probability |
| 20 min | [Guided Practice](#guided-practice) | Hand calcs |
| 15 min | [Wrap-up](#wrapup) | Review Guided Practice|

---
<a name="opening"></a>
## Opening (5 min)
- Review Current Lesson Objectives

<a name="introduction"></a>
## Introduction: Tools of the Trade (10 mins)

### Local machine
On your local machine you have a variety of tools at your disposal, including:

1. Text editor
2. Programs, packages and tools
3. Your files

All of these can be accessed through a **Terminal** and many can also be accessed through a **GUI** or Graphical User Interface.

Let's take a look at the file directory system through `Finder` and then through the `Terminal`. Pull up the class folder on `Finder/Explorer`. Then navigate to the same folder via `Terminal`.

Today we are going to review some of the tools we use in data science and see how they fit into the wider  environment.

**Command Line**: This is your portal to your computer and the outside world.

<a name="demo1"></a>
## Command Line Demonstration
Demonstration of a few commands

1. `cd`
2. `pwd`
3. `mkdir`
4. `open`

As we mentioned, we can access many tools with Terminal. Let's walk through a few that are important for data science.

So far we have been using Jupyter notebook in place of a text editor. However, there are lots of other options available, including: Vim, Sublime Text and Atom.

**Check**: What is a text editor? Can you name any other examples?

<a name="demo2"></a>
## Text Editor - Sublime Text

Let's do a demonstration of Sublime Text with Python.

<a name="intro2"></a>
## Jupyter Notebook
Where does Jupyter Notebook fit in?

From the Jupyter site
"The Jupyter Notebook is a web application that allows you to create and share documents that contain live code, equations, visualisations and explanatory text.""

Jupyter notebooks combine two components:

- A web application: a browser-based tool for interactive authoring of documents which combine explanatory text, mathematics, computations and their rich media output.

- Notebook documents: a representation of all content visible in the web application, including inputs and outputs of the computations, explanatory text, mathematics, images and rich media representations of objects.

As you just saw, Terminal allows us to run programs such as Python or Javascript (node). It also allows us to reach out to the outside world and add packages we may need.

When we do this with Python we often use a tool called **pip** (or **conda**). Let's use pip to install a package. We could do this with a GUI, but the best way is to use the Command Line.

Here we will checkout a popular [Python Library, Beautiful Soup](http://www.crummy.com/software/BeautifulSoup/bs4/doc/#installing-beautiful-soup):

```python
pip install beautifulsoup4

# or

conda install beautifulsoup4
```

#### Outside World
As we saw with pip, the Command Line can connect us to the outside world. In data this is particularly important.

Let's say we have HIPAA protected data. Often times it will be the data we will leave on an external computer that we need to communicate with. We can do this through the Command Line.

**Note: HIPAA is a policy that protects health data for people. It requires extra security so you can't leave data around on your local computer.**

Ok! so we have see a few of the ways that we can use Terminal to enable our data analysis and help make it more powerful.

Now lets talk about a tool that make version control much easier.

<a name="intro3"></a>
### Introduction to Git

Git is a way of tracking changes we have made to our programs and go back in time to fix errors. It is also a powerful tool for collaborating with colleagues allowing you to work on different aspects of the project simultaneously and merge all the changes together seamlessly. Let's see how it works. There are lots of ways to use git one common tool is Github (it is a way of sharing your code with others on your team or with the world).

Let's see it in action. As I am sure you have guessed, a common way to do this is through Command Line! You can also use the github GUI.

```
git add
git commit
git push
```

When a colleague wants to implement our change, they can use a command called `git pull`.

Ok! That was a lot of material. Let's review.

**Check:**
1. What are the big advantages of using Command Line?

2. What is a GUI?

3. Will I destroy my computer if I use Terminal?


<a name="#lab1"></a>
## Independent Practice: GIT and Command Line (50 min)

**Alternative Resources:**

- [Github Challenges](https://try.github.io/levels/1/challenges/1)
- [Python the Hard Way](http://learnpythonthehardway.org/book/appendixa.html)
- [Codecademy Command Line](https://www.codecademy.com/learn/learn-the-command-line)

<a name="intro4"></a>
## Introduction: Odds and Probability
How proficient are you with statistical odds? Let's review some quick basics about odds and probability so you can test your familiarity with these concepts.

<a name="guided-practice"></a>
## Guided Practice: Odds and Probability (20 min)

<a name="wrapup"></a>
## Review (5-15 mins)

- What did we cover today?
- What are some common data science tools?
- Why are these tools useful?
- What questions do you have?

***

### BEFORE NEXT CLASS
|   |   |
|---|---|
| **PROJECT** | TBA |

### ADDITIONAL RESOURCES
- If any