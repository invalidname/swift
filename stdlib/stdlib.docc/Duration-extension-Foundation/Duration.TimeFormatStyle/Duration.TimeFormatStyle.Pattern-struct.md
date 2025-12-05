# ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

The units --- including hours, minutes, or seconds --- and the configuration of those units, used to format a duration.

Use a pattern when initializing a ``Swift/Duration/TimeFormatStyle``, or creating a time format style from the convenience method ``Swift/Duration/TimeFormatStyle/time(pattern:)``.

Use the type properties ``hourMinute``, ``hourMinuteSecond``, or ``minuteSecond`` to create patterns with default behavior. To customize how a pattern handles zero-padding and fractional parts, use one of the type methods that take these customizations as parameters.

## Topics

### Creating a pattern

- ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct/hourMinute(padHourToLength:roundSeconds:)``
- ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct/hourMinuteSecond(padHourToLength:fractionalSecondsLength:roundFractionalSeconds:)``
- ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct/minuteSecond(padMinuteToLength:fractionalSecondsLength:roundFractionalSeconds:)``

### Using common patterns

- ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct/hourMinute``
- ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct/hourMinuteSecond``
- ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct/minuteSecond``

### Encoding and decoding

- ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct/init(from:)``
- ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct/encode(to:)``

### Hashing

- ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct/hashValue``
- ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct/hash(into:)``

### Comparing patterns

- ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct/==(_:_:)``
