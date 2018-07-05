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
> robot --version

## Install Robot framework IDE (RIDE) 
> pip install -U https://github.com/HelioGuilherme66/RIDE/archive/v1.7.2.zip

Note: RIDE depends on wxPython (Mac only)
### Install wxPython 
> pip install wxPython==4.0.1

### Install PyPubSub 3.3.0 for Python 2
> pip install PyPubSub==3.3.0

### Run RIDE
> ride.py

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

Remark: For Mac user, if you import the SSHLibrary in your test suite, make sure the robot is running in 64 bit python

## Serial connection
### Install robotframework-seriallibrary
https://pypi.org/project/robotframework-seriallibrary/

## Mobile Web & App test
### Install pytest-runner
> pip install pytest-runner

### Install AppiumLibrary
> pip install robotframework-appiumlibrary

### Install Appium Server (or download and install Appium Desktop)
> npm install -g appium

### Launch Appium Server with appropiate arguments
> To be confirmed

### Alternative: Appium Desktop
http://appium.io/downloads.html
https://www.youtube.com/watch?v=IOSUBda2-g4
Through the appium desktop, it is easy to inspect the UI element for testing

### Android app test
#### How to generate .apk
https://developer.android.com/studio/run/

#### Useful tools: UI Automator Viewer for Android testing (Optional)
> $ANDROID_SDK/tools/bin/uianimatorviewer

### iOS app test
#### Install Carthage
> brew install carthage

#### How to export .ipa
https://wiki.genexus.com/commwiki/servlet/wiki?34616,HowTo%3A+Create+an+.ipa+file+from+XCode,

For local testing, instead of exporting the .ipa file, the .app file is the alternative to start the app. For example 
#### More reading
[iOS XCUITest on simulator](http://appium.io/docs/en/drivers/ios-xcuitest/)

[iOS XCUITest on real devices](http://appium.io/docs/en/drivers/ios-xcuitest-real-devices/)

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
