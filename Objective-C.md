# Objective-C

> How do we locate a class using the class name?

Use NSClassFromString from NSObjCRuntime.h.

```objectivec
Class class = NSClassFromString(classname);
```

> How do we execute a class method via method name?

Use NSSelectorFromString to obtain a selector and send message to a Class object via methodForSelector. Cast the return IMP to a function pointer that takes proper arguments and call that method.

```objectivec
Class class = NSClassFromString(classname);
SEL selector = NSSelectorFromString(methodname);
IMP imp = [class methodForSelector:selector];
id (*func)(id, SEL, id) = (void *)imp;
func(class, selector, data);
```

> How do we assert a failure?

Use NSAssert from NSException.h.

```objectivec
// condition is a BOOL variable.
// message is an NSString * variable.
NSAssert(condition, message);
```

> What is macro `NS_ASSUME_NONNULL_BEGIN` used for?

This macro is used for indicating that simple pointer types in the audited regions will be assumed to be nonnull. When the header is used from Swift, the code will be cleaner.

Read [Nullability and Objective-C](https://developer.apple.com/swift/blog/?id=25) to know more.
