###Introduction  
`pip` is PyPi command tool, used to install python dependency, it works like npm in Node.js. 

###Samples  

```
$ pip install SomePackage            # latest version
$ pip install SomePackage==1.0.4     # specific version
$ pip install 'SomePackage>=1.0.4'     # minimum version
```
or  
```
pip install -r requirements.txt
```

More complex usage, please see: [pip install examples](https://pip.pypa.io/en/stable/reference/pip_install/#pip-install-examples)  


For `requirements.txt`, the format is:  

```
#
####### example-requirements.txt #######
#
###### Requirements without Version Specifiers ######
nose
nose-cov
beautifulsoup4
#
###### Requirements with Version Specifiers ######
#   See https://www.python.org/dev/peps/pep-0440/#version-specifiers
docopt == 0.6.1             # Version Matching. Must be version 0.6.1
keyring >= 4.1.1            # Minimum version 4.1.1
coverage != 3.5             # Version Exclusion. Anything except version 3.5
Mopidy-Dirble ~= 1.1        # Compatible release. Same as >= 1.1, == 1.*
#
###### Refer to other requirements files ######
-r other-requirements.txt
#
#
###### A particular file ######
./downloads/numpy-1.9.2-cp34-none-win32.whl
http://wxpython.org/Phoenix/snapshot-builds/wxPython_Phoenix-3.0.3.dev1820+49a8884-cp34-none-win_amd64.whl
#
###### Additional Requirements without Version Specifiers ######
#   Same as 1st section, just here to show that you can put things in any order.
rejected
green
#
```

More complex usage, please see: [requirements file format](https://pip.pypa.io/en/stable/reference/pip_install/#requirements-file-format)  