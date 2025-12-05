# ``Swift/Duration/UnitsFormatStyle/Attributed-swift.struct/format(_:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a locale-aware attributed string representation from a duration value.

Use this method when you want to create a format style and repeatedly use it to format different durations. For one-off cases with default formatting, call the ``Duration/formatted()`` method of ``Duration`` instead.

- Parameter duration: The duration value to format.
- Returns: A string representation of the duration, according to the style's pattern and locale.
