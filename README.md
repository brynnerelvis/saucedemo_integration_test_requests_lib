# saucedemo_integration_test_requests_lib

Python library for saucedemo integration tests that uses Python requests package. It encapsulates requests Session class and implement
basic operations of interacting with saucedemo backend through requests library.


## Installation 

### Add as git submodule
Add this repository as git submodule in related test result-test-<test_name>. e.g in test_selenium_web_app dir run:

git submodule add git@github.com:brynnerelvis/saucedemo_integration_test_requests_lib.git
If this is the first git submodule in the project, then a file named ".gitmodules" will be created with the following contents:

[submodule "integration-test-requests-lib"]
    path = saucedemo_integration_test_requests_lib
    url =  git@github.com:brynnerelvis/saucedemo_integration_test_requests_lib.git
The above content would be appended to the file if there were already git submodule(s) in the repository

      .......
     [submodule "integration-test-requests-lib"]
        path = saucedemo_integration_test_requests_lib
        url =  git@github.com:brynnerelvis/saucedemo_integration_test_requests_lib.git
As gitlab requirements about git submodule, the url should be a relative path if the submodule is on the same Gitlab server.
Please update the url as shown below:

     [submodule "integration-test-requests-lib"]
        path = saucedemo_integration_test_requests_lib
        url =  ../../brynnerelvis/saucedemo_integration_test_requests_lib.git
Finally, commit changes  in .gitmodules(Add it to git if it is newly created) to git repository

Usage
By default, submodule default (master/main) branch will be used  after adding it to your repository. If you want to use different branch
then cd to the submodule and checkout to the desired branch.

 cd saucedemo_integration_test_requests_lib
 git checkout <branch>
 cd ..
Afterwards, you can install the submodule in your local python virtualenv with pip install

pip install --editable saucedemo_integration_test_requests_lib/
pip install with --editable option allows one to edit the submodule even after Installation.
When you run "pip install --editable saucedemo_integration_test_requests_lib/", pip uses setup.py in the root folder of the
submodule to install saucedemo_requests_lib package and its dependencies. You can then import classes and modules from
saucedemo_requests_lib just like normal python package.

#### Pycharm integration
If you are using Pycharm IDE for development, you can easily add saucedemo_requests_lib to your repo python path using Pycharm. This way
Pycharm will know of the package and give you auto suggestions when importing classes and modules. This is important because it increases your
productivity, and it is just very convenient.
What you need to do is to add "saucedemo_integration_test_requests_lib" dir as python packages "source" directory in Pycharm.
To do this, open Pycharm "settings" and go to "project Structure" in "Project" menu, look for "saucedemo_integration_test_requests_lib"
right click at it and click  at "sources" in the context menu that popups. To know that the folder has be added as one of the sources,
right click on "saucedemo_integration_test_requests_lib" and you will see that "sources" is ticked, otherwise you have to click on it to tick it.

###Sphinx Docs
Sphinx is used to generate documentation for saucedemo_requests_lib. To generate documentation, make sure Sphinx is installed.
For better reader experience, sphinx-rtd-theme is used.
pip install Sphinx
pip install sphinx-rtd-theme
docs directory in the root dir contains necessary config files for Sphinx to generate the documentation.
Using build_docs.sh HTML files are generated and saved to docs/build/html dir. You can then serve them locally or
copy them to be served in some remote server.
