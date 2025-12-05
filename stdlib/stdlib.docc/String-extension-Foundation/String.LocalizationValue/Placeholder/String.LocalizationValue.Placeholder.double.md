# ``Swift/String/LocalizationValue/Placeholder/double``

@Metadata {
    @DocumentationExtension(mergeBehavior: override)
}

The double-precision floating-point type, as used for replacement values with the localized string placeholder syntax.

To insert a `double` into a placeholder, use the syntax `\(placeholder: .double)`.

The various `String(localized:)` initializers apply a locale-appropriate `FormatStyle` to the numeric value, based on the `locale:` parameter or the `LocalizedStringResource`.
