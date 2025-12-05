# ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct/minuteSecond(padMinuteToLength:fractionalSecondsLength:roundFractionalSeconds:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Returns a pattern to format a duration with minutes and seconds only, with the given unit configurations.

- Parameters:
    - padMinuteToLength: Padding for the minute field. For example, setting this value to `2` formats five minutes as `05:00` in the `en_US` locale.
    - fractionalSecondsLength: The length of the fractional seconds. For example, setting this value to `2` formats five minutes as `5:00.00` in the `en_US` locale.
    - roundFractionalSeconds: The rule to use for rounding the seconds value, given the remaining fractional seconds value. Use one of the cases from the ``FloatingPointRoundingRule`` enumeration.
- Returns: A ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct`` that formats a duration with minutes and seconds, using the given unit configurations.
