# ``Swift/Duration/TimeFormatStyle/Attributed-swift.struct``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

A format style that formats durations as attributed strings.

Apply the ``Swift/Duration/TimeFormatStyle/Attributed-swift.struct`` property to a configured ``Swift/Duration/TimeFormatStyle`` to produce an instance of this style. You can then format a duration with this style to create a formatted <doc://com.apple.documentation/documentation/Foundation/AttributedString>. The formatted attributed string contains instances of <doc://com.apple.documentation/documentation/Foundation/AttributeScopes/FoundationAttributes/DateFieldAttribute> for runs with formatted durations.

The following example formats a duration as an attributed string:

    let duration = Duration.seconds(70 * 60 + 32) +
        Duration.milliseconds(400)
    let style = Duration.TimeFormatStyle(pattern: .hourMinuteSecond).attributed
    let attributedDuration = duration.formatted(style)

The resulting `attributedDuration`, representing the string `1:10:32` contains the following runs:

| Run   |    Attributes                                   | 
|-------|-------------------------------------------------| 
| `1`   | `Foundation.DurationFormatAttribute = hours`    |
| `:`   | None                                            |
| `10`  | `Foundation.DurationFormatAttribute = minutes`  |
| `:`   | None                                            |
| `32`  | `Foundation.DurationFormatAttribute = seconds`  |

## Topics

### Formatting a duration

- ``Swift/Duration/TimeFormatStyle/Attributed-swift.struct/format(_:)``

### Working with locales

- ``Swift/Duration/TimeFormatStyle/Attributed-swift.struct/locale(_:)``

### Encoding and decoding

- ``Swift/Duration/TimeFormatStyle/Attributed-swift.struct/init(from:)``
- ``Swift/Duration/TimeFormatStyle/Attributed-swift.struct/encode(to:)``

### Hashing

- ``Swift/Duration/TimeFormatStyle/Attributed-swift.struct/hashValue``
- ``Swift/Duration/TimeFormatStyle/Attributed-swift.struct/hash(into:)``

### Supporting types

- ``Swift/Duration/TimeFormatStyle/Attributed-swift.struct/FormatInput``
- ``Swift/Duration/TimeFormatStyle/Attributed-swift.struct/FormatOutput``

### Comparing attributed styles

- ``Swift/Duration/TimeFormatStyle/Attributed-swift.struct/==(_:_:)``

