# python unit test project template with continuous integration (ci).

Things I learned:

0. Including a `__init__.py` in an arbitrary folder lets python know it is a python folder. This (somehow) helps to import modules form parent/sibling directories (from unit test files in a different folder).
1. One can make an entire python project executable with one or two commands. To do so, the developer write all the python packages (and required versions) in a `requirements.txt` like: `numpy>=1.11.2`. Next, the user can "install"/download all the required packages with command:`conda install --yes --file requirements.txt`, after which the user can directly run the `main.py` if the user wants (if no paths/extra manual steps are required by the code).
2. To run python tests you can include the `-m` command like `python -m test_addTwo.py` to run a library module as a script (I think this helps by finding/importing relative parent/sibling python files/modules.)



[![Build
Status](https://travis-ci.org/ucsf-bmi-203-2017/example.svg?branch=master)](https://travis-ci.org/ucsf-bmi-203-2017/example)

Example python project with testing.

## usage

To use the package, first make a new conda environment and activate it

```
conda create -n exampleenv python=3
source activate exampleenv
```

then run

```
conda install --yes --file requirements.txt
```

to install all the dependencies in `requirements.txt`. Then the package's
main function (located in `example/__main__.py`) can be run as follows

```
python -m example
```

## testing

Testing is as simple as running

```
python -m pytest
```

from the root directory of this project.
