# pipenv Reference

#### install pipenv from pip
```
pip install pipenv
```

#### install python package "requests"
```
pipenv install requests
```
if this is new directory, you should now see two new files: `Pipfile` and `Pipfile.lock`


#### uninstall python package "requests"
```
pipenv uninstall requests
```

#### activate environment
```
pipenv shell
```
#### deactivate environment
```
exit
```

#### run python script.py without activating environment
```
pipenv run python script.py
```

#### remove virtual environment
```
pipenv --rm
```

#### create virtual environment based on Pipfile
```
pipenv install
```

#### check virtual environment path
```
pipenv --venv
```

#### check for package vulnerability
```
pipenv check
```

#### move Pipfile to Pipfile.lock: (dev -> production)
```
pipenv lock
```

#### install packages based on Pipfile.lock: (production)
```
pipenv install --ignore-pipfile
```
