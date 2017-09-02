# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Data Science Projects

## Project Specs

Each project includes objectives, requirements, starter, rubric and suggested resources - all of which tie into the overall competencies for each unit. Dive into the detailed project spec files to read more about each project.

## Project Directory

1. **[Unit Projects](./unit-projects/README.md)**
    - [Unit Project 1](./unit-projects/project-01/README.md)
    - [Unit Project 2](./unit-projects/project-02/README.md)
    - [Unit Project 3](./unit-projects/project-03/README.md)
    - [Unit Project 4](./unit-projects/project-04/README.md)

2. **[Final Project](./final-project/README.md)**
    - [Final Project, part 1](./final-project/part-01/README.md)
    - [Final Project, part 2](./final-project/part-02/README.md)
    - [Final Project, part 3](./final-project/part-03/README.md)
    - [Final Project, part 4](./final-project/part-04/README.md)
    - [Final Project, part 5](./final-project/part-05/README.md)

## Project Timeline

| Unit | Project | Assigned | Due |
| --- | --- | :---: | --- |
| **Unit 1** | [Unit Project 1](./unit-projects/project-01/README.md) | [Lesson 01](../lessons/lesson-01/README.md) | [Lesson 03](../lessons/lesson-03/README.md) |
| **Unit 1** | [Unit Project 2](./unit-projects/project-02/README.md) | [Lesson 03](../lessons/lesson-03/README.md) | [Lesson 05](../lessons/lesson-05/README.md) |
| **Unit 2** | [Final Project, part 1](./final-project/part-01/README.md) | [Lesson 01](../lessons/lesson-01/README.md) | [Lesson 08](../lessons/lesson-08/README.md) |
| **Unit 2** | [Unit Project 3](./unit-projects/project-03/README.md) | [Lesson 05](../lessons/lesson-05/README.md) | [Lesson 10](../lessons/lesson-10/README.md) |
| **Unit 2** | [Unit Project 4](./unit-projects/project-04/README.md) | [Lesson 09](../lessons/lesson-09/README.md) | [Lesson 12](../lessons/lesson-12/README.md) |
| **Unit 3** | [Final Project, part 2](./final-project/part-02/README.md) | [Lesson 08](../lessons/lesson-08/README.md) | [Lesson 14](../lessons/lesson-14/README.md) |
| **Unit 3** | [Final Project, part 3](./final-project/part-03/README.md) | [Lesson 14](../lessons/lesson-14/README.md) | [Lesson 16](../lessons/lesson-16/README.md) |
| **Unit 3** | [Final Project, part 4](./final-project/part-04/README.md) | [Lesson 16](../lessons/lesson-16/README.md) | [Lesson 18](../lessons/lesson-18/README.md) |
| **Unit 3** | [Final Project, part 5](./final-project/part-05/README.md) | [Lesson 18](../lessons/lesson-18/README.md) | Lesson 20 |

---

## Project Completion

In order to pass this course, General Assembly students **must**:

- Complete and submit 80% of all course homework assignments.
- Complete and submit the final project, including all 5 milestones.

### Grading and Using GitHub in the Classroom

Students should create their own individual course repositories to store notes and host graded assignments.

Students should pull in weekly materials released by instructors to their individual repositories. Students can create pull requests to the instructor's course repository for short assignments or homework submission.

For project submission, students should link to their personal project commits so instructors can view their work.

## git commands
Below there is a list of commands to work with a branch of the ds2melb repository. _Replace `student_name` with your slack handle_.

### Create your own branch

1. ensure you have cloned the repository correctly

    $ git clone git@github.com:ga-students/ds2melb.git

2. create your own local branch

    $ git checkout -b {student_name}

3. **IMPORTANT** push your branch to the github repository
(if you do not do this then you may have problems later when you want to commit or merge)

    $ git push -u origin {student_name}

from now on you can work in this branch.

### Update the repository **from** the `master`
Do this periodically!

    $ git checkout {student_name}
    $ git merge origin/master

as you work you can commit changes to your local repositories on a regular basis. This will allow you to track your own code changes and perhaps roll back mistakes if you need to. Do not worry, all your changes are private and wont be seen on the server until you finally push to the server.

    $ git commit -a -m "completed up to section 3 , need to sleep now ... "
    # ...
    # do stuff
    # ...

    $ git commit -a -m "completed up to section 6 , struggling with logistic regression ???? "

### Submit your work

use the `-m` option to provide a commit comment
the `push` command will send your changes up to your branch on github

    $ git checkout {student_name}
    $ git commit -a -m "this is my submission for project3"
    $ git push

## git GUI Alternatives

Alternatively you could use a nice cross platform gui tool like [gitKraken](https://www.gitkraken.com/features)