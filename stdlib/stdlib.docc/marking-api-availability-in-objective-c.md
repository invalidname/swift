# Marking API Availability in Objective-C

Use a macro to denote the availability of an Objective-C API.

## Overview

In Swift, you use the `@available` attribute to control whether a declaration is
available to use when building an app for a particular target platform. Similarly,
you use the availability condition `#available` to execute code conditionally based
on required platform and version conditions. Both kinds of availability specifier
are also available in Objective-C.

For detailed information about specifying and checking platform availability,
see [`available`][] and [Checking API Availability][]
in [The Swift Programming Language][tspl].

[`available`]: https://docs.swift.org/swift-book/documentation/the-swift-programming-language/attributes#available
[Checking API Availability]: https://docs.swift.org/swift-book/documentation/the-swift-programming-language/controlflow#Checking-API-Availability
[tspl]: https://docs.swift.org/swift-book/

### Mark Availability

Use the `API_AVAILABLE` macro to add availability information in Objective-C:

```occ
@interface MyViewController : UIViewController
- (void) newMethod API_AVAILABLE(ios(11), macosx(10.13));
@end
```

This is equivalent to using the `@available` attribute on a declaration in Swift:

```swift
@available(iOS 11, macOS 10.13, *)
func newMethod() {
    // Use iOS 11 APIs.
}
```

### Check Availability

Use the `@available()` keyword to check availability information in a conditional
statement in Objective-C:

```occ
if (@available(iOS 11, *)) {
    // Use iOS 11 APIs.
} else {
    // Alternative code for earlier versions of iOS.
}
```

This is equivalent to the following conditional in Swift:

```swift
if #available(iOS 11, *) {
    // Use iOS 11 APIs.
} else {
    // Alternative code for earlier versions of iOS.
}
```
