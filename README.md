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

1. [qorpent.kernel|https://github.com/comdiv/qorpent.kernel] - core MSBUILD/XBUILD only framework,
that provide packaging and build environment for all other packages, it's must-be package
2. [qorpent.sys|https://github.com/comdiv/qorpent.sys] - Qorpent Application Framework (QAF) 
core libraries, IoC-based, low-coupled, contains multi-targeted action based MVC engine to
quickly externalize, secure and integrate your solution