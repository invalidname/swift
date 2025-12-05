# ``Swift/String/LocalizationValue/StringInterpolation/appendInterpolation(_:specifier:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Appends a type, convertible to a string with a format specifier, to a string interpolation.

Don’t call this method directly; the compiler uses it when interpreting string interpolations.

- Parameters:
  - value: The value to append.
  - specifier: A format specifier to convert `value` to a string representation, like `%f` for a `Double`, or `%x` to create a hexidecimal representation of a `UInt32`.
