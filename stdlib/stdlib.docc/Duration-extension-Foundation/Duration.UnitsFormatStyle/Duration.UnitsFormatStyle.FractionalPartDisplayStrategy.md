# ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

A strategy that determines how to format the fractional part of a duration if the allowed units can't represent it exactly.

When using a ``Swift/Duration/UnitsFormatStyle``, specifying a `FractionalPartDisplayStrategy` enables you to decide how to balance between accuracy and verbosity when you're not using all of the available units (hours, minutes, and seconds). When a formatted duration has a fractional part, you can hide it entirely, round the unit up or down while hiding the fractional part, or show the unit with a fraction.

The following example shows different display strategies used with a duration of 1 hour, 15 minutes and unit format styles that only show hours.

    let duration = Duration.seconds(75 * 60) // 1 minute, 15 seconds
    let hide = duration.formatted(
        .units(allowed: [.hours],
               width: .wide,
               fractionalPart: .hide)) // 1 hour
    let hideRounded = duration.formatted(
        .units(allowed: [.hours],
               width: .wide,
               fractionalPart: .hide(rounded:.up))) // 2 hours
    let show = duration.formatted(
        .units(allowed: [.hours],
               width: .wide,
               fractionalPart: .show(length: 2))) // 1.25 hours

## Topics

### Creating a fractional part display strategy

- ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy/init(lengthLimits:roundingRule:roundingIncrement:)``

### Using common strategies

- ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy/hide``
- ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy/hide(rounded:)``
- ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy/show(length:rounded:increment:)``

### Working with strategy properties

- ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy/minimumLength``
- ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy/maximumLength``
- ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy/roundingIncrement``
- ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy/roundingRule``

### Encoding and decoding

- ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy/init(from:)``
- ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy/encode(to:)``

### Hashing

- ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy/hashValue``
- ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy/hash(into:)``

### Comparing fractional part display strategies

- ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy/==(_:_:)``
