
# Since mater has permission to merge, the master-new branch will no longer be maintained. You can directly maintain the master, and the pr can also be submitted to the master
# ACRPGServer

utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## What is ACRPGServer?

ACRPGServer  is a lightweight, fast, scalable, distributed plugin framework. NF is greatly inspired by OGRE and Bigworld.

## Features
- Easy-to-use, interface-oriented design
- An extensible plugin framework that makes getting your application running quick and easy
- A clean, uncluttered design and stable engine that has been used in several commercial products
- A high performance actor model (by a safe thread pool)
- Event and attribute-driven, making it clear and easy to maintain your business
- Based on standard C++ development, ensuring cross-platform support
- An existing C++ and C# game client for rapid development
- Cross-platform support


## Dependencies

- libevent
- easylogging++
- google protobuf
- hiredis
- ajson
- concurrentqueue
- RapidXML
- LuaIntf
- navigation
- lua

## IF YOU CAN NOT BUILD THE DEPENDENCIES THEN PLEASE RUN THE CMDS BELOW TO SET UP THE ENVIRONMENT:

* sudo apt-get install g++
* sudo apt-get install cmake
* sudo apt-get install automake
* sudo apt-get install zip unzip

## Supported Compilers

* GCC >= 7 (**Tested on Ubuntu 16.04**)
* MSVC >= VS2019 (**Tested on Win10**)

## Build and Install
### FOR WINDOWS, MSVC >= 2019

1. Git pull all source
2. Run the script file named **build_dep.bat** where located /Dependencies

3. Build the solution(if u build failed, please build again(**not rebuild all**))
4. Run the binary file by **_Out/rund.bat**

### FOR LINUX(UBUNTU, CENTOS) ---- please use administrator(or sudo) to do these:
1. Git pull all source
2. Run **install4cmake.sh** to build NF (or run cd /Dependencies  ./build_dep.sh then run buildServer.sh)
3. Run the binary file by **_Out/rund.sh**

### IF YOU LIVING IN A COUNTRY CANNOT ACCESS GITHUB FASTLY PLZ BUILD NF WITH VPN



```cpp

#ifndef NFC_HELLO_WORLD1_H
#define NFC_HELLO_WORLD1_H

#include "NFComm/NFPluginModule/NFIPluginManager.h"

class HelloWorld1
    : public NFIModule
{
public:
    HelloWorld1(NFIPluginManager* p)
    {
        pPluginManager = p;
    }

    virtual bool Init();
    virtual bool AfterInit();

    virtual bool Execute();

    virtual bool BeforeShut();
    virtual bool Shut();

protected:

};

#endif


#include "HelloWorld1.h"

bool HelloWorld1::Init()
{
    // Use this for initialization
	
    std::cout << "Hello, world1, Init" << std::endl;

    return true;
}

bool HelloWorld1::AfterInit()
{
    // AfterInit is called after Init
	
    std::cout << "Hello, world1, AfterInit" << std::endl;

    return true;
}

bool HelloWorld1::Execute()
{
    // Execute is called once per frame
	
    //std::cout << "Hello, world1, Execute" << std::endl;

    return true;
}

bool HelloWorld1::BeforeShut()
{
    //before final
	
    std::cout << "Hello, world1, BeforeShut" << std::endl;

    return true;
}

bool HelloWorld1::Shut()
{
    //final
	
    std::cout << "Hello, world1, Shut" << std::endl;

    return true;
}

```



### How to Create a New LuaScriptModule

## Step 1
Create a Lua Script File, and Must Contain following functions
- awake()
- init()
- ready_execute()
- after_init()

- before_shut()
- shut()

Mostly like this
# [test_module.lua]

```lua
test_module = {}
register_module(test_module,"test_module");


function test_module.awake()

end

function test_module.init()
end

function test_module.after_init()
end

function test_module.ready_execute()
end

function test_module.before_shut()
end

function test_module.shut()
end

```

##Step 2
Add your LuaScriptModule Infomation into [script_list.lua]


```lua
ScriptList={
    {tbl=nil, tblName="TestModule"},
    {tbl=nil, tblName="TestModule2"},
}

load_script_file(ScriptList)
```



##Hot fix
Add your lua script file name on here [script_reload.lua]

-------------------
New Feature in future: Blue Print System

-------------------

### Amazing  open source projects:
**breeze**
* Auther: zsummer
* Github: https://github.com/zsummer/breeze
* Description:A fast, scalable, distributed game server framework for C++


**gce**
* Auther: nousxiong
* GitHub: https://github.com/nousxiong/gce
* Description: The Game Communication Environment (GCE) is an actor model framework for online game development.

**moon**
* Auther: bruce
* GitHub: https://github.com/sniper00/moon.git
* Description: A  cross-platform,lightweight,scalable game server framework  written in C++, and suport Lua Script.






