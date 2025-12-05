# ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct/hourMinute(padHourToLength:roundSeconds:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Returns a pattern to format a duration with hours and minutes only, with the given unit configurations.

- Parameters:
    - padHourToLength: Padding for the hour field. For example, setting this value to `2` formats one hour as `01:00` in the `en_US` locale.
    - roundSeconds: The rule to use for rounding the minutes value, given the remaining seconds value. Use one of the cases from the ``FloatingPointRoundingRule`` enumeration.
- Returns: A ``Swift/Duration/TimeFormatStyle/Pattern-swift.struct`` that formats a duration with hours and minutes only, using the given unit configurations.
