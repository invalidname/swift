# ``Swift/Duration/UnitsFormatStyle``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

A format style that shows durations with localized labeled components

This style produces formatted strings that break out a duration's individual components, like "2 min, 3 sec".

Create a `UnitsFormatStyle` by providing a set of allowed ``Swift/Duration/UnitsFormatStyle/Unit`` instances --- such as hours, minutes, or seconds --- for formatted strings to include. You also specify a width for displaying these units, which controls whether they appear as full words ("minutes") or abbreviations ("min"). The initializers also take optional parameters to control things like the handling of zero units and fractional parts. Then create a formatted string by calling ``Swift/Duration/formatted(_:)`` on a duration, passing the style, or ``Swift/Duration/UnitsFormatStyle/format(_:)`` on the style, passing a duration. You can also use the style's ``/Swift/Duration/TimeFormatStyle/attributed-swift.property`` property to create a style that produces <doc://com.apple.documentation/documentation/Foundation/AttributedString> instances, which contains attributes that indicate the unit value of formatted runs of the string.

In situations that expect a ``Swift/Duration/UnitsFormatStyle``, such as ``Swift/Duration/formatted(_:)``, you can use the convenience function `.units(allowed:width:maximumUnitCount:zeroValueUnits:valueLength:fractionalPart:)` to create a ``Swift/Duration/UnitsFormatStyle``, rather than using the full initializer.

If you want to reuse a style to format many durations, call ``format(_:)`` on the style, passing in a new duration each time.

The following example creates `duration` to represent 1 hour, 10 minutes, 32 seconds, and 400 milliseconds. It then creates a ``Swift/Duration/UnitsFormatStyle`` to show the hours, minutes, seconds, and milliseconds parts, with a wide width that presents the full name of each unit.

    let duration = Duration.seconds(70 * 60 + 32) + Duration.milliseconds(400)
    let format = duration1.formatted(
         .units(allowed: [.hours, .minutes, .seconds, .milliseconds],
                width: .wide))
    // format == "1 hour, 10 minutes, 32 seconds, 400 milliseconds"

The formatted string omits any units that aren't needed to accurately represent the value. In the above example, a duration of exactly one minute would format as `1 minute`, omitting the hours, seconds, and milliseconds parts. To override this behavior and show the omitted units, use the initializer's' `zeroValueUnits` parameter.

## Topics

### Creating a units format style

- ``Swift/Duration/UnitsFormatStyle/init(allowedUnits:width:maximumUnitCount:zeroValueUnits:valueLength:fractionalPart:)``
- ``Swift/Duration/UnitsFormatStyle/init(allowedUnits:width:maximumUnitCount:zeroValueUnits:valueLengthLimits:fractionalPart:)``
- ``Swift/Duration/UnitsFormatStyle/units(allowed:width:maximumUnitCount:zeroValueUnits:valueLength:fractionalPart:)``
- ``Swift/Duration/UnitsFormatStyle/units(allowed:width:maximumUnitCount:zeroValueUnits:valueLengthLimits:fractionalPart:)``


### Formatting a duration

- ``Swift/Duration/UnitsFormatStyle/format(_:)``

### Formatting a duration as an attributed string

- ``Swift/Duration/UnitsFormatStyle/attributed-swift.property``
- ``Swift/Duration/UnitsFormatStyle/Attributed-swift.struct``

### Working with units

- ``Swift/Duration/UnitsFormatStyle/allowedUnits``
- ``Swift/Duration/UnitsFormatStyle/Unit``
- ``Swift/Duration/UnitsFormatStyle/maximumUnitCount``
- ``Swift/Duration/UnitsFormatStyle/valueLengthLimits``

### Working with unit widths

- ``Swift/Duration/UnitsFormatStyle/unitWidth-swift.property``
- ``Swift/Duration/UnitsFormatStyle/UnitWidth-swift.struct``


### Working with zero values

- ``Swift/Duration/UnitsFormatStyle/zeroValueUnitsDisplay``
- ``Swift/Duration/UnitsFormatStyle/ZeroValueUnitsDisplayStrategy``

### Working with fractional values

- ``Swift/Duration/UnitsFormatStyle/fractionalPartDisplay``
- ``Swift/Duration/UnitsFormatStyle/FractionalPartDisplayStrategy``

### Working with locales

- ``Swift/Duration/UnitsFormatStyle/locale``
- ``Swift/Duration/UnitsFormatStyle/locale(_:)``

### Encoding and decoding

- ``Swift/Duration/UnitsFormatStyle/init(from:)``
- ``Swift/Duration/UnitsFormatStyle/encode(to:)``

### Hashing

- ``Swift/Duration/UnitsFormatStyle/hashValue``
- ``Swift/Duration/UnitsFormatStyle/hash(into:)``

### Supporting types

- ``Swift/Duration/UnitsFormatStyle/FormatInput``
- ``Swift/Duration/UnitsFormatStyle/FormatOutput``
