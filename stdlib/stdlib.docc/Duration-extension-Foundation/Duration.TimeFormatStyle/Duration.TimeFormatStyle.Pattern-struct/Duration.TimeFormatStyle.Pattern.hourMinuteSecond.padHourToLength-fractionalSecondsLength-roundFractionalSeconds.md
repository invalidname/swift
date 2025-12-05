# ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct/hourMinuteSecond(padHourToLength:fractionalSecondsLength:roundFractionalSeconds:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Returns a pattern to format a duration with hours, minutes, and seconds, with the given unit configurations.

- Parameters:
    - padHourToLength: Padding for the hour field. For example, setting this value to `2` formats one hour as `01:00` in `en_US` locale.
    - fractionalSecondsLength: The length of the fractional seconds. For example, setting this value to `2` formats one hour as `1:00:00.00` in the `en_US` locale.
    - roundFractionalSeconds: The rule to use for rounding the seconds value, given the remaining fractional seconds value. Use one of the cases from the ``FloatingPointRoundingRule`` enumeration.
- Returns: A ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct`` that formats a duration with hours, minutes, and seconds, using the given unit configurations.
