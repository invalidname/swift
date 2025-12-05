# ``Swift/Duration/TimeFormatStyle``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

A format style that shows durations in a compact, localized format with separators.

This style produces formatted strings that uses separators between components, like "2:03"

Create a `TimeFormatStyle` by providing a ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct`` and an optional locale. The pattern specifies which units (hours, minutes, and seconds) to include in the formatted string, with optional configuration of the units. Then create a formatted string by calling ``Swift/Duration/formatted(_:)`` on a duration, passing the style, or ``Swift/Duration/TimeFormatStyle/format(_:)`` on the style, passing a duration. You can also use the style's ``/Swift/Duration/TimeFormatStyle/attributed-swift.property`` property to create a style that produces <doc://com.apple.documentation/documentation/Foundation/AttributedString> instances, which contains attributes that indicate the unit value of formatted runs of the string.

In situations that expect a ``Swift/Duration/TimeFormatStyle``, such as ``Swift/Duration/formatted(_:)``, you can use the convenience function ``Swift/Duration/TimeFormatStyle/time(pattern:)`` to create a ``Swift/Duration/TimeFormatStyle``, rather than using the full initializer.

If you want to reuse a style to format many durations, call ``format(_:)`` on the style, passing in a new duration each time.

The following example creates `duration` to represent 1 hour, 10 minutes, 32 seconds, and 400 milliseconds. It then creates a ``Swift/Duration/TimeFormatStyle`` to show hours, minutes, and seconds, padding the hours part to two digits and limiting the fractional seconds to two digits. When used with the ``Swift/Duration/formatted(_:)`` method, the resulting string is `01:10:32.40`.

    let duration = Duration.seconds(70 * 60 + 32) + Duration.milliseconds(400)
    let format = duration.formatted(
        .time(pattern: .hourMinuteSecond(padHourToLength: 2,
                                         fractionalSecondsLength: 2)))
    // format == "01:10:32.40"

## Topics

### Creating a time format style

- ``Swift/Duration/TimeFormatStyle/init(pattern:locale:)``
- ``Swift/Duration/TimeFormatStyle/time(pattern:)``
- ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct``

### Formatting a duration

- ``Swift/Duration/TimeFormatStyle/format(_:)``

### Formatting a duration as an attributed string

- ``Swift/Duration/TimeFormatStyle/attributed-swift.property``
- ``Swift/Duration/TimeFormatStyle/Attributed-swift.struct``

### Using a style pattern

- ``Swift/Duration/TimeFormatStyle/pattern-swift.property``
- ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct``

### Working with locales

- ``Swift/Duration/TimeFormatStyle/locale``
- ``Swift/Duration/TimeFormatStyle/locale(_:)``

### Encoding and decoding

- ``Swift/Duration/TimeFormatStyle/init(from:)``
- ``Swift/Duration/TimeFormatStyle/encode(to:)``

### Hashing

- ``Swift/Duration/TimeFormatStyle/hashValue``
- ``Swift/Duration/TimeFormatStyle/hash(into:)``

### Supporting types

- ``Swift/Duration/TimeFormatStyle/FormatInput``
- ``Swift/Duration/TimeFormatStyle/FormatOutput``

### Comparing time format styles

- ``Swift/Duration/TimeFormatStyle/==(_:_:)``
