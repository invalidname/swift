# ``Swift/String/LocalizationValue/Placeholder/float``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

The single-precision floating-point type, as used for replacement values with the localized string placeholder syntax.

To insert a `float` into a placeholder, use the syntax `\(placeholder: .float)`.

The various `String(localized:)` initializers apply a locale-appropriate `FormatStyle` to the numeric value, based on the `locale:` parameter or the `LocalizedStringResource`.
