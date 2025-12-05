# ``Swift/Duration/TimeFormatStyle/attributed-swift.property``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

A property that formats the duration as an attributed string.

Apply the `attributed` property to a configured ``Swift/Duration/TimeFormatStyle`` to produce an ``Swift/Duration/TimeFormatStyle/Attributed-swift.struct`` style. You can then format a duration with this style to create a formatted <doc://com.apple.documentation/documentation/Foundation/AttributedString>. The formatted attributed string contains instances of <doc://com.apple.documentation/documentation/Foundation/AttributeScopes/FoundationAttributes/DateFieldAttribute> for runs with formatted durations.

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
