# Part 2: Flask

For this part 2 option, you will make your website interactive using Flask, a
framework for building websites using the Python programming language.
 * Flask: https://flask.palletsprojects.com/en/2.0.x/
 * Python: https://www.python.org/

## Getting set up

### Installing Python

First, you will need to install Python. This is outside the scope of this
document, but you can find many good tutorials for handling your computer's
setup by Googling for "install python [YOUR OS HERE]".

Make sure you install a recent version. At the time that I'm writing this, the
most recent version is 3.10. Flask supports Python versions 3.6 and above.

Note that while macOS does come with Python out of the box, that version is
very old and is not supported by modern libraries. You should install a new
version of Python.

Verify that you have installed Python correctly by opening your terminal or
command prompt application and running the command `python --version`. This
should show you something like:
```
simon@rosalyn:~$ python --version
Python 3.9.2
```

Next, you should also verify that you have Pip, a package manager for Python
libraries, installed. It should have been installed when you installed Python:
```
simon@rosalyn:~$ pip --version
pip 21.3.1 from /home/simon/.pyenv/versions/3.9.2/lib/python3.9/site-packages/pip (python 3.9)
```

### Installing Flask
From a terminal, run the command `pip install Flask`. This will download Flask
and some dependencies:
```
simon@rosalyn:~$ pip install Flask
Collecting Flask
  Downloading Flask-2.0.2-py3-none-any.whl (95 kB)
     |████████████████████████████████| 95 kB 1.9 MB/s             
Collecting Jinja2>=3.0
  Downloading Jinja2-3.0.3-py3-none-any.whl (133 kB)
     |████████████████████████████████| 133 kB 4.6 MB/s            
Requirement already satisfied: Werkzeug>=2.0 in ./.pyenv/versions/3.9.2/lib/python3.9/site-packages (from Flask) (2.0.2)
Collecting itsdangerous>=2.0
  Downloading itsdangerous-2.0.1-py3-none-any.whl (18 kB)
Requirement already satisfied: click>=7.1.2 in ./.pyenv/versions/3.9.2/lib/python3.9/site-packages (from Flask) (7.1.2)
Collecting MarkupSafe>=2.0
  Downloading MarkupSafe-2.0.1-cp39-cp39-manylinux_2_5_x86_64.manylinux1_x86_64.manylinux_2_12_x86_64.manylinux2010_x86_64.whl (30 kB)
Installing collected packages: MarkupSafe, Jinja2, itsdangerous, Flask
  Attempting uninstall: MarkupSafe
    Found existing installation: MarkupSafe 1.1.1
    Uninstalling MarkupSafe-1.1.1:
      Successfully uninstalled MarkupSafe-1.1.1
  Attempting uninstall: Jinja2
    Found existing installation: Jinja2 2.11.3
    Uninstalling Jinja2-2.11.3:
      Successfully uninstalled Jinja2-2.11.3
Successfully installed Flask-2.0.2 Jinja2-3.0.3 MarkupSafe-2.0.1 itsdangerous-2.0.1
```

Verify that Flask was installed by running the helper program:
```
simon@rosalyn:~$ flask --version
Python 3.9.2
Flask 2.0.2
Werkzeug 2.0.2
```

(Werkzeug is a low-level library that Flask uses for a lot of things. Don't
worry about what exactly. It's not important for this project.)

### Make your website!
 1. Put index.html in the folder called "templates". This folder will hold all
    of the code for your website's frontend.
 3. Put style.css the folder called "static". This folder will hold any files 
    you want your website to include that aren't interactive or dynamic. You
    could also put images, music, JavaScript scripts, and anything else like
    that here.
 3. Update the line in index.html where the stylesheet is loaded (the <link>) so
    that it loads "/static/style.css" instead of just "style.css"
 4. Create a file called application.py and put the following code in:

```python
from flask import Flask, render_template

app = Flask(__name__)


@app.route("/")
def index():
    return render_template("index.html")
```

### Run your website
Linux/macOS/BSD/etc.
```
simon@rosalyn:~/your/project/dir$ export FLASK_APP=app.py
simon@rosalyn:~/your/project/dir$ flask run
 * Serving Flask app 'app.py' (lazy loading)
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

Windows cmd.exe:
```
C:\your\project\folder> set FLASK_APP=app.py
C:\your\project\folder> flask run
 * Serving Flask app 'app.py' (lazy loading)
[omitted]
```

Once you've run the appropriate commands, open your web browser and visit
http://127.0.0.1:5000 to see the results. It should look exactly the same as
before.

### Explore a bit more
At this point, you're done. However I strongly encourage you to keep exploring
and maybe add some cool new features to your website.

Take a look through the documentation, especially the quickstart section, to get
an idea of what's possible: https://flask.palletsprojects.com/en/2.0.x/

## Submitting your project
Zip up _only_ the folder containing your Flask app and submit it on Moodle.
