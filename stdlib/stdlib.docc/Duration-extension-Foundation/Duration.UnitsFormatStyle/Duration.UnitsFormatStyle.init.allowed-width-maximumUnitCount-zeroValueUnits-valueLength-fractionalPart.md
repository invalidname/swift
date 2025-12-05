# ``Swift/Duration/UnitsFormatStyle/init(allowedUnits:width:maximumUnitCount:zeroValueUnits:valueLength:fractionalPart:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Creates a units format style using the given parameters.

Use this convenience function in situations that expect a ``Swift/Duration/UnitsFormatStyle``, such as ``Swift/Duration/formatted(_:)``, as an alternative to using the full initializer.

- Parameters:
    - allowedUnits: The units that the formatted string may include.
    - width: The width of the unit and the spacing between the value and the unit.
    - maximumUnitCount: The maximum number of duration units to include in the output string.
    - zeroValueUnits: The strategy for handling leading units with zero values.
    - valueLength: The padding or truncating behavior of the unit value, as an `Int`.
    - fractionalPart: The strategy for displaying a duration if a formatted string can't represent it exactly with the allowed units.
