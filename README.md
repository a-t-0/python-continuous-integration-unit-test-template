# Python unit test project template with continuous integration (ci).

## Things I learned:

0. Including a `__init__.py` in an arbitrary folder lets python know it is a python folder. This (somehow) helps to import modules form parent/sibling directories (from unit test files in a different folder).
1. One can make an entire python project executable with one or two commands. To do so, the developer write all the python packages (and required versions) in a `requirements.txt` like: `numpy>=1.11.2`. Next, the user can "install"/download all the required packages with command:`conda install --yes --file requirements.txt`, after which the user can directly run the `main.py` if the user wants (if no paths/extra manual steps are required by the code).
2. To run python tests you should browse to the `/test/` folder in anaconda, or any parent folder. **Don't** and run `python -m test_algs.py`. Instead: type: `python -m pytest`. The pytest is a dedicated python function that scans for all files that contain `test_` and run them.
3. You can set up automated travis test integration by going to https://travis-ci.org/ logging in with your github user account, and then under the tab repositories click plus and select your repository on which  you want to set up travis-ci automated testing. Next, you can go to: https://travis-ci.org/dashboard and click on "trigger build" for that repository to create the first build. I assume all following commits to master trigger new builds.



4. You can include the fancy icons showing how solid your repository is with the following "badges".

5. To get the Travis Build badge on your repository, you can copy the link towards the build from the repository folder in the travis-ci website. That website is: https://travis-ci.org/<your github username>/<your repository name>. On that website the travis build button is shown, you can click it to get the link for that button. For this repository it returned: https://travis-ci.org/a-t-0/python-continuous-integration-unit-test-template.svg?branch=master
Which can then be written as:
[![Build
Status](https://travis-ci.org/a-t-0/python-continuous-integration-unit-test-template.svg?branch=master)](https://travis-ci.org/ucsf-bmi-203-2017/example)
Ps. The build is failing deliberatly because 2 unit tests are failing (to show they correctly detect faulty code).

6. You can "unwrap urls" in a readme so that you don't have very long urls in your text. An example is done here with the `README.md` variable `black_badge`:
[black_badge]

<!-- Un-wrapped URL's below (Mostly for Badges) -->
[black_badge]: https://img.shields.io/badge/code%20style-black-000000.svg

7. The black repository is a tool to help developers improve their python formatting. The new repository is located here: https://github.com/psf/black This is the badge: 
[![Code Style: Black][black_badge]](https://github.com/ambv/black)  

7. The python package can be included
[![Python 3.6][python_badge]](https://www.python.org/downloads/release/python-382/)

8. The licence can be included:
[![License: Apache 2.0][apache_badge]](https://www.apache.org/licenses/LICENSE-2.0)

9. **IF** you have more nested folder directories, for example like:
```
|-parent_folder/sub_folder/src/some_folder/some_other_folder/alg.py
|-parent_folder/sub_folder/test/test_algs.py
```
Then you can import the `alg.py` file from the `test_algs.py` with command: 
```
from ..src.some_folder/some_other_folder import algs
```
Furthermore, one can/should specify the test location for the continuous integration to: 
```
# run tests
script:
    "python -m pytest -v parent_folder/sub_folder/*"
```

## Usage

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

## Testing

Testing is as simple as running

```
python -m pytest
```

from the root directory of this project.


<!-- Un-wrapped URL's below (Mostly for Badges) -->
[black_badge]: https://img.shields.io/badge/code%20style-black-000000.svg
[python_badge]: https://img.shields.io/badge/python-3.8-blue.svg
[apache_badge]: https://img.shields.io/badge/license-Apache%202.0-brightgreen.svg
