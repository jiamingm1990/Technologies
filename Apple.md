# Apple Technologies

## Dynamic Libraries

> What problem is dynamic library trying to solve?

To improve the performance of an app from the following three aspects:

1. Reduce the size of an app's executable file.
2. Minimize app's use of memory.
3. Reduce launch time.

Read [Overview of Dynamic Libraries](https://developer.apple.com/library/archive/documentation/DeveloperTools/Conceptual/DynamicLibraries/100-Articles/OverviewOfDynamicLibraries.html) for more details.

> What are dynamic libraries?

Static libraries are archives of object files. They are linked into an app's executable file and got loaded into memory at launch time. In contrast, dynamic libraries are not statically linked into the app and can be loaded into memory when it is actually needed, either at launch time or as it runs.

Read [What Are Dynamic Libraries](https://developer.apple.com/library/archive/documentation/DeveloperTools/Conceptual/DynamicLibraries/100-Articles/OverviewOfDynamicLibraries.html#//apple_ref/doc/uid/TP40001873-SW2) for more details.

## Frameworks

> What problem is framework trying to solve?

Frameworks serve the same purpose as static and dynamic libraries. Frameworks offer the following advantages:

1. Frameworks group related, but separate resource together. Easier to install, uninstall and locate.
2. Frameworks can include a variety of resource types than libraries.
3. Multiple versions of a framework can be included in one bundle. Be backward compatible for older programs.
4. Only one copy of a framework's read-only resources in memory.

Read [What are Frameworks](https://developer.apple.com/library/archive/documentation/MacOSX/Conceptual/BPFrameworks/Concepts/WhatAreFrameworks.html) for more details.

> What are frameworks?

A framework is a hierarchical directory that encapsulates shared resources in a single package.

A framework is also a bundle and its content can be accessed using programming interface.

Read [What are Frameworks](https://developer.apple.com/library/archive/documentation/MacOSX/Conceptual/BPFrameworks/Concepts/WhatAreFrameworks.html) for more details.

> How can I find the location of system frameworks for developers?*

In terminal, use `find` command. For example, search for Cocoa.framework.

```bash
mengjiaming@mengjiaming Technologies % find /Library/Developer -name "Cocoa.framework"
/Library/Developer/CommandLineTools/SDKs/MacOSX11.3.sdk/System/Library/Frameworks/Cocoa.framework
/Library/Developer/CommandLineTools/SDKs/MacOSX10.15.sdk/System/Library/Frameworks/Cocoa.framework
```

## Bundles

> What problem is bundle trying to solve?

Organize code and resources in a structure and provide abstraction interface for locating and accessing them.

Read [Bundle](https://developer.apple.com/documentation/foundation/bundle) for more details.

> What are bundles?

Bundles represent apps, frameworks, plug-ins and many other specific types of content. They are the representation of code and resources stored in a directory on disk.

Read [Bundle](https://developer.apple.com/documentation/foundation/bundle) for more details.

## Bundle Resources

> What are bundle resources?

Bundle resources are images, audio files, user interface files and property lists. There are two kinds of property lists. Entitlements store key-value pairs that grant an executable permission to use a service or technology. Information property lists contain key-value pairs that identity and configure a bundle.

Read [Bundle Resources](https://developer.apple.com/documentation/bundleresources) for more details.

## Profiles

> What problem is profile trying to solve?

Profiles or provisioning profiles protect the device from the harm of running malicious apps. A profile should be either trusted by Apple App Store or the device user.

Read [Profiles](https://developer.apple.com/documentation/appstoreconnectapi/profiles#overview) for more details.

> What are profiles?

Profiles or provisioning profiles include signing certificates, device identifiers, and a bundle ID.

Read [Profiles](https://developer.apple.com/documentation/appstoreconnectapi/profiles#overview) for more details.

> Does simulator bundles need profiles?

No. Only physical device bundles need profiles. For example, for a TestApp, the iPhone bundle includes an extra `embedded.mobileprovision` resource, but the Simulator bundle does not.

```vim
/Users/mengjiaming/Library/Developer/Xcode/DerivedData/TestApp-cwoqdhukudrvhabypdtznduwiqjs/Build/Products/
▾ Debug-iphoneos/
  ▾ TestApp.app/
    ▸ _CodeSignature/
      embedded.mobileprovision
      Info.plist
      PkgInfo
      TestApp*
  ▸ TestApp.swiftmodule/
▾ Debug-iphonesimulator/
  ▾ TestApp.app/
    ▸ _CodeSignature/
      Info.plist
      PkgInfo
      TestApp*
  ▸ TestApp.swiftmodule/
```

## Code Signing

> What problem is code signing trying to solve?

Certify that an app was created by a trusted developer. Ensure that a piece of code has not been altered after it is signed. Code signing does not guarantee a piece of code is free of security vulnerabilities.

Read [About Code Signing](https://developer.apple.com/library/archive/documentation/Security/Conceptual/CodeSigningGuide/Introduction/Introduction.html#//apple_ref/doc/uid/TP40005929-CH1-SW1) for more details.

> What is code signing?

Code signing is an Apple security technology. A piece of code is hashed into digest message and the digest message is signed by a trusted developer with a private key to produce a digital signature. The operating system uses the public key in the certificate to decrypt the signature and verify if the code has been altered.

Read [About Code Signing](https://developer.apple.com/library/archive/documentation/Security/Conceptual/CodeSigningGuide/Introduction/Introduction.html#//apple_ref/doc/uid/TP40005929-CH1-SW1) for more details.

## Command Line Tools

> How can I open a directory in Finder using terminal command?

Use `open` command. For example, open the MacOSX 10.15 SDK home directory.

```bash
open /Library/Developer/CommandLineTools/SDKs/MacOSX10.15.sdk
```

> How can I know my default XCode version?

Use `xcodebuild -version` command.

> Where can I find all the Apple Downloads?

<https://developer.apple.com/download/all/>

> How can I switch my default XCode path?

Use `sudo xcode-select -s`. For example, before switching, I see the following output by typing command `xcode-select -p`:

```bash
/Applications/Xcode.app/Contents/Developer
```

After executing `sudo xcode-select -s /Applications/Xcode12.4.app`, my output becomes:

```bash
/Applications/Xcode12.4.app/Contents/Developer
```

## Xcode

> Can I debug a release app?

Yes. A release app can still be debugged, but as the code has been compiled with optimization, stepping may behave oddly and variables may not be available.

> How can I attach the code to a running process?

Add some breakpoints. Click **Debug** menu and select **Attach to Process**. For example, in the following image, the code is attached to process Amazon (PID: 6257).

<img src="images/Screen Shot 2021-11-13 at 9.14.52 PM.png" alt="Console Screen Shot" width="480px">

> How can I install a compiled app into Simulator without recompiling it again?

Press Control + Command + R. Or click **Product** menu and select **Perform Action** and select **Run Without Building**.

## Console

> How can I know the process ID of an app running in Simulator?

Open `Console` app and find the running Devices. Select that device and start to log messages. Take some action in the app and find a message from targeted app. The PID can be seen from the Info section. For example, in the following image, the Amazon app PID is 6257 in Simulator iPhone 11.

<img src="images/Screen%20Shot%202021-11-13%20at%208.47.13%20PM.png" alt="Console Screen Shot" width="480px">

## App Transport Security (ATS)

> What problem is App Transport Security (ATS) trying to solve?

To improve privacy and data integrity for all apps and app extension.

> What is App Transport Security (ATS)?

All networking connections made by the app are secured by the Transport Layer Security (TLS) protocol. ATS blocks connections that do not meet minimum security requirements.

Read [Preventing Insecure Network Connections](https://developer.apple.com/documentation/security/preventing_insecure_network_connections) to know more details.

> What is in the scope of ATS?

Networking calls that rely on the URL Loading System. ATS does not apply to calls from lower-level networking interfaces like the Network framework or CFNetwork.

## App Files Format

> What is the usage of .xcconfig?

Define variables to configure build setting. The variables are used for different build phases, such as compiling, code signing, packaging, etc.

Inside a .xcconfig file, we can include other .xcconfig files. The variable key is usually capalized words connected by underscore. The variable value can refer to other variables through ${OTHER_VARIABLE} or other .plist files, .entitlements files, etc.
