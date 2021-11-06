# Apple Technologies

## Dynamic Libraries

> What problem is dynamic libaries trying to solve?

To improve the performance of an app from the following three aspects:

1. Reduce the size of an app's executable file.
2. Minimize app's use of memory.
3. Reduce launch time.

Read [Overview of Dynamic Libraries](https://developer.apple.com/library/archive/documentation/DeveloperTools/Conceptual/DynamicLibraries/100-Articles/OverviewOfDynamicLibraries.html) for more details.

> What are Dynamic Libraries?

Static libraries are archives of object files. They are linked into an app's executable file and got loaded into memory at launch time. In contrast, dynamic libraries are not statically linked into the app and can be loaded into memory when it is actually needed, either at launch time or as it runs.

Read [What Are Dynamic Libraries](https://developer.apple.com/library/archive/documentation/DeveloperTools/Conceptual/DynamicLibraries/100-Articles/OverviewOfDynamicLibraries.html#//apple_ref/doc/uid/TP40001873-SW2) for more details.

## Frameworks

> What problem is frameworks trying to solve?

Frameworks serve the same purpose as static and dynamic libraries. Frameworks offer the following advantages:

1. Frameworks group related, but separate resource together. Easier to install, uninstall and locate.
2. Frameworks can include a variety of resource types than libraries.
3. Multiple versions of a framework can be included in one bundle. Be backward compatible for older programs.
4. Only one copy of a framework's read-only resources in memory.

Read [What are Frameworks](https://developer.apple.com/library/archive/documentation/MacOSX/Conceptual/BPFrameworks/Concepts/WhatAreFrameworks.html) for more details.

> What are Frameworks?

A Framework is a hierachical directory that encapsulates shared resources in a single package.

A Framework is also a bundle and its content can be accessed using programming interface.

Read [What are Frameworks](https://developer.apple.com/library/archive/documentation/MacOSX/Conceptual/BPFrameworks/Concepts/WhatAreFrameworks.html) for more details.

> How can I find the location of system frameworks for developers?*

In terminal, use `find` command. For example, search for Cocoa.framework.

```bash
mengjiaming@mengjiaming Technologies % find /Library/Developer -name "Cocoa.framework"
/Library/Developer/CommandLineTools/SDKs/MacOSX11.3.sdk/System/Library/Frameworks/Cocoa.framework
/Library/Developer/CommandLineTools/SDKs/MacOSX10.15.sdk/System/Library/Frameworks/Cocoa.framework
```

## Command Line Tools

> How can I open a directory in Finder using terminal command?

Use `open` command. For example, open the MacOSX 10.15 SDK home directory.

```bash
open /Library/Developer/CommandLineTools/SDKs/MacOSX10.15.sdk
```
