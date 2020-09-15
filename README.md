# python unit test project template with continuous integration (ci).

Things I learned:

0. Including a `__init__.py` in an arbitrary folder lets python know it is a python folder. This (somehow) helps to import modules form parent/sibling directories (from unit test files in a different folder).
1. One can make an entire python project executable with one or two commands. To do so, the developer write all the python packages (and required versions) in a `requirements.txt` like: `numpy>=1.11.2`. Next, the user can "install"/download all the required packages with command:`conda install --yes --file requirements.txt`, after which the user can directly run the `main.py` if the user wants (if no paths/extra manual steps are required by the code).
2. To run python tests you should browse to the `/test/` folder in anaconda, or any parent folder. **Don't** and run `python -m test_algs.py`. Instead: type: `python -m pytest`. The pytest is a dedicated python function that scans for all files that contain `test_` and run them.
3. You can set up automated travis test integration by going to https://travis-ci.org/ logging in with your github user account, and then under the tab repositories click plus and select your repository on which  you want to set up travis-ci automated testing. Next, you can go to: https://travis-ci.org/dashboard and click on "trigger build" for that repository to create the first build. I assume all following commits to master trigger new builds.
4. To get the Travis Build badge on your repository, you can copy the link towards the build from the repository folder in the travis-ci website. That website is: https://travis-ci.org/<your github username>/<your repository name>. On that website the travis build button is shown, you can click it to get the link for that button. For this repository it returned:

Which can then be written as:
[![Build
Status](https://travis-ci.org/a-t-0/python-continuous-integration-unit-test-template.svg?branch=master)](https://travis-ci.org/ucsf-bmi-203-2017/example)

4. You can include the fancy icons showing how solid your repository is with the following "badges":



[![Python 3.6][python_badge]](https://www.python.org/downloads/release/python-382/)
[![License: Apache 2.0][apache_badge]](https://www.apache.org/licenses/LICENSE-2.0)
[![Code Style: Black][black_badge]](https://github.com/ambv/black) The black repository is a tool to help developers improve their python formatting. The new repository is located here: https://github.com/psf/black
[![CICD: GitHub Actions][build_status]](https://github.com/kswannet/GammaPy/actions)


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
