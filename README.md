# dotpyvenv
A simple oh-my-zsh plugin, forked from jeanpantoja's.

## Description
This plugin automagically switch to a python virtual enviroment located (that you
previously have created with virtualenv program) in a folder named
".venv". If you have the virtualenv folder in a diferente folder you
can create a .pyvenvdir file and put the custom dir inside this
file, the plugin will search for your custom folder fisrt.

### Differences with the original
The only difference is the default directory for the virtualenv. In jeanpantoja's
plugin it's ".pyvenv", in my fork is ".venv" to enable better integration with
[pipenv](https://pypi.org/project/pipenv/) (note that to do so you must set
`PIPENV_VENV_IN_PROJECT`).
I'm not using a pipenv specialized tool because they spawn a `pipenv shell`,
taking time to cd into a pipenv directory and doubling the time to spawn a new
one is such a location. This plugin is much more lightweight.

Of course you may wonder why I use a plugin like this if I'm also using pipenv,
but I don't think that's really the point. Anyway, it's just a matter of habits,
in time I may get rid of this.

## Installation

I install plugins via [antibody](https://github.com/getantibody/antibody), for other
installation methods please refer to the original README or your favourite plugin manager.

## TODO

Given we have the directory structure below

```
projects
+-- .pyvenv
+-- project_a
|   +-- .pyvenv
```

when we exec `cd projects` the plugin will load the virtual environment at projects. Now we are
inside projects folder and we will exec `cd project_a`, the virtualenv should be switched
from projects/.pyvenv to projects/project_a/.pyvenv, this is not happening yet!
