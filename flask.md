## install
```bash
pip install flask
pip install flask-script
```

## app
```python
from flask import Flask

class DevConfig(object):
    DEBUG = True  # must be upper case

app = Flask(__name__)
app.config.from_object(DevConfig)
```

## manager
```python
from flask_script import Manager, Server
from flask_script import Command
from main import app

manager = Manager(app)


class Hello(Command):
    'hello world'
    def run(self):
        print 'hello world'

manager.add_command('hello', Hello())
manager.add_command('runserver', Server())
if __name__ == '__main__':
    manager.run()
```

```bash
python manager.py runserver -h 127.0.0.1 -p 5001
```

