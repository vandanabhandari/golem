Golem - Test Automation Framework 
==================================================
[![Build Status](https://travis-ci.org/lucianopuccio/golem.svg?branch=master)](https://travis-ci.org/lucianopuccio/golem)
[![Documentation Status](https://readthedocs.org/projects/golem-framework/badge/?version=latest)](https://golem-framework.readthedocs.io/en/latest/?badge=latest)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![Join the chat at https://gitter.im/golem-framework/golem](https://badges.gitter.im/golem-framework/golem.svg)](https://gitter.im/golem-framework/golem?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)


Instructions specifically for Running the Tentrr Test:
--------------------------------------
This framework works with python 3.4+ above. Make sure you have an initialized python3 env before you start cloning the project. 

I recommend to use pipenv to intialize a virtual python3 env

If you’re on MacOS, you can install Pipenv easily with Homebrew:

```
$ brew install pipenv
```

To initialize and spawn a python 3 virtual environment 

```
pipenv shell --three
```

git clone the project and check out Tentrr branch

```
git clone git@github.com:DowneyTung/golem.git 
cd golem
git checkout Tentrr
```

install the dependencies and setup

```
python setup.py install
```

cd into the tentrr directory and run the full_regression suite in parallel from command line
```
cd tentrr
golem run Tentrr full_regression
```

if you want to run each test separately

```
golem run Tentrr map_pin_test
golem run Tentrr navigate_to_campsite_test
golem run Tentrr search_test
```

if you want to spwan up the UI interface for this test framework, you can also 
```
cd tentrr (if you are not in the tentrr directory)
golem gui
```



**(Technically you can ignore the content below because it is not related to the Tentrr test, but do keep reading if you are interested in this test automation framework)**


Intro 
--------------------------------------

>Automate end to end tests in minutes, not hours.


Golem is a complete test automation tool and framework for end-to-end testing. It creates powerful, robust and maintainable test suites, it's easy to learn even without a lot of programming knowledge. It is based on Selenium Webdriver and it can be extended using Python.

**It can:**
* Use the Page Object pattern
* Write tests with multi data sets (data-driven)
* Run tests in parallel.
* Test APIs
* Run tests remotely (Selenium Grid or a cloud testing provider)
* It can be executed from Jenkins or any other CI tool 


**It has:**
* A complete GUI module (a web application) to write and execute tests
* A reporting engine and a web reports module
* An interactive console


**Please note**: Golem is still in beta. Read the changelog before upgrading.

***

## Contents

* [Screen Captures](#screen-captures)
* [Pre-requisites](#pre-requisites)
* [Installation](#installation)
* [Quick Start](#quick-start)
* [Documentation](#documentation)
* [Example Projects](#documentation)
* [Roadmap](#roadmap)
* [License](#license)


Screen Captures
--------------------------------------

**Test Builder**
<p align="center">
    <img width="700" style="border: 1px solid #d3d3d3; padding: 5px" src="./images/test-case.png" />
</p>


**Test as Pure Python Code**
<p align="center">
    <img width="700" style="border: 1px solid #d3d3d3; padding: 5px" src="./images/example-test-code.png" />
</p>


**Report Dashboard**
<p align="center">
    <img width="700" style="border: 1px solid #d3d3d3; padding: 5px" src="./images/report-dashboard.png" />
</p>


**Execution Report**
<p align="center">
    <img width="700" style="border: 1px solid #d3d3d3; padding: 5px" src="./images/execution-report.png" />
</p>


**Test Execution Detail**
<p align="center">
    <img width="700" style="border: 1px solid #d3d3d3; padding: 5px" src="./images/test-execution-detail.png" />
</p>


Pre-requisites
--------------------------------------

Basic knowledge of Selenium Webdriver is required. Check out [this docs](https://golem-framework.readthedocs.io/en/latest/installation.html) first.


Installation
--------------------------------------

Golem works with Python 3.4+

```
pip install golem-framework
```

Read the full installation guide here: [https://golem-framework.readthedocs.io/en/latest/installation.html](https://golem-framework.readthedocs.io/en/latest/installation.html)

Quick Start
--------------------------------------

**Create a test directory anywhere in your machine**

```
golem-admin createdirectory <test_directory>
```

**Download the latest webdriver executables**

```
cd <test_directory>
webdriver-manager update
``` 

Webdriver executables can be downloaded manually. Place them in a known location (e.g. in <test_directory>/drivers) and make sure the settings.json has the correct path to the executables (e.g. "chromedriver_path": "./drivers/chromedriver\*"). Note: use '\*' wildcard to match latest version automatically.

The latests versions of the webdrivers can be found here:
* Chrome: (https://sites.google.com/a/chromium.org/chromedriver/)
* Firefox: (https://github.com/mozilla/geckodriver/releases)
* IE: (http://selenium-release.storage.googleapis.com/index.html)

For more information check [this page](https://golem-framework.readthedocs.io/en/latest/web-drivers.html) of the documentation.

**Start the Web Module**

```
golem gui
```


The Web Module can be accessed at http://localhost:5000/

By default, the following user is available: username: *admin* / password: *admin*


**Run a Test From Console**

```
golem run <project> <test>
```

Flags:

* -b | --browsers: a list of browsers, by default use defined in settings.json or Chrome
* -t | --threads: run in parallel, default 1 (not parallel)
* -e | --environments: a list of environments, default is none


Documentation
--------------------------------------

Read the full documentation here: [https://golem-framework.readthedocs.io/](https://golem-framework.readthedocs.io/)


Example Projects
--------------------------------------

Here is a repo with example working projects usign Golem: [https://github.com/lucianopuccio/golem-demo](https://github.com/lucianopuccio/golem-demo)


Roadmap
--------------------------------------

- Integrate with Appium for mobile testing
- Improve API test Golem actions
- Video recording


License
--------------------------------------

[MIT](https://tldrlegal.com/license/mit-license)