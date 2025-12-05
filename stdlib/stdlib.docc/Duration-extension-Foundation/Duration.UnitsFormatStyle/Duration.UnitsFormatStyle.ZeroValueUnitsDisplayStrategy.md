# ``Swift/Duration/UnitsFormatStyle/ZeroValueUnitsDisplayStrategy``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

A strategy that determines how to format a unit whose value is zero.

When using a ``Swift/Duration/UnitsFormatStyle``, specifying a `ZeroValueUnitsDisplayStrategy` enables you to decide whether show a unit whose value is zero.

The following example creates a duration of 25 seconds, then formats it with two different styles. The first style uses the ``hide`` display strategy, which omits the hours and minutes, since their value is `0`. The second uses ``show(length:)`` to create two-digit representations of the hour and minute fields.

    let duration = Duration.seconds(25)
    let hide = duration.formatted(
        .units(allowed: [.hours, .minutes, .seconds],
               width: .abbreviated,
               zeroValueUnits:.hide)) // 25 sec
    let showTwo = duration.formatted(
        .units(allowed: [.hours, .minutes, .seconds],
               width: .abbreviated,
               zeroValueUnits:.show(length: 2))) // 00 hr, 00 min, 25 sec

## Topics

### Using common strategies

- ``Swift/Duration/UnitsFormatStyle/ZeroValueUnitsDisplayStrategy/hide``
- ``Swift/Duration/UnitsFormatStyle/ZeroValueUnitsDisplayStrategy/show(length:)``

### Encoding and decoding

- ``Swift/Duration/UnitsFormatStyle/ZeroValueUnitsDisplayStrategy/init(from:)``
- ``Swift/Duration/UnitsFormatStyle/ZeroValueUnitsDisplayStrategy/encode(to:)``

### Hashing

- ``Swift/Duration/UnitsFormatStyle/ZeroValueUnitsDisplayStrategy/hashValue``
- ``Swift/Duration/UnitsFormatStyle/ZeroValueUnitsDisplayStrategy/hash(into:)``

### Comparing fractional part display strategies

- ``Swift/Duration/UnitsFormatStyle/ZeroValueUnitsDisplayStrategy/==(_:_:)``
