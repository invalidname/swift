# ``Swift/Duration/UnitsFormatStyle/attributed-swift.property``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

A property that formats the duration as an attributed string.

Apply the `attributed` property to a configured ``Swift/Duration/UnitsFormatStyle`` to produce an ``Swift/Duration/UnitsFormatStyle/Attributed-swift.struct`` style. You can then format a duration with this style to create a formatted   <doc://com.apple.documentation/documentation/Foundation/AttributedString>. The formatted attributed string contains instances of <doc://com.apple.documentation/documentation/Foundation/AttributeScopes/FoundationAttributes/DateFieldAttribute> and <doc://com.apple.documentation/documentation/Foundation/AttributeScopes/FoundationAttributes/MeasurementAttribute> for runs with formatted durations.

The following example formats a duration as an attributed string:

    let duration = Duration.seconds(70 * 60 + 32) +
        Duration.milliseconds(400)
    let style = Duration.UnitsFormatStyle(allowedUnits: [.hours, .minutes, .seconds],
                                          width: .abbreviated).attributed
    let attributedDuration = duration.formatted(style)

The resulting `attributedDuration`, representing the string `1 hr, 10 min, 32 sec` contains the following runs:

| Run        |    Attributes                                                                              | 
|------------|--------------------------------------------------------------------------------------------| 
| `1`        | `Foundation.MeasurementAttribute = value`, `Foundation.DurationFormatAttribute = hours`    |
| (space)    | `Foundation.DurationFormatAttribute = hours`                                               |
| `hr`       | `Foundation.DurationFormatAttribute = hours`, `Foundation.MeasurementAttribute = unit`     |
| `,  `      | None                                                                                       |
| `10`       | `Foundation.MeasurementAttribute = value`, `Foundation.DurationFormatAttribute = minutes`  |
| (space)    | `Foundation.DurationFormatAttribute = minutes`                                             |
| `min`      | `Foundation.DurationFormatAttribute = minutes`, `Foundation.MeasurementAttribute = unit`   |
| `,  `      | None                                                                                       |
| `32`       | `Foundation.MeasurementAttribute = value`, `Foundation.DurationFormatAttribute = seconds`  |
| (space)    | `Foundation.DurationFormatAttribute = seconds`                                             |
| `sec`      | `Foundation.DurationFormatAttribute = seconds`, `Foundation.MeasurementAttribute = unit`   |
