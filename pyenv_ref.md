# pyenv Reference

#### install python version 3.6.4
```
pyenv install 3.6.4
```

#### list all installed python versions
```
pyenv versions
```

#### set python version 3.6.4 for global
```
pyenv global 3.6.4
```

#### set python version 3.6.4 for local directory
```
pyenv local 3.6.4
```

#### check python version in current directory
```
python --version
```

#### if python version not switching
Either run
```
eval "$(pyenv init -)"
```
in terminal, or append it to `~/.bash_profile`.