# ``Swift/String/LocalizationValue/StringInterpolation/appendInterpolation(_:)-8knpq``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

Appends a value representable as a format specifier to a string interpolation.

Don’t call this method directly; the compiler uses it when interpreting string interpolations.

- Parameters:
  - value: The format specifier to append.

This method handles numeric format specifiers like `%i` and `%d`, but not the object specifier `%@`.
