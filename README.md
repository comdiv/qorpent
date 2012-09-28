qorpent
=======

Root of Qorpent Application Framework (information central)

Qorpent is a ultimate framework for building service/ajax/multiagent oriented systems
with .NET/MONO.

It extrimelly cut ages of traditional ASP.NET web application practices and
give to developers package oriented tool set and rich class library that
allows following:

1. Centralize code repositories without needs to merge real VCS allocation
2. Provide unified build/deploy process based on pure MSBUILD/XBUILD scripts
with cutting edges of really badly formed VS and MONODEVELOP project/solution files
3. Your can create a functional solution, api or content set, allocate and describe
it as Qorpent Package and your package after it can be used in automatic application
build and install process
4. Deploy of web applications became extremally fast, simple and controllable
u can create very simple scripts that will automatically deploy/update any
configuration of target application folders/servers or farms
5. Qorpent is GIT-friendly, default toolset for creation packages 
can be created with repository automatically

We provide two default packages which provides core functionality and allow quick start 
writing Qorpent-based applications:

1. [https://github.com/comdiv/qorpent.kernel] - core MSBUILD/XBUILD only framework,
that provide packaging and build environment for all other packages, it's must-be package
2. [https://github.com/comdiv/qorpent.sys] - Qorpent Application Framework (QAF) 
core libraries, IoC-based, low-coupled, contains multi-targeted action based MVC engine to
quickly externalize, secure and integrate your solution


# QUICK START
Requirements:
1) Install GIT
2a) On Windows - Install .NET Framework 4.0 or higher
2b) On Linuz - Install last build of MONO Project packages
3a) Optionally : on Windows - check that IIS configured to work with .NET
3б) Optionally : on Linux - setup Apache configs to work with mono-mod (xsp4 has some auth issues)
4) On Windows - msbuild.exe must be in system %PATH%

NOTICE:
Due to orientation of usage in secure environment, Qorpent.Mvc have some 
embeded filters to prevent guest access. Ensure that your IIS or Apache 
REQUIRE at least basic authentication for serving your appications.

INSTALLATION 
Decide where yout Qorpent Package Repository (QPR) will be placed (note that you can have many QPR)
assume we choose to use <PATH> folder:
mkdir <PATH>
cd <PATH>
git clone https://github.com/comdiv/qorpent.kernel
git clone https://github.com/comdiv/qorpent.sys

CREATE EMPTY APPLICATION
Notice - qorpent have both BUILD and INSTALL case of work but INSTALL can call build of 
requested libraries if they not still build, BUILD case works as total rebuild of ALL
code. Here in quick start we will simply call to 'installall' which
calls all available package to be INSTALL, packages will decide install or not due to 
call parameters.

Windows:
rem here we will create web-application in folder c:\tmp\qptfirst with qorpent.core package installed
msbuild qorpent.kernel\installall /p:AppDir=c:\tmp\qptfirst;IsWeb=True;qorpent_sys=True

Linux
# here we will create web-application in folder ~/tmp/qptfirst with qorpent.core package installed
msbuild qorpent.kernel\installall /p:AppDir=~/tmp/qptfirst;IsWeb=True;qorpent_sys=True

If all well you will see that Qorpent build source code and ship binaries and contents to 
given application folder.

After regestering app in IIS/Apache you can try open in web browser qorpent application whit basic
echo action:
http://localhost[:PORT]/[APPNAME]/_sys/echo.qweb?x=1&y=2
XML with echoed parameters must be returned
http://localhost[:PORT]/[APPNAME]/_sys/echo.json.qweb?x=1&y=2
JSON response will be returned
http://localhost[:PORT]/[APPNAME]/_sys/echo.md5.qweb?x=1&y=2
md5 hash of parametets rerurned...

As you see here - qorpent MVC provide way to have controllers (actions) with totally ignorance
of output subsystem and no handly writed views needed or controller - based realization to 
provide way for multi-targeting single command for different usage (xml service, ajax component,
change controll).

IT IS JUST PREVIEW OF QORPENT - see API/user references in Wiki and in package's documentation.

Enjoy QAF, and let be less FAQ!


