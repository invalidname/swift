# ``Swift``

@Metadata {
  @PageImage(purpose: card, source: "Swift-PageImage-card.png", alt: "An orange Swift logo on a gradient background.")
}

Build apps using a powerful open language.

## Overview

Swift includes modern features like type inference, optionals, and closures, which
make the syntax concise yet expressive. Swift ensures your code is fast and efficient,
while its memory safety and native error handling make the language safe by design.
Writing Swift code is interactive and fun in Swift Playgrounds, playgrounds in Xcode,
and REPL.

```swift
var interestingNumbers = [
    "primes": [2, 3, 5, 7, 11, 13, 17],
    "triangular": [1, 3, 6, 10, 15, 21, 28],
    "hexagonal": [1, 6, 15, 28, 45, 66, 91]
]

for key in interestingNumbers.keys {
    interestingNumbers[key]?.sort(by: >)
}

print(interestingNumbers["primes"]!)
// Prints "[17, 13, 11, 7, 5, 3, 2]"
```

### Learn Swift

If you're new to Swift, read [The Swift Programming Language](https://docs.swift.org/swift-book/)
for a quick tour, a comprehensive language guide, and a full reference manual. If
you're new to programming, check out [Swift Playgrounds](https://www.apple.com/swift/playgrounds/)
on iPad.

Swift is developed in the open. To learn more about the open source Swift project
and community, visit [Swift.org](https://swift.org).

## Topics

### Essentials

- <doc://com.apple.documentation/documentation/updates/swift>
- <doc:AdoptingSwift6>

### Standard Library

- ``Swift/Int``
- ``Swift/Double``
- ``Swift/String``
- ``Swift/Array``
- ``Swift/Dictionary``
- <doc:swift-standard-library>

### Observation

- <doc:Observation>

### Distributed Actors

- <doc:Distributed>

### Regular Expression DSL

- <doc:RegexBuilder>

### Low-Level Atomic Operations

- <doc:Synchronization>

### Data Modeling

- <doc:choosing-between-structures-and-classes>
- <doc:adopting-common-protocols>

### Data Flow and Control Flow

- <doc:maintaining-state-in-your-apps>
- <doc:preventing-timing-problems-when-using-closures>

### Language Interoperability with Objective-C and C

- <doc:objective-c-and-c-code-customization>
- <doc:migrating-your-objective-c-code-to-swift>
- <doc:cocoa-design-patterns>
- <doc:handling-dynamically-typed-methods-and-objects-in-swift>
- <doc:using-objective-c-runtime-features-in-swift>
- <doc:imported-c-and-objective-c-apis>
- <doc:calling-objective-c-apis-asynchronously>

### Language Interoperability with C++

- <doc:MixingLanguagesInAnXcodeProject>
- <doc:CallingAPIsAcrossLanguageBoundaries>
 
