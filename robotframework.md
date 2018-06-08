# Robot framework
## Capabilities
- Web GUI Tests
- Database Tests
- API Tests
- File System Tests
- Mobile Web & App Tests

## Install robot framework
> pip install --no-cache-dir robotframework

Robot framework report and log generator
> rebot --version

> pybot --version

## Install Robot framework IDE (RIDE) 
RIDE depends on wxPython
> pip install robotframework-ride

### Useful shortcut key
| Shortcut Key          |      Function      |
|-----------------------|--------------------|
|Ctrl+Space             |Get Hint            |

## Web GUI test
### Install robotframework-seleniumlibrary
> pip install robotframework-seleniumlibrary

### Add browser driver
This is needed by selenium to run in particular browser

## Database test
### Install Database library
https://franz-see.github.io/Robotframework-Database-Library/
> pip install robotframework-databaselibrary
### Install Python Module that you will use to connect to the database
For example (mysql):
> pip install mysqlclient

(oracle)
> pip install JayDeBeApi

## Remote system test
https://www.youtube.com/watch?v=BJhBiT2xoK0
### Install SSHLibrary
> pip install robotframework-sshlibrary

## Serial connection
### Install robotframework-seriallibrary
https://pypi.org/project/robotframework-seriallibrary/

## Mobile Web & App test
### Install AppiumLibrary
> pip install robotframework-appiumlibrary
### Install Appium Server (or download and install Appium Desktop)
> npm install -g appium

### Launch Appium Server with appropiate arguments


### Alternative: Appium Desktop
http://appium.io/downloads.html
https://www.youtube.com/watch?v=IOSUBda2-g4

## Foundation of Robot Framework
### Variable
Variables are case-insensitive
#### Scalar
```
${MYVARIABLE}
```
#### List
```
@{MYLISTVARIABLE}
@{MYLISTVARIABLE}[0]
@{MYLISTVARIABLE}[1]
```
#### Dictionary
```
&{MYDICTVARIABLE}
key1=value1
key2=value2
&{MYDICTVARIABLE}[key1]
```
#### Environment
```
%{HOME}
%{USER}
```
#### Automatic variabls
http://robotframework.org/robotframework/latest/RobotFrameworkUserGuide.html
```
${TEST NAME}
@{TEST TAGS}
```

## Keywords
### Library keywords
#### Common library keywords for testing
| Keywords              |      Descriptions     |
|-----------------------|-----------------------|
|Open Browser           |                       |
|Input Text             |                       |
|Input Password         |                       |
|Click Button           |                       |
|Close Browser          |                       |
|Log To Console         |                       |

### User keywords
 - Custom keywords

## Setup/Teardown
Available in TestCase and TestSuite

## Run test in CLI
### all test
> robot SuiteFile

### by test name
> robot -t Test1 -t Test2 SuiteFile

### by tag name
#### include tag
> robot -i Tag1 -t Tag2 SuiteFile

> robot -i T* SuiteFile
#### exclude tag
> robot -e T* SuiteFile

### send result to directory
> robot -d Results SuiteFile

### critical vs non-critical

## Jenkin integration
https://www.youtube.com/watch?v=EF7GHvN5KwU

<!-- anchor -->

<center>
<br><br>
Copyright © 2018 Alex Choi
</center>
