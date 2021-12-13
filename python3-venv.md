### Python Virtual Environment in `Debian 11`
***
#### Context  

The latest `Debian 11` release, `Bullseye` is shipped with `python3` by default.   
The following error message will show up if a user wants to use `venv` the good old way `python -m venv venv`:

	The virtual environment was not created successfully because ensurepip is not
    available.  On Debian/Ubuntu systems, you need to install the python3-venv
    package using the following command.
    apt-get install python3-venv
    You may need to use sudo with that command.  After installing the python3-venv
    package, recreate your virtual environment.

#### Install `python3-venv`  
```bash
	# apt update && apt upgrade
	# apt install python3-venv
``` 
#### Test 

Once the package is installed, rest of the part is similar to the good old days.   
**Creating a python virtual environment**  
Create a test environment in `test_pyVenv`  
```bash
	$ python3 -v -m venv test_pyVenv
```   
`-v` gives a verbose output and `-m` runs `venv` as an independent module.  

**Directory Structure**   
```bash

	$ ls test_pyVenv/* 
	
	test_pyVenv/pyvenv.cfg

	test_pyVenv/bin:
	activate  activate.csh  activate.fish  Activate.ps1  easy_install  easy_install-3.9  pip  pip3  pip3.9  python  python3  python3.9

	test_pyVenv/include:

	test_pyVenv/lib:
	python3.9

	test_pyVenv/lib64:
	python3.9

	test_pyVenv/share:
	python-wheels

```  
`lib` and `lib64` directories come with required tools in `lib64/python3.9/site-packages/` directory.  
Any packages installed in the virtual environment will be installed here.  

**Activating a python virtual session**  
`cd` into virtual directory  
```bash
	$ cd test_pyVenv
```  
Run

```bash
	$ . bin/activate
```  
or
```bash
	$ source bin/activate
```  
Get into the virtual environment 
```bash
	(test_pyVenv) user@hostname:~/test_pyVenv$ 

```  
**Installing a package with pip3**  
Install a python package e.g. `selenium`  
```bash
	$ pip3 install selenium
```  
Check if the package is installed  
```bash
	$ ls lib64/python3.9/site-packages/ # or
	$ ls lib/python3.9/site-packages/  
	...
		selenium
		selenium-4.1.0.dist-info
	...
```  
and 
```python
	Python 3.9.2 (default, Feb 28 2021, 17:03:44) 
	[GCC 10.2.1 20210110] on linux
	Type "help", "copyright", "credits" or "license" for more information.
	>>> import selenium
	>>> 

```		

**Deactivating a python virtual session**  
Run 
```bash
   $ deactivate
```  
