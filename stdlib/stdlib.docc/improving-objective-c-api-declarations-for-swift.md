# Improving Objective-C API Declarations for Swift

Use the `NS_REFINED_FOR_SWIFT` macro to change how an API is imported into Swift.

## Overview

If you want to expose an Objective-C API to Swift with a different declaration, but
a similar underlying implementation, use the `NS_REFINED_FOR_SWIFT` macro. When you
import an Objective-C API into Swift, you can adopt Swift-only types such as tuples.
You can also reorder, combine, and rename parameters so the API matches other Swift
APIs.

### Choose a New Name and Declaration

The example below shows an Objective-C API that can be expressed more succinctly
once it's imported into Swift:

```occ
@interface Color : NSObject

- (void)getRed:(nullable CGFloat *)red
         green:(nullable CGFloat *)green
          blue:(nullable CGFloat *)blue
         alpha:(nullable CGFloat *)alpha;

@end
```

Calling the `getRed(red:green:blue:alpha:)` method in Swift requires passing four
in-out parameters. A reimagined Swift computed property that expresses the same functionality—getting
the components of a color—can be written as a four-element tuple:

```swift
var rgba: (red: CGFloat, green: CGFloat, blue: CGFloat, alpha: CGFloat)
```

The new name is shorter, but still understandable because it uses an industry-standard
initialism for color components: RGBA. The property defined by the new declaration
is easier to use in Swift.

### Expose the Existing Implementation

Applying the `NS_REFINED_FOR_SWIFT` macro exposes the existing Objective-C API for
reuse in your refined API. The existing API is renamed with double underscores (`__`)
when it's imported, to help prevent you from accidentally using the existing API
elsewhere.

The example below adds the `NS_REFINED_FOR_SWIFT` macro to the `getRed(red:green:blue:alpha:)`
method:

```occ
@interface Color : NSObject

- (void)getRed:(nullable CGFloat *)red
         green:(nullable CGFloat *)green
          blue:(nullable CGFloat *)blue
         alpha:(nullable CGFloat *)alpha NS_REFINED_FOR_SWIFT;

@end
```

The following rules determine how an API's existing interface is imported:

- Initializer methods are imported by Swift with double underscores (`__`) prepended
to their first argument labels.
- Object subscripting methods are imported by Swift as methods with double underscores
(`__`) prepended to their base names, rather than as a Swift subscript, if either
the getter or setter method is marked as `NS_REFINED_FOR_SWIFT`.
- Other methods are imported with double underscores (`__`) prepended to their base
names.

### Reuse the Existing Implementation

You reuse an API by using its new name to call it in the implementation of a new
API in Swift.

The implementation of the new `rgba` property reuses the existing `__getRed(red:green:blue:alpha:)`
method to ensure that functionality remains the same between Swift and Objective-C:

```swift
extension Color {
    var rgba: (red: CGFloat, green: CGFloat, blue: CGFloat, alpha: CGFloat) {
        var r: CGFloat = 0.0
        var g: CGFloat = 0.0
        var b: CGFloat = 0.0
        var a: CGFloat = 0.0
        __getRed(red: &r, green: &g, blue: &b, alpha: &a)
        return (red: r, green: g, blue: b, alpha: a)
    }
}
```
