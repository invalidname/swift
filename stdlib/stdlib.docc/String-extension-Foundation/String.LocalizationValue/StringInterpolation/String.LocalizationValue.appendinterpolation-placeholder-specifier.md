# ``Swift/String/LocalizationValue/StringInterpolation/appendInterpolation(placeholder:specifier:)``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Appends a placeholder to a string interpolation, using the provided format specifier.

Don’t call this method directly; the compiler uses it when interpreting string interpolations.

- Parameters:
  - placeholder: The value to append.
  - specifier: A format specifier to convert `value` to a string representation, like `%f` for a `Double`, or `%x` to create a hexidecimal representation of a `UInt32`.

