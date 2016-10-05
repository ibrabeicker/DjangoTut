# DjangoTut

First create a project
```
$ mkdir my_project
```
Then, create a virtualenv. This is important to keep your project dependencies under control, no more installing every new package that you need into your OS. We will use Python 3 for the environment because we want to run any command calling *python* to use Python 3. 

```
$ cd my_project
$ virtualenv -p python3 env
```

The env folder will be called 'env' for brevity. Now activate the env:

```
$ source env/bin/activate
```

Now you're inside the desired env. Packages installed with pip will be available for this env only and will leave your OS packages untouched. Install Django and postgres driver
```
$ pip install Django
$ pip install psycopg2
```

Create the project
```
$ django-admin startproject my_project
```

We now have 3 folders inside eachother named `my_project`. For convention, let's rename the second-level folder to `src` because that's where all the source code of our project will reside. We now should have a project layout as following:

```
my_project
  |- env/
  `- src/
     |- my_project/
     `- manage.py
```

Other developers in our project will need to create their copies of our env. Because of that we will create a file listing all of our dependencies:

```
$ pip freeze > requirements.txt
```

### First commit

Time to make our first commit. Some files must be ignored, including our env folder, that contains a bunch of binaries and installed libraries. It's a best practice to keep those out of versioning so we will create a file named `.gitignore` in our top level folder.

`.gitignore`
```
.idea/
.sass-cache/
__pycache__
env/
```
Since I'm using PyCharm, I've included the folder `.idea` so we don't mess and create conflicts with eachother's IDE files.

```
$ git init
$ git add -A
$ git commit -m "Our first commit"
```





