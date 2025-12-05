# ``Swift/Duration/formatted()``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Formats the string using a localized hour-minute-second time pattern.

The following example shows the effect of applying the default formatting to a duration of two seconds:

    let duration = Duration.seconds(2)
    let formattedDuration = duration.formatted() // "0:00:02"

This method uses a default ``Swift/Duration/TimeFormatStyle``. To modify the formatting, customize a ``Swift/Duration/TimeFormatStyle`` or ``Swift/Duration/UnitsFormatStyle``, then call ``Swift/Duration/formatted(_:)`` on the duration, passing in the style. You can also call `format(_:)` on the style, passing in a duration.

- Returns: A localized formatted string that describes the duration, such as `1:30:56` for a duration of 1 hour, 30 minutes, and 56 seconds in the U.S. English locale. In the Finnish locale, this returns `1.30.56`.
